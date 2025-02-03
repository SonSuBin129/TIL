## issue

[백준 18110번](https://www.acmicpc.net/problem/18110) 문제를 풀다가 round가 이상해서 의문이 생겼다.
<br/><br/>

## content

**💡 요약** <br/>
우리가 흔히 생각하는 반올림과 파이썬 `round` 함수의 반올림은 조금 다르다.

### round 함수란?

파이썬에서 제공하는 기본 내장 함수인 round 함수는,<br/>
주어진 숫자를 지정한 소수점 자릿수에 맞춰 반올림하는 역할을 한다.

```python
round(number, ndigits)

round(3.141592, 2) # 3.14
round(3.141592, 3) # 3.142
round(3.141591) # 3
```

round 함수는 위와 같은 구문을 가지고 있으며, 두개의 인자를 받는다. number는 반올림할 숫자, ndigits는 출력될 소수점 자릿수이다.
지정하지 않으면 정수로 반올림된다.

<br/>

여기서 문제는, 파이썬의 round는 사사오입이이 아니고, 오사오입으로 처리한다.

- 사사오입 (일반적으로 생각하는 방법)<br/>
  4 이하의 숫자는 내림, 5 이상의 숫자는 올림
- 오사오입<br/>
  5 미만의 숫자는 내림, 5 초과의 숫자는 올림
  -> 그렇다면 5는?
  <br/>-> 5의 앞자리 수가 홀수이면 올림, 짝수이면 내림

**즉, 0.5는 0, 1.5는 2가 되어버림**

0.5를 반올림하기 위해서 직접 함수를 만드는 방법을 사용해야한다.

```python
def roundUp(num):
    if (num - int(num)) >= 0.5:
        return int(num) + 1
    else:
        int(num)
```

<br/>

아니면 `Decimal` 모듈을 사용하는 방법도 있다.

```python
from decimal import *
# 0.5 반올림하게 하는 세팅
getContext().rounding = decimal.ROUND_HALF_UP

print(round(Decimal(2,5),0))
```

<br/>

## 🧷 참조

- [백준 18110번 solved.ac](https://velog.io/@hamsangjin/%EB%B0%B1%EC%A4%80-18110%EB%B2%88-solved.ac-%ED%8C%8C%EC%9D%B4%EC%8D%AC)
- [Python 내장 함수 round(): 소수점 자리에 맞춰 반올림](https://ctkim.tistory.com/entry/%ED%8C%8C%EC%9D%B4%EC%8D%AC-round-%ED%95%A8%EC%88%98)
- [Python round 함수 반올림 오류 해결](https://yangnyang.tistory.com/10)
