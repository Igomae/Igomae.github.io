---
title:  "정렬 알고리즘 1. 선택 정렬"

categories:
  - 알고리즘
tags:
  - 정렬
  - 선택 정렬
---

# 정렬 알고리즘
이산수학 수업에서 정렬 알고리즘에 대해 공부했다. 이번 글에서는 **선택 정렬**에 대해 정리해보려고 한다.  

## 1. 선택 정렬(selction sort)의 과정
선택 정렬은 가장 작은 인덱스를 찾아 맨 앞으로 끌어오는 정렬이다. (최솟값 중심 정리 - 오름차순 기준)  
1. 먼저 맨 앞 원소(`i=0`)의 인덱스를 `min_idx`에 저장한다.  
2. `i+1`번째 원소부터 마지막 원소 중 가장 작은 원소의 인덱스를 `min_idx`에 저장한다.  
3. `i`번째 인덱스에 해당하는 원소와 `min_idx`에 해당하는 원소를 교환한다.  
4. 다음 순회에서는 `i+1`번째 인덱스를 `min_idx`에 저장하고 위 과정을 반복한다.

## 2. 선택 정렬 (최솟값 중심 정리)의 코드
```python
def selectionSort(list):
    for i in range(len(list)):
        # 정렬되지 않고 남아있는 원소들 중 최솟값을 찾음
        min_idx = i
        for j in range(i+1, len(list)):
            if list[min_idx] > list[j]:
                min_idx = j
        # 처음 원소와 최소 원소를 교환한다.
        list[i], list[min_idx] = list[min_idx], list[i]
```
