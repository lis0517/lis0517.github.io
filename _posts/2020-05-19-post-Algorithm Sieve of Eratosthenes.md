---
layout: post
title: "Algorithm : Sieve of Eratosthenes (에라토스테네스의 체)"

categories:
  - Algorithm
tags:
  - C++
  - Algorithm
---

## Sieve of Eratosthenes  
---  
O(N^2)의 성능을 가지는 2중 for문 소수 찾기를  
바꿔주는 알고리즘이다.  
  
***  
   
## 알고리즘 설명  
   
__해결 전략__  
  
1. n을 입력받는다.  
2. n이 1이하이면 소수는 없으므로 0을 반환한다.  
3. 판별용으로 쓸 배열을 전부 소수라는 가정으로 초기화한다.  
4. 2부터 반복을 시작한다.  
5. 검사하지않은 숫자라면  
- 5.1 해당 숫자를 정답 배열에 추가한다.  
- 5.2 반복문으로 해당 숫자의 배수를 전부 검사된 값으로 처리한다.  
6. 4번으로 돌아가 반복한다.  
    
``` c++
int sieve_of_erastosthenes(int n)
{
    if(n <= 1) return 0;

    vector<int> prime; 

    bool * isprime = new bool[n+1];
    for(int i=2; i <= n; ++i) isprime[i] = true;

    for(int i=2; i <= n; ++i)
    {
        if(isprime[i])
        {
            prime.push_back(i);
            for(int j = i * i; j <= n; j += i)
            {
                isprime[j] = false;
            }
        }
    }

    /*처리할 내용*/

    return prime.size();
}
```


