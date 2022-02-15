
# static member variable (정적 멤버 변수)
- 같은 클래스인 모든 인스턴스(객체)에서 접근할 수 있다.
> 공유한다.
- 인스턴스(객체) 를 통하지 않아도 접근할 수 있다.
> object.static_member_vairable : 가능
> className::static_member_vairable : 가능
- **인스턴스를 생성해주기 전에도 정적 멤버변수가 존재한다.**
- 정적 멤버 변수의 정의는 cpp 에서 만들기
- **class 의 선언에서 정적 멤버 변수는 초기화 하면 안됨**
- class 선언 부분은 메모리에 생성해서 변수처럼 사용하지 않기 때문

- 모든 static 데이터는 초기화될때 0 초기화
```
className name
{
    public:
        static data_type name;
}

data_type className::name = 1;
```


# static member function (정적 멤버 함수)
- this 포인터를 사용할 수 없다.
> this : static 이 아닌 것에서 사용 가능
> 정적으로 접근할 수 있는 것에만 가능
- this 를 통한 것들은 사용할 수 없다.

- 멤버 변수의 경우 인스턴스마다 가지고 있지만 멤버 함수의 경우 인스턴스들이 공유한다.

- static 이 아닌 멤버 함수의 경우 인스턴스(this) 를 통해 멤버함수에 접근해줘야한다.
> (멤버 함수의 경우 어느 메모리에 저장되어 동일한 클래스인 객체들이 공유하기 때문)
