[프로그래머스 같은 숫자는 싫어](https://programmers.co.kr/learn/courses/30/lessons/12906)

~~효율성 테스트가 있어 살짝 쫄음 :happy:~~

- 풀이
  - 배열 arr의 크기 : 1,000,000이기 때문에 시간 복잡도는 **O(N^2)**까지임을 생각하고 시작하기
  - 가장 무난하게 **반복문**을 통해 s[i]값과 이후 값이 같지 않다면 빈리스트 a에 추가를 하며 반복문을 실행하기!!
    - 이렇게 반복문을 수행하면 가장 마지막의 숫자를 놓치기 때문에 input으로 들어온 s리스트의 마지막 값을 a리스트에 추가시키기!!
  - 이렇게 하면 성공 :happy:

- 소스코드

```python
def solution(s):
    a = []
    for i in range(0,len(s)-1):
        if s[i] != s[i+1]:
            a.append(s[i])
    a.append(s[-1])   
    return a
```



- 뒷이야기

  - 내가 구성한 로직보다 정말 파이썬 스럽게 작성한 사람이 있어.. 참고자료 차 올려본다!!

    ~~파이썬 스럽게 작성하도록 분발하자 머혁이.. :sob:~~

```python
     a = []
     for i in s:
         if a[-1:] == [i]: continue
         a.append(i)
     return a
```

