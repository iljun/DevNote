# 버블 정렬(Bubble Sort)
1번째와 2번째 원소를 비교하여 정렬, 2번째와 3번째를 비교하여 정렬하는 방식으로
n-1번째와 n번째 원소까지 비교하여 정렬한후, 다시 처음으로 돌아와 n-2번째와 n-1번째까지 비교하는 정렬방식
최대 n(n-1)/2만큼 정렬한다.

시간복잡도는 O(N^2)이며 이미 정렬된 자료에서는 O(N)의 성능을 보여준다.

안정 정렬이다.

## 코드
```
   public void bubbleSort(int[] arr) {
  
          int[] list = arr.clone();
          for (int i = list.length - 1; 0 <= i; i--) {
              for (int j = 0; j < i; j++) {
                  if (list[j+1] < list[j]) {
                      int tmp = list[j];
                      list[j] = list[j + 1];
                      list[j + 1] = tmp;
                  }
              }
          }
  
          System.out.println(Arrays.toString(list));
      }

```
