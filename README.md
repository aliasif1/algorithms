# Common Algorithms/Problems
This Repository contains python code for common DS-Algorithm problems/cases

### Sorting
1. Selection Sort 
```
# Selection Sort
def selectionSort(arr):
    n = len(arr)
    for i in range(n-1):
        minElement = i
        for j in range(i+1,n):
            if arr[j] < arr[minElement]:
                minElement = j
        if minElement != i:
            arr[i], arr[minElement] = arr[minElement], arr[i]
    return arr
```

2. Bubble Sort
```
# Bubble Sort
def bubbleSort(arr):
    n = len(arr)
    for i in range(n-1):
        for j in range(n-1-i):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
```
3. Insertion Sort 
```
# Insertion sort 
def insertionSort(arr):
    n = len(arr)
    for i in range(1,n):
        j = i
        while(j >=1 and arr[j] < arr[j-1]):
            arr[j], arr[j-1] = arr[j-1], arr[j]
            j-=1
    return arr
```
4. Merge Sort 
```
# Merge sort
def mergeSort(arr):
    if len(arr) == 1:
        return arr
    arr1 = arr[:len(arr)//2]
    arr2 = arr[len(arr)//2:]
    return merge(mergeSort(arr1), mergeSort(arr2))
    
def merge(arr1, arr2):
    i = 0
    j = 0
    arr = []
    while(i<len(arr1) and j<len(arr2)):
        if (arr1[i] <= arr2[j]):
            arr.append(arr1[i])
            i+=1
        else:
            arr.append(arr2[j])
            j+=1
    while(i<len(arr1)):
        arr.append(arr1[i])
        i+=1
    while(j<len(arr2)):
        arr.append(arr2[j])
        j+=1
    return arr
```
5. Quick Sort
```
# Quick Sort
def quickSort(arr):
    n = len(arr)
    quickSortRecur(arr,0,n-1)
    return arr
    
def quickSortRecur(arr,start,end):    
    index = partition(arr, start, end)
    if index is not None:
        quickSortRecur(arr, start, index-1)
        quickSortRecur(arr, index+1, end)
    
def partition(arr, start, end):
    if start >= end:
        return None
    pivot = arr[end]
    p = start
    for i in range(start, end):
        if arr[i] < pivot:
            # swap
            arr[p], arr[i] = arr[i], arr[p]
            p+=1
    # swap 
    arr[p], arr[end] = arr[end], arr[p]
    return p
``` 
