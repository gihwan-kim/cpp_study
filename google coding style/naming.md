

## 1. Class 이름 : Camel-Case
> Camel-Case 를 사용
> 첫글자 대문자
> 각 단어 구분을 대문자




## 2. 기본적인 데이터를 저장하는 용도로는 struct 를 사용하자
- struct 는 access modifier 의 기본값이 public 이다.




## 3. member filed : Snake-Case
**member filed 의 끝문자는 '_' 문자를 써주자**
```
class ClassName {
    int member_filed_name_;
}

```



## 4. memeber function : Camel-Case
```
class ClassName {
    int DoSomething();
}
```
> 일반함수도 동일




## 5. Getter member function
- getter 함수의 경우 member field 의 이름과 동일하게
- 끝에 '_' 안 붙임
```
class ClassName {
    int member_filed_;
    int member_filed() { return (member_filed) };
}

```




## 6. public protected private 순서로 사용하자
- 외부에서 접근할 수 있는게 상위에 있는게 더 보기 편하다.

```
class ClassName {
    public:
        ...
    protected:
        ...
    private:
        ...
}

```



## 7. declaration 과 definition 을 구분해주자.




## 8. constructor 를 선언할때 explicit 을 사용하자.
- implicit conversion constructor 가 호출되는 것을 방지한다.




## 9. namespace 이름 : Snake-Case
- 주석은 namespace 끝에 "namespace 가 끝났다" 는 내용을 넣어줘서 어느 namespace 가 어디까지 이루어져 있는지 알려주는게 좋다.




## 10. using namespace 대신 using 을 사용하자.
- namespace 전체를 사용할 경우 충돌할 수 있음
