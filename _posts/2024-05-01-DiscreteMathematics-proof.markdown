---
layout: post
title:  "Discrete Mathematics: Proof"
date:   2024-05-01 09:00:00 +0900
categories: [Discrete Mathematics]
---

### basic information   
// 기본사항   
   
// 정의   
// - 공리 (axiom)   
// - 증명 (proof)   
// - 정리 (theorem)   
- definition   
  - axiom   
  - proof   
  - theorem   
   
// 증명 방법   
// - 직접 증명법 : 공리와 정의, 그리고 정리를 논리적으로 직접 연결하여 증명함   
// - 수학적 귀납법 : 자연수 n에 대한 명제의 성질을 증명하는 데 유용한 증명 방법   
// -- 기본단계, 귀납가정, 귀납단계를 이용함   
// - 간접 증명법 : 증명해야 할 명제를 증명하기 쉬운 형태로 변형하여 증명하는 방법   
// -- 대우 증명법, 모순 증명법, 반례 증명법, 존재 증명법 등   
// - 그 외 : 전수 증명법, 조합적 증명법, 컴퓨터 이용 증명법   
- proof method   
  - direct proof : proving axioms, definitions, and theorems by connecting them logically and directly   
  - proof by mathematical induction : a useful method of proof to prove the nature of a proposition for a natural number n   
    - Basic steps, inductive assumptions, and inductive steps are used   
  - indirect proof : It is a method of proving the proposition to be proved by transforming it into a form that is easy to prove   
    - proof by transposition, proof by contradiction, proof by counter-example, existence proof, etc.   
  - other methods of proof : proof by exhaustion, combinatorial proof, computer-assisted proof   
   
#### axiom   
// 공리   
   
// 어떤 다른 명제들을 증명하기 위해 전제로 사용되는 가장 기본적인 가정으로, 별도의 증명 없이 참으로 이용되는 명제를 공리라고 함   
- The most basic assumption used as a premise to prove some other propositions, the propositions that are really used without additional proof are called axioms   
   
// 예시   
// - 두 점이 주어졌을 때, 두 점을 통과하는 직선을 그릴 수 있다 (유클리드 기하학)   
// - 어떤 자연수도 그 수의 다음 수가 존재한다 (페아노의 공리)   
// - 어떤 것도 포함하지 않는 집합이 존재한다 (공리적 집합론)   
- Example   
  - Given two points, a straight line is drawn through them (Euclidean geometry)   
  - Any natural number has the next number (Peano’s axioms)   
  - There is a set that does not contain anything (axiomatic set theory)   
   
#### proof   
// 증명   
   
// 증명이란 특정한 공리들을 가정하고, 그 가정하에 제안된 명제가 참임을 입증하는 작업임   
- Proof is the work of presuming specific axioms and proving that the proposed proposition is true under that assumption   
   
#### theorem   
// 정리   
   
// 공리로부터 증명된 명제를 정리라고 함   
- Proposition proved by axiom is called theorem   
   
// 보조정리 (lemma)   
// - 정리를 증명하는 과정 중에 사용되는 증명된 명제   
- lemma   
  - a lemma is a proven proposition which is used as a stepping stone to a larger result   
   
// 따름정리 (corollary)   
// - 정리로부터 쉽게 도출되는 부가적인 명제   
- corollary   
  - an additional proposition easily derived from a theorem   
  - a corollary typically follows a theorem   
   
<br />
### direct proof   
// 직접 증명법   
   
// 다른 말로 연역법 (deduction) 이라고도 함   
// - 연역법 : 이미 증명된 하나 또는 둘 이상의 명제를 전제로 하여 새로운 명제를 결론으로 이끌어내는 것   
// 명제를 변형하지 않고 증명함   
// 주로 공리와 정의, 그리고 이미 증명된 정리를 논리적으로 직접 연결해 증명하는 형식을 따름   
- In other words, deduction   
  - deduction : To draw a conclusion to a new proposition on the premise of one or more propositions that have already been proven   
- Proving proposition without transformation   
- It mainly follows the form of proof by logically connecting axioms with definitions and theorems that have already been proven   
   
