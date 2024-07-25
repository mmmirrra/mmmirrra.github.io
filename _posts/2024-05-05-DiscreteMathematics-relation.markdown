---
layout: post
title:  "Discrete Mathematics: Relation"
date:   2024-05-05 09:00:00 +0900
categories: [Discrete Mathematics]
---

<style>
    .characterOverline {
        text-decoration : overline;
    }
</style>

### Basic Information   
// 기본사항   
   
#### Cartesian Product   
// 곱집합   
   
// 집합 A와 B의 곱집합 (Cartesian Product) A x B 는 A의 원소와 B의 원소의 모든 순서쌍 (ordered pair) 들의 집합   
// - 즉, A x B = {(a, b) \| a ∈ A, b ∈ B}   
- A Cartesian Product A x B is a set of ordered pairs of elements of A and B   
  -  That is, A x B = {(a, b) \| a ∈ A, b ∈ B}   
   
#### Relation   
// 관계   
   
// 집합 X에서 집합 Y로의 (이항)관계 ((binary) relation) R은 X x Y 의 부분집합임   
// - R ⊂ X x Y   
// (x, y) ∈ R   
// - ⇒ x는 y와 R의 관계가 있다   
// - ⇒ xRy로 표기   
// (x, y) ∉ R   
// - ⇒ x는 y와 R의 관계가 없다   
// - ⇒ x<span class="characterOverline">R</span>y로 표기   
// X = Y 이면 R을 X에서의 관계라고 함   
- The (binary) relation ((binary) relation) R from set X to set Y is a subset of X x Y   
  - R ⊂ X x Y   
- (x, y) ∈ R   
  - ⇒ x and y have a relation of R   
  - ⇒ Marked as xRy   
- (x, y) ∉ R   
  - ⇒ X and y have no relation of R   
  - ⇒ Marked as x<span class="characterOverline">R</span>y   
- If X = Y, R is called the relation on X   
   
#### Example 1 of relation   
// 관계 예시 1   
   
// 학생집합 X = {Min Su, Young Su, Yun, Sodam}   
// 과목집합 Y = {C language, Algorithm, Graphics, Networks}   
// X에서 Y로의 관계 \|X x Y\| = 16   
- Student set X = {Min Su, Young Su, Yun, Sodam}   
- Subject set Y = {C language, Algorithm, Graphics, Networks}   
- Relation from X to Y \|X x Y\| = 16   
   
||C language|Algorithm|Graphics|Networks|
|:---:|:---:|:---:|:---:|:---:|
|Min Su|O|O|O||
|Young Su||O||O|
|Yun||O|O||
|Sodam|O||O|O|
   
```
∴ Course relation R = { (Min Su, C language)
                       , (Min Su, Algorithm)
                       , (Min Su, Graphics)
                       , (Young Su, Algorithm)
                       , (Young Su, Networks)
                       , (Yun, Algorithm)
                       , (Yun, Graphics)
                       , (Sodam, C language)
                       , (Sodam, Graphics)
                       , (Sodam, Networks) }
```
   
#### Example 2 of a relation   
// 관계 예시 2   
   
// 관계 R = {(a, b) \| b = \|a\|, a와 b는 실수} 일 때   
// - ① (-1, 1) ∈ R?   
// -- ⇒ 맞음 : -1의 절대값은 1이므로 맞음   
// - ② (1, -1) ∈ R?   
// -- ⇒ 틀림 : 1의 절대값은 1인데 b가 -1이므로 틀림 ⇒ (1, -1) ∉ R   
// - ③ R의 그래프를 그리시오    
- When relation R = {(a, b) \| b = \|a\|, a and b are real numbers}   
  - ① (-1, 1) ∈ R?   
    - ⇒ Correct : Absolute value of -1 is 1 so correct   
  - ② (1, -1) ∈ R?   
    - ⇒ Wrong : Absolute value of 1 is 1 but b is -1 so wrong ⇒ (1, -1) ∉ R   
  - ③ Draw a graph of R   
    - ⇒   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelation1.png)
   
<br />
### An expression of a relation   
// 관계의 표현   
   
// 화살표 도표   
// 방향 그래프   
// 부울행렬   
- Arrow Chart   
- Directed graph   
- Boolean matrix   
   
