
# [ stream ? ]
- [stream](learncpp.com/cpp-tutorial/input-and-output-io-streams/)
- 기본적으로 c++ 에서 입출력은 stream 으로 구현된다.
- 순차적으로 접근할 수 있는 연속된 바이트라는 추상적인 의미를 가진다.

- 보통 두가지 유형의 스트림으로 다룬다.
    1. input stream
        > 키보드, 파일, 네트워크 등의 데이터 생산자를 통한 입력에 사용된다.
    2. output stream
        > 데이터를 필요로하는 대상(모니터, 파일 등)을 위해 출력을 저장한다.

    > 입력, 출력 모두 필요로 하는 장치도 있음

### c++ 에서의 입 출력
1. istream : input stream 처리할때 사용되는 클래스
> "stream >> (extration operator)"
2. ostream : output stream 처리할떄 사용되는 클래스
> "stream << insertion operator"
3. iostream : input, output 둘다.

### c++ 에서의 표준 stream

- standard stream : 컴퓨터 프로그램의 환경에 따라 미리 연결된 스트림
```
    1. cin
    2. cout
    3. cerr
    4. clog
```