#### Example 1   
// 예시 1   
   
// 두 홀수의 합은 짝수임을 증명하라   
- Prove that the sum of two odd numbers is even   
   
// [증명] 두 홀수를 각각 x, y라고 하자   
// - ⇒ x = 2a + 1, y = 2b + 1 (단, a, b는 정수)   
// - ⇒ x + y = 2a + 1 + 2b + 1 = 2a + 2b + 2 = 2(a + b + 1)   
// -- a + b + 1 은 정수 + 정수 + 정수 이므로 합도 정수임   
// - ⇒ x + y = 2(정수)   
// -- 2 × 정수는 짝수임   
// - ∴ 두 홀수의 합인 x + y 도 짝수. ■   
- [proof] Let x and y be the odd numbers, respectively   
  - ⇒ x = 2a + 1, y = 2b + 1 (a and b are integers)   
  - ⇒ x + y = 2a + 1 + 2b + 1 = 2a + 2b + 2 = 2(a + b + 1)   
    - a + b + 1 is integer + integer + integer so sum is integer   
  - ⇒ x + y = 2(integer)   
    - 2 × integer is even   
  - ∴ The sum of two odd numbers, x + y is also even. ■   
   
#### Example 2   
// 예시 2   
   
// 두 유리수의 합이 유리수임을 증명하라   
- Prove that the sum of two rational numbers is a rational number   
   
// [증명] r, s를 유리수라 하자   
// - ⇒ r = <sup>a</sup> / <sub>b</sub> (단, a와 b는 정수이고 b ≠ 0)   
// - ⇒ s = <sup>c</sup> / <sub>d</sub> (단, c와 d는 정수이고 d ≠ 0)   
// - ⇒ r + s = <sup>a</sup> / <sub>b</sub> + <sup>c</sup> / <sub>d</sub> = <sup>ad + bc</sup> / <sub>bd</sub>   
// -- <sub>bd</sub>는 정수 × 정수 이므로 곱도 정수임. b ≠ 0, d ≠ 0 이므로 b × d ≠ 0   
// --- ⇒ <sub>bd</sub>는 0이 아닌 정수임   
// -- <sup>ad</sup>는 정수에 대한 곱셈이므로 정수임. <sup>bc</sup>는 정수에 대한 곱셈이므로 정수임. <sup>ad + bc</sup>는 정수에 대한 덧셈이므로 정수임   
// - 유리수는 <sup>임의의 정수</sup> / <sub>0이 아닌 정수</sub> 로 표현할 수 있음   
// -- ⇒ <sup>ad + bc</sup> 와 <sub>bd</sub> 는 정수, <sub>bd</sub> ≠ 0 이므로   
// - ∴ 두 유리수의 합은 유리수. ■   
- [proof] Let r and s be the rational number   
  - ⇒ r = <sup>a</sup> / <sub>b</sub> (a and b are integers and b ≠ 0)   
  - ⇒ s = <sup>c</sup> / <sub>d</sub> (c and d are integers and d ≠ 0)    
  - ⇒ r + s = <sup>a</sup> / <sub>b</sub> + <sup>c</sup> / <sub>d</sub> = <sup>ad + bc</sup> / <sub>bd</sub>   
    - Since <sub>bd</sub> is integer × integer, the multiplication is also integer. b ≠ 0, d ≠ 0, so b × d ≠ 0   
      - ⇒ <sub>bd</sub> is a nonzero integer   
    - <sup>ad</sup> is an integer because it is a multiplication of an integer. <sup>bc</sup> is an integer because it is a multiplication of an integer. <sup>ad + bc</sup> is an integer because it is an addition to an integer   
  - rational numbers can be expressed as <sup>any integer</sup> / <sub>nonzero integer</sub>   
    - ⇒ <sup>ad + bc</sup> and <sub>bd</sub> are integers, and <sub>bd</sub> ≠ 0   
  - ∴ The sum of the two rational numbers is a rational number. ■   
   
#### Pascal's triangle   
// 파스칼 삼각형   
   