#### Arrow Chart   
// 화살표 도표   
   
// X에서 Y로의 관계 R   
- Relation R from X to Y   
  - x ∈ X, y ∈ Y, (x, y) ∈ R   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationArrowDiagram1.png)
   
#### Example of Arrow Chart   
// 화살표 도표 예시   
   
- A = {1, 2, 3, 4}, B = {-1, 0, 1, 2}   
   
// ① (x, y) ∈ A x B 에 대해, (x, y) ∈ R 이기 위한 필요충분조건은 y ＞ x 임   
- ① For (x, y) ∈ A x B, the necessity and sufficient conditions for (x, y) ∈ R are y ＞ x   
  - {(x, y) \| y ＞ x}   
  - ⇒ ∴ R = {(1, 2)}   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationArrowDiagram2.png)
   
- ② S = {(x, y) ∈ A X B \| x = y}   
  - ⇒ ∴ S = {(1, 1), (2, 2)}   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationArrowDiagram3.png)
   
- ③ T = {(3, 0), (2, 0), (1, 0)}   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationArrowDiagram4.png)
   
#### Directed graph   
// 방향 그래프   
   
// 그래프 : 점[꼭지점] (vertex) 과 선[변] (edge) 으로 이루어진 도형   
- Graph : A figure consisting of points [vertex] and sides [edge]   
  - G = (V, E)   
   
// 3개의 꼭지점과 2개의 변을 가지는 그래프   
- A graph with three vertices and two edges   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationDirectionalGraph1.png)
   
// 방향 그래프   
// - G = (V, E)에서   
- Directed graph   
  - In G = (V, E)   
   
// -- 변이 방향을 가지면 G는 방향 그래프   
    - If the edge has a direction, G is a directed graph   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationDirectionalGraph2.png)
   
// -- 변이 방향을 가지지 않으면 G는 무향그래프   
    - If the edge dose no have a direction, G is a undirected graph   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationDirectionalGraph3.png)
   
- x, y ∈ X, (x, y) ∈ R   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationDirectionalGraph4.png)
   
#### Example of Directed graph   
// 방향 그래프 예시   
   
// 관계 T를 방향 그래프로 나타내시오   
- Display the relation T as a directed graph   
  - A = {1, 2, 3}   
  - T = {(1, 1), (1, 2), (2, 1), (2, 2), (3, 1), (3, 2)}   
⇒   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationDirectionalGraph5.png)
   
#### Boolean matrix   
// 부울행렬   
   
- X = {x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>m</sub>}, Y = {y<sub>1</sub>, y<sub>2</sub>, ..., y<sub>n</sub>}, (x<sub>i</sub>, y<sub>j</sub>) ∈ R   
- ⇔ m x n boolean matrix M<sub>R</sub> = (a<sub>ij</sub>)   
- a<sub>ij</sub> = {   
    0 ((x<sub>i</sub>, y<sub>i</sub>) ∉ R)   
    1 ((x<sub>i</sub>, y<sub>j</sub>) ∈ R)   
    }   
   
```
aij = { 0 ((xi, yi) ∉ R)
        1 ((xi, yj) ∈ R) }
```
   
#### Example of Boolean matrix   
// 부울행렬 예시   
   
// 관계 T (M<sub>T</sub>) 를 부울행렬로 나타내시오   
- Display the relation T (M<sub>T</sub>) as a boolean matrix   
  - A = {1, 2, 3}   
  - T = {(1, 1), (1, 2), (2, 1), (2, 2), (3, 1), (3, 2)}   
⇒   
   
```
          1 2 3
     1 ┌ 1 1 0 ┐
MT = 2 │ 1 1 0 │
     3 └ 1 1 0 ┘
```
   
\|A x A\| = 9   
\|T\| = 6   
   
<br />
### The property of a relation   
// 관계의 성질   
   
