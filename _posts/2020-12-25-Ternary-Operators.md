---
title:  "Ternary operators"
excerpt: "삼항연산자"

categories: 
  - Algorithm
tags:
  - study
toc: true
toc_label: "Algorithm of Python"
---

## Python Ternary operators
> 파이썬은 일반적으로 " ? : " 으로 간단히 표기되는 삼항연산자와 다르다

### A and B or C
if else 만 알고 있었는데 논리 연산의 방법으로 a and b or c도 가능하다  
a에 조건, b에 True일 때 결과값, c 에 False일 때 결과값

```python
print(3 > 5 and '5가 큼' or '3이 작음')
> 3이 작음
```

다만, b의 값이 0이 되는 경우 문제발생  
a가 참이면 b가 출력되야하는데 c가 출력됨

```python
print(100 == 100 and 100-100 or 100+100)
> 200
```

이러한 문제때문인지 if else 형태로 활용가능함
### True if condition else False
```python
print('5가 큼' if 3 > 5 else '3이 작음')
> 3이 작음
```

```python
print(100 - 100 if 100 == 100 else 100+100)
> 0
```

위와 같이 쓸 수 있음