
# [99클럽 코테 스터디] 17일차 TIL - 나머지가 1이 되는 수 찾기


문제 설명

n을 x로 나누어 나머지가 1이 되는 수 중 가장 작은 x를 구하기

문제 분석

O(N)의 시간복잡도로 문제를 해결하기 위해, 단순히 반복문을 활용하여 조건을 만족하는 수 중 가장 작은 수를 찾는다.

*코드-Python*

```Python
def solution(n):
    answer = 0
    
    for i in range(1, n):
        if n%i == 1:
            return i
    
    return answer
```

