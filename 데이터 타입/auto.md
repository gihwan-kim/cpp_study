자동 변수 (함수 매개변수, 함수, 블록 안에서 선언된 변수)에서만 사용 가능
> auto 는 자동 변수에서만 사용


1. 함수의 리턴 타입 추론
2. 구조적 바인딩에 사용
3. 표현식의 타입 추론
4. non-type 탬플릿 매개변수의 타입을 추론하는데 사용
5. decltype(auto) 에서 사용
6. 함수에 대한 또 다른 문법으로 사용
7. 제너릭 람다 표현식에서 사용

- 변수를 선언할때 auto
> 컴파일 시간에 결정

- auto 로 표현식의 타입을 추론하면 함수에 지정된 reference 나 const 가 제거된다.
```
const std::string message = "message";

const std::string &foo()
{
	return (message);
}

auto data = foo();

// const 가 사라져 data 의 타입은 std::string 이 됨

```

- const 나 reference 를 제거하고 싶지 않으면
```
const auto

auto &
```