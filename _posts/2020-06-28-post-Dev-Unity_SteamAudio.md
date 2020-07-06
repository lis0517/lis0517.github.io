---
layout: post
title: "Dev : Steam Audio"

categories:
  - Dev
tags:
  - Knowledge
  - Unity
  - C#
---

## Steam Audio  

Steam Audio는 Escape from tarkov 업데이트 방향을 통해 알게되었다.    
Escape from tarkov의 사운드 시스템은 위, 아래 구분이 없으며 벽 너머에 있는 소리도 감쇄되지않고 들리기에 적과의 거리 판단이 힘들다는 단점이 존재했다.  
그래서 도입하기로 한 것이 Steam Audio이며 유니티의 오디오 시스템을 개선시킬 수 있지만 그 효과가 상당한지, 최적화 요소는 충분한지가 불분명하다.  
설명에 따르면 Simulation setting을 높게 설정하거나 Occlusion sampling이 많거나 실시간 반사를 계산하는 양이 많아지는 경우이다.  
Steam Audio는 Unity, Unreal 플러그인이 존재하지만 사용하는 개발자들은 적어 정보를 찾기가 어렵다.  
최대한 옵션을 건들고 문서를 읽으며 파악을 하고있지만 이것을 만약 회사에서 사용한다면 만족할만한 결과를 낼 정도를 다룰 수 있을지가 미지수이다.  


### 목표   
  
1. 오브젝트 음향    
2. 건물 밖에 좀비가 모여있다면 건물 안에서 들리는 소리  
3. 오브젝트에 적중했을 때 소리  
4. 플레이어가 내는 사운드는 발소리를 제외하고 Steam Audio를 사용하지않아도 될 것 같음

***  
   
 