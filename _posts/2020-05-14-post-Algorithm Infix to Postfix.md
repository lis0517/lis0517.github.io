---
layout: post
title: "Algorithm : Infix to Postfix (중위 표현식에서 후위 표현식으로)"

categories:
  - Algorithm
tags:
  - C++
  - Algorithm
---

## Infix to Postfix 
---  
중위 표기식에서 후위 표기식으로 변경해주는 알고리즘이다.  
stack 응용에서 한번 쯤 다뤄볼만한 예제이다.  
  
ex) (Infix) 1+2/3-(4+5)x6 -> (Postfix) 123/+45+6x- 

***  

## 먼저 알고 가야할 것  
  
해당 문제를 푸는 데 연산 우선 순위가 존재하기 때문에  
알아두고 알고리즘을 설계한다.  
  
__'(' < '+' = '-' < 'x' = '/'__  
  
## 알고리즘 설명  
   
__변환하는 법__  
  
1. '(' 를 만나면 스택에 푸시한다.  
2. ')' 를 만나면 스택에서 '('가 나올 때까지 pop을 수행하여 출력 또는 저장하고 '('은 pop을 하여 버린다.  
3. 연산자를 만나면 스택에서 그 연산자보다 낮은 우선 순위의 연산자를 만날 때까지 pop하여 출력 또는 저장한 뒤에 자신을 push한다.  
4. 피연산자는 그냥 출력 또는 저장한다.
5. 모든 과정이 끝나면 스택에 남아있는 모든 연산자들을 pop을 하여 출력 또는 저장한다.  
  
``` c++
string infix2Postfix(string infixExpression)
{
    string postExpression;
    stack<char> st;

    for (auto c : infixExpression)
    {
        switch (c)
        {
        case '(':
            st.push(c);
            break;
        case ')':
            while (st.top() != '(')
            {
                postExpression.push_back(st.top());
                st.pop();
            }
            st.pop();
            break;
        case '+':
        case '-':
            //+와 -는 (를 제외하고 스택에서 꺼낼 수 있다.
            while (st.size() > 0 && st.top() != '(')
            {
                postExpression.push_back(st.top());
                st.pop();
            }
            st.push(c);
            break;
        case '*':
        case '/':
            //*와 /는 자신보다 우선 순위가 높은 연산자가 없다.
            //+,-를 만나기 전까지 *와 /를 꺼낸 뒤 자신을 집어넣는다.
            while (st.size() > 0 && (st.top() == '*' || st.top() == '/'))
            {
                postExpression.push_back(st.top());
                st.pop();
            }
            st.push(c);
            break;
        default:
            postExpression.push_back(c);
            break;
        }
    }
    //남은 연산자를 모두 더해준다.
    while (st.size() > 0)
    {
        postExpression.push_back(st.top());
        st.pop();
    }
    return postExpression;
}
```

__계산하는 법__  
  
1. 연산자를 만날 때까지 이동.  
2. 연산자를 만났다면 피연산자 두개를 해당 연산자와 계산후 저장  
3. 반복  

``` c++
bool isOperator(char c)
{
    return (c == '*' || c == '-' || c == '+' || c == '/');
}

double postExpressCaculator(string postExpress)
{
    vector<double> temp;
    //C++11 이하에서는 iterator나 인덱스로 접근
    for (auto c : postExpress)
    {
        if (isOperator(c))
        {
            //숫자 배열에서 뒤에 있는 것을 가져오고 제거함
            double a = temp.back(); temp.pop_back();
            double b = temp.back(); temp.pop_back();
            switch (c)
            {
            case '+':
                temp.push_back(a + b);
                break;
            case '-':
                temp.push_back(a - b);
                break;
            case '*':
                temp.push_back(a * b);
                break;
            case '/':
                temp.push_back(a / b);
                break;
            }
        }
        else {
            char i = c - '0';
            temp.push_back(i);
        }
    }
    return temp[0];
}
```
  




