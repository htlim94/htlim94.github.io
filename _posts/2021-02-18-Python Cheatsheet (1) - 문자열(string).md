---
title:  "Python Cheatsheet (1) - 문자열(string)"
excerpt: "본 포스트는 Python 언어의 기초개념과 문법, 주요 함수들을 요약하여 정리한 Cheatsheet 시리즈의 일환입니다."

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

### 숫자형 종류
- `123` `1.2` `4.24e10` `0o177` `0x8ff`

### 문자열 종류
- `'Python\'s favorite food'`
- `"Python's favorite food"`
- `'''hello world'''`
- `"""hello world"""`

### 가독성을 위한 문자열 줄바꿈
```python
"First sentence. \
Second sentence."
```

### 개행을 포함한 문자열
```python
"Life is too short\nYou need python"
```
```python
'''  
Life is too short  
You need python  
'''
```

## 3. 기본

### 거듭제곱, 나눗셈, 몫반환, 나머지반환
- `a ** b`
- `a / b`
- `a // b`
- `a % b`

### 문자열에 이스케이프 문자 포함하기
- `r"Newlines by \n"`

### 문자열 연산
- `"Python" + " studying"`
- `"Python" * 4`

### Indexing
- `string[0:3]`

### Formatting
- `"I eat %d%% of %s" % (98, "apples")`
- `"%10.4f" % 3.141592`  
  → `'    3.1415'`
- `"I eat {0:0.4f}% of {fruit}".format(98.123123, fruit="apples")`  
  → `I eat 98.1231% of apples`  
  `{0:0.4f}`을 `{0.4f}`로 간소화 가능

## 4. 함수

### count
- `"Python good".count('o')`  
  → `3`

### find, index
- `"Python good".find('o')`  
  → `4`
  만약 없는 문자면 `-1` 반환
- `"Python good".index('o')`  
  → `4`
  만약 없는 문자면 오류 발생

### join, split
- `", ".join('abcd')` `", ".join(['a', 'b', 'c', 'd'])`  
  → 'a, b, c, d'
- `"a b c d".split()` `"a:b:c:d".split(':') `  
  → ['a', 'b', 'c', 'd']

### upper, lower
- `"hi".upper()`  
  → `HI`
- `"HI".lower()`  
  → `hi`

### strip
- `" hi ".lstrip()`  
  → `'hi '`
- `" hi ".rstrip()`  
  → `' hi'`
- `" hi ".strip()`  
  → `'hi'`

### replace
- `"Python good".replace("good", "bad")`  
  → `Python bad`