// 집합 A에서의 관계 R (R ⊂ A x A) 이   
// - ① 반사적 (reflexive)   
// -- ∀a ∈ A, (a, a) ∈ R   
// - ② 대칭적 (symmetric)   
// -- ∀a, b ∈ A, (a, b) ∈ R ⇒ (b, a) ∈ R   
// - ③ 추이적 (transitive)   
// -- ∀a, b, c ∈ A, ((a, b) ∈ R ∧ (b, c) ∈ R) ⇒ (a, c) ∈ R   
- Relation R (R ⊂ A x A) in set A is   
  - ① Reflexive   
    - ∀a ∈ A, (a, a) ∈ R   
  - ② Symmetric   
    - ∀a, b ∈ A, (a, b) ∈ R ⇒ (b, a) ∈ R   
  - ③ Transitive   
    - ∀a, b, c ∈ A, ((a, b) ∈ R ∧ (b, c) ∈ R) ⇒ (a, c) ∈ R   
   
#### Type of property   
// 성질의 종류   
   
// 예시   
// - 다음 관계 R, S, T의 성질을 확인하시오   
- Example   
  - Check the properties of the following relations : R, S, and T   
   
(1) R   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationNatureOfRelation1.png)
   
R = {(1, 1), (1, 2), (2, 2), (2, 3), (3, 1), (3, 3)}   
// ⇒ ∴ 반사적임. 대칭적 아님. 추이적 아님   
⇒ ∴ It's reflexive. It's not symmetric. It's not transitive   
   
(2) S   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationNatureOfRelation2.png)
   
S = {(1, 1), (1, 2), (1, 3), (2, 1), (2, 2), (3, 1), (3, 3)}   
// ⇒ ∴ 반사적임. 대칭적임. 추이적 아님   
⇒ ∴ It's reflexive. It's symmetric. It's not transitive   
   
(3) T   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationNatureOfRelation3.png)
   
T = {(1, 1), (1, 2), (2, 1), (2, 2), (3, 1), (3, 2)}   
// ⇒ ∴ 반사적 아님. 대칭적 아님. 추이적임   
⇒ ∴ It's not reflexive. It's not symmetric. It's transitive   
   
#### Relation property and Boolean matrix   
// 관계의 성질과 부울행렬   
   
// - ① 반사적 (reflexive)   
// -- ∀a ∈ A, (a, a) ∈ R   
- ① Reflexive   
  - ∀a ∈ A, (a, a) ∈ R   
⇒   
   
```
           a b … n
      a ┌ 1        ┐
MR =  b │   1      │
     … │     …   │
      m └        1 ┘
```
   
// - ② 대칭적 (symmetric)   
// -- ∀a, b ∈ A, (a, b) ∈ R ⇒ (b, a) ∈ R   
- ② Symmetric   
  - ∀a, b ∈ A, (a, b) ∈ R ⇒ (b, a) ∈ R   
⇒   
   
```
           a   …   b  …   n
      a ┌ …  …  ★  …  … ┐
     … │ …  …  …  …  … │
MR =  b │ ★  …  …  …  … │
     … │ …  …  …  …  … │
      m └ …  …  …  …  … ┘
```
   
// ⇔ M<sub>R</sub> 이 대칭행렬 (즉, M<sub>R</sub> = M<sup>T</sup><sub>R</sub>)   
⇔ M<sub>R</sub> is symmetric matrix (That is, M<sub>R</sub> = M<sup>T</sup><sub>R</sub>)   
   
// - ③ 추이적 (transitive)   
// -- ∀a, b, c ∈ A, ((a, b) ∈ R ∧ (b, c) ∈ R) ⇒ (a, c) ∈ R   
- ③ Transitive   
  - ∀a, b, c ∈ A, ((a, b) ∈ R ∧ (b, c) ∈ R) ⇒ (a, c) ∈ R   
⇒   
   
```
           a   b   c   …   n
      a ┌ …  1   1   …  … ┐
MR =  b │ …  …  1   …  … │
     … │ …  …  …  …  … │
      m └ …  …  …  …  … ┘
```
   
⇒ M<sub>R<sub>2</sub></sub> = M<sub>R<sub>1</sub></sub> ⊙ M<sub>R<sub>1</sub></sub>   
// 추이적 아님   
- It's not transitive   
   
