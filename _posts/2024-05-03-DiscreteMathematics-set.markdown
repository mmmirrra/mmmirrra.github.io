---
layout: post
title:  "Discrete Mathematics: Set"
date:   2024-05-03 09:00:00 +0900
categories: [Discrete Mathematics]
---

### Basic Information   
// 기본사항   
   
#### Logic and Set theory   
// 논리학과 집합론   
   
// 논리합 (p(x) ∨ q(x)) = 합집합 (A ∪ B)   
// 논리곱 (p(x) ∧ q(x)) = 교집합 (A ∩ B)   
- Disjucntion (p(x) ∨ q(x)) = Union set (A ∪ B)   
- Conjunction (p(x) ∧ q(x)) = Intersection set (A ∩ B)   
   
#### Sets and Elements   
// 집합과 원소   
   
// 무정의 용어 (정의 없이 사용하는 용어)   
// - 직관적으로 이해할 수 있으나 다른 용어로 정의하기 힘든 대상을 표현하기 위해 사용됨   
// 집합은 무정의 용어임   
- Terms used without definition   
  - Used to represent objects that are intuitively understandable but difficult to define in other terms   
- A set is a term used without definition   
   
// 'Georg Cantor' 의 집합   
// - "우리의 직관이나 사고로부터 한정적이고 분리된 객체들의 전체 M에서의 수집"   
- A set of 'Georg Cantor'   
  - "Collection of objects that are limited and separate from our intuition or thinking in the whole M"   
   
#### How to display a set   
// 집합의 표시법   
   
// S가 하나의 집합이라고 하자   
// - a를 S의 원소이고, b를 S의 원소가 아니라고 할 때   
// -- a ∈ S, b ∉ S   
- Suppose that S is a set   
  - If a is an element of S and b is not an element of S   
    - a ∈ S, b ∉ S   
   
// 집합의 표기 방법   
// - S는 중괄호 ( { , } ) 로 표시함   
// -- 원소나열법   
// ---  예시 : S = {1, 2, 3}   
// -- 조건나열법   
// --- 예시 : S = {x \| 0 ＜ x ＜ 4인 자연수}   
// - 집합의 크기 : \|S\|   
// -- 예시 : \|S\| = 3   
- How to mark a set   
  - S in brackets ( { , } )   
    - Tabular form   
      - Example : S = {1, 2, 3}   
    - Set-builder notation   
      - Example : S = {x \| A natural number of 0 ＜ x ＜ 4}   
  - Set Size : \|S\|   
    - Example : \|S\| = 3   
   
#### Subset   
// 부분집합   
   
// A의 모든 원소가 B의 원소이면 A는 B의 부분집합이라 함   
// A ⊆ B 또는 A ⊂ B 로 표기함   
// 즉, A ⊆ B ⇔ ∀x (x ∈ A → x ∈ B)   
- If all elements of A are elements of B, A is a subset of B   
- Write A ⊆ B or A ⊂ B   
- That is, A ⊆ B ⇔ ∀x (x ∈ A → x ∈ B)   
   
#### Proper subset   
// 진부분집합   
   
// A는 B의 진부분집합   
// - ⇔ A ⊆ B, B ⊈ A   
// - ⇔ A ⊆ B, A ≠ B   
- A is a true subset of B   
  - ⇔ A ⊆ B, B ⊈ A   
  - ⇔ A ⊆ B, A ≠ B   
   
#### Equal   
// 상동, 상등, 동치   
   
- A = B ⇔ A ⊆ B and B ⊆ A   
   
#### Disjoint, Pairwise Disjoint   
// 서로소, 쌍으로 서로소   
   
// 집합 A와 B는 서로소 (disjoint) ⇔ A ∩ B = ∅   
- Sets A and B are disjoint ⇔ A ∩ B = ∅   
   
// n개의 집합 A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub> 은 쌍으로 서로소 (pairwise disjoint)   
// - ⇔ A<sub>i</sub> ∩ A<sub>j</sub> = ∅ (i ≠ j, 1 ≤ i, j ≤ n)   
// - ⇔ ∩<sub>i ∈ I</sub>A<sub>i</sub> = ∅ 또는 ∩<sup>n</sup><sub>i = 1</sub>A<sub>i</sub> = ∅ (→ A<sub>1</sub> ∩ A<sub>2</sub> ∩ ... ∩ A<sub>n</sub> = ∅)   
- n sets A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub> are pairwise disjoint   
  - ⇔ A<sub>i</sub> ∩ A<sub>j</sub> = ∅ (i ≠ j, 1 ≤ i, j ≤ n)   
  - ⇔ ∩<sub>i ∈ I</sub>A<sub>i</sub> = ∅ or ∩<sup>n</sup><sub>i = 1</sub>A<sub>i</sub> = ∅ (→ A<sub>1</sub> ∩ A<sub>2</sub> ∩ ... ∩ A<sub>n</sub> = ∅)   
   
