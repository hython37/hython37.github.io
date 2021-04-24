---
title:  "Built-in Functions"
excerpt: "Python Methods"

categories: 
  - Algorithm
tags:
  - study
toc: true
toc_label: "Algorithm of Python"
---

## 파이썬 내장함수
> 파이썬 내장함수 관련 포스팅, 알고리즘 문제를 풀다가 확실히 모르는 내용 또는 동작원리 등을 알고 싶을 때 내용을 추가할 예정입니다.


### arr.reverse()
리스트에서만 사용 가능하며, 요소를 뒤집는다. 순서x

```python
def solution(arr):
    left, right = 0, len(arr)-1
    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1
    return arr
```

### zip(*iterable)
길이가 같은 자료형을 묶어 주는 역할을 하는 함수

```python
for score1, score2 in zip([20, 50, 40], [10, 50, 70]):
    print(score1, score2)

> 20 10
  50 50
  40 70
```
이와 같은 형태로 많이 쓰인다.


다음과 같은 튜플 자료형으로 출력된다.

```python
for score in zip([20, 50, 40], [10, 50, 70]):
    print(score)

> (20, 10)
  (50, 50)
  (40, 70)
```

### format()
1. 반올림
```python
a = 3.145

print(format(round(a, 2), ".2f"))
> 3.15

print(format(a, ".2f"))
> 3.15
```

2. 진수 변환
```python
a = 60

print(format(a, '#b'))
print(format(a, 'b'))
print(format(a, '#o'))
print(format(a, 'o'))
print(format(a, '#x'))
print(format(a, 'x'))

> 0b111100
> 111100
> 0o74
> 74
> 0x3c
> 3c
```

하나씩 추가 예정입니다.