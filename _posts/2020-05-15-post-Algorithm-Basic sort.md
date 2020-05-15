---
layout: post
title: "Algorithm : 기초 정렬"

categories:
  - Algorithm
tags:
  - Algorithm
  - Knowledge
---

##  1. Selection Sort (선택 정렬)  
***  
#### 선택 정렬이란?  
  
현재 들어갈 위치에 맞게 들어갈 값을 찾아 정렬하는 알고리즘  

***  
  
#### 전략  
  
1. 인덱스의 처음에서 n-2가 되면 반복을 끝낸다.  
2. 배열의 i항부터 n-1항까지 최소값을 찾아서 그 항을 min에 저장한다.  
3. i항과 min항을 교환한다.  
4. i를 하나 증가시키고 2번 항목으로 돌아가 반복한다.  

***  
  
#### 코드  
  
``` c++
void selection_sort(int a[], int n)
{
	int minindex=0;
	int min=0;
	for(int i = 0; i < n-1; ++i)
	{
		minindex = i;
		min = a[i];
		for(int j = i+1; j < n; ++j)
		{
			if(a[j] < min)
			{
				minindex = j;
				min = a[j];
			}
		}
		a[minindex] = a[i]; //i항과 min항을 교환
		a[i] = min;
	}
}
```

***  
  
##  2. Insertion Sort (삽입 정렬)  
***  
#### 삽입 정렬이란?  
  
이미 정렬이 된 부분에 새로운 키를 삽입하는 동작을 반복해 정렬하는 알고리즘이다.  

***  
  
#### 전략  
  
1. 두번째 인덱스부터 시작한다.  
2. a[j-1] < a[i]이고 j > 0인 동안  
- a[j] = a[j-1]하여 a[i]를 삽입할 공간을 만든다.  
- i를 하나 감소한다.  
3. a[j] = a[i] 빈 공간에 a[i]를 삽입  
4. i를 증가시키고 2번으로 돌아감  

***  
  
#### 코드  
  
``` c++
void insert_sort(int a[], int n)
{
	int j = 0;
	int t = 0;
	for(int i=1; i < n-1; ++i)
	{
		t = a[i]; // a[i]를 할 때 컴파일러가 주소를 읽어 i를 더하는 작업을 하는데 변수에 할당하면 최적화를 할 수 있다.
		j = i;
		while(a[j-1] < a[i] && j > 0)
		{
			a[j] = a[j-1];
			j--;
		}
		a[j] = t; 
	}
}
```

***  
  
##  3. Bubble Sort (거품 정렬)  
***  
#### 거품 정렬이란?  
  
연속된 두개 인덱스를 비교하여 정한 기준의 값을 뒤로 넘겨 정렬하는 방법  

***  
  
#### 전략  
  
1. i = 0부터 n-1가 되면 끝냄  
2. j가 n-i이 되면 5번으로 이동  
3. a[j-1] > a[j]이면 두 값을 교환  
4. j를 하나 증가시키고 2번으로 이동  
5. i를 하나 증가시키고 1번으로 이동  

***  
  
#### 코드  
  
``` c++
void bubble_sort(int a[], int n)
{
	int t;
	for(int i=0; i < n-1; i++)
	{
		for(int j=1; j < n-i; j++)
		{
			if(a[j] < a[j-1])
			{
				t = a[j-1];
				a[j-1] = a[j];
				a[j] = t;
			}
		}
	}
}
```

***  
  
