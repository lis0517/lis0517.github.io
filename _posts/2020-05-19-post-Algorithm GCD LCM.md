---
layout: post
title: "Algorithm : GCD & LCM (최대공약수 최소공배수)"

categories:
  - Algorithm
tags:
  - C++
  - Algorithm
---

## GCD 
---  
최대 공약수를 구하는 알고리즘으로 가장 유명한 것이  
유클리드의 알고리즘이다.  
   
***  
  
## 최적화 되지않은 알고리즘 설명  
   
최대 공약수의 성질을 이용해 뺄셈과 두 값의 교환이라는 동작으로  
구할 수 있으며 A와 B라는 정수가 최대 공약수 G를 가지면 이렇게  
표현가능하다.  
  
A = a x G, B = b x G (a와 b는 서로소이다.)  
  
따라서 해당 식이 성립가능하다.  
GCD(a,b) = GCD(a-b, b) - 식1  
GCD(a,b) = GCD(b, a) - 식2  
GCD(a,0) = a -식3  
  
__해결 전략__  
  
1. 임의의 두 정수 u와 v를 입력받는다.  
2. v가 u보다 크다면 v와 u의 값을 교환한다.  
3. u에다가 u-v값을 저장  
4. u가 0이면 v가 최대 공약수이다.  
  
``` c++
int get_gcd(int u, int v)
{
    int t;
    while(u)
    {
        if(u < v)
        {
            t=u; u = v; v = t;
        }
        u = u-v;
    }
    return v;
}
```
  
## 최적화 된 알고리즘 설명  
  
뺄셈으로 최대 공약수를 구하게 된다면 연산수가 많아서 성능이 좋지 못하다.  
뺄셈을 하면서 얻은 규칙으로 최적화를 하게 된다.  
250과 30을 예로 들었을 때 10과 30으로 되는데 10은 250을 30으로 나눈  
나머지 값임을 알 수있다.  
  
__해결 전략__  
  
1. 임의의 두 정수 u와 v를 입력받는다.  
2. v가 0인가? 이면 u가 최대 공약수
- 2.1. u에 u%v를 대입
- 2.2. u와 v의 값을 교환  
3. 2로 돌아감 
  
``` c++
int gcd_modulus(int u,int v)
{
    int t;
    while(v != 0)
    {
        t = u%v;
        u = v;
        v = t;
    }
    return u;
}
```
  
## LCM  
    
최소 공배수는 최대 공약수를 이용해 계산한다.  
최대 공약수 x 최소 공배수 = a x b;  
  
따라서 식은 (최소 공배수 = a x b / 최대 공약수)가 된다.  

``` c++

int get_lcm(int u, int v)
{
    return u*v / gcd_modulus(u,v);
}

```