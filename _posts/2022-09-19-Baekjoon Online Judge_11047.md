---
layout: single
title: "[백준 알고리즘] - 11399번문제 : ATM"
categories:
  - Baekjoon Online Judge
tags:
  - Algorithm
  - Greedy
  - Python
  - Bakejoon
  - Online Judge
---

# ✈ [백준 알고리즘] 문제 11047번 : 동전 0

[★ 백준 알고리즘 11047번 : 동전 0](https://www.acmicpc.net/problem/11047)

👀 문제 설명

- 준규가 가지고 있는 동전은 총 N종류이고, 각각의 동전을 매우 많이 가지고 있다.

- 동전을 적절히 사용해서 그 가치의 합을 K로 만들려고 한다. 이때 필요한 동전 개수의 최솟값을 구하는 프로그램을 작성하시오.

___

👀 입력

- 첫째 줄에 N과 K가 주어진다. (1 ≤ N ≤ 10, 1 ≤ K ≤ 100,000,000)
- 둘째 줄부터 N개의 줄에 동전의 가치 Ai가 오름차순으로 주어진다. (1 ≤ Ai ≤ 1,000,000, A1 = 1, i ≥ 2인 경우에 Ai는 Ai-1의 배수)

___

👀 출력

- 첫째 줄에 K원을 만드는데 필요한 동전 개수의 최솟값을 출력한다.

---

👀 문제 해결 아이디어

- 개수의 최솟값을 구하려면 **제일 큰 동전단위부터 K를 나눈다.**

---

👀 소스 코드

```python
n, k = map(int, input().split())  # 동전 개수, 만드려는 돈 입력 받기
a = []
count = 0

for i in range(n): # n입력 받은 만큼 동전 종류 입력받기
    a.append(int(input()))

a.sort(reverse=True)  # 제일 큰 값부터 몫을 구하기 위한 내림차순 정렬

for j in a:
    count += k // j 
    k %= j

print(count)
```

