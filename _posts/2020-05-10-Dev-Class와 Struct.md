---
title: "[Dev] class와 struct"

categories:
   -Dev
tags:
   - C++
   - C#
   - Knowledge
---

#Class와 Struct 차이에 대한 공부   
 
 struct와 class의 차이는 있는 걸까?   
아마 이 질문을 C++에서 받게된다면 C++에서 C나 C#에서의 struct를 생각하게 해 오답을 말하게 하는 함정이 아닐까 생각한다.   
C++에서 struct와 class의 차이는 기본 접근 제어 지시자가 public, private라는 것 밖에 없다.   
메모리 또한 struct나 class는 따로 new를 해주지않는다면 스택 메모리에 올라간다.   
C#에서는 그래도 class와 struct의 차이점이 늘었다.  
기본 접근 제어 지시자가 다른 것이 그대로 왔고 C++에서는 가능했던 struct의 상속이 불가능하다는 점이 생겼다.   
메모리 관점에서는 class는 참조타입 struct는 값타입으로 분리되었다.      

그러면 C++에서는 차이가 크게 없는데 왜 struct와 class가 나뉘어진 것일까?   
이에 대해서는 의견이 많이 갈리기에 누구 말이 맞냐 판단하기 힘들었지만 가장 유력한 것은   
기존 C를 이용하던 개발자나 라이브러리 등에 대해서 호환성을 제공한 것이라는 의견이다.   