#### Partition   
// 분할   
   
// 집합 A를 ∅이 아닌 부분집합들로 나눌 때 A의 모든 원소들이 각각 나누어진 부분집합들 중 하나에만 포함될 경우 이 부분집합들 전체의 집합을 A의 분할이라고 함   
// 집합 P = {A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub>}이 집합 A의 분할 ⇔ ① ∪<sup>n</sup><sub>i = 1</sub>A<sub>i</sub> = A and ② ∩<sup>n</sup><sub>i = 1</sub>A<sub>i</sub> = ∅   
- When a set A is divided into subsets that are not ∅, if all elements of A are contained only in one of the subsets that are divided, then the set of all of these subsets is called the partition of A   
- Set P = {A<sub>1</sub>, A<sub>2</sub>, ..., A<sub>n</sub>} is a split of set A ⇔ ① ∪<sup>n</sup><sub>i = 1</sub>A<sub>i</sub> = A and ② ∩<sup>n</sup><sub>i = 1</sub>A<sub>i</sub> = ∅   
   
// 자명한 분할 (trivial partition)   
// - A ≠ ∅ ⇒ P = {A}   
// - 예시 : A = {1, 2, 3} ⇒ P = { {1, 2, 3} }   
- Trivial partition   
  - A ≠ ∅ ⇒ P = {A}   
  - Example : A = {1, 2, 3} ⇒ P = { {1, 2, 3} }   
   
// 예시 1   
// - 집합 {1, 2, 3} 의 모든 분할을 구하시오   
- Example 1   
  - Find all partitions of the set {1, 2, 3}   
    - { {1}, {2}, {3} }   
    - { {1, 2}, {3} }   
    - { {1, 3}, {2} }   
    - { {1}, {2, 3} }   
    - { {1, 2, 3} }   
   
// 예시 2   
// - Z가 모든 정수의 집합일 때 Z<sub>0</sub> = {z \| z = 2k, k는 정수}, Z<sub>1</sub> = {z \| z = 2k + 1, k는 정수} 라면, {Z<sub>0</sub>, Z<sub>1</sub>}은 Z의 분할인가?   
// → Z<sub>0</sub>는 짝수, Z<sub>1</sub>은 홀수임   
// → Z<sub>0</sub> ∪ Z<sub>1</sub> = Z   
// → Z<sub>0</sub> ∩ Z<sub>1</sub> = ∅   
// ∴ {Z<sub>0</sub>, Z<sub>1</sub>}은 Z의 분할이다   
- Example 2   
  - When Z is the set of all integers, If Z<sub>0</sub> = {z \| z = 2k, k is an integer} and Z<sub>1</sub> = {z \| z = 2k + 1, k is an integer}, then is {Z<sub>0</sub>, Z<sub>1</sub>} a partition of Z?   
  - → Z<sub>0</sub> is even, and Z<sub>1</sub> is odd   
  - → Z<sub>0</sub> ∪ Z<sub>1</sub> = Z   
  - → Z<sub>0</sub> ∩ Z<sub>1</sub> = ∅   
  - ∴ {Z<sub>0</sub>, Z<sub>1</sub>} is a partition of Z   
   
#### Power set   
// 멱집합   
   
// 집합 A의 모든 부분집합들의 집합을 A의 멱집합이라고 하고, P(A) 로 표기함   
- The set of all subsets of the set A is called the power set of A and is written as P(A)   
   
// 예시   
// - 집합 S = {a, b, c} 일 때 S의 멱집합 P(S) 을 구하시오   
- Example   
  - Find the power set P(S) of S when the set S = {a, b, c}   
    - ∴ P(S) = { ∅, {a}, {b}, {c}, {a, b}, {a, c}, {b, c}, {a, b, c} }   
   
// 멱집합의 원소의 개수   
- Number of elements in a power set   
  - |S| = n → |P(S)| = 2<sup>n</sup>   
   
<br />
### Set Operator   
// 집합연산   
   
