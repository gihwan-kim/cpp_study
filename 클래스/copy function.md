# 대입 연산자는 *this 의 참조자를 반환할 것

- C++ 의 대입 연산자는 여러개가 연속될 수 있다.
```int a = b = c = 2;```
- 대입 연산이 사슬처럼 엮이면 대입 연산자가 좌변 인자에 대한 참조자를 반환하도록
```
class ClassNmae {
public:
    ClassName &operator=(const ClassName &rhs)
    {
        return (*this);
    }
}

```


- 모든 형태의 대입 연산자에서도 좌변 객체의 참조자를 리턴해줘야함
    > +=, -=, *= ...

# operator= 에서 자기 자신을 대입하지 않도록 주의 하자
- 내부적으로 동적할당을 한다는 지 메모리를 건드리는 대입 연산자의 경우 위험할 수 있다.
- 자기 자신인지 확인하기
```
ClassName &operator=(const ClassName &rhs)
{
    if (this == &rhs)
        return (*this);
}

```


# 객체 복사 함수
- 보통 잘 설꼐한 객체 지향 시스템에서 객체를 복사하는 함수는 두개만 있다.
> 복사 생성자
> 복사 대입 연산자
- 기본적으로 컴파일러가 생성해주지만 기능이 부족할 경우 직접 만들어 줄 수 있다.
- 복사함수를 구현해주었으면 데이터 멤버를 추가하거나 삭제할 경우 해당 멤버에 대해 복사 함수에서 코드를 수정해줘야한다.

### 상속을 사용할 경우 객체 복사 함수
- 자식 클래스에서 복사 함수를 구현할때 부모 클래스의 복사 함수를 제대로 구현해놓지 않으면
    > 컴파일러가 default 복사 생성자를 호출한다.
- 부모 클래스의 복사 생성자, 복사 대입 연산자 함수를 호출해주어야한다.
```
class ChildClass: public PaerntClass {
    ChildCalss(const ChildClass &_child);
    ChildClass &operator=(const ChildClass &_child);
}


ChildCalss::ChildCalss(const ChildClass &_child)
    : ParentClass(_child) // parent copy
{
    // child copy
}

ChildClass &ChildCalss::operator=(const ChildClass &_child)
{
    // paernt copy
    PaerntClass::operatr=(_child);

    // child copy
}

```

### 객체 복사 함수를 만들떄
- 해당 클래스의 모든 데이터 멤버를 복사해야한다.
- 클래스가 상속한 부모 클래스의 복사 함수도 호출해줘야한다

### 코드를 줄이기 위해서 복사 함수에서 다른 복사 함수를 호출하는 쓰레기같은 짓은 하지말자
- 복사 대입 연산자에서 복사 생성자를 호출하는 것은 말이 안된다.
    > 이미 존재하는 객체를 생성자를 호출해서 또 생성하는 역할이 필요하지 않다.

- 복사 생성자에서 복사 대입 연산자를 호출하는 것은 말이 안된다.
    > 생성자의 역할은 새로 만들어진 객체를 초기화하는 것
    > 대입 연산자는 이미 초기화가 끝난 객체에게 값을 주는 것

- 코드가 중복되는 것 같으면 따로 함수로 만들어 양쪽 복사 함수에 넣어 중복을 해결해주기
    > private, init함수