---
layout: post
title: "Dev : Rotation"

categories:
  - Dev
tags:
  - Knowledge
  - Unity
---

## Rotation  
  
### 조건  

- 입력된 위치를 바라보도록 회전하고 싶음  
- 정해진 시간에 맞게 회전이 완료되도록 하고 싶음
  
***  
  
### 코드  
   
```C#

var v = targetPosition.position - transform.position;
float radian = Mathf.Atan2(v.x, v.z);
float degree = radian * Mathf.Rad2Deg;

//...

if(percentage <= lerpDuringTime)
{
   transform.rotation = Quaternion.Lerp(transform.rotation, Quaternion.Euler(0, m_Degree, 0), percentage);
}
```  
  
### 설명  
  
[__Atan2 함수에 대해서 참고__](https://zzoyu.tistory.com/73)  
  
바라볼 위치와 자신의 위치를 빼서 바라보는 벡터를 구한다.  
벡터의 x와 z축을 이용해 radian 각을 구한다.  
degree로 변환하여 Quaternion 변환에 사용한다.  
  
### 실행  
  
[!회전](https://drive.google.com/uc?id=1UOZuq4LJpYxXSJqeWZF8IfuHw8uv2nLM)