### 헷갈리는 개념 정리

- CPU time = (CPI X IC)/Clock Rate
  (Clock rate = 1/Clock Cycle Time)

* $$CPI = (\text{다른 작업들 실행 시간}) + (\text{메모리 접근 시간: Hit Time})$$

* $$Hit\ Time(\text{시간}) = Hit\ Time(\text{사이클 수}) \times Clock\ Cycle\ Time(\text{한 박자 시간})$$
  -> $$Clock\ Cycle\ Time = \frac{Hit\ Time(\text{시간})}{Hit\ Time(\text{사이클 수})}$$

* AMAT(Average Memory Access Time) = Time for a hit + miss rate(cache miss rate) x miss penalty(could be memory access time)
  여기서 평균 메모리는 main memory 뿐만 아니라 기억 장치 계층 전체(Cache + RAM)을 의미함. (그래서 더하는 것임)