|||||||1|||||||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
||||||1||1||||||
|||||1||2||1|||||
||||1||3||3||1||||
|||1||4||6||4||1|||
||1||5||10||10||5||1||
|1||6||15||20||15||6||1|
   
// 파스칼 삼각형은 이항계수 (二項係數 binomial coefficients) 들을 삼각형 모양으로 만들어 놓음   
- Pascal's triangle is a triangular array of the binomial coefficients   
   
// 이항계수 예시   
- Example of binomial coefficients   
  - (x + y)<sup>5</sup> = 1x<sup>5</sup> + 5x<sup>4</sup>y<sup>1</sup> + 10x<sup>3</sup>y<sup>2</sup> + 10x<sup>2</sup>y<sup>3</sup> + 5x<sup>1</sup>y<sup>4</sup> + 1y<sup>5</sup>   
  - (x + y)<sup>6</sup> = 1x<sup>6</sup> + 6x<sup>5</sup>y<sup>1</sup> + 15x<sup>4</sup>y<sup>2</sup> + 20x<sup>3</sup>y<sup>3</sup> + 15x<sup>2</sup>y<sup>4</sup> + 6x<sup>1</sup>y<sup>5</sup> + 1y<sup>6</sup>   
   
// 이항정리   
// - (x + y)<sup>n</sup> = ∑<sup>n</sup><sub>k = 0</sub> C(n, k) x<sup>n - k</sup>y<sup>k</sup>   
// - C(n, k) 는 계수임   
- binomial theorem   
  - (x + y)<sup>n</sup> = ∑<sup>n</sup><sub>k = 0</sub> C(n, k) x<sup>n - k</sup>y<sup>k</sup>   
  - C(n, k) is a coefficient   
   
// 이항계수   
// - C(n, k) ≡ <sub>n</sub>C<sub>k</sub> ≡ (<sup>n</sup><sub>k</sub>) = <sup>n!</sup> / <sub>k!(n - k)!</sub>   
// - C 는 조합 Combination 의 약자임. 순서에 상관 없음. 전체 n 개 중 k 개를 꺼내는 것   
// - ! 는 자연수의 계승, 팩토리얼 factorial 임. 팩토리얼은 그 수보다 작거나 같은 모든 양의 정수의 곱임   
// - 위의 파스칼 삼각형 중 (1 5 10 10 5 1) 행의 첫번째 10에 대한 이항계수는 C(5, 2) = C(4, 2) + C(4, 1)   
- binomial coefficient   
  - C(n, k) ≡ <sub>n</sub>C<sub>k</sub> ≡ (<sup>n</sup><sub>k</sub>) = <sup>n!</sup> / <sub>k!(n - k)!</sub>   
  - C stands for combination. It doesn't matter the order. Taking out k out of all n   
  - ! is the factual of natural numbers. Factorial is a multiplication of all positive integers less than or equal to that number   
  - Among the Pascal triangles above, the binomial coefficient for the first 10 in row (15 10 10 51) is C(5, 2) = C(4, 2) + C(4, 1)   
   
#### Pascal's triangle theorem   
// 파스칼 삼각형 정리   
   
// n, k 는 양의 정수이고, k ≤ n 이라고 가정하면 C(n + 1, k) = C(n, k) + C(n, k - 1) 이다   
- n, k is a positive integer, and assuming k ≤ n, C(n + 1, k) = C(n, k) + C(n, k - 1)   
   
- [proof] C(n, k) + C(n, k - 1)   
  - ⇒ <sup>n!</sup> / <sub>k!(n - k)!</sub> + <sup>n!</sup> / <sub>(k - 1)!(n - (k - 1))!</sub>   
  - ⇒ <sup>n!</sup> / <sub>k!(n - k)!</sub> + <sup>n!</sup> / <sub>(k - 1)!(n - k + 1)!</sub>   
  - ⇒ <sup>(n - k + 1)n!</sup> / <sub>(n - k + 1)k!(n - k)!</sub> + <sup>kn!</sup> / <sub>k(k - 1)!(n - k + 1)!</sub>   
  - ⇒ <sup>(n - k + 1)n! + kn!</sup> / <sub>k!(n - k + 1)!</sub>   
  - ⇒ <sup>(n + 1)n!</sup> / <sub>k!(n - k + 1)!</sub>   
  - ⇒ <sup>(n + 1)!</sup> / <sub>k!((n + 1) - k)!</sub>   
  - ∴ C(n + 1, k). ■   
      