// U : 전체집합, A ⊂ U, B ⊂ U 라 할 때   
// - 합집합 : A ∪ B = {x ∈ U \| x ∈ A ∨ x ∈ B}   
// -- 논리합 (disjucntion : or, ∨) : p ∨ q   
// - 교집합 : A ∩ B = {x ∈ U \| x ∈ A ∧ x ∈ B}   
// -- 논리곱 (conjunction : and, ∧) : p ∧ q   
// - 차집합 : A - B = {x ∈ U \| x ∈ A ∧ x ∉ B}   
// - 여집합 (보집합) : A<sup>c</sup> = U - A = {x ∈ U \| x ∉ A}   
// -- 부정 (negation : not, ~, ﹁) : ~p   
// - 대칭차집합 : A ⊕ B = {x ∈ U \| x ∈ A ∪ B ∧ x ∉ A ∩ B}   
// -- 배타적 논리합 (xor, ⊕) : p ⊕ q ≡ (p ∧ ~q) ∨ (~p ∧ q)   
- When U(Universal set), A ⊂ U, B ⊂ U   
  - Union set : A ∪ B = {x ∈ U \| x ∈ A ∨ x ∈ B}   
    - Disjucntion (or, ∨) : p ∨ q   
  - Intersection set : A ∩ B = {x ∈ U \| x ∈ A ∧ x ∈ B}   
    - Conjunction (and, ∧) : p ∧ q   
  - Difference set : A - B = {x ∈ U \| x ∈ A ∧ x ∉ B}   
  - Complement set : A<sup>c</sup> = U - A = {x ∈ U \| x ∉ A}   
    - Negation (not, ~, ﹁) : ~p   
  - Symmetric difference set : A ⊕ B = {x ∈ U \| x ∈ A ∪ B ∧ x ∉ A ∩ B}   
    - Exclusive or (xor, ⊕) : p ⊕ q ≡ (p ∧ ~q) ∨ (~p ∧ q)   
   
#### Cartesian product   
// 곱집합   
   
// U : 전체집합, A ⊂ U, B ⊂ U 라 할 때 A의 원소 a와 B의 원소 b로 만들어지는 순서쌍 (ordered pair) (a, b) 들의 집합을 A와 B의 곱집합이라 함   
// - (a, b) ≠ (b, a)   
// - A × B = {(a, b) \| a ∈ A, b ∈ B}   
- When U(Universal set), A ⊂ U, B ⊂ U, the set of ordered pairs (a, b) made of elements a of A and b of B is called the Cartesian product set of A and B   
  - (a, b) ≠ (b, a)   
  - A × B = {(a, b) \| a ∈ A, b ∈ B}   
   
- Example   
  - A = {1, 2}, B = {a, b}   
  - A × B = {(1, a), (1, b), (2, a), (2, b)}   
  - B × A = {(a, 1), (a, 2), (b, 1), (b, 2)}   
   
// 르네 데카르트 (René Descartes)   
// - cogito ergo sum   
// -- I think therefore I am   
// 데카르트의 카르트 cartes 와 곱집합의 Cartes 은 같은 단어임   
- René Descartes   
  - cogito ergo sum   
    - I think therefore I am   
- Cartes in Descartes and Cartes in the product set are the same words   
   
#### Example 1   
   
// 전체집합 U = {1, 2, 3, 4, 5} 이다   
// A = {1, 2, 3}, B = {2, 3, 4} 일 때 A ∪ B, A ∩ B, A - B, A<sup>c</sup> 을 구하시오   
// - → A ∪ B = {1, 2, 3, 4}   
// - → A ∩ B = {2, 3}   
// - → A - B = {1}   
// - → A<sup>c</sup> = {4, 5}   
- Universal set U = {1, 2, 3, 4, 5}   
- Find A ∪ B, A ∩ B, A - B, A<sup>c</sup> when A = {1, 2, 3}, B = {2, 3, 4}   
  - → A ∪ B = {1, 2, 3, 4}   
  - → A ∩ B = {2, 3}   
  - → A - B = {1}   
  - → A<sup>c</sup> = {4, 5}   
   
#### Example 2   
   
// A = {1, 2, 3}, B = {2, 3, 4} 일 때 A ⊕ B 를 구하시오   
// - → A ⊕ B = {1, 4}   
- Find A ⊕ B when A = {1, 2, 3}, B = {2, 3, 4}   
  - → A ⊕ B = {1, 4}   
   
<br />
### The algebraic laws of a set   
// 집합의 대수법칙   
   
#### Properties of the size of a set   
// 집합의 크기에 관한 성질   
   
