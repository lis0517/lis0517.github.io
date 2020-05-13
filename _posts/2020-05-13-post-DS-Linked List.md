---
layout: post
title: "Data Structure : Linked List (연결 리스트)"

categories:
  - Algorithm
tags:
  - Data Structure
  - Knowledge
---

##  Linked List에 대하여  
***  
#### Linked List란?  
  
연속된 메모리 상에 위치해있던 배열과 달리  
원소를 저장할 때 그 다음 원소의 위치를 포함시켜 저장하는 자료구조  
원소들은 이리저리 흩어져있다.  
  
### Linked List의 종류  
  
1. __단일 연결리스트(Singly Linked List)__ :  
- 각 원소가 자신의 다음 원소의 주소와 데이터만 들고 있음. 이전 원소가 무엇인지 모름  
2. __이중 연결리스트(Doubly Linked List)__ :  
- 각 원소가 자신의 다음 원소와 이전 원소 주소를 들고 있음.  
3. __원형 연결리스트(Circular Linked List)__ :  
- 끝과 처음이 연결되어 있음.  
  
#### Linked List의 성질  
  
1. K번째 원소를 확인 및 변경하기 위해 O(K)가 필요  
- K번째 요소를 찾고싶다면 시작부터 K번째까지 탐색해야함.  

2. 임의의 위치에 원소를 추가 및 제거할 때 O(1)  
- 단, 해당 주소를 알고있는 경우이다. 찾아가는 시간을 포함하면 O(1)이 아니지만  
- 제외하면 해당 노드의 이전 노드와 다음노드의 가르키는 값만 변경하면 되기 때문이다.    
  
3. Cache hit rate가 낮지만 추가 할당이 쉽다.  
- 데이터가 메모리상 연속되어 있지않아 공간 지역성이 낮기 때문이다.  
- 추가 할당이 어렵던 배열과 달리 연결 리스트는 새로운 원소를 필요한 곳에 연결하기만하면  
- 추가 할당이 이루어진다.    
  
#### Linked List 조작에 따른 시간 복잡도  
  
임의의 위치에 있는 원소를 확인 및 변경 = O(N)  
임의의 위치에 원소를 추가 및 제거 = O(1)    
  
#### STL List  
  
Linked List는 C++ STL에서 list로 대체 가능하다.  
push_back, push_front, pop_back, pop_front 함수가 있으며  
처음과 끝에 추가 및 제거하는 역할을 한다.  
해당 함수들은 O(1)의 시간 복잡도를 가진다.  
iterator가 주소 역할을 한다.  
  
