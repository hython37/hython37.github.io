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
> 파이썬 내장함수가 실제로 어떻게 되어있는지 모르겠지만 내장함수의 로직을 정리하고 싶었습니다.

### arr.reverse()

```python
def solution(arr):
    left, right = 0, len(arr)-1
    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1
    return arr
```

하나씩 추가 예정입니다.