<br />
### proof by mathematical induction   
// 수학적 귀납법   
   
// 모든 자연수 n에 대해 명제를 증명하는 데 유용   
- Useful for proving propositions for all natural numbers n   
   
// 3단계 과정   
// 1. 기본단계 (basis)   
// - n의 출발점에서 명제가 성립하는가 확인   
// -- n이 0일 때도 있음   
// 2. 귀납가정 (inductive assumption)   
// - n = k 일 때 명제가 성립한다고 가정   
// 3. 귀납단계 (inductive step)   
// - n = k + 1 일 때도 명제가 성립함을 증명   
- a three-step process   
  1. basis   
      - Check whether the proposition is established at the starting point of n   
        - Sometimes n is 0   
  2. inductive assumption   
      - Assume that the proposition is established when n = k   
  3. inductive step   
      - Prove that the proposition holds even when n = k + 1   
   
#### Example 1   
// 예시 1   
   
// n이 자연수일 때 다음을 증명하시오   
// 1 + 2 + ... + n = <sup>n(n + 1)</sup> / <sub>2</sub>   
- Prove that when n is a natural number   
- 1 + 2 + ... + n = <sup>n(n + 1)</sup> / <sub>2</sub>   
   
// [풀이] S(n) 을 1 + 2 + ... + n = <sup>n(n + 1)</sup> / <sub>2</sub> 라 하자   
// 1. 기본단계 (basis)   
// - S(1) 은 1 = <sup>1(1 + 1)</sup> / <sub>2</sub> 이므로 성립   
// 2. 귀납가정 (inductive assumption)   
// - S(k) 가 참이라고 가정   
// -- 1 + 2 + ... + k = <sup>k(k + 1)</sup> / <sub>2</sub>   
// 3. 귀납단계 (inductive step)   
// - S(k + 1) : 1 + 2 + ... + k + (k + 1) = <sup>(k + 1)((k + 1) + 1)</sup> / <sub>2</sub>   
// -- ⇒ <sup>k(k + 1)</sup> / <sub>2</sub> + (k + 1)   
// -- ⇒ <sup>k(k + 1) + 2(k + 1)</sup> / <sub>2</sub>   
// -- ⇒ <sup>(k + 1)(k + 2)</sup> / <sub>2</sub>   
// -- ⇒ <sup>(k + 1)((k + 1) + 1)</sup> / <sub>2</sub>   
// - ∴ 수학적 귀납법에 의해 주어진 명제는 참. ■   
- [Solving] Let S(n) be 1 + 2 + ... + n = <sup>n(n + 1)</sup> / <sub>2</sub>   
  1. basis   
      - S(1) is established because 1 = <sup>1(1 + 1)</sup> / <sub>2</sub>   
  2. inductive assumption   
      - Assume that S(k) is true   
        - 1 + 2 + ... + k = <sup>k(k + 1)</sup> / <sub>2</sub>   
  3. inductive step   
      - S(k + 1) : 1 + 2 + ... + k + (k + 1) = <sup>(k + 1)((k + 1) + 1)</sup> / <sub>2</sub>   
        - ⇒ <sup>k(k + 1)</sup> / <sub>2</sub> + (k + 1)   
        - ⇒ <sup>k(k + 1) + 2(k + 1)</sup> / <sub>2</sub>   
        - ⇒ <sup>(k + 1)(k + 2)</sup> / <sub>2</sub>   
        - ⇒ <sup>(k + 1)((k + 1) + 1)</sup> / <sub>2</sub>   
- ∴ Based on proof by mathematical induction, the proposition given is true. ■   
   
<br />
### indirect proof   
// 간접 증명법   
   
