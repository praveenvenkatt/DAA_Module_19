# EX 1B Merge Sort
## DATE: 
## AIM:
To write a python program to sort the first half of the list using merge sort.

## Algorithm
1. If the array has more than one element, split it into two halves.
2. Recursively apply merge sort on both halves.
3. Compare elements of both halves and merge them into a sorted array.
4. Copy any remaining elements from the left or right half.
5. Return the fully sorted array.
## Program:
```
/*
Program to implement Merge Sort
Developed by: Praveen V
Register Number:  212222040121
*/
```

```
def merge(arr,l,m,r):
    n1=m-l+1
    n2=r-m
    L=[0]*(n1)
    R=[0]*(n2)
    for i in range(0,n1):
        L[i]=arr[l+i]
    for j in range(0,n2):
        R[j]=arr[m+1+j]
    
    i=0
    j=0
    k=l
    
    while i<n1 and j<n2:
        if(L[i]<=R[j]):
            arr[k]=L[i]
            i+=1
        else:
            arr[k]=R[j]
            j+=1
        k+=1
    while i<n1:
        arr[k]=L[i]
        i+=1
        k+=1
    while j<n2:
        arr[k]=R[j]
        j+=1
        k+=1
def mergeSort(arr,l,r):
    if l<r:
        m=l+(r-l)//2
        mergeSort(arr,m+1,r)
        merge(arr,l,m,r)
        
arr=[]
n=int(input())
for i in range(n):
    arr.append(int(input()))
print("Given array is")
for i in range(n):
    print(arr[i],end=' ')
mergeSort(arr,0,n-1)
print("\n\nSorted array is")
for i in range(n):
    print(arr[i],end=' ')
```


## Output:
![Screenshot 2025-04-26 103457](https://github.com/user-attachments/assets/4920251d-54b9-4377-bf5a-008c4dd5c3d5)
## Result:
The program successfully sorts the first half of the given array using merge sort. where only the first half is sorted, and the second half remains unchanged.
