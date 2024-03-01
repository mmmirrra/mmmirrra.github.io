---
layout: post
title:  "Discrete Mathematics: Concept"
date:   2024-03-01 09:00:00 +0900
categories: [DiscreteMathematics]
---

### 지식?   
DATA -> INFORMATION -> KNOWLEDGE -> WISDOM   
   
<br />
### 수학 Mathematics?   
- 영어 Mathematics의 어원은 '배우는 모든 것'이라는 뜻   
- 수나 연산에 국한된 것이 아닌 일반적인 학문이나 지식, 좀더 구체적으로는 직접 사물을 상대하지 않고 배우거나 생각함으로써 알게 되는 지식   
- 생각의 과정을 연습하고 문제 해결 능력을 키우는 도구   
   
|수학|이산수학|
|:---|:---|
|- 대수학 : 방정식<br />- 해석학 : 극한, 수열, 급수, 미분, 적분 등<br />- 기하학|- 연속수학<br />- 이산수학|
   
<br />
### 이산수학에서 실력을 높이려면?   
지식 체계를 만드는 훈련을 해야 함   
   
<br />
### 이산수학 Discrete Mathematics 이란?   
- 이산적인 수학구조에 대해서 연구하는 학문   
- 이산적 데이터를 처리하기 위해 필요한 수학   
   
#### 이산수학을 배우는 이유   
- 컴퓨터과학의 기초를 이해하기 위해   
- 문제해결 방법을 모델링하는 과정을 이해하고 훈련하기 위해   
- 수학적 논리전개 방법을 익히기 위해   
- 새로운 개념을 체계화시키고 표현할 수 있는 역량을 함양하기 위해   
   
#### 주요내용   
- 논리 Logic   
- 증명 Proofs   
- 귀납법 Induction   
- 집합 Sets   
- 행렬 Matrices   
- 관계 Relations   
- 함수 Functions   
- 부울대수 Boolean Algebra   
- 그래프 Graphs   
- 트리 Trees   
- 조합이론 Combinatorial Theory   
- 재귀식 Recursion   
- 계수 Counting   
- 이산확률 Discrete Probability   
- 고급계산기법 Advanced Counting Techniques   
- 정수론 Number Theory   
- 암호화 Cryptography   
- 오토마타 및 형식언어 Automata and Formal Language   
- 모델링 계산 Modeling Computation   
   
#### 학습방법   
- 약속을 잘 지키자   
  - 정의, 정리   
  - 기호논리학   
  - 암기   
- 연습하자   
  - 지식 체계를 만드는 훈련   
  - 논리적 사고 및 표현 방법의 훈련   
- 예습과 복습을 하자   
   
<br />
### 이산수학의 도구, 기법, 방법론   
방법론 : 누가, 언제 어디서, 왜, 어떠한 도구와 기법을 사용해야 하는가에 관한 내용   
   
#### 수학의 도구, 기법, 방법론   
   
|도구|기법|방법론|
|:---:|:---:|:---:|
|- 정의, 정리|- 가우스 소거법(일차연립 방정식)<br />- 근의 공식(2차, 3차 방정식)<br />등|상황에 따라 가장 효과적이고 효율적인 도구와 기법을 선택하는 것|
   
#### 문제해결   
   
|수학적 모델링을 이용한 문제해결|정보 모델링을 이용한 문제해결|
|:---:|:---:|
|문제<br />↓<br />추상모델<br />↓<br />변형된 모델<br />↓<br />문제의 해결책|문제<br />↓<br />정보<br />↓<br />처리<br />↓<br />문제의 해결책|
   
#### 추상화 abstraction   
|국어사전의 추상화|컴퓨터과학에서의 추상화|
|:---|:---|
|일정한 인식 목표를 추구하기 위해 여러가지 표상이나 개념에서 특정한 특성이나 속성을 빼냄|문제와 관련된 핵심내용만 남기고 관련없는 내용을 제거하여 문제를 단순화 시키는 과정|
   