// 증명해야 할 명제를 증명하기 쉬운 형태로 변형하여 증명하는 방법   
// - 대우 증명법   
// - 모순 증명법   
// - 반례 증명법   
// - 존재 증명법   
- How to prove a proposition by transforming it into a form that is easy to prove   
  - proof by transposition   
  - proof by contradiction   
  - proof by counter-example   
  - existence proof   
   
#### proof by transposition   
// 대우 증명법   
   
- P → Q ⇔ ~Q → ~P   
   
// 예시   
// - x²이 홀수라면 x도 홀수임을 증명하시오   
// - [풀이] "x²이 홀수라면 x도 홀수"의 대우는 "x가 홀수가 아니라면 x²도 홀수가 아니다"   
// -- ⇒ x는 짝수 ⇒ x = 2k (단, k는 정수)   
// -- ⇒ x² = (2k)² = 4k² = 2(2k²)   
// -- ⇒ 2k²도 정수이므로 x²는 짝수   
// -- ∴ 대우 증명법에 의해 주어진 명제는 참. ■   
- Example   
  - Prove that if x² is odd, then x is also odd   
  - [Solving] The transposition of "x is odd if x² is odd" is "x² is not odd if x is not odd."   
    - ⇒ x is an even ⇒ x = 2k (k is an integer)   
    - ⇒ x² = (2k)² = 4k² = 2(2k²)   
    - ⇒ 2k² is also an integer, so x² is even   
    - ∴ The proposition given by the Daewoo Proof Law is true. ■   
   
#### proof by contradiction   
// 모순 증명법   
   
// P → Q 를 증명할 때 ~P를 가정하면 모순이 발생함을 보임   
- It shows that a contradiction occurs when ~P is assumed when P → Q is proved   
   
// 모순 증명법의 다른 이름   
// - 귀류법 (歸謬法) : 오류로 귀착된다는 것을 보임   
// - 배리법 (背理法) : 이치에 어긋나게 된다는 것을 보임   
- Another name for the proof by contradiction   
  - proof by contradiction : showing that it results in error   
  - indirect proof : showing that it goes against the grain of reason   
   
// 예시   
// - √2가 유리수가 아님을 증명하시오   
// - [풀이] √2가 유리수라고 가정하자   
// -- ⇒ √2 = <sup>a</sup> / <sub>b</sub> (단, a와 b는 서로소 관계인 0이 아닌 정수. 기약분수)   
// -- ⇒ 2 = <sup>a²</sup> / <sub>b²</sub>   
// -- ⇒ 2b² = a²   
// -- ⇒ a²이 짝수 ⇒ a도 짝수   
// --- a = 2c 로 치환하여 대입 (c는 정수)   
// -- ⇒ 2b² = (2c)²   
// -- ⇒ 2b² = 4c²   
// -- ⇒ b² = 2c²   
// -- ⇒ b²이 짝수 ⇒ b도 짝수   
// -- a도 짝수, b도 짝수이므로 서로소 관계가 아님 ⇒ 모순   
// -- ∴ √2는 유리수가 아님. ■   
- Example   
  - Prove that √2 is not a rational number   
  - [Solving] assuming √2 is a rational number   
    - ⇒ √2 = <sup>a</sup> / <sub>b</sub> (a and b are nonzero integers that are disjoint from each other. irreducible fraction)   
    - ⇒ 2 = <sup>a²</sup> / <sub>b²</sub>   
    - ⇒ 2b² = a²   
    - ⇒ a² is even ⇒ a is even   
      - Substituting by a = 2c (c is an integer)   
    - ⇒ 2b² = (2c)²   
    - ⇒ 2b² = 4c²   
    - ⇒ b² = 2c²   
    - ⇒ b² is even ⇒ b is even   
    - a is even and b is even, so that are disjoint from each other ⇒ a contradiction   
    - ∴ √2 is not a rational number. ■   
   
#### proof by counter-example   
// 반례 증명법   
   
// 한정자 (quantifer) 가 포함된 명제의 증명   
// - 전체한정자 (∀) 가 사용된 명제가 거짓임을 증명 → 반례 증명법   
- Proof of propositions containing quantifier   
  - Proof that the proposition used by the universal quantifier (∀) is false → proof by counter-example   
   
