---
layout: post
title: "Dev : ScriptableObject에 대한 글"

categories:
  - Dev
tags:
  - Knowledge
  - Unity
  - C#
---

## Scriptable Object 소개  

[설명](https://docs.unity3d.com/Manual/class-ScriptableObject.html)  


#### Scriptable Object를 어떻게 써왔는지  

나는 주로 Scriptable Object를 Editor 상에서 프로젝트에 사용할 데이터를 미리 저장하는 용도로 사용한다.    
하지만 이것을 저장하려는 목적까지 이루려고 하다보니 Scriptable Object의 본질과는 멀어지는 느낌을 받아서 사용 방법과 데이터 설계를 다시 해보려고한다.    
  
#### 주의점  

Scrptable Object는 github에서 변경된 부분만 추적이 가능한 것이 아닌 전체가 변경된 것으로 처리되기에 주의해야된다.  
게임이 실행 될 때 내부의 값을 변경한다면 이 데이터를 사용하는 모든 인스턴스들에 영향을 받는다.  

#### 어떻게 바꿀 것인가?  
  
Scriptable Object는 정말 단순하게 값을 가져오는 용도로 쓰기만 하는 것이다.  
내부 값을 전달하기 위한 용도로 interface를 상속 받는다.  
인게임에서 사용할 데이터는 따로 class나 struct로 작성하여 관리한다.  
uniqueId는 데이터마다 다르기에 ScriptableObject에 놓지않는다.  
ScriptableObject에 넣을 만한 건 tableId(itemCode) 정도가 있을 것같다.


#### 예시  

``` c++

[System.Serializable]
public class IngameData : IData
{
	private string uniqueId;
	private float currentHp;
	private float currentGold;

	#region <IData Property>

	public float CurrentHp => currentHp;
	public float CurrentGold => currentGold;

	#endregion

	//새로 생성
	public IngameData(float _hp,  float _gold)
	{
		uniqueId = Guid.NewGuid().ToString();
		currentHp = _hp;
		currentGold = _gold;
	}

	//저장 된 것 불러올 때
	public IngameData(string _guid, float _hp, float _gold)
	{
		uniqueId = _guid;
		currentHp = _hp;
		currentGold = _gold;
	}
}


public class DataObject : ScriptableObject 
{
	[SerializeField] private float maxHp;
	[SerializeField] private float maxDamage;
	[SerializeField] private float minDamage;

	public float MaxHp => maxHp;
	public float MaxDamage => maxDamage;
	public float MinDamage => minDamage;
}

```

ScriptableObject는 게임에 필요한 정보에만 집중했고 IngameData는 현재 정보에 집중했다.  
ScriptableObject를 관리하는 곳에서는 ScriptableObject를 불러와서 복사본을 만든 뒤에 그 복사본을 다루는 것이 맞는 것같다.  
이 방법도 훗날 잘못된 점이 생겨 수정될 수 있다. 다만 현재는 이 방법이 내가 생각한 것중 제일 나은 것같다.  

***  
   
 