---
title: "기초정복, 3301"
excerpt: "거스름돈"
categories: 
  - Algorithm
tags:
  - study
  - greedy
  - python
toc: true
toc_label: "Algorithm of Python"
---

## 3301 : 거스름돈
[코드업 바로가기](https://codeup.kr/problem.php?id=3301){: target="_blank"}

**문제 설명**

어떤 가게의 욕심쟁이 점원은 거스름돈을 나눠줄때 거스름돈의 개수를 적게해서 주고자 한다.

거스름돈을 입력 받아 점원이 줄 수 있는 최소 거스름돈의 개수를 출력하시오.

예를 들어 54520원인 경우,

거스름돈으로 50000원권 1장, 1000원권 4장, 500원 1개, 10원 2개 해서 총 8개이다.

(※ 현재 우리나라가 사용하고 있는 화폐를 사용한다. **10원 50원 100원 500원 1,000원 5,000원 10,000원 50,000원**)

**입력**

거스름돈 n이 입력된다. ( n은10이상의 int 범위 )

**출력**

최소 거스름돈의 개수를 출력한다.

**입력 예시**

54520

**출력 예시**

8

### 문제 정리
잔돈을 최소로 하기 위해 가장 큰 단위 순으로 잔돈을 줘야 한다고 생각했다. 그래서 가장 큰 단위 순으로
cash 라는 리스트를 만들고, 입력 받은 거스름돈을 줄여나갔다. 여기서 고려할 점은 특정 단계에서 잔돈이 음수가 되는 순간이다. 거스름돈을 더 많이 준 것이므로 되돌리는 과정을 거친 후 다음 단계로 넘어간다.

```python
cash = [50000, 10000, 5000, 1000, 500, 100, 50, 10]
change = int(input())
cnt = 0

for c in cash:
    while change > 0:
        change -= c
        cnt += 1
    if change < 0:
        change += c
        cnt -= 1

print(cnt)
```