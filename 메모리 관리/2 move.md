
### std::move ?
> 프로그래머가 move semantics 를 사용할지 결정하는 기능

- 파라미터를 r-value 로 리턴해 어떤 함수 또는 생성자에서 move semantics 를 사용할 수 있도록 한다.


### std::move 의 주의사항
- move semantics 는 어차피 사라질 데이터를 다른 데이터에 이동 시켜주는 기능을 전제로 한다
- std::move 를 사용하고 나면 argument 는 더 이상 해당 데이터를 가리키지 않는다.
```
std::move(res1);
// std::move 를 사용한 다음에 res1 은 이동 시켰기 때문에 더이상 사용할 수 없다.
```