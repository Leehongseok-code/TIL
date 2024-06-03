
# [99클럽 코테 스터디] 23일차 TIL - 최소 힙


출처: https://www.acmicpc.net/problem/1927

문제 설명

입력받은 값에 대해, 입력값이 0이면 배열에서 가장 작은 값을 pop하고, 자연수면 해당 값을 배열에 넣는다. 명령을 수행한 뒤의 결과값을 출력하라.

문제 분석

Python에서 제공하는 heapq 라이브러리를 이용한다.

*코드-Python*

```Python
import heapq

n = int(input())
q = []

answers = []
for i in range(n):
    k = int(input())
    if k!=0:
        heapq.heappush(q, k)
    else:
        if q:
            answers.append(heapq.heappop(q))
        else:
            answers.append(0)
        
for answer in answers:
    print(answer)
            
```
