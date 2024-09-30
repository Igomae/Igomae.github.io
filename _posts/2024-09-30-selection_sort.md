# 정렬 알고리즘
## 1. 선택 정렬(selction sort)
선택 정렬은 가장 작은 인덱스를 찾아 맨 앞으로 끌어오는 정렬입니다. (오름차순 정렬 기준)  
1. 먼저 맨 앞 원소(`i=0`)의 인덱스를 `min_idx`에 저장합니다.  
2. `i+1`번째 원소부터 마지막 원소 중 가장 작은 원소의 인덱스를 `min_idx`에 저장합니다.  
3. `i`번째 인덱스에 해당하는 원소와 `min_idx`에 해당하는 원소를 교환합니다.  
4. 다음 순회에서는 `i+1`번째 인덱스를 `min_idx`에 저장하고 위 과정을 반복합니다.  
코드로 확인해봅시다
```python
def selectionSort(list):
    # Traverse through all array elements
    for i in range(len(list)):
        # Find the minimum element in remaining unsorted array
        min_idx = i
        for j in range(i+1, len(list)):
            if list[min_idx] > list[j]:
                min_idx = j
        # Swap the found minimum element with the first element
        list[i], list[min_idx] = list[min_idx], list[i]
```
