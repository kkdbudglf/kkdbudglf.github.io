---
layout: single
title: "[구현 알고리즘] - 상하좌우"
categories:
  - Algorithm
tags:
  - Algorithm
  - Implementation 
  - Python
---

# ✈ [구현 알고리즘] 상하좌우

[★ 구현 알고리즘이란?](https://kkdbudglf.github.io/algorithm/Implement-Algorithm/)

👀 문제 설명

- 여행가 A는 **N X N** 크기의 정사각형 공간위에 서있다. 이 공간은 1 X 1 크기의 정사각형으로 나누어져 있다. 가장 왼쪽 위 좌표는 (1, 1)이며, 가장 오른쪽 아래 좌표는 (N, N)에 해당한다. 여행가 A는 **상, 하, 좌, 우 방향으로 이동**할 수 있다. 시작 좌표는 항상 (1, 1)이다. 우리 앞에는 여행가 A가 이동할 계획이 적힌 계획서가 놓여있다.
- 계획서에는 하나의 줄에 띄어쓰기를 기준으로 하여 L, R, U, D중 하나의 문자가 반복적으로 적혀있다. 각 문자의 의미는 다음과 같다.

- L: **왼쪽**으로 한 칸 이동
- R: **오른쪽**으로 한 칸 이동
- U: **위**로 한 칸 이동
- D: **아래**로 한 칸 이동



- 이때 여행가 A가 N X N 크기의 정사각형 공간을 벗어나는 움직임은 무시된다. 예를 들어 (1, 1)의 위치에서 L 혹은 U를 만나면 무시된다. 

  ![상하좌우 맵](../../images/2022-09-20-UP, DOWN, LEFT, RIGHT/상하좌우 맵.jpg)

___

👀 입력

- 첫째 줄에 공간의 크기를 나타내는 N이 주어집니다. (1 <= N <= 100)
- 둘째 줄에 여행가 A가 이동할 계획서 내용이 주어집니다.

___

👀 출력

- 첫째 줄에 여행가 A가 최종적으로 도착할 지점의 좌표 (X, Y)를 공백을 기준으로 구분하여 출력합니다.

---

👀 문제 해결 아이디어

- 이동할 계획서와 move_types = ['L', 'R', 'U', 'D'] 를 비교한다.

---

👀 소스 코드

```python
# n 입력 받기
n = int(input())
x, y = 1, 1
plans = input().split()

# L, R, U, D
dx = [0, 0, -1, 1]
dy = [-1, 1, 0, 0]
move_types = ['L', 'R', 'U', 'D']

# plans 하나씩 대입
for plan in plans:
    # 이동 후 좌표 구하기
    for i in range(len(move_types)):
        if plan == move_types[i]:
            nx = x + dx[i]
            ny = y + dy[i]
    # 정사각형 공간을 벗어나는지 확인
    if nx < 1 or ny < 1 or nx > n or ny > n:
        continue
    x, y = nx, ny
print(x, y)
```