```
           a b c
      a ┌ 0 1 0 ┐    ┌ 0 1 0 ┐   ┌ 0 0 1 ┐
MR2 = b │ 0 0 1 │ ⊙ │ 0 0 1 │ = │ 0 0 0 │
      c └ 0 0 0 ┘    └ 0 0 0 ┘   └ 0 0 0 ┘
```
   
// 추이적임   
- It's transitive   
   
```
           a b c
      a ┌ 0 1 1 ┐    ┌ 0 1 1 ┐   ┌ 0 0 1 ┐
MR2 = b │ 0 0 1 │ ⊙ │ 0 0 1 │ = │ 0 0 0 │
      c └ 0 0 0 ┘    └ 0 0 0 ┘   └ 0 0 0 ┘
```
   
// 집합 A에서의 관계 R이 주어졌을 때, A의 원소가 관계 R을 통해 도착할 수 있는 원소를 살펴보자. A의 임의의 원소에서 한 번만에 도착할 수 있는 순서쌍의 집합을 R<sub>1</sub>이라고 하고, 두 번만에 도착할 수 있는 순서쌍의 집합을 R<sub>2</sub>라고 하며, k번만에 도착할 수 있는 순서쌍의 집합을 관계 R<sub>k</sub>라고 하자. 주어진 관계 R이 추이적이 되기 위해서는 다음을 만족해야 한다   
// - R<sub>1</sub>, R<sub>2</sub>, ..., R<sub>k</sub>, ... ⊆ R   
// 예를 들어, 집합 A가 A = {1, 2, 3} 이고 A에 대한 관계 R이 R = {(1, 2), (2, 3)} 이라 하자. 관계 R<sub>1</sub>은 R<sub>1</sub> = {(1, 2), (2, 3)} 이고, 관계 R<sub>2</sub>는 R<sub>2</sub> = {(1, 3)} 이다. 세 번만에 도착할 수 있는 원소는 없으므로 R<sub>3</sub>는 R<sub>3</sub> = ∅ 이다   
// 따라서 주어진 관계 R이 추이적이 되기 위해서는 R<sub>1</sub>, R<sub>2</sub> ⊆ R 이 되어야 하지만 R<sub>2</sub>는 R에 포함되지 않았으므로 R은 추이적이 아니다   
- Given the relation R in the set A, let's look at the elements that A can arrive through the relation R. In any element of A, let R<sub>1</sub> denote the set of ordered pair that can arrive in 1 time, R<sub>2</sub> denote the set of ordered pair that can arrive in 2 times, and Relation R<sub>k</sub> denote the set of ordered pair that can arrive in k times. In order for a given relation R to be transitive, the following must be satisfied   
  - R<sub>1</sub>, R<sub>2</sub>, ..., R<sub>k</sub>, ... ⊆ R   
- For example, let the set A be A = {1, 2, 3} and the relation R for A be R = {(1, 2), (2, 3)}. Relation R<sub>1</sub> is R<sub>1</sub> = {(1, 2), (2, 3)}, and relation R<sub>2</sub> is R<sub>2</sub> = {(1, 3)}. R<sub>3</sub> is R<sub>3</sub> = ∅ because no element can arrive at it three times   
- Therefore, for a given relation R to be transitive, it must be R<sub>1</sub> and R<sub>2</sub> ⊆ R, but R<sub>2</sub> is not transitive because R<sub>2</sub> is not included in R   
   
#### Examples of relation property and Boolean matrices   
// 관계의 성질과 부울행렬 예시   
   
// A = {1, 2, 3, 4}   
// A에서의 관계 R, S, T의 성질을 설명하시오   
- A = {1, 2, 3, 4}   
- Explain the properties of R, S, and T in relation to A   
   
(1) R = {(1, 1), (2, 2), (3, 3)}   
   
```
     ┌ 1 0 0 0 ┐
MR = │ 0 1 0 0 │
     │ 0 0 1 0 │
     └ 0 0 0 0 ┘
```
   
// ⇒ ∴ 반사적 아님. 대칭적임. 추이적임   
⇒ It's not reflexive. It's symmetric. It's transitive   
   
(2) S = {(1, 1), (1, 2), (1, 3), (1, 4), (2, 3), (2, 4), (3, 4)}   
   