// 반례 증명법 예시   
// - 다음 명제가 거짓임을 증명하시오   
// - 모든 실수 a, b에 대해 a² = b² 이면 a = b 이다   
// - [풀이] 반례로서 a = -2, b = 2 일 경우   
// -- ⇒ a² = b² 을 만족하지만 a ≠ b 이다   
// -- ∴ 거짓. ■   
- Example of a proof by counter-example   
  - Prove that the following proposition is false   
  - For every real number a and b, a² = b² is a = b   
  - [Solving] For counter-example, a = -2, b = 2   
    - ⇒ It satisfies a² = b², but it is a ≠ b   
    - ∴ false. ■   
   
#### existence proof   
// 존재 증명법   
   
// 한정자 (quantifer) 가 포함된 명제의 증명   
// - 존재한정자 (∃) 가 사용된 명제가 참임을 증명 → 존재 증명법   
// -- 구성적 존재 증명법   
// -- 비구성적 존재 증명법   
- Proof of propositions containing quantifier   
  - Proof that the proposition used by the existential quantifier (∃) is true → existence proof   
    - constructive proof of existence   
    - nonconstructive proof of existence   
   
#### constructive proof of existence   
// 구성적 존재 증명법   
   
// 명제함수 ∃xP(x) 를 증명할 때 P(x) 를 참으로 만드는 x를 찾거나 찾는 과정을 제시함   
- When we prove the propositional function ∃xP(x), we present the process of finding or finding x that makes P(x) true   
   
// 예시   
// - a<sup>b</sup>이 무리수가 되는 유리수 a, b가 존재함을 증명하시오   
// - [풀이] a가 2, b가 <sup>1</sup> / <sub>2</sub> 이라고 하자   
// -- ⇒ a<sup>b</sup> = 2<sup><sup>1</sup> / <sub>2</sub></sup> = √2 (무리수)   
// -- ∴ 참. ■   
- Example   
  - Prove that there are rational numbers a, b where a<sup>b</sup> is irrational numbers   
  - [Solving] assuming a is 2 and b is <sup>1</sup> / <sub>2</sub>   
    - ⇒ a<sup>b</sup> = 2<sup><sup>1</sup> / <sub>2</sub></sup> = √2 (irrational numbers)   
    - ∴ true. ■   
   
#### nonconstructive proof of existence   
// 비구성적 존재 증명법   
   
// 명제함수 ∃xP(x) 를 증명할 때 P(x) 를 참으로 만드는 x를 찾지 않고 우회적으로 명제가 타당함을 보이는 방법   
- How to show that a proposition is valid indirectly without finding x that makes P(x) true when proving the proposition function ∃xP(x)   
   
// 예시   
// - a<sup>b</sup>이 유리수가 되는 무리수 a, b가 존재함을 비구성적인 방법을 사용해 증명하시오   
// - [풀이] q = √2<sup>√2</sup> 이라고 하자. q는 유리수 혹은 무리수 일 수 있음   
// -- 1. 만약 q가 유리수라면 a와 b는 모두 무리수   
// --- ∴ 명제는 참. ■   
// -- 2. 만약 q가 무리수라면 a = √2<sup>√2</sup>, b = √2 라고 둔다   
// --- ⇒ a<sup>b</sup> = (√2<sup>√2</sup>)<sup>√2</sup> = √2<sup>(√2√2)</sup> = √2<sup>2</sup> = 2   
// --- ⇒ a<sup>b</sup> 는 유리수   
// --- ∴ 명제는 참. ■   
// -- ∴ 명제는 참. ■   
- Example   
  - Use the nonconstructive proof of existence to prove that there are irrational numbers a, b where a<sup>b</sup> is rational numbers   
  - [Solving] assuming q = √2<sup>√2</sup>. q may be rational number or irrational number   
    1. If q is a rational number, then both a and b are irrational numbers   
        - ∴ The proposition is true. ■   
    2. If q is an irrational number, let a = √2<sup>√2</sup>, b = √2   
        - ⇒ a<sup>b</sup> = (√2<sup>√2</sup>)<sup>√2</sup> = √2<sup>(√2√2)</sup> = √2<sup>2</sup> = 2   
        - ⇒ a<sup>b</sup> is a rational number   
        - ∴ The proposition is true. ■   
  - ∴ The proposition is true. ■   
   
