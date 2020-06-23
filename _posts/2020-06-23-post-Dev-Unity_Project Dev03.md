---
layout: post
title: "Dev : Project-03"

categories:
  - Dev
tags:
  - Knowledge
  - Unity
  - C#
  - Series
---

## 3 ~ 4일차  

  
### 진행 결과  
  
1. 총알 -> 탄창 -> 총 순으로 관리가 될 예정   
2. 현재 사용 될 총알 조사 후 수치 입력  
3. BulletItem class는 IBulletItem과 IInventoryItem 인터페이스를 상속받았음  
- 이를 통해 필요한 데이터와 함수를 분리하여 얻어올 수 있을 것이라고 생각
4. 땅에 버렸을 때 모델링으로 실체화되어야 한다면 새로운 interface를 추가할 예정  
5. Magazine class 제작 중
6. 이전 플레이어 움직임을 처리 수정
- input으로 단순 방향을 정해 처리해서 바라보고 있는 쪽으로 움직이지않았음 따라서 (input.x * transform.right,.., input.y * transform.forward)으로 변경   

***  
   
### 실행  

![움직임](https://drive.google.com/uc?id=1vhXkidklxs8Mh4fpOroUsetx75fruz7v)  
![총알](https://drive.google.com/uc?id=1uQeQK3-g7TFfuEnPhnNCZsFfkXSAFWu_)