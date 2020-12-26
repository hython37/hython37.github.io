---
title: "기초정복, 2001"
excerpt: "최소 대금"
categories: 
  - Algorithm
tags:
  - study
  - greedy
  - python
toc: true
toc_label: "Algorithm of Python"
---

## 2001 : 최소 대금
[코드업 바로가기](https://codeup.kr/problem.php?id=2001){: target="_blank"}

**문제 설명**

파파 파스타 가게는 점심 추천 파스타와 생과일 쥬스 세트 메뉴가 인기가 좋다.

이 세트 메뉴를 주문하면 그 날의 3 종류의 파스타와 2 종류의 생과일 쥬스에서 하나씩 선택한다.

파스타와 생과일 쥬스의 가격 합계에서 10%를 더한 금액이 대금된다.

어느 날의 파스타와 생과일 쥬스의 가격이 주어 졌을 때, 그 날 세트 메뉴의 대금의 최소값을 구하는 프로그램을 작성하라.

**입력**

입력은 5 행으로 이루어지며, 한 줄에 하나씩 양의 정수가 적혀있다.

1행의 정수는 첫 번째 파스타 가격이다.

2행의 정수는 두 번째 파스타 가격이다.

3행의 정수는 세 번째 파스타 가격이다.

4행의 정수는 첫 번째 생과일 쥬스 가격이다.

5행의 정수는 두 번째 생과일 쥬스의 가격이다.

(모든 파스타와 생과일 쥬스의 가격은 100 원이상 2000원 이하이다.)

**출력**

그날 세트 메뉴의 최소 대금을 소수 첫째자리까지 출력하시오.



**입력 예시**

800  
700  
900  
198  
330

**출력 예시**

987.8

### 문제 정리
세트메뉴는 파스타 1개, 주스 1잔으로 구성된다. 세트메뉴의 가격은 파스타와 주스를 합한 가격에 10% 를 더한 값이다.

모든 세트메뉴의 가격을 구한 뒤 그 중 최소값을 출력하였다. 

```python
pasta = []
for t in range(3):
    pasta.append(int(input()))
juice = []
for t in range(2):
    juice.append(int(input()))

set_price = []
for p in pasta:
    for j in juice:
        set_price.append((p+j)*1.1)
        
print(format(min(set_price), '.1f'))
```