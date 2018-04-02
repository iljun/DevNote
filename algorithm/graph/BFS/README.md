# BFS
트리나 그래프에 탐색에 이용되는 알고리즘이다.
큐를 사용해 구현한다.

현재 정점에서 인접한 모든 정점을 방문하고 이동할 정점이 없을경우
다음 정점의 인접한 모든 정점을 방문하는 방식이다.

인접행렬로 구현했을 경우 시간복잡도는 O(V^2)이다.
인접리스트로 구현했을 경우 시간복잡도는 O(V+E)이다.

## 코드
```
    static List<List<Integer>> list;//정점 인접리스트
    static int N;//정점 리스트 갯수
        
    public void BFS(Integer start){
        Queue<Integer> queue = new LinkedList<>();
        queue.add(start);
    
        boolean[] visited = new boolean[N];
        visited[start] = true;
    
        while(!queue.isEmpty()){
            Integer currentPoint = queue.poll();
    
            for(int i=0; i<list.get(currentPoint).size(); i++){
                Integer nextPoint = currentPoint + list.get(currentPoint).get(i);
    
                if(!visited[nextPoint]){
                    queue.offer(nextPoint);
                    visited[nextPoint] = true;
                }
            }
        }
    }
    
    class Point{
        int x;
        Point nextPoint;
    
        public Point(int x){
            this.x = x;
            this.nextPoint = null;
        }
    }

```

