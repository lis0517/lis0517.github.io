---
layout: post
title: "Data Structure : Deque (덱)"

categories:
  - Algorithm
tags:
  - Data Structure
  - Knowledge
---

##  Deque에 대하여  
***  
### Deque란?  
  
양 쪽 끝에서 삽입과 삭제가 가능한 자료 구조    

***  
  
### Deque의 성질  
  
1. 원소의 추가 및 제거가 O(1)   

2. 제일 앞/뒤 원소 확인이 O(1)  
  
3. 제일 앞/뒤가 아닌 나머지 원소들의 확인 / 변경이 원칙적으로 불가능  

***  
  
### STL Deque  
  
STL Deque는 Double Ended Queue보다 Vector에 가까운 느낌이다.  
pop_front, pop_back, push_front, push_back과 vector에 존재하던  
insert, erase도 가지고 있다. 또, 인덱스로 원소에 접근하는 것이 가능하다.  
  
Deque는 front연산에도 O(1)의 성능으로 처리할 수 있기에 Vector의 상위 호환이  
아닌가라고 생각할 수 있지만 Deque는 Vector와 달리 메모리 상에 연속되어 있지  
않기 때문에 상황에 맞는 것을 사용하는 것이 좋다.  
예를 들면 앞/뒤에서 추가/삭제가 일어나는 알고리즘이라면 Deque이 효율적이다.  
  
