---
layout: post
title: "Dev : Project-01"

categories:
  - Dev
tags:
  - Knowledge
  - Unity
  - C#
  - Series
---

## 1일차는 아니지만..  
  
### 목표  

- 기존 만들던 개인 프로젝트를 데모 버전까지 제작  
- 기간은 길게 잡아 2020년 12월까지  
- PC / FPS  
- 게임 키워드는 생존  
- 4가지의 특수 AI  
- 지역은 2개로 존재  
- 플레이 기록은 저장되나 죽으면 삭제  
- Escape from tarkov처럼 해당 지역을 탈출하는 내용  
- 탈출 지역은 연막으로 표시되야함  
- 탈출 지역들은 정해진 시간이 있으며 해당 시간 안에 탈출하지 못하면 M.I.A 판정  
- 보스는 생각 안하는 중 (사람만 등장하는 것이 아니다보니 종족이 달라 서로 싸울 수 있음)  
  
* 기간 안에는 프로젝트가 6 : 다른 공부가 4의 비율로 지켜져야 됨
  
***  
  
### 오늘 진행 내용  
  
Player의 움직임을 Controller에서 처리하도록 함.  
설계를 할 때 최대한 SOLID 원칙을 계속 보며 지키려했으나 잘 지켜졌는지가 의문  
Controller 안에서 키 입력을 받았을 때의 정보 가공을 시작하고 해당 정보는 interface 형태로 전달된다. 
전달 방법은 Controller 안에 있는 Action delegate를 이용.  
해당 기능 delegate와 연결이 필요한 클래스의 함수를 등록하는 방법으로 의존을 줄였다.  
그리고 Controller안에서는 Lerp를 통해 각 방향에 대한 값과 속도가 일정 시간에 완료되도록 했다.  
  

### 실행  
  
![움직임](https://drive.google.com/uc?id=1f6oJjP3aFONYueamR0cDo36QBWbMMbFp)