// 합집합의 크기   
// - 정리   
// -- 집합 A, B가 유한집합이면 다음이 성립한다   
// --- |A ∪ B| = |A| + |B| - |A ∩ B|   
// - 증명   
// -- → A ∪ B = A ∪ (B - A) 이고, A와 B - A는 서로소이므로   
// -- → ① |A ∪ B| = |A| + |B - A|   
// -- → B = (B - A) ∪ (A ∩ B) 이고, B - A와 A ∩ B는 서로소이므로   
// -- → |B| = |B - A| + |A ∩ B|   
// -- → ② |B - A| = |B| - |A ∩ B|   
// -- → ②번 식을 ①번 식에 대입하면   
// -- → |A ∪ B| = |A| + |B| - |A ∩ B| 이므로 증명되었다   
- Size of the union set   
  - Theorem   
    - If the sets A and B are finite set, then the following holds true   
      - |A ∪ B| = |A| + |B| - |A ∩ B|   
  - Proof   
    - → A ∪ B = A ∪ (B - A), and A and B - A are disjoint   
    - → ① |A ∪ B| = |A| + |B - A|   
    - → B = (B - A) ∪ (A ∩ B), and B - A and A ∩ B are disjoint   
    - → |B| = |B - A| + |A ∩ B|   
    - → ② |B - A| = |B| - |A ∩ B|   
    - → If substitute equation ② into equation ①   
    - → |A ∪ B| = |A| + |B| - |A ∩ B|, so it's proof   
   
// 따름정리   
// - 정리   
// -- 집합 A, B, C 가 유한집합이면   
// --- |A ∪ B ∪ C| = |A| + |B| + |C| - |A ∩ B| - |A ∩ C| - |B ∩ C| + |A ∩ B ∩ C|   
- Corollary   
  - Theorem   
    - If the sets A, B and C are finite set   
      - |A ∪ B ∪ C| = |A| + |B| + |C| - |A ∩ B| - |A ∩ C| - |B ∩ C| + |A ∩ B ∩ C|   
   
// 서로소인 집합의 합집합의 크기   
// - 정리   
// -- 집합 A, B가 유한집합이면서 서로소이면   
// --- |A ∪ B| = |A| + |B| 이다   
// - 증명   
// -- 합집합의 크기 정리 : |A ∪ B| = |A| + |B| - |A ∩ B|   
// -- 그런데 A와 B는 서로소이므로 |A ∩ B| = 0 이다   
// -- 따라서 |A ∪ B| = |A| + |B| 이다   
- Size of the union set of disjoint sets   
  - Theorem   
    - If the sets A and B are finite set and disjoint   
      - then |A ∪ B| = |A| + |B|   
  - Proof   
    - Theorem the size of the union set : |A ∪ B| = |A| + |B| - |A ∩ B|   
    - But since A and B are disjoint, |A ∩ B| = 0   
    - Therefore, |A ∪ B| = |A| + |B|   
   
#### Inclusion relationships and Identity   
// 포함관계 및 항등식   
   
// 교집합, 합집합, 포함관계의 이행성   
// - 모든 집합 A, B, C에 대해서 다음을 만족한다   
// -- 교집합   
// --- 1. (A ∩ B) ⊆ A   
// ---- p ∧ q → p   
// --- 2. (A ∩ B) ⊆ B   
// ---- p ∧ q → q   
// -- 합집합   
// --- 1. A ⊆ (A ∪ B)   
// --- 2. B ⊆ (A ∪ B)   
// -- 이행성   
// --- 만약 A ⊆ B 이고 B ⊆ C 이면 A ⊆ C 이다   
// --- 'p → q' & 'q → r' ⇒ p → r   
- Intersection set, union set, inclusion relationship transitivity   
  - For all sets A, B, and C, the following is satisfied   
    - Intersection set   
      - 1. (A ∩ B) ⊆ A   
        - p ∧ q → p   
      - 2. (A ∩ B) ⊆ B   
        - p ∧ q → q   
    - Union set   
      - 1. A ⊆ (A ∪ B)   
      - 2. B ⊆ (A ∪ B)   
    - Transitivity   
      - If A ⊆ B and B ⊆ C, then A ⊆ C   
      - 'p → q' & 'q → r' ⇒ p → r   
   
