[프로그래머스 비밀지도](https://programmers.co.kr/learn/courses/30/lessons/17681)

- 풀이
  - 주어진 2가지 배열을 zip()을 사용해 a1,a2로 값을 저장한다.
  - a1과 a2를 2진수로 변환시키고 or인 |를 사용하여 두 값을 비교해 num에 저장한다.
  - 이때 해당 2진수가 앞의 값이 0이되어 지도 한변의 길이 n의 값보다 작다면 0을 추가시킨다.
  - 완성된 2진수 지도에서 1은 #, 2는 ' '로 변환시켜 변수 answer에 추가시킨다.



```python
def solution(n, arr1, arr2):
    answer = []
    for a1,a2 in zip(arr1,arr2):
        print(a1,a2)
        num = str(bin(a1 | a2))[2:]
        
        num = '0'*(n-len(num))+num
        print(num)
        num = num.replace('1','#')
        num = num.replace('0',' ')
        answer.append(num)
    return answer
```



