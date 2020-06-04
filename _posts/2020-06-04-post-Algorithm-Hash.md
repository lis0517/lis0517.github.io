---
layout: post
title: "Algorithm : Hash"

categories:
  - Algorithm
tags:
  - Algorithm
  - Knowledge
---

##  Hash Function (해쉬 함수)  
***  
#### 해쉬 함수란?  
  
임의의 길이 데이터를 고정된 길이의 데이터로 매핑하는 함수  

***  
  
#### 코드  
  
``` c++

unsigned int g = 31;
int mod = 100000000;

int hash_func(const char * name)
{
	int address=0;
	whlie(*name)
	{
		address = (g * adress + *name++) % mod;
	}
	return address;
}
```

***  
  
##  Hash Table (해쉬 테이블)  
***  
#### 해쉬 테이블이란?  
  
해쉬 함수로 나온 결과값들을 이용해 만든 테이블.  

***  
  
##  Hash Collsion (충돌)  
***  
####  해쉬 충돌이란?
  
두 입력 값에 동일한 결과를 발생하는 것을 뜻한다.  

***  
  
#### 충돌을 회피하기 위한 방법  
  
1. Open Addressing :   
- 원소를 저장하는 인덱스를 바꾸는 충돌 회피 방법이다.  
Linear probling이라고도 한다.  
2. Chaning :  
- LinkedList 구조로 여러개 담는 방법이다.  
제일 뒤에 연결하면 O(n)의 비용이 추가할 때마다 발생하므로  
앞에 삽입하여 O(1)의 성능으로 삽입한다.    

***  
  
