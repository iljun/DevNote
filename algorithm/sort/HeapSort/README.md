# 힙 정렬(Heap Sort)
힙의 성질을 이용한 정렬 알고리즘이다.

정렬의 조건에 따라 힙에 모든 원소를 삽입한 후 힙이 빌때까지 루트노드를 출력하는 정렬방법

시간복잡도는 균일하게 O(log N)이 적용된다.

불안정 정렬이다.
## 코드
```
 public void heapSort(int[] list) {
        List<Integer> result = new ArrayList<>();
        List<Integer> arr = Arrays.stream(list).boxed().collect(Collectors.toList());
        for(int i=0; i<list.length; i++) {
            arr = heapify(arr);
            result.add(arr.get(0));
            arr.remove(0);
        }
        System.out.println(result.toString());
    }

    private List<Integer> heapify(List<Integer> list){
        for(int i=list.size()-1; i>0; i--){
            if(list.get(i)<list.get(i/2)){
                int tmp = list.get(i);
                list.set(i,list.get(i/2));
                list.set(i/2,tmp);
            }
        }
        return list;
    }

```

