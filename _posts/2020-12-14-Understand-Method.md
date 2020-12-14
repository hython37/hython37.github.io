---
title:  "함수 이해하기"
excerpt: "lambda X map"

categories: 
  - Algorithm
tags:
  - study
toc: true
toc_label: "Algorithm of Python"
---

## lambda 와 map 함수 이해하기
> 알고리즘 풀이를 이해해봅시다.  
(알고있는 내용을 정리한 것으로 정확하지 않음)

| score                            | return                   |
| -------------------------------- | ------------------------ |
| [90, 87, 87, 23, 35, 28, 12, 46] | [1, 2, 2, 7, 5, 6, 8, 4] |

각 점수에 해당하는 순위를 출력하는 문제입니다.

```python
def solution(score):
    answer = [0] * len(score)
    for i in range(len(score)):
        answer[i] = sum(map(lambda x:x > score[i], score))+1 #here
    return answer
```
map 함수는 map(<u>함수</u>, <u>리스트</u>) 와 같은 형태로 쓰여  
**<u>리스트</u> 각 요소에 <u>함수</u>를 적용시켜** 리스트를 만드는 함수입니다.

lambda 는 함수의 정의 축약식 정도로 이해하고 있습니다.  
위와 같이 `lambda x:x > score[i]` 라고 하면 `원소 x(정의역)에 대해 결과 값 x > score[i](치역)을 나타내는 함수` 로 알고 있습니다.

그러므로 위 solution 함수의 #here 는  
**<u>score</u> 각 요소에 <u>lambda x: x > score[i]</u>[^1] 를 적용시켜** 만든  
`리스트의 총합+1`의 값을 answer[i] 자리에 저장합니다.  

<hr/>
[^1]: 결과 값 `x > score[i]`는 T/F 로 1 or 0 이 기록되어 x 가 score`[i]` 보다 크면 1이다.