```
     ┌ 1 1 1 1 ┐
MS = │ 0 0 1 1 │
     │ 0 0 0 1 │
     └ 0 0 0 0 ┘
```
   
// ⇒ ∴ 반사적 아님. 대칭적 아님. 추이적임   
⇒ It's not reflexive. It's not symmetric. It's transitive   
   
(3) T = {(1, 4), (2, 3), (3, 2), (4, 1)}   
   
```
     ┌ 0 0 0 1 ┐
MT = │ 0 0 1 0 │
     │ 0 1 0 0 │
     └ 1 0 0 0 ┘
```
   
// ⇒ ∴ 반사적 아님. 대칭적임. 추이적 아님   
⇒ It's not reflexive. It's symmetric. It's not transitive   
   
<br />
### Type of relation   
// 관계의 종류   
   
// 역관계   
// 합성관계   
// 동치관계   
// 동치류   
- Inverse relation   
- Composition relation   
- Equivalence relation   
- Equivalence class   
   
#### Inverse relation   
// 역관계   
   
// X, Y : 집합   
// R : X에서 Y로의 관계   
// R<sup>-1</sup> : R의 역관계 (inverse relation)   
// R<sup>-1</sup> = {(y, x) \| (x, y) ∈ R} ⊂ Y x X   
- X, Y : Set   
- R : Relation from X to Y   
- R<sup>-1</sup> : Inverse relation of R   
- R<sup>-1</sup> = {(y, x) \| (x, y) ∈ R} ⊂ Y x X   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationInverseRelation1.png)
   
#### Example of inverse relation   
// 역관계 예시   
   
// R과 S의 역관계 구하기   
- Find the inverse relation between R and S   
   
- A = {1, 2, 3, 4}, B = {0, 1, 2, 3}   
   
- R = {(x, y) \| y = x - 1, x ∈ A, y ∈ B}   
  - ⇒ R = {(1, 0), (2, 1), (3, 2), (4, 3)}   
  - ⇒ ∴ R<sup>-1</sup> = {(0, 1), (1, 2), (2, 3), (3, 4)}   
   
- S = {(1, 2), (2, 3), (3, 0), (4, 1)}   
  - ⇒ ∴ S<sup>-1</sup> = {(2, 1), (3, 2), (0, 3), (1, 4)}   
   
#### Composition relation   
// 합성관계   
   
// A, B, C : 집합   
// R : A에서 B로의 관계   
// S : B에서 C로의 관계   
// R과 S의 합성관계 (composition relation)   
// S ◦ R = {(a, c) \| a ∈ A, b ∈ B, c ∈ C, (a, b) ∈ R, (b, c) ∈ S}   
// S ◦ R ⊂ A x C (A에서 C로의 관계)   
- A, B, C : Set   
- R : Relation from A to B   
- S : Relation from B to C   
- Composition relation of R and S   
- S ◦ R = {(a, c) \| a ∈ A, b ∈ B, c ∈ C, (a, b) ∈ R, (b, c) ∈ S}   
- S ◦ R ⊂ A x C (Relation from A to C)   
   
#### Example 1 of composition relation   
// 합성관계 예시 1   
   
// S ◦ R 구하기   
- Fine S ◦ R   
   
- A = (a, b, c), B = {1, 2, 3}, C = (x, y, z)   
- R = {(a, 1), (b, 3), (c, 1)}   
- S = {(1, x), (2, y), (3, z)}   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/discreteMathematicsRelationCompositionRelation1.png)
   
- ∴ S ◦ R = {(a, x), (b, z), (c, x)}   
   
#### Example 2 of composition relation   
// 합성관계 예시 2   
   
// S ◦ R 구하기   
- Fine S ◦ R   
   
- R = Set of Real Numbers   
- R = {(a, b) \| b = a + 1} ⊂ R<sup>2</sup>   
- R = {(b, c) \| c = b - 5} ⊂ R<sup>2</sup>   
- ∴ S ◦ R = {(a, c) \| c = a - 4} ⊂ R<sup>2</sup>   
   
#### Boolean matrix representation of composition relation   
// 합성관계의 부울행렬 표현   
   
