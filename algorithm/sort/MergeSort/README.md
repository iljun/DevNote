# 병합 정렬(Merge Sort)
분할정복 방법을 적용한 알고리즘이다.

정렬 되지 않은 리스트를 반으로 분리한다. 이 과정을 리스트의 갯수가 0또는 1개가 될때까지 반복한다.

리스트를 모두 분할한 후 분할된 리스트를 두개씩 정렬후 병합한다. 이 과정을 재귀적으로 반복.
이후 리스트가 모두 병합됐을때 정렬이 완료된 정렬이다.

일괄적으로 O(Nlog N)이라는 시간복잡도를 나타낸다.

안정정렬이다.

## 코드
```
 public void mergeSort(int[] list, int length) {

        int mid = length / 2;

        int[] leftList = new int[mid];
        int[] rightList = new int[length - mid];

        if (length == 1)
            return;

        for (int i = 0; i < leftList.length; i++) {
            leftList[i] = list[i];
        }

        for (int i = 0; i < rightList.length; i++) {
            rightList[i] = list[mid + i];
        }

        mergeSort(leftList, leftList.length);
        mergeSort(rightList, rightList.length);
        merge(leftList, rightList, list);

    }

    private void merge(int[] left, int[] right, int[] list) {
        int l = 0;
        int r = 0;
        int m = 0;

        while (left.length != l && right.length != r) {
            if (left[l] < right[r]) {
                list[m++] = left[l++];
            } else {
                list[m++] = right[r++];
            }
        }


        while (right.length != r) {
            list[m++] = right[r++];
        }

        while (left.length != l) {
            list[m++] = left[l++];
        }


    }

```