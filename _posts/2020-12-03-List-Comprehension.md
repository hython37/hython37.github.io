---
title:  "List Comprehension 이해하기"
excerpt: "List Comprehension 2차원 출력"

categories: 
  - Algorithm
tags:
  - study
toc: true
toc_label: "Algorithm of Python"
---

## List Comprehension 2차원 출력 이해하기
구구단 2단부터 9단의 결과값 중 3 과 7의 배수가 아닌 수를  
2차원 배열로 출력하기

### 1. 일반적인 for 문
```python
result = []
for i in range(2, 10):
    arr = []
    for j in range(1, 10):
        num = i * j
        if num % 3 and num % 7:
            arr.append(num)
    result.append(arr)
print(result)
```

### 2. List Comprehension
```python
result = [[i*j for j in range(1, 10) if i*j % 3 and i*j % 7] for i in range(2, 10)]
print(result)
```

보통 리스트 컴프리헨션의 경우, 2차원을 1차원으로 만들 때 사용한다고 하는데,
갑자기 궁금해서 찾아보니 방법이 있길래 시도해보았습니다.

다음과 같은 차이점이 존재합니다.
```python
# 2차원 출력의 경우, col 열이 앞, row 행이 뒤(바깥 for문이 밖에 있어 이해하기 쉽다.)
arr = [[row*col for col in range(1, 10)] for row in range(2, 10)]
print(arr)
=> [[2, 4, 6, 8, 10, 12, 14, 16, 18], [3, 6, 9, 12, 15, 18, 21, 24, 27], [4, 8, 12, 16, 20, 24, 28, 32, 36], [5, 10, 15, 20, 25, 30, 35, 40, 45], [6, 12, 18, 24, 30, 36, 42, 48, 54], [7, 14, 21, 28, 35, 42, 49, 56, 63], [8, 16, 24, 32, 40, 48, 56, 64, 72], [9, 18, 27, 36, 45, 54, 63, 72, 81]]

# 1차원 출력의 경우, row 행이 앞, col 열이 뒤(바깥 for문이 앞에 있어 헷갈린다.)
arr = [row*col for row in range(2, 10) for col in range(1, 10)]
print(arr)
=> [2, 4, 6, 8, 10, 12, 14, 16, 18, 3, 6, 9, 12, 15, 18, 21, 24, 27, 4, 8, 12, 16, 20, 24, 28, 32, 36, 5, 10, 15, 20, 25, 30, 35, 40, 45, 6, 12, 18, 24, 30, 36, 42, 48, 54, 7, 14, 21, 28, 35, 42, 49, 56, 63, 8, 16, 24, 32, 40, 48, 56, 64, 72, 9, 18, 27, 36, 45, 54, 63, 72, 81]
```