<br />
### 알고리즘 Algorithm 언어   
- 어떠한 문제를 해결하기 위한 여러 동작들의 유한한 모임   
- <cite>a set of instructions, sometimes called a procedure or a function, that is used to perform a certain task</cite> [Wikipedia]   
- <cite>an explicit step-by-step procedure for solving the problem</cite> [Dossey, et al.]   
   
#### 알고리즘 표현 방법   
- 컴퓨터 프로그래밍 언어 Computer Programming Language   
- 순서도 Flow Chart   
- 의사코드 Pseudo Code (기본 제어구조)   
   
#### Computer Programming Language   
- 컴퓨터 작동을 위한 동작을 세밀하게 지시   
- 알고리즘의 핵심요소가 잘 드러나지 않음   
- 중요하지 않은 부차적인 표현에 신경써야 함   
- 통일된 언어가 존재하지 않음   
   
#### Flow Chart   
- 장점 : 알고리즘의 작동방식을 도식화함   
- 단점 : 내용이 복잡하거나 프로그램의 크기가 클 경우에 표현하기 어려움   
   
#### Pseudo Code   
- 모호한 부분은 프로그래밍 언어의 문법을 채용하여 명확하게 기술   
- 구체적으로 표현할 필요가 없는 부분은 자연어를 통해 설명식으로 기술   
- 알고리즘의 작동방식을 설명하는 용도로만 사용   
- C언어를 기반으로 하는 의사코드 사용   
   
|할당문|제어문|
|:---|:---|
|ex) K = 100|- 순차문 Sequence<br />- 조건문 Selection<br />- 반복문 Iteration|
   
#### 3가지 제어구조 control structure   
|Sequence Structure|Selection Structure|Iteration Structure|
|:---:|:---:|:---:|
|할당문|- if문<br />- switch문|- for문<br />- while문<br />- foreach문|
|↓<br />A<br />↓<br />B<br />↓<br />C<br />↓|↓<br />A<br />↓<br />◇<br />Y↓ N↓<br />B C|↓<br />A ←<br />↓<br />B<br />↓<br />◇<br />Y↓ N↑<br />C<br />↓|
   
#### 순차구조를 사용한 의사코드 예시   
```
x ← 0;
x ← x + 1;
x ← x + 2;
```
   
#### 선택구조 if문을 사용한 의사코드 예시   
```
if (x > 0) print "pos";
else if (x < 0) print "neg";
else print "zero";
```
   
#### 선택구조 if문을 사용한 의사코드 예시   
```
switch (x)
{
  case 0;
    print '0';
    break;
  case 1;
    print '1';
    break;
  default;
    print "I don't know the number";
    break;
}
```
   
#### 반복구조 for문을 사용한 의사코드 예시   
```
for x ← 5 to 0
{
  print x;
} 
print "fire";
```
   
#### 반복구조 while문을 사용한 의사코드 예시   
```
x ← 5;
while x >= 0 do
{
  print x;
  x ← x - 1;
}
print "fire";
```
   
#### 반복구조 foreach문을 사용한 의사코드 예시   
```
foreach x in {5, 4, 3, 2, 1, 0}
{
  print x;
}
print "fire";
```
   
### 이산수학의 응용분야   
|이산수학 주제|컴퓨터 응용 분야|
|:---|:---|
|Logic|전문가 시스템|
|Proofs|컴퓨터 프로그램의 효과성 및 효율성 입증|
|Sets|계산 이론, 데이터베이스 등|
|Matrices|2차원 그래픽, 3차원 그래픽, 기계학습|
|Relations|관계형 데이터베이스|
|Functions|컴퓨터 언어|
|Boolean Algebra|계산 이름, 디지털 논리회로|
|Graphs|자연어 처리, 컴퓨터 네트워크|
|Trees|자료 탐색, 컴퓨터 네트워크, 데이터베이스, 회로망 설계|
|Combinatorial Theory|계산 이론|
|Number Theory|정보 보안|
|Automata and Formal Language|계산 이론, 문제 해결 가능성|
   
<br />
<cite>출처: 한국방송통신대학교 컴퓨터과학과</cite>
