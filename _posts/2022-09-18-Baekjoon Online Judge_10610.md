---
layout: single
title: "[백준 알고리즘] - 10610번문제 : 30"
categories:
  - Baekjoon Online Judge
tags:
  - Algorithm
  - Greedy
  - Python
  - Bakejoon
  - Online Judge
---

# ✈ [백준 알고리즘] 문제 10610번 : 30

[★ 백준 알고리즘 10610번 : 30](https://www.acmicpc.net/problem/10610)

👀 문제 설명

- 👩‍🦰 어느 날, 미르코는 우연히 길거리에서 양수 N을 보았다. 미르코는 30이란 수를 존경하기 때문에, 그는 길거리에서 찾은 수에 포함된 숫자들을 섞어 30의 배수가 되는 가장 큰 수를 만들고 싶어한다.
- 마르코를 도와 그가 만들고 싶어하는 수를 계산하는 프로그램을 작성하라.

___

👀 입력

- N을 입력받는다. N는 최대 10의(5승) 개의 숫자로 구성되어 있으며, 0으로 시작하지 않는다.

___

👀 출력

- 미르코가 만들고 싶어하는 수가 존재한다면 그 수를 출력하라. 그 수가 존재하지 않는다면, -1을 출력하라.

---

👀 문제 해결 아이디어

- 이 문제는 **'배수 판정법'**을 다룬다. [★ 배수 판정법](https://ko.wikipedia.org/wiki/%EB%B0%B0%EC%88%98_%ED%8C%90%EC%A0%95%EB%B2%95)
- 3의 배수 판정법에 의하면, **모든 자리 수의 합이 3의 배수**이다.
  - 210 -> 2 + 1 + 0 = **3** 👍
  - 3360 -> 3 + 3 + 6 + 0 = **12**👍
  - 1234 -> 1 + 2 + 3 + 4 = **10** 👎

- 또한, 이 문제는 **30의 배수이기 때문에 일의 자리에 0이 있는지 확인**해야 한다.

---

👀 소스 코드

```python
n = int(input()) # 정수 입력 받기
str_n = str(n) # 입력 받은 정수 문자형으로 변환하여 저장
save = [] # 리스트 생성

end = False # while 문 돌기 위한 변수

   	
    # - 입력 받은 정수 내림차순 정렬 - 

while not end:
    for i in str_n:
        save.append(int(i))
    save.sort(reverse=True)

    # - 일의 자리가 0인지 확인 -
    if save[len(save)-1] != 0:
        print(-1)
        end = True

    # - 입력된 정수들을 다 더한 후 3의 배수일 때 -
    elif sum(save) % 3 == 0:
        for j in save:
            print(j, end="")
            end = True

    # - 입력된 정수들을 다 더한 후 3의 배수가 아닐 때 -
    else:
        print(-1)
        end = True
```



