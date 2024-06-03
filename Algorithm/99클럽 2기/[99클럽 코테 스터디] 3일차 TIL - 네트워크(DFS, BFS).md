# 99클럽 코테 스터디 3일차 TIL - 네트워크(DFS, BFS)



• 오늘의 학습 키워드: DFS, BFS
• 공부한 내용 본인의 언어로 정리하기: 재귀함수를 활용한 DFS로 하나로 이어진 네트워크의 개수를 셀 수 있다.
• 오늘의 회고
    ◦ 어떤 문제가 있었고, 나는 어떤 시도를 했는지: 하나로 이어진 경로의 개수를 세는 방식을 고민하다가, DFS의 적용을 도전하였다.
    ◦ 어떻게 해결했는지: DFS를 재귀로 구현하여 각 정점을 시작점으로 했을 때의 경로 개수를 계산하였다.
    ◦ 무엇을 새롭게 알았는지: 한붓그리기와 간접 연결은 별도로 생각할 필요가 있다.
    ◦ 내일 학습할 것은 무엇인지: 연결 관계 외에도 한붓그리기 경로에도 DFS를 적용할 수 있는 방법을 고민해 볼 예정이다.


*코드-Python*

```Python

def solution(n, computers):
    answer = 0
    
    graph = {}
    
    for i in range(1, n+1):
        graph[i] = []
        
    for i in range(n):
        for j in range(n):
            if computers[i][j] == 1:
                graph[i+1].append(j+1)
    
    
    visited = [False] * (n+1)
    
    def dfs(graph, start):
        visited[start] = True
        
        for node in graph[start]:
            if visited[node] == True:
                continue
            dfs(graph, node)
    
            
    cnt = 0
        
    for i in range(1, n+1):
        if visited[i] == False:
            dfs(graph, i)
            cnt += 1
    
    
    
    answer = cnt
    
    return answer
```

#99클럽 #코딩테스트 준비 #개발자 취업 #항해99 #TIL