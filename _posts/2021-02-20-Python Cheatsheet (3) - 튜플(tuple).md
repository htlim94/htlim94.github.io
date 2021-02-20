---
title:  "Python Cheatsheet (3) - 튜플(tuple)"
excerpt: "본 포스트는 Python 언어의 기초개념과 문법, 주요 함수들을 요약하여 정리한 Cheatsheet 시리즈의 일환입니다."
date: 2021-02-20
lastmod: 2021-02-20
changefreq: daily
priority: 1.0

categories:
  - Cheatsheet
tags:
  - python
  - basic
---

## 1. 개요
본 포스트는 Python 언어의 기초개념과 문법, 주요 함수들을 요약하여 정리한 Cheatsheet 시리즈의 일환입니다.  
실무에 투입되는 사용자가 빠르게 접근할 수 있도록 디테일은 과감하게 삭제하였습니다.  
때문에 Python을 처음 접하는 사람에게 적합한 포스트가 아닙니다.

암기를 최소화하고 필요한 것을 즉각 찾아보며 프로그래밍하는 습관을 기르고자 합니다.

## 2. 정의

- `()` `(1,)` `(1, 2, 3)` `1, 2, 3`
- `a = (1, 2, 'A', 'B')`, immutable

## 3. 기본

### Slicing
- `a[3]`  
  → `'B'`

### 연산
- `(1, 2, 3) + (4, 5, 6)`  
  → `(1, 2, 3, 4, 5, 6)`

### 길이
- `len(a)`  
  → `4`

### Packing
- `c = (3, 4)`

### Unpacking
- `a, b = c`

### `tmp`변수 없이 값바꾸기
- `x, y = y, x`

## 4. for문에서의 사용
```python
for a in enumerate(list): # index와 value가 tuple로 묶임
    print('{}번째 값: {}'.format(a[0], a[1]))

for a in enumerate(list):
    print('{}번째 값: {}'.format(*a)) # *은 tuple을 쪼갠다는 의미
```

```python
for a in dict.items(): # key와 value가 tuple로 묶임
    print('{}의 나이는:{}'.format(a[0], a[1]))

for a in dict.items():
    print('{}의 나이는:{}'.format(*a)) # *은 tuple을 쪼갠다는 의미
```