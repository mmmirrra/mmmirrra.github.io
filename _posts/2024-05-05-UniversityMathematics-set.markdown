---
layout: post
title:  "University Mathematics: Set"
date:   2024-05-05 09:00:00 +0900
categories: [University Mathematics]
---

### Set   
// 집합   
   
// 각각이 서로 명확하게 구별되어 있는 원소 (element) 들을 명확히 정의하여 전체로 묶은 것   
// - 집합의 개념은 독일 수학자 칸토어 (Cantor, G.) 가 1885년에 정립   
- Elements that are clearly distinguished from each other are clearly defined and grouped together   
  - The concept of set was established in 1885 by German mathematician Cantor (Cantor, G.)   
   
// a가 집합 A의 원소라는 것을 기호로는 a ∈ A 로 나타냄   
- The symbol a ∈ A indicates that a is an element of set A   

// 집합을 나타내는 방법으로는 원소나열법과 조건제시법이 있음   
// - 원소 나열법   
// -- 집합의 원소에 속하는 모든 원소를 나열하여 표시하는 방법   
// -- 예시 : A = {1, 2, 3, 4, ...}   
// - 조건 제시법   
// -- 원소가 만족하는 조건이나 관계식으로 표현   
// -- 예시 : A = {x\|x는 자연수}   
- Methods of representing a set include tabular form and set-builder notation   
  - tabular form   
    - List all elements that belong to the elements of the set   
    - Example : A = {1, 2, 3, 4, ...}   
  - set-builder notation   
    - Expressing in terms of conditions or relational expressions that satisfy an element   
    - Example : A = {x\|x is a natural number}   
   
#### Subset   
// 부분집합   
   
// 집합 B는 집합 A의 부분집합 (subset)   
// - 집합 B에 속한 모든 원소들이 집합 A에 속할 때 (B ⊂ A)   
// - x ∈ B 이면 x ∈ A 이다 ⇔ B ⊂ A   
- Set B is a subset of set A   
  - If all the elements in set B belong to set A, then (B ⊂ A)   
  - If x ∈ B then x ∈ A ⇔ B ⊂ A   
   
// 집합 A, B가 주어졌을 때, 'x ∈ B 이면 x ∈ A 이다'가 성립하면서 A ≠ B 일 경우, 집합 B는 집합 A의 진부분집합   
// - 예시 : 다음 두 집합 사이의 포함관계를 가장 잘 표현한 것은?   
// -- ① A = {n\|n은 자연수}, B = {n\|n은 짝수}   
// -- ② A = {x\|x > 1}, B = {x\|x² > 1}   
- Given sets A and B, if 'If x ∈ B is x ∈ A' is established and 'A ≠ B' then set B is the true subset of set A   
  - Example : Which best expresses the inclusion relationship between the following two sets?   
    - ① A = {n\|n is a natural number}, B = {n\|n is a even number}   
    - ② A = {x\|x > 1}, B = {x\|x² > 1}   
   
// 두 집합이 모두 같은 원소로 구성되어 있을 때, '두 집합은 같다'고 하고 다음과 같이 표현함   
// - A = B   
- When both sets are made up of the same elements, 'the two sets are the same' and are expressed as follows   
  - A = B   
   
//  집합에서는 가장 커다란 집합 U를 전체집합 (universal set) 또는 모 (母) 집합이라고 함   
// - 이와는 반대적인 개념으로 한 개의 원소도 포함하지 않은 집합을 생각하여, 그것을 공집합 (empty set) 이라 하고 기호로 ∅로 표현   
// - 공집합은 모든 집합의 부분집합   
- In a set, the largest set U is called a universal set or parent set   
  - Considering a set that does not contain a single element in the opposite concept, it is called an empty set and expressed in ∅ as a symbol   
  - An empty set is a subset of all sets   
   
#### Venn diagram   
// 벤다이어그램   
   
// 집합들 사이의 관계를 그림으로 나타내어 눈으로 보기 쉽게 표현   
// - 전체 집합 U를 하나의 직사각형 내부로 나타내고, 그 부분집합 A는 원이나 타원 등의 내부로 표시   
- Illustrate the relationship between sets to make them easier to see   
  - The entire set U is represented inside a rectangle, and its subset A is represented inside, such as a circle or ellipse   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/universityMathematicsVennDiagram.png)
   
