
# [ string stream ]
> #include <sstream>

### stringstream 클래스
- 스트림은 문자열(정확히 말하면 string)에 부착할 수 있다.
```
    즉, string으로부터 읽고 string에 쓰는 일을 스트림에서 제공하는 서식화 기능을
    써서 할 수 있다는 이야기이다.
    이러한 스트림을 가리켜 문자열 스트림이라고 하며,
    실제로 stringstream이란 이름의 클래스가 <sstream>에 정의되어 있다.
```
- insertion, extraction operator 를 사용하여 문자열을 작업할 수 있는 문자열에대한 스트림 클래스
- 비슷한 점
```
    > insertion operator('<<'), extraction operator('>>') 을 사용할 수 있다.
    > istream, ostream 처럼 string stream 은 buffer 를 제공 한다.
```
- 다른 점
```
    > string stream 은 I/O channel (키보드, 모니터 등) 에 연결되어 있지않다.
```
- strings 를 위한 클래스

### stringstream 에 데이터 입력하는 법
- insertion operator : <<
- str() member function

- 1. insertion operator : <
```
    stringsream 의 경우 문자열에 추가됨

    stringstream os;
    os << "hello world";
    os << "hello world2";
    // os :  'hello worldhello world2'
```
> " " 빈칸을 통해 입력할 내용을 구분할 수 있다.
- Ex. 01
```
    stringstream os;

    int i = 12345;
    double b = 67.89;

    os << i << d;
    // 1234567.89 붙어서 들어감
```
- Ex. 02
```
    stringstream os;

    int i = 12345;
    double b = 67.89;

    os << i << " " << d;
    // 12345, 67.89 끊어서 들어감
    // 공백이 들어감
```
- 2. str 함수를 사용해서 버퍼에 값 설정
```
    stringstream os;
    os.str("en grade!"); // stringstream 버퍼에 "en grade!" 설정됨
```

- (stringstream object).str("") : stringstream 버퍼에 들어간 내용이 빈칸으로 대체됨
- (stringstream object).str()   : stringstream 의 복사본을 string 객체로 리턴 해줌
- (stringstream object).claer() : state 까지 초기화 시킴

    ### stringstream 의 데이터 출력하는 법
- extraction operator : >>
> ">>" 연산자는 문자열을 통해 반복된다.
> ">>" 연산자를 연속해서 사용할 때마다 stream 에서 다음으로 추출가능한 값들이 리턴된다.
- str() memeber function
> str() 함수는 stream 전체의 값을 리턴한다.
> 만약 ">>" 가 이미 stream 에 사용됐더라도 상관 없다.

- 1. extraction operator : >>
```
    std::stringstream os;
    os << "12345 67.89"; // insert a string of numbers into the stream 공백으로 구분됨

    std::string strValue;
    os >> strValue;

    std::string strValue2;
    os >> strValue2;

    // print the numbers separated by a dash
    std::cout << strValue << " - " << strValue2 << '\n';

    => 12345 - 67.89 출력
```
- 2. str() memeber function
```
    std::stringstream os;
    os << "12345 67.89" << '\n';
    cout << os.str();
```

### stringstream 활용
- 숫자를 string 으로 변환할 수 있다.

### 재사용하기 위해서 stringstream 비우기
> stringsream 의 멤버함수들임

> flush() : Synchronizes the associated stream buffer with its controlled output sequence.
> flush 로 비우는게 아니다.

- 방법 1. str() 사용해서 C 스타일의 빈문자열로 설정하기
```
    std::stringstream os;
    os << "Hello ";

    os.str(""); // erase the buffer

    os << "World!";
    std::cout << os.str();
```
- 방법 2. str() 사용해서 빈 std::string 객체로 설정하기
```
    std::stringstream os;
    os << "Hello ";

    os.str(std::string{}); // erase the buffer

    os << "World!";
    cout << os.str();
```
- error flag 리셋 하기
>    clear() 함수 사용