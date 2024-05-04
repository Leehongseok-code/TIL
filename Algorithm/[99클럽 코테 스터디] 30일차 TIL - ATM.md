
# [99클럽 코테 스터디] 30일차 TIL - ATM

문제 출차: https://www.acmicpc.net/problem/11399

문제 설명

n명의 사람이 ATM에서 돈을 인출하는 데 걸리는 시간이 함께 주어질 때, 모든 사람이 대기하는 시간을 최소가 되는 시간을 출력하시오.

문제 분석

각각의 사람이 현금 인출을 위해 기다리는 시간이 적어지려면, 앞사람이 최대한 돈을 빠르게 인출해야 한다. 즉, 각 사람들이 현금 인출을 위한 대기 시간이 오름차순으로 돈을 인출할 때 인원들이 대기하는 시간이 최소가 된다.

*코드-Python*

```Python

n = int(input())

ps = list(map(int, input().split(' ')))

ps.sort()

answer = 0
cur = 0
for p in ps:
    cur += p
    answer += cur
    
print(answer)
            
```