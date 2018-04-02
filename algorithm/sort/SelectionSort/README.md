# 선택 정렬(Selection Sort)
첫번째 원소부터 n번쨰 원소까지 제일 작은원소를 첫번째 정렬, 

두번째 원소부터 n번째 원소중 가장 작은것을 두번째 원소로 정렬하는 방식을 이용해 (n-1)까지 반복한다.

시간복잡도는 O(N^2)이다. 

BestCase와 WorstCase에서 동일한 시간 복잡도를 보여준다.

불안정 정렬이다.

## 코드
```
 public void selectSort(int[] list) {

        int[] arr = list.clone();

        for (int i = 0; i < arr.length; i++) {
            int minIndex = i;
            for (int j = i + 1; j < arr.length; j++) {
                if (arr[minIndex] > arr[j]) {
                    minIndex = j;
                }
            }

            int tmp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = tmp;
        }

        System.out.println(Arrays.toString(arr));
    }

```
