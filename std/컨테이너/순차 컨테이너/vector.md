- vector 의 destructor 는 요소 객체의 소멸자를 호출하도록 정의돼있다.

- vector 의 경우 순차 컨테이너이기 때문에 for문의 index 변수와 size() 메서드를 사용해 반복을 구현할 수 있다.

# vector 에서 iterator 를 사용하면 좋은 경우

1. 요소 또는 연속된 여러 요소를 컨테이너의 원하는 지점에 추가할 때
2. std 알고리즘을 사용할 때
3. 컨테이너를 순차적으로 접근할 때 인덱스로 원소에 접근하는 것 보다 iterator 를 사용하는 것이 더 효율적이다.
> vector 의 경우 아닌 경우도 있긴하지만 list, map, set 은 iterator 를 사용하는게 더 효율적이다.

# vector 의 메모리 할당 방식

- vector 는 C 스타일의 배열 처럼 연속된 메모리 공간을 가진다.
- 요소를 추가하거나 삭제하는 등의 메모리 재할당이 발생하면 요소를 참조하던 기존의 iterator 는 무효가 된다.

Ex.
```
erase(iterator) 를 호출하면 해당 요소가 삭제되고 그 다음 요소의 iterator 가 리턴됨
파라미터(iterator) 를 다시 사용할 수 없기 때문에 리턴된 iterator 를 사용
```


# reserve(n)

- vector 저장 공간을 지정해준다.
- 현재 용량보다 n 이 더 클경우 저장공간을 재할당
- 아닌 경우 vector 의 용량에 영향을 주지 않음
- vector size 에 영향을 주지 않음
- vector data(elements) 를 수정하지 않는다.