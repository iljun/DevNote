# 삽입 정렬(Insertion Sort)
k번쨰 원소를 정렬할때 첫번째 원소부터 k-1번째 원소까지 비교해 중간에 끼워넣어 정렬하는 알고리즘

중간에 끼워넣고 그 다음 자료들은 한칸씩 뒤로 밀린다.

자료구조에 따라 뒤로 밀려나는 시간이 오래걸릴수 있다는 단점이 존재.
이미 정렬되어 있는 자료에서는 최고의 속도를 자랑하는 알고리즘이다.

시간복잡도는 O(N^2)이다.

안정정렬이다.

## 코드
```
  public void insertionSort(int[] list) {

        int[] arr = list.clone();

        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < i; j++) {
                if (arr[i] < arr[j]) {
                    int tmp = arr[i];
                    for (int k = i; k > j; k--) {
                        arr[k] = arr[k - 1];
                    }
                    arr[j] = tmp;
                }
            }
        }

        System.out.println(Arrays.toString(arr));
    }

```