// A, B, C : 유한 집합 (\|A\| = m, \|B\| = n, \|C\| = p)   
// R : A에서 B로의 관계   
// S : B에서 C로의 관계   
// S ◦ R : A에서 C로의 관계   
// - ⇒ M<sub>R</sub> 은 m x n 부울행렬   
// - ⇒ M<sub>S</sub> 은 n x p 부울행렬   
// - ⇒ M<sub>S ◦ R</sub> 은 m x p 부울행렬   
// - ⇒ M<sub>S ◦ R</sub> 은 M<sub>R</sub> ⊙ M<sub>S</sub>   
- A, B, C : Finite set (\|A\| = m, \|B\| = n, \|C\| = p)   
- R : Relation from A to B   
- S : Relation from B to C   
- S ◦ R : Relation from A to C   
  - ⇒ M<sub>R</sub> is an m x n Boolean matrix   
  - ⇒ M<sub>S</sub> is an n x p Boolean matrix   
  - ⇒ M<sub>S ◦ R</sub> is an m x p Boolean matrix   
  - ⇒ M<sub>S ◦ R</sub> is M<sub>R</sub> ⊙ M<sub>S</sub>   
   
#### Example of Boolean matrix representation of composition relation   
// 합성관계의 부울행렬 표현 예시   
   
// S ◦ R 구하기   
- Find S ◦ R   
   
- A = {a, b, c}, B = {1, 2, 3}, C = (x, y, z)   
- R = {(a, 1), (b, 3), (c, 1)}   
- S = {(1, x), (2, y), (3, z)}   
- S ◦ R = {(a, x), (b, z), (c, x)}   
   
```
          1 2 3
     a ┌ 1 0 0 ┐
MR = b │ 0 0 1 │
     c └ 1 0 0 ┘
```
   
```
          x y z
     1 ┌ 1 0 0 ┐
MS = 2 │ 0 1 0 │
     3 └ 0 0 1 ┘
```
   
```
                         x y z
                    a ┌ 1 0 0 ┐
MS ◦ R = MR ⊙ MS = b │ 0 0 1 │
                    c └ 1 0 0 ┘
```
   
#### Equivalence relation   
// 동치관계   
   
// R : 집합 A에서 관계   
// R이 반사적, 대칭적, 추이적이면 R을 동치관계라고 부른다   
- R : Relation in set A   
- If R is reflexive, symmetric, and transitive, then R is called an Equivalence relation   
   
// 예시 1   
// - 실수에서의 상등 관계 R (=)   
// -- ① aRa (a = a)   
// -- ② aRb ⇒ bRa (a = b ⇒ b = a)   
// -- ③ (aRb ∧ bRc) ⇒ aRc   
// --- ((a = b ∧ b = c) ⇒ a = c)   
- Example 1   
  - Equal relation R (=) in real number   
    - ① aRa (a = a)   
    - ② aRb ⇒ bRa (a = b ⇒ b = a)   
    - ③ (aRb ∧ bRc) ⇒ aRc   
      - ((a = b ∧ b = c) ⇒ a = c)   
   
// 예시 2   
// - A = {0, 1, 2, 3}   
// - R : A에서의 관계로 부등호 관계 (≤)   
// - R (≤) 이 동치관계인가?   
// - ⇒ a ≤ a : 반사적임   
// - ⇒ a ≤ b ⇏ b ≤ a : 대칭적이 아님 (∵ 0 ≤ 1 ⇏ 1 ≤ 0)   
// - ⇒ a ≤ b and b ≤ c ⇒ a ≤ c : 추이적임 (∵ 0 ≤ 1 and 1 ≤ 3 ⇒ 0 ≤ 3)   
// - ∴ 동치관계 아님   
- Example 2   
  - A = {0, 1, 2, 3}   
  -  R : Relation at A, inequal relation (≤)   
  - Is R (≤) equivalence relation?   
  - ⇒ a ≤ a : It's reflexive   
  - ⇒ a ≤ b ⇏ b ≤ a : It's not symmetric (∵ 0 ≤ 1 ⇏ 1 ≤ 0)   
  - ⇒ a ≤ b and b ≤ c ⇒ a ≤ c : It's transitive (∵ 0 ≤ 1 and 1 ≤ 3 ⇒ 0 ≤ 3)   
  - ∴ It's not equivalence relation   
   
