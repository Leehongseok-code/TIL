
# [99클럽 코테 스터디] 20일차 TIL - 영화감독 숌


출처: https://www.acmicpc.net/problem/1436

문제 설명

666이 포함되는 영화 시리즈 제목을 만들기 위해, 666이 포함되는 수 중 N번째로 큰 수를 출력하기


문제 분석

완전탐색 형태의 해결 방법을 사용하기 위해, 1부터 차례대로 숫자를 증가시키며, 숫자에 "666"이 포함될 때마다 카운트를 올린다. N과 카운트가 일치할 경우 break하여 무한루프를 빠져나온다.

*코드-Python*

```Python
num = int(input())
answer = 0
k = 0
i = 0
while True:
    if "666" in str(i):
        k += 1
    if k == num:
        answer = i
        break
    i+=1

print(answer)

```
