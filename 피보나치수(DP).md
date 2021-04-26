[프로그래머스 피보나치 수](https://programmers.co.kr/learn/courses/30/lessons/12945?language=python3)

- 문제가 비교적 흔하게 접하고 쉬운 문제기 때문에 python과 C로 풀어봤다.

- DP알고리즘을 배우기 전엔 이전값을 담는 배열을 만들지않고 바로 계산을 했는데 

  이전값을 **기록**하며 이전것을 **사용**하는 알고리즘인 만큼 배열로 만들어봤다.

- 주의할 점

  - 2 이상의 n이 입력되었을 때, n번째 피보나치 수를 **1234567으로 나눈 나머지**를 리턴하는 함수, solution을 완성해 주세요.

    - 파이썬으로 했을 때 아무 탈없이 넘어갔는데 C와 JS로 구현을 해보니  다른 언어는 dp에 값을 저장할떄 계속 1234567을 나눠줘야했다.

    - 계속 1234567나눠주면 나중에 문제가 생기지 안을까 해서 구글링을 해보니

      [1234567로 나누는 이유](https://russwest.tistory.com/41)라는 정보를 알아냈다!!

    - 결론은 int형이 할당할 수 있는 수를 초과하여 오류가 생겼고 이를 해경하기 위해

      (A+B)%C = ((A%C)+(B%C))%C 라는 성질을 이용했다고 한다...

```python
#반복적인 작업을 수행한다면 DP 알고리즘을 사용
def solution(n):
    answer = 0
    dp = [0]*100001
    dp[0] = 0
    dp[1] = 1
    
    for i in range(2,n+1):
        dp[i] = (dp[i-1] + dp[i-2])%1234567
        #dp[i] = (dp[i-1] + dp[i-2])
    answer = dp[n]
    #answer = dp[n]%1234567 
    return answer
```

```c
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int n) {
    int answer = 0;
    int dp[100001] = {0,};
    dp[1] = 1;
    for(int i=2;i<=n;i++){
        dp[i] = (dp[i-1]+dp[i-2])%1234567;
    }
    answer = dp[n];
    return answer;
}
```

