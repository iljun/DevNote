# DFS
트리나 그래프의 탐색에 사용되는 알고리즘이다.
BFS와는 다르게 스택을 사용해 구현하고,

현재 정점에서 인접한 정점이 존재하면 인접한 정점으로 계속 이동하는 알고리즘이다.

시간복잡도는 BFS와 동일하다.

## 코드
```
    static List<List<Integer>> list;//인접 리스트
    static int N;
    static boolean[] visited;
    public void DFS(int x){
        visited[x] = true;
    
        for(int i=0; i<list.get(x).size(); i++){
            if(!visited[list.get(x).get(i)]){
                DFS(list.get(x).get(i));
            }
        }
    }
```