[프로그래머스 내적](https://programmers.co.kr/learn/courses/30/lessons/70128)

- 풀이
  - 문제는 상당히 쉬어 특별한 풀이법은 이야기 하지않고 이번 풀이의 핵심인 zip()클레스를 한번더 사용해보는 차원으로 풀어보았다~!!

- 소스코드

```python
def solution(a, b):
    answer=0
    lists = list(zip(a,b))
    print(lists)
    for x,y in lists:
        answer+=x*y
    return answer
```

