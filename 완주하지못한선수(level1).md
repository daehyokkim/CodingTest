[프로그래머스 완주하지 못한 선수](https://programmers.co.kr/learn/courses/30/lessons/42576)

- 풀이

  -  마라톤 참가 선수 (**participant**)와 완주에 성공한  선수(**completion**)르 담은 두 리스트를 

    각각 collections 모듈의 Counter 클래스를 활용해 **선수명(key) : 동명이인수(value)** 형태인 **dict형식**으로 변환 후 두 리스트를 빼 완주하지 못한 1명의 선수이름(key)을 출력!!

 - 소스코드

```python
import collections

def solution(participant, completion):
    answer = collections.Counter(participant) - collections.Counter(completion)
    return list(answer.keys())[0]
```

