---
layout: post
title: "Data Structure : Queue (큐)"

categories:
  - Algorithm
tags:
  - Data Structure
  - Knowledge
---

##  Queue에 대하여  
***  
### Queue란?  
  
스택이 한 쪽이 막혀있던 긴 통으로 설명됐다면 큐는 양 쪽이  
뚫린 통으로 설명된다. 한 쪽 끝에서 원소를 넣고 반대 쪽에서  
뺄 수있는 FIFO(First in first out) 구조이다. 

***  
  
### Queue의 성질  
  
1. 원소의 추가 및 제거가 O(1)  

2. 제일 앞 / 뒤 원소 확인이 O(1)  

3. 제일 앞 / 뒤가 아닌 나머지 원소들의 확인 / 변경이 원칙적으로 불가능  

***    
  
### STL Queue  
  
push, pop, front, back, empty, size를 주로 사용한다.  
queue가 비어있을 때 pop, front, back 함수를 실행하게 되면  
런타임 에러가 발생하므로 주의해야 한다. 
  
