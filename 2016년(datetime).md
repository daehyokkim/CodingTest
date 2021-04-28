[프로그래머스 2016년](https://programmers.co.kr/learn/courses/30/lessons/12901?language=python3)

- Level 2단계의 문제  [소수찾기](https://programmers.co.kr/learn/courses/30/lessons/42839)와 [가장큰수](https://programmers.co.kr/learn/courses/30/lessons/42746)를 풀지 못했다.. :sweat:

  그래서 이전 Level 1단계를 모두 풀고 차근차근 올라가기위해 1단계부터 시작하기!!

- 풀이

  - 문제의 핵심은 datetime을 사용할 수 있는지를 물어보는 내용인거같다.

    - [날짜/시간 모듈 활용강의](https://dojang.io/mod/page/view.php?id=2463)를 통해 정확히 datetime의 사용법을 배웠다!!

  - 우선 datetime의 `datetime(year,month,day)`함수를 통해 특정 년월일을 지정하고

    `strftime("%a")`으로 원하는 데이터만을 출력했다. 

    이때 **%a는 요일을 가져오는 코드**이다.

  - 원하는 정보가 소문자가 함께 있어 string.upper()함수를 사용해서 대문자로 출력하니 성공!!

  ```python
  import datetime
  
  def solution(a, b):
      
      d= datetime.datetime(2016,a,b)
      day = d.strftime('%a')
      answer=day.upper()
      return answer
  ```

  

  

