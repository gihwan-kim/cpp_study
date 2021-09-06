> <string>

# std::stoi

```
int stoi (const string&  str, size_t* idx = 0, int base = 10);
int stoi (const wstring& str, size_t* idx = 0, int base = 10);
```

> string 을 정수로 변환
> 특정 진법으로 str 을 파싱한다.

- str
> String 객체

- idx
> idx 번째부터 변환

- base
> 변환할 진법

# stc::stof
```
float stof (const string&  str, size_t* idx = 0);
float stof (const wstring& str, size_t* idx = 0);
```

> string을 float 으로 변환


# std::stod
```
double stod (const string&  str, size_t* idx = 0);
double stod (const wstring& str, size_t* idx = 0);
```

> string 을 double 로 변환

- whitespace 가 아닌 문자가 나올때까지 whitespace 를 제거함
- 가능한 많은 유효한 부동 소수점 표현 문자들을 받아서 부동 소수점 수로 변환

### 유효한 부동 소수점 표현 문자

1. 10진수 부동 소수점 표현
    +, -
    비어있지않은 연속된 10 진 정수, 소수점수
    'e', 'E', '-' '+' 기호 비어있지 않은 연속된 10진 정수

### 예외처리

1. std::invalid_argument
> 변환을 수행할 수 없음

2. std::out_of_range
> 결과 데이터 타입의 범위를 벗어날 경우


# std::isprint
```
Defined in header <cctype>
int isprint( int ch );
```
> ch 가 출력할 수 있는 문자인지 확인한다.
> 정수, 소문자, 기타 문자, 여백