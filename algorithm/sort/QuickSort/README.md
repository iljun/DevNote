# 퀵 소트(Quick Sort)
평균적인 상황에서 가장 효율적인 알고리즘이다.

가장 적절한 원소를 선택하고(Pivot) 이 원소를 기준으로 원소보다 작은 원소는 Pivot의 왼쪽에 위치,
큰 원소는 Pivot의 오른쪽에 위치하게 된다.
이후 Pivot의 양쪽에서 또다시 Pivot을 선택해 위와 같은 방법으로 정렬을 하게된다.
각각의 크기가 0이나 1인경우 재귀가 끝나게된다.

시간복잡도는 O(Nlog N) 최악의 경우에는 O(N^2)의 시간복잡도를 가진다. 
최악의 경우는 Pivot을 계속 최대값이나 최소값으로 정하는 경우이다.

불안정 정렬이다.
## 코드
```
  public void quickSort(int[] list, int left, int right) {
  
          if (left < right) {
              int partition = partition(list, left, right);
              quickSort(list, left, partition - 1);
              quickSort(list, partition + 1, right);
          }
  
      }
  
  public int partition(int[] list, int begin, int end) {
        int left = begin;
        int right = end;
  
        int pivot = list[(left + right) / 2];//비교 pivot값
  
        while (left < right) {
            while (list[left] < pivot)//pivot보다 큰값이 나올때까지
                left++;
  
            while (pivot < list[right])//pivot보다 작은값이 나올때까지
                right--;
  
            if (left < right) {
                int tmp = list[left];
                list[left] = list[right];
                list[right] = tmp;
            }
        }
        System.out.println(Arrays.toString(list));
        return left;
  
      }
```