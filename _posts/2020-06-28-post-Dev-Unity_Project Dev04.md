---
layout: post
title: "Dev : Project-04"

categories:
  - Dev
tags:
  - Knowledge
  - Unity
  - C#
  - Series
---

## 4번째 글  
  
### 진행 결과  
  
1. 근접 공격 추가  
- 플레이어 앞을 기준으로 160도의 범위에 근접 공격을 가함  
- 특정 행동 중일때 다른 행동을 막는 로직 추가  
2. 부자연스럽던 움직임 수정  
- mouse input에서 들어온 변수를 반대로 사용하고 있었음  
3. AKM 애니메이터 제작 중  
4. GunItem class 개발 중  
- Assault Rifle, MarksmanRifle, SniperRifle, SMG처럼 특징을 통해 총을 나눠야하는지 고민 중  
5. Magazine class 개발 완료(현재 기획 안에서는)  
- 탄창에 총알 채우고 비우기 테스트 완료, ScriptableObject로 미리 데이터 생성  
6. 플레이어 회전을 SmoothDampAngle을 이용해 부드럽게 회전하도록 수정  
- 기존 화면 회전은 끊기는 느낌이 강하여 수정함     

***  
   
### 실행  
  
![근접](https://drive.google.com/uc?id=1Sr7JN8z9JoCEJUSSJ_u7a7nPGS_4VaKC)  
![근접결과](https://drive.google.com/uc?id=1GfigsENWxDHVEH3G8RxVWpPjbnWKXHm2)  
![총알](https://drive.google.com/uc?id=1Ox_2wOMMQSFkHBcHV1Zulls4TlmmbNe_)  
![Scriptable](https://drive.google.com/uc?id=19f7wlczlwdmsZ6xJaT8VUt0fqQbfrsIo)  