// 원소 논증   
// - 집합 X, Y에 대해 X ⊆ Y 를 증명하고자 할 때 ∀x ∈ X → x ∈ Y 임을 보인다   
// - 예시 : A ∩ B ⊆ B의 증명   
// -- x ∈ A ∩ B → x ∈ A ∧ x ∈ B → x ∈ B   
- Element prove   
  - To proof X ⊆ Y for sets X, Y, show that ∀x ∈ X → x ∈ Y   
  - Example : Proof of A ∩ B ⊆ B   
    - x ∈ A ∩ B → x ∈ A ∧ x ∈ B → x ∈ B   
   
// 집합의 항등식   
// - U : 전체집합, A, B, C ⊂ U 라 하자   
// -- 교환법칙   
// --- A ∪ B = B ∪ A   
// --- A ∩ B = B ∩ A   
// -- 결합법칙   
// --- (A ∪ B) ∪ C = A ∪ (B ∪ C)   
// --- (A ∩ B) ∩ C = A ∩ (B ∩ C)   
// -- 분배법칙   
// --- A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C)   
// --- A ∩ (B ∪ C) = (A ∩ B) ∪ (B ∩ C)   
// -- 항등법칙   
// --- A ∪ ∅ = A   
// --- A ∩ U = A   
// -- 보수법칙   
// --- A ∪ A<sup>c</sup> = U   
// --- A ∩ A<sup>c</sup> = ∅   
// -- 이중보수법칙   
// --- (A<sup>c</sup>)<sup>c</sup> = A   
// ---- ~(~p) = p   
// -- 멱등법칙   
// --- A ∪ A = A   
// --- A ∩ A = A   
// ---- p ∧ p ∧ ...  ∧ p = p   
// -- 전체한계법칙   
// --- A ∪ U = U   
// --- A ∩ ∅ = ∅   
// -- 드모르간의 법칙   
// --- (A ∪ B)<sup>c</sup> = A<sup>c</sup> ∩ B<sup>c</sup>   
// --- (A ∩ B)<sup>c</sup> = A<sup>c</sup> ∪ B<sup>c</sup>   
// -- 흡수법칙   
// --- A ∪ (A ∩ B) = A   
// --- A ∩ (A ∪ B) = A   
// -- U와 ∅의 여집합   
// --- U<sup>c</sup> = ∅   
// ---- ~True = False   
// --- ∅<sup>c</sup> = U   
// ---- ~False = True   
// -- 차집합법칙   
// --- A - B = A ∩ B<sup>c</sup>   
- An identity of a set   
  - When U(Universal set), A, B, C ⊂ U   
    - Commutative law   
      - A ∪ B = B ∪ A   
      - A ∩ B = B ∩ A   
    - Associative law   
      - (A ∪ B) ∪ C = A ∪ (B ∪ C)   
      - (A ∩ B) ∩ C = A ∩ (B ∩ C)   
    - Distributive law   
      - A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C)   
      - A ∩ (B ∪ C) = (A ∩ B) ∪ (B ∩ C)   
    - Identity law   
      - A ∪ ∅ = A   
      - A ∩ U = A   
    - Complement law   
      - A ∪ A<sup>c</sup> = U   
      - A ∩ A<sup>c</sup> = ∅   
    - Double complement law   
      - (A<sup>c</sup>)<sup>c</sup> = A   
        - ~(~p) = p   
    - Idempotent law   
      - A ∪ A = A   
      - A ∩ A = A   
        - p ∧ p ∧ ...  ∧ p = p   
    - The law of the total limit   
      - A ∪ U = U   
      - A ∩ ∅ = ∅   
    - De Morgan's law   
      - (A ∪ B)<sup>c</sup> = A<sup>c</sup> ∩ B<sup>c</sup>   
      - (A ∩ B)<sup>c</sup> = A<sup>c</sup> ∪ B<sup>c</sup>   
    - Absorption law   
      - A ∪ (A ∩ B) = A   
      - A ∩ (A ∪ B) = A   
    - Complement set of U and ∅   
      - U<sup>c</sup> = ∅   
        - ~True = False   
      - ∅<sup>c</sup> = U   
        - ~False = True   
    - Difference set law   
      - A - B = A ∩ B<sup>c</sup>   
   
// 포함관계에 대한 동치   
// - U : 전체집합, A, B ⊂ U 라 할 때 다음은 모두 동치이다   
- Equivalence for inclusion relationships   
  - When U(Universal set), A, B ⊂ U, all of the following are equivalent   
    - A ⊆ B   
    - B<sup>c</sup> ⊆A<sup>c</sup>   
    - A ∪ B = B   
    - A ∩ B = A   
    - A<sup>c</sup> ∪ B = U   
    - A ∩ B<sup>c</sup> = ∅   
    - A - B = ∅   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