<br />
### The operation of a Set   
// 집합의 연산   
   
#### Union set   
// 합집합   
   
// 합집합 A ∪ B   
// - 집합 A, B가 주어졌을 때, A ∪ B = {x\|x ∈ A 또는 x ∈ B}   
- Union set A ∪ B   
  - Given sets A and B, A ∪ B = {x\|x ∈ A or x ∈ B}   
   
// 합집합의 기본 성질   
// 1. A ∪ A = A   
// 2. A ∪ U = U   
// 3. A ∪ ∅ = A   
// 4. A ⊂ A ∪ B, B ⊂ A ∪ B   
// 5. A ⊂ C 이고 B ⊂ C 이면 A ∪ B ⊂ C   
// 6. A ⊃ B 이면 A ∪ B = A   
// 7. A ∪ B = B ∪ A (교환법칙)   
// 8. (A ∪ B) ∪ C = A ∪ (B ∪ C) = A ∪ B ∪ C (결합법칙)   
- Basic properties of union set   
    1. A ∪ A = A   
    2. A ∪ U = U   
    3. A ∪ ∅ = A   
    4. A ⊂ A ∪ B, B ⊂ A ∪ B   
    5. If A ⊂ C and B ⊂ C then A ∪ B ⊂ C   
    6. If A ⊃ B then A ∪ B = A   
    7. A ∪ B = B ∪ A (commutative property)   
    8. (A ∪ B) ∪ C = A ∪ (B ∪ C) = A ∪ B ∪ C (associative property)   
   
// A, B, C의 합집합은 A ∪ B ∪ C 로 쓰고, 다음과 같이 정의   
// - A ∪ B ∪ C = {x\|x ∈ A 또는 x ∈ B 또는 x ∈ C}   
- The combination of A, B, C is written as A ∪ B ∪ C and defined as   
  - A ∪ B ∪ C = {x\|x ∈ A or x ∈ B or x ∈ C}   
   
#### Intersection set   
// 교집합   
   
// 교집합 A ∩ B   
// - 집합 A, B가 주어졌을 때, A ∩ B = {x\|x ∈ A 이고 x ∈ B}   
- Intersection set A ∩ B   
  - Given sets A and B, A ∩ B = {x\|x ∈ A and x ∈ B}   
   
// 교집합의 기본 성질   
// 1. A ∩ A = A   
// 2. A ∩ U = A   
// 3. A ∩ ∅ = ∅   
// 4. A ∩ B ⊂ A, A ∩ B ⊂ B   
// 5. C ⊂ A 이고 C ⊂ B 이면 C ⊂ A ∩ B   
// 6. A ⊂ B 이면 A ∩ B = A   
// 7. A ∩ B = B ∩ A (교환법칙)   
// 8. (A ∩ B) ∩ C = A ∩ (B ∩ C) = A ∩ B ∩ C (결합법칙)   
- Basic properties of intersection set   
    1. A ∩ A = A   
    2. A ∩ U = A   
    3. A ∩ ∅ = ∅   
    4. A ∩ B ⊂ A, A ∩ B ⊂ B   
    5. If C ⊂ A and C ⊂ B then C ⊂ A ∩ B   
    6. If A ⊂ B then A ∩ B = A   
    7. A ∩ B = B ∩ A (commutative property)   
    8. (A ∩ B) ∩ C = A ∩ (B ∩ C) = A ∩ B ∩ C (associative property)   
   
// A, B, C의 교집합은 A ∩ B ∩ C 로 나타내고, 다음과 같이 정의   
// - A ∩ B ∩ C = {x\|x ∈ A 이고 x ∈ B 이고 x ∈ C}   
- The intersection of A, B, C is indicated by A ∩ B ∩ C and is defined as   
  - A ∩ B ∩ C = {x\|x ∈ A and x ∈ B and x ∈ C}   
   
#### Complement   
// 여집합   
   
// 여집합 A<sup>c</sup>   
// 전체집합 U에 속하지만 A에는 속하지 않는 모든 원소의 집합   
// - A<sup>c</sup> = {x ∈ U\|x ∉ A}   
- Complement A<sup>c</sup>   
- The set of all elements that belong to the entire set U but not to A   
  - A<sup>c</sup> = {x ∈ U\|x ∉ A}   
   
