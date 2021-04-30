[프로그래머스 로또의 최고 순위와 최저 순위](https://programmers.co.kr/learn/courses/30/lessons/77484)

- 풀이
  - 구매한 로또 번호 중 지워진 번호를 **0의 갯수를 저장**하는 **zero**변수와 지워지지 않은 번호가  당첨 번호 일때 **당첨 갯수**를 저장하는 **cnt** 변수를 생성 후 반복문으로 탐색한다.

  - **당첨 순위를 반환**하는 `ranking()함수`를 구현

  - `ranking()`함수에 **cnt값과 zero값을 더한**(cnt+zero) 값을 매개변수로 주어 **가장 높은 당첨 순위**를 추출하고 :happy:

    `ranking()`함수에 **cnt값**을 매개변수로 주어 **최소 당첨 순위**를 추출하고 :cry:

    -END-

    - 이유

      cnt값으로 최소를 구한 이유는 알 수 없는 번호는 모두 당첨 번호가 아닐 수 있기 때문에 zero값을 제외한 cnt값으로만 최소값을 판단했다!! :seedling:

- 소스코드

```python
def solution(lottos, win_nums):
    answer = []
    cnt = 0
    zero = 0
    for i in lottos:
        if i == 0:
            zero +=1
            continue
        for j in win_nums:
            if i == j:
                cnt += 1
    answer.append(ranking(cnt+zero))
    answer.append(ranking(cnt))
                                
    return answer

def ranking(sum):
    if sum == 6:
        return 1
    elif sum == 5:
        return 2
    elif sum == 4:
        return 3
    elif sum == 3:
        return 4
    elif sum == 2:
        return 5
    else:
        return 6
```