// 나머지 함수는 하나의 식을 다른 값으로 나눈 뒤 나머지를 구하는 함수이다. 예를 들어 '8 mod 5 = 3' 이고 '13 mod 5 = 3' 이다. 두 정수 m, n에 대해 양의 정수 d로 나머지 연산을 하였을 때 같은 값이 나오는 경우가 있는데 이때의 m과 n은 d에 관한 모듈로 합동이라 하고 'm ≡ n (mod d)' 로 표기한다. 예를 들어 8과 13은 5에 관한 모듈로-5 합동이라는 사실을 '8 ≡ 13 (mod 5)' 와 같이 표기한다   
// 'm ≡ n (mod 3)' 을 만족하는 (m, n) 의 순서쌍들의 집합을 관계 R 이라 했을 때 다음을 만족한다   
// - ① 임의의 a에 대해서 a ≡ a (mod 3) 이다   
// - ② a ≡ b (mod 3) 이면, b ≡ a (mod 3) 이다   
// - ③ a ≡ b (mod 3) 이고, b ≡ c (mod 3) 이면, a ≡ c (mod 3) 이다   
// 위의 사실로부터 3에 관한 모듈로 합동은 반사적, 대칭적, 추이적 성질을 만족하므로 동치관계이다. 그리고 3 대신에 임의의 자연수를 대입하더라도 항상 반사적, 대칭적, 추이적임을 보일 수 있기 때문에 모듈로 합동 관계는 항상 동치관계임을 알 수 있다   
- The remaining function is a function that divides one expression by another value and then obtains the rest. For example, '8 mod 5 = 3' and '13 mod 5 = 3'. The same value may come out when the remaining operation is performed with a positive integer d for two integers m and n, and m and n are modules about d and are called congruent and expressed as 'm ≡ n (mod d)'. For example, the fact that 8 and 13 are modulo-5 congruence with respect to 5 is expressed as '8 ≡ 13 (mod 5)'   
- If the set of ordered pairs of (m, n) that satisfy 'm ≡ n(mod 3)' is called relation R, then the following is satisfied   
  - ① a ≡ a (mod 3) for any a   
  - ② If a ≡ b (mod 3), then b ≡ a (mod 3)   
  - ③ If a ≡ b (mod 3), and b ≡ c (mod 3), then a ≡ c (mod 3)   
- From the above facts, the modular congruence of 3 is equivalence relation because it satisfies reflexive, symmetric, and transitive properties. And even if an arbitrary natural number is substituted instead of 3, it can always be shown to be reflexive, symmetric, and transitive, so it can be seen that the modular joint relation is always equivalence relation   
   
#### Equivalence class   
// 동치류   
   
// A : 집합   
// R : A에서의 동치관계   
// A의 임의의 원소 a에 대해서   
// [a] = {x ∈ A \| (a, x) ∈ R} 를 a의 동치류라고 부른다   
- A : Set   
- R : Equivalence relation in A   
- For any element a in A   
- [a] = {x ∈ A \| (a, x) ∈ R} is called an Equivalence class of a   
   
// 예시   
// - 집합 A = {0, 1, 2} 에서의 관계 R = {(0, 0), (1, 1), (1, 2), (2, 1), (2, 2)} 에 관해 서로 다른 동치류를 모두 찾으시오   
- Example   
  - Find all the different Equivalence classes for relation R = {(0, 0), (1, 1), (1, 2), (2, 1), (2, 2)} in set A = {0, 1, 2}   
   
```
     ┌ 1 0 0 ┐
MR = │ 0 1 1 │
     └ 0 1 1 ┘
```
   
// ⇒ R은 반사적임. 대칭적임. 추이적임   
// ⇒ 동치관계임   
⇒ R is reflexive. R is symmetric. R is transitive   
⇒ It's equivalence relation   
   
// ⇒ 동치류   
⇒ Equivalence class   
- [0] = {x ∈ A \| (0, x) ∈ R} = {0}   
- [1] = {x ∈ A \| (1, x) ∈ R} = {1, 2}   
- [2] = {x ∈ A \| (2, x) ∈ R} = {1, 2}   
∴ {0}, {1, 2}   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
