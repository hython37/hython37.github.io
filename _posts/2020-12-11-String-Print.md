---
title:  "문자열 반복 출력"
excerpt: "문자열 순회하기"

categories: 
  - Algorithm
tags:
  - study
toc: true
toc_label: "Algorithm of Python"
---

## 문자열 순회 출력하기
> 입력 숫자만큼 반복출력

| tile_length |    answer     |
| ----------- | ------------- |
| 11          | "RRRGGBRRRGG" |

```python
def solution(tile_length):
    answer = ''
    com = 'RRRGGB'
    for i in range(tile_length):
        answer += com[i % 6]  # 6자리 반복, 1개씩 덧붙이기
    return answer
```