<br />
### a variety of proof methods   
// 다양한 증명 방법   
   
#### proof by exhaustion   
// 전수 증명법   
   
// 명제에서 유도될 수 있는 경우의 수가 적을 때 일일이 모든 경우의 수를 조사하는 방법   
- To investigate the number of all cases one by one when the number of cases that can be derived from a proposition is small   
   
// 예시   
// - n이 5이하의 자연수일 때 (n + 1)<sup>2</sup> ≥ 2<sup>n</sup> 임을 증명하시오   
// - [풀이]   
// -- n = 1 일 때 ⇒ (1 + 1)<sup>2</sup> ≥ 2<sup>1</sup>   
// -- n = 2 일 때 ⇒ (2 + 1)<sup>2</sup> ≥ 2<sup>2</sup>   
// -- n = 3 일 때 ⇒ (3 + 1)<sup>2</sup> ≥ 2<sup>3</sup>   
// -- n = 4 일 때 ⇒ (4 + 1)<sup>2</sup> ≥ 2<sup>4</sup>   
// -- n = 5 일 때 ⇒ (5 + 1)<sup>2</sup> ≥ 2<sup>5</sup>   
// -- ∴ n이 5이하의 자연수일 때 (n + 1)<sup>2</sup> ≥ 2<sup>n</sup> 성립. ■   
- Example   
  - Prove that (n + 1)<sup>2</sup> ≥ 2<sup>n</sup> when n is a natural number of 5 or less   
  - [Solving]   
    - When n = 1 ⇒ (1 + 1)<sup>2</sup> ≥ 2<sup>1</sup>   
    - When n = 2 ⇒ (2 + 1)<sup>2</sup> ≥ 2<sup>2</sup>   
    - When n = 3 ⇒ (3 + 1)<sup>2</sup> ≥ 2<sup>3</sup>   
    - When n = 4 ⇒ (4 + 1)<sup>2</sup> ≥ 2<sup>4</sup>   
    - When n = 5 ⇒ (5 + 1)<sup>2</sup> ≥ 2<sup>5</sup>   
    - ∴ When n is a natural number of 5 or less (n + 1)<sup>2</sup> ≥ 2<sup>n</sup> is established. ■   
   
#### combinatorial proof   
// 조합적 증명법   
   
// 두 집합의 원소의 개수가 동일함을 증명할 때 사용됨   
- Used to prove that the number of elements in two sets is equal   
   
// 1. 전단증명   
// - 원소가 n개인 집합 A와 원소가 m개인 집합 B를 찾은 후, 두 집합이 일대일 관계를 보여 n = m 임을 증명함   
// 2. 중복산정   
// - 동일한 집합의 원소를 두 가지 서로 다른 방법으로 센 다음, 그 결과가 각각 n과 m이라면 n = m 임을 증명함   
1. bijective proof   
    - After finding the set A with n elements and the set B with m elements, the two sets show a one-to-one relationship, proving that n = m   
2. double counting proof   
    - Count the same set of elements in two different ways, and prove that if the result is n and m, respectively, then n = m   
   
#### computer-assisted proof   
// 컴퓨터를 이용한 증명 방법   
   
// 증명하기가 복잡한 경우 컴퓨터의 데이터 처리능력을 이용하여 증명함   
- Proof using the data processing power of the computer if it is complicated to prove   
   
// 4색 정리   
// - 평면을 유한개의 부분으로 나누어 각 부분에 색을 칠할 때, 서로 맞닿는 부분을 다른 색으로 칠한다면 네 가지 색으로 충분하다   
- Four colors theorem   
  - When dividing a plane into a finite number of parts and painting each part, four colors are sufficient if the parts that come into contact with each other are painted different colors   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
