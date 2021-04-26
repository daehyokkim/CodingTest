[프로그래머스 게임 맵 최단거리](https://programmers.co.kr/learn/courses/30/lessons/1844)

- 그래프가 주어지고 최단거리를 찾는 문제가 주어졌다!! :scream:

  다행이 dfs/bfs문제를 풀어보아 쉽게 풀 수 있었다.

  먼저 그래프(행렬)이 주어지고 최단거리를 구하라??? ---> **DFS/BFS 부터 생각**

- 문제를 어떻게 접했을까~?

  - 먼저 주어진 변수의 범위가 100이하인 것을 보아 시간복잡도는 양호할거 같다!!

    [시간복잡도 참고](https://github.com/daehyokkim/TIL/blob/master/Algorithm/Big_O.md)

  - 다음으로 DFS/BFS를 정하기~

  - 인접한 그래프위치(행,열)를 방문하며 비교하기 위해 동,서,남,북의 배열 생성

  - 동서남북을 모두 확인하며 벽(0)인지 길(1)인지 비교하며 움직이고 다음길이 정해지면 

    다음길에 이전길의 값을 더하며 이동거리를 측정함

:star2::star2::star2:파이썬에서 재공하는 deque는 아주 빠른녀석이기 때문에 BFS 알고리즘을 사용할떈 **필수**지여라~~

```python
from collections import deque
def solution(maps):
    n = len(maps)
    m = len(maps[0])
    answer = 0
    dx = [0,1,0,-1]
    dy = [1,0,-1,0]
    #di = ['동','남','서','북']
    x=0
    y=0
    
def bfs(x,y):
    de =deque()
    de.append((x,y))
    
    while de:
        x,y=de.popleft()
        for i in range(4):
            nx = x+dx[i]
            ny = y+dy[i]
            #행렬범위에 벗어나지 않게 조건달기
            if nx<0 or nx>=n or ny<0 or ny>=m:
                continue
            #벽(0)은 피해주고~
            if maps[nx][ny] == 0:
                continue
            #길이라면 이동!!
            if maps[nx][ny] == 1:
                maps[nx][ny] = maps[x][y] + 1
                #만약 도착지점이라면 return
                if nx == n-1 and ny == m-1:
                    return maps[n-1][m-1]
                de.append((nx,ny))
                
    return -1
answer = bfs(x,y)
return answer
```