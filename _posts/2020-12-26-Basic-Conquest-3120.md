---
title: "기초정복, 3120"
excerpt: "리모컨"
categories: 
  - Algorithm
tags:
  - study
  - greedy
  - python
toc: true
toc_label: "Algorithm of Python"
---

## 3120 : 리모컨
[코드업 바로가기](https://codeup.kr/problem.php?id=3120){: target="_blank"}

**문제 설명**

컴퓨터실에서 수업 중인 정보 선생님은 냉난방기의 온도를 조절하려고 한다.

냉난방기가 멀리 있어서 리모컨으로 조작하려고 하는데, 리모컨의 온도 조절 버튼은 다음과 같다.

1) 온도를 1도 올리는 버튼

2) 온도를 1도 내리는 버튼

3) 온도를 5도 올리는 버튼

4) 온도를 5도 내리는 버튼

5) 온도를 10도 올리는 버튼

6) 온도를 10도 내리는 버튼

이와 같이 총 6개의 버튼으로 목표 온도를 조절해야 한다.

현재 설정 온도와 변경하고자하는 목표 온도가 주어지면 이 버튼들을 이용하여 목표 온도로 변경하고자 한다.

이 때 버튼 누름의 최소 횟수를 구하시오.

예를 들어, 7도에서 34도로 변경하는 경우,

7 -> 17 -> 27 -> 32 -> 33 -> 34

이렇게 총 5번 누르면 된다.

**입력**

현재 온도a 와 목표 온도b가 입력된다. ( 0 <= a , b <= 40 )

**출력**

최소한의 버튼 사용으로 목표온도가 되는 버튼의 횟수를 출력한다.

**입력 예시**
7 34

**출력 예시**
5

### 문제 정리
문제를 보고 재귀로 풀면 될 것 같다는 생각을 했지만 아직 재귀에 미숙하므로 기초적인 조건문을 활용해 풀어보았다.

온도차를 점점 좁혀나간다는 생각으로 풀었다. 여기서 고려할 점은 차이가 양수인지 음수인지, 차이값이 몇인지 2 가지다. 차이값의 범위에 따라 한번에 온도를 올리고 내릴 수 있기 때문이다.

특히 4, 8, 9 차이값의 경우 단계를 줄일 수 있다. 8을 예로 들면, +5 +1 +1 +1 로 4번 조작 보다 +10 -1 -1 로 3번 조작으로 단축할 수 있다. 4, 9는 최소 2번, 8은 최소 3번이다. 음수도 동일

```python
a, b = map(int, input().split())
cnt = 0
difference = abs(a-b)
while difference:
    if a > b:
        if difference >= 10:
            a -= 10
        elif difference == 9:
            a -= 9
            cnt += 1
        elif difference == 8:
            a -= 8
            cnt += 2
        elif difference >= 5:
            a -= 5
        elif difference == 4:
            a -= 4
            cnt += 1
        elif difference >= 1:
            a -= 1
    else:
        if difference >= 10:
            a += 10
        elif difference == 9:
            a += 9
            cnt += 1
        elif difference == 8:
            a += 8
            cnt += 2
        elif difference >= 5:
            a += 5
        elif difference == 4:
            a += 4
            cnt += 1
        elif difference >= 1:
            a += 1
    cnt += 1
    difference = abs(a-b)
print(cnt)
```