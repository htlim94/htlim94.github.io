---
title:  "[Python] NumPy 기초 (1)"
excerpt: "본 포스트는 Python 언어의 기초개념과 문법, 주요 함수들을 요약하여 정리한 Cheatsheet 시리즈의 일환입니다."
date: 2021-03-08
lastmod: 2021-03-08
changefreq: daily
priority: 1.0

categories:
  - Cheatsheet
tags:
  - python
  - numpy
  - datascience
---

## 1. 개요
넘파이(NumPy)는 파이썬(Python)언어의 주요 라이브러리로, 행렬연산에 사용됩니다.
대규모 다차원 배열과 정교한 broadcasting 기능, 높은 호환성 등으로 데이터 분석 업무에 널리 사용되고 있습니다.
DataCamp의 **Python For Data Science Ceat Sheet NumPy Basics** 문서를 참고하였습니다.

### NumPy 로딩
`import numpy as np`

### 1차원, 2차원, 3차원 array와 axis
![](/assets/images/2021-03-08/array_axis.png)

## 2. 정의

### list -> ndarray
- `np.array([1,2,3])`, 1D ndarray
- `np.array([(1.5,2,3), (4,5,6)], dtype = float)`, 2D ndarray, float type
- `np.array([[(1.5,2,3), (4,5,6)], [(3,2,1), (4,5,6)]], dtype = float)`, 3D ndarray, float type

### Placeholder 지정(초기화)
- `np.zeros((3,4))`, 0으로 이루어진 3x4 array 생성
- `np.ones((2,3,4),dtype=np.int16)`, 1로 이루어진 2x3x4 array 생성
- `np.full((2,2),7)`, 7로 이루어진 2x2 array 생성
- `np.eye(2)`, 2x2 단위 행렬 생성
- `np.random.random((2,2))` Create an array with random values
- `np.empty((3,2))`, 3x2 비어있는 array 생성

- `np.arange(10,25,5)`, 10부터 25미만까지 5간격으로 데이터 생성
- `np.linspace(0,2,9)`, 0부터 2까지 균일한 간격으로 9개의 데이터 생성
- `np.logspace(0.1,1,20)`, 10^0.1부터 10^1까지 균일한 간격으로 20개의 데이터 생성

## 3. 데이터 입출력

### 디스크에 저장
- `np.save('./my_array', a)`, 1개 배열 저장, 확장자: npy
- `np.savez('./array.npz', a, b)`, 여러개 배열 저장, 확장자: npz
- `np.load('./my_array.npy')`, npy/npz파일 읽어오기

### 텍스트 파일로 저장
- `np.savetxt("myarray.txt", a, delimiter=" ")`, txt/csv파일로 저장
- `np.loadtxt("./myfile.txt")`, txt/csv파일 읽어오기
- `np.genfromtxt("my_file.csv", delimiter=',')`, txt/csv파일 읽어오기: loadtxt보다 세밀한 기능 제공

## 4. 데이터 타입

- `np.int64`, 부호 있는 정수 타입(64-bit)
- `np.uint32`, 부호 없는 정수 타입(32-bit)
- `np.float32`, 부동소수 타입(32-bit)
- `np.complex`, 복소수 타입(128-bit float)
- `np.bool`, Boolean 타입
- `np.object`, 파이썬 객체 타입
- `np.string_`, 고정자리 문자열 타입
- `np.unicode_`, 고정자리 유니코드 타입

## 5. 상태 검사(Inspecting)

- `a.shape`, Array의 shape 속성
- `len(a)`, 일차원 array의 길이
- `b.ndim`, Array의 차원 수
- `e.size`, Array의 요소 수: shape(k, m, n) -> k*m*n
- `b.dtype`, Array의 타입 확인
- `b.dtype.name`, Array의 타입 이름 확인
- `b.astype(int)`, Array의 요소 타입 변환: 실제 값이 변하는 것이 아닌 보이는 값만 변화

## 6. 도움말

- `np.info(np.ndarray.dtype)`
- `np.info(np.squeeze)`