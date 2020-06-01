---
layout: post
title: "Algorithm : Divide and Conquer Sort"

categories:
  - Algorithm
tags:
  - Algorithm
  - Knowledge
  - Sort
---

##  1. Quick Sort (퀵 정렬)  
***  
#### 퀵 정렬이란?  
  
기준 원소(pivot)을 하나 잡아 수열을 좌우로 나눈 후에 각각을 따로 정렬하는 정렬법.  

***  
  
#### 전략  
  
1. 주어진 배열에서 임의로 pivot을 하나 잡는다.  
2. pivot의 왼쪽은 pivot보다 작고 오른쪽은 큰 것이 와야한다.  
3. pivot을 제외한 나머지 배열의 제일 왼쪽 오른쪽에 포인터를 2개 둔다.  
4. L은 pivot보다 큰 값을 찾을 때까지, R은 작은 것을 찾을 때까지 움직인다.  

***  
  
#### 특징  
  
Merge sort와 비교할 때 Quick sort는 추가 메모리도 필요없고 평균 속도도 빠르다.  
그러나 같은 key를 가진 원소들이 sorting을 한 후 순서가 바뀌는 unstable sort이고 최악의 경우가 O(N^2)이다.  

***  
  
#### 시간 복잡도  
  
평균 O(NlogN) 최악 O(N^2)  

***  
  
#### 코드  
  
``` c++
void quick_sort(int * arr, int st, int en)
{
	if(en-st <= 1) return; //base condition

	int pivot = arr[st];
	int l = st + 1;
	int r = en - 1;

	while(true)
	{
		
		while(l <= r && arr[l] <= pivot) l++;//피봇보다 큰 값을 찾을 때까지
		while(r >= l && arr[r] >= pivot) r++;//피봇보다 작은 값을 찾을 때까지
		if(l > r) break; // 서로 지나쳤을 경우 탈출
		swap(arr[l], arr[r]);
	}
	swap(arr[st], arr[r]);
	quick_sort(arr, st, r);//pivot 왼쪽 기준 정렬
	quick_sort(arr, r+1, en);//pivot 오른쪽 기준 정렬
}
```

***  
  
##  2. Merge Sort (병합 정렬)  
***  
#### 병합 정렬이란?  
  
이미 정렬이 된 부분에 새로운 키를 삽입하는 동작을 반복해 정렬하는 알고리즘이다.  

***  
  
#### 전략  
  
1. 주어진 리스트를 2개로 나눈다.  
2. 나눈 리스트 2개를 정렬한다.  
3. 정렬된 리스트를 합친다.  

***  
  
#### 특징  
  
같은 key를 가진 원소들이 sorting을 거친 이후에도 순서가 달라지지않는 stable sort이다.  

***  
  
#### 시간 복잡도  
  
O(NlogN)  
[이유](https://lis0517.github.io/algorithm/2020/05/13/post-Algorithm-O(n))    

***  
  
#### 코드  
  
``` c++
void merge(int st, int en)
{
    int mid = (st + en) / 2;
    int index0 = st;// 값을 넣기 위한 idx
    int index1 = st;// 시작 부분을 탐색할 idx
    int index2 = mid;// 중간 지점부터 탐색할 idx
    
    while (index1 < mid && index2 < en)
    {
        if (arr[index1] < arr[index2])
        {
            temp[index0++] = arr[index1++];
        }
        else 
        {
            temp[index0++] = arr[index2++];
        }
    }

    while (index1 < mid) temp[index0++] = arr[index1++];
    while (index2 < en) temp[index0++] = arr[index2++];

    for (int i = st; i < en; ++i) arr[i] = temp[i];
}

void merge_sort(int st, int en)
{
    if (en - st == 1) return; //길이가 1인 경우
    if (en - st == 1)//길이가 2인 경우
    {
        if (arr[st] > arr[st + 1]) //앞이 더 크다면
        {
            int tmp = arr[st + 1];
            arr[st + 1] = arr[st];
            arr[st] = tmp;
        }
        return;
    }
    int mid = (st + en) / 2;
    merge_sort(st, mid);
    merge_sort(mid, en);
    merge(st, en);
}
```  
  
