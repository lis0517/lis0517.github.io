---
layout: post
title: "Data Structure : Stack (스택)"

categories:
  - Algorithm
tags:
  - Data Structure
  - Knowledge
---

##  Stack에 대하여  
***  
### Stack이란?  
  
밑이 막힌 긴 통으로 설명된다. 따라서 입, 출구가 같아  
먼저 들어온 것이 아래에 깔리는 FILO(First in last out) 구조이다.  

***  
  
### Stack의 성질  
  
1. 원소의 추가와 제거가 O(1)  

2. 제일 상단의 원소 확인 O(1)  

3. 상단을 제외한 나머지 원소의 확인 / 변경이 원칙적으로 불가능하다  

***  
  
### STL Stack  
  
push, pop, top, empty, size 함수를 주로 사용한다.  
stack이 비어 있을 때 top이나 pop을 하면 런타임 에러가 발생하므로  
주의해야한다.
  
