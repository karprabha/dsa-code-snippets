# DSA Code Snippets
- [DSA Code Snippets](#dsa-code-snippets)
  - [1. Heap](#1-heap)
    - [1.1. Build Min Heap](#11-build-min-heap)

## 1. Heap

### 1.1. Build Min Heap
```cpp
void buildMinHeap(int arr[],int n){
  for(int i=(n-2)/2;i>=0;i--)
    minHeapify(arr,i,n);
}

void minHeapify(int arr[],int i,int n){
  int left = 2*i+1;
  int right = 2*i +2;
  int smallest = i;

  if(left<n && arr[left] < arr[smallest])
    smallest = left;
  
  if(right<n && arr[right] < arr[smallest])
    smallest = right;
  
  if(smallest != i){
    swap(arr[smallest],arr[i]);
    minHeapify(arr,smallest,n);
  }
}
```