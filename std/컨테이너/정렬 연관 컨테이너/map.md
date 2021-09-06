


```
<map> 헤더파일
template < class Key,                                     // map::key_type
           class T,                                       // map::mapped_type
           class Compare = less<Key>,                     // map::key_compare
           class Alloc = allocator<pair<const Key,T> >    // map::allocator_type
           > class map;

```
# 템플릿 파라미터

1. key
> key 타입

2. T
> value 타입
> 데이터를 해당 타입으로 저장한다.

2. Compare
> key 비교를 위한 비교 함수 객체(comparsion function object)
> 두 개의 key argument 를 파라미터로 받음
> bool return
> 우선 순위를 비교 첫 번째 arg 가 두 번째 arg 보다 앞에 있으면 true 리턴
> 같은 key 를 가질 수 없다.
> 기본 값 less<T>
> custom 함수 객체를 생성해서 넣어 주면 key 값들을 임의의 조건으로 정렬가능

- key-value 쌍으로 저장
- key 를 기준으로 추가, 조회, 삭제 연산


# custom key class
- [참고사이트](https://en.cppreference.com/w/cpp/container/map/map)
1. comparasion struct
```
struct PointCmp {
    bool operator()(const Point& lhs, const Point& rhs) const {
        return lhs.x < rhs.x; // NB. intentionally ignores y
    }
};

```
2. comparsion lambda

# 원소 추가하기

1. insert() 메서드
> 키/쌍을 pair 객체나 initializer_list 로 지정
```
pair 객체 : make_pair(key, data)

initializer_list : {key, data}
```

2. insert_or_assign() 메서드
3. operator[]
4. emplace() 메서드

# iterator
- 순차 컨테이너와 비슷하게 작동
- iterator 는 pair (key/value로 구성) 를 가리킨다.
```
pair.first	: key
pair.second.getValue() : value


iter->second.getValue()
```


# 데이터 조회하기

1. operator[]
> 해당 데이터가 있는지 알고 있는 상태에서 호출해야한다.


# 데이터 삭제하기
> erase()
1. 특정 위치의 데이터를 삭제 : O(1)
2. iterator 를 사용한 삭제	: O(log N)