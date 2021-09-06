

- 범위 [first, last) 에서 value 와 같거나 큰 값을 찾아 리턴
- 값을 찾을 수 없을 경우 마지막 iterator 를 리턴
- 범위 [first, last) 는 (element < value) 또는 comp(element, value) 에 의해 나뉘어져 있어야한다.


### Parameters

- first, last : 범위
- value : 데이터와 비교할 값
- comp : 비교 함수
> bool pred(const Type1 &a, const Type2 &b);
> 굳이 const 일 필요는 없음

### Return

- value 보다 적지않은(같거나 큰) 값 중에서 첫 번째 데이터를 가리키는 iterator 를 리턴
- 없으면 마지막 iterator 리턴


### 복잡도

- log2(last - first) + O(1)

- non-random access iterator 경우 선형시간( O(N) )
> set, multiset 의 iterator 는 random access 이므로 멤버함수 lower_bound 를 사용할 것
