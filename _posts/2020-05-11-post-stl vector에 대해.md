---
layout: post
title: "Dev : STL vector 사용에 관한 내용"

categories:
  - Dev
tags:
  - C++
  - STL
  - Knowledge
---

## STL Vector  
***  

__vector__ 관련 레퍼런스는 책이나 검색하면 더 잘나올 것이므로 생략한다.  

#### 2차원 배열 초기화  
``` c++  
vector<vector<int>> v(y, vector<int>(x, initialized_value));  
```  
여기서 initialized_value에 들어갈 값은 생략해도 된다.  

***  

#### 3차원 배열 초기화  
``` c++  
 vector<vector<vector<int>>> v(z, vector<vector<int>>(y, vector<int>(x, initialized_value)));  
```  
***

  