// 여집합의 기본 성질   
// 1. A ∪ A<sup>c</sup> = U   
// 2. A ∩ A<sup>c</sup> = ∅   
// 3. A<sup>c</sup> = B<sup>c</sup> 이면 A = B   
// 4. A<sup>c</sup> = ∅ ⇔ A = U   
// 5. A<sup>c</sup> = U ⇔ A = ∅   
// 6. (A<sup>c</sup>)<sup>c</sup> = A   
- Basic properties of complement   
    1. A ∪ A<sup>c</sup> = U   
    2. A ∩ A<sup>c</sup> = ∅   
    3. If A<sup>c</sup> = B<sup>c</sup> then A = B   
    4. A<sup>c</sup> = ∅ ⇔ A = U   
    5. A<sup>c</sup> = U ⇔ A = ∅   
    6. (A<sup>c</sup>)<sup>c</sup> = A   
   
#### Difference set   
// 차집합   
   
// 차집합 A - B   
// 집합 A, B가 주어졌을 때, 집합 A - B = {x\|x ∈ A 이고, x ∉ B}   
// - A - B = A ∩ B<sup>c</sup> = A - (A ∩ B)   
- Difference set A - B   
- Given sets A and B, set A - B = {x\|x ∈ A and x ∉ B}   
  - A - B = A ∩ B<sup>c</sup> = A - (A ∩ B)   
   
<br />
### Fundamental Theorem of Set Operation   
// 집합 연산의 기본정리   
   
#### Distributive property of set operations   
// 집합 연산의 분배법칙   
   
1. A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C)   
2. A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C)   
   
#### De Morgan's laws   
// 드모르간 (De Morgan) 의 법칙   
   
1. (A ∪ B)<sup>c</sup> = A<sup>c</sup> ∩ B<sup>c</sup>   
2. (A ∩ B)<sup>c</sup> = A<sup>c</sup> ∪ B<sup>c</sup>   
   
<br />
### Number of elements and the classical definition of probability   
// 원소의 수와 고전적 확률   
   
#### Number of elements in a finite set   
// 유한집합 원소 개수   
   
// 유한집합 A의 원소의 개수는 일반적으로 기호 n(A) 로 나타냄   
// - n(A ∪ B) = n(A) + n(B) - n(A ∩ B)   
- The number of elements in a finite set A is usually indicated by the symbol n(A)   
  - n(A ∪ B) = n(A) + n(B) - n(A ∩ B)   
   
// 순서쌍 (ordered pair) 과 곱집합 (Cartesian product)   
// - 임의의 실수 a, b를 짝을 지어 표현한 것을 순서쌍이라고 함   
// - 집합 A와 B의 모든 순서쌍 집합 A, B가 주어졌을 때, (a, b)의 집합을 곱집합이라고 하며 다음과 같이 표현   
// -- A x B = {(a, b)\|a ∈ A, b ∈ B}   
- Ordered pair and Cartesian product   
  - An ordered pair is the expression of any real number a, b   
  - Given all ordered pairs of sets A and B, the set of (a, b) is called a cartesian product and is expressed as follows   
    - A x B = {(a, b)\|a ∈ A, b ∈ B}   
   
// A = B 일 경우 A x B = A x A = A²   
// n(A x B) = n(A)n(B)   
- IF A = B then A x B = A x A = A²   
- n(A x B) = n(A)n(B)   
   
#### The meaning of classical probability   
// 고전적 확률의 의미   
   
// 표본공간 (sample space) 과 사건 (event)   
// - 표본공간은 통계적 실험에서 발생가능한 모든 결과 집합이며 사건은 표본공간의 부분집합   
- Sample space and event   
  - The sample space is the set of all possible outcomes in a statistical experiment, and the event is a subset of the sample space   
   
// 사건 A가 발생할 고전적 의미의 확률   
// - P(A) = <sup>사건A에 속하는 원소의 개수</sup> / <sub>표본공간의 전체 원소의 개수</sub>   
- the probability of occurrence of event A in the classical definition   
  - P(A) = <sup>Number of elements belonging to event A</sup> / <sub>Total number of elements in the sample space</sub>   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
