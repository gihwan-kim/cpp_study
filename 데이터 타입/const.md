https://www.learncpp.com/cpp-tutorial/const-constexpr-and-symbolic-constants/


# Run-time, Compile-time constant 차이

1. Run-time constant
run time 에만 해당 값이 초기화된다. (프로그램이 동작하고 있을 때)
Ex.
함수 parameter type
const 가 유저의 입력 값으로 초기화될 때


2. Compile-time constant
compile-time 에 초기화될 값이 결정된다. (프로그램이 컴파일 될떄)
```
    const double gravity {9.8};
    const int something { 1 + 2};
```