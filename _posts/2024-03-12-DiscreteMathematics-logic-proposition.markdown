---
layout: post
title:  "Discrete Mathematics: Logic, Proposition"
date:   2024-03-12 09:00:00 +0900
categories: [Discrete Mathematics]
---

### Logic
// 논리   

// 명제논리   
// - 명제   
// 술어논리   
// - 명제함수   
- Proposition logic   
  - Proposition   
- Predicate logic   
  - Propositional function   
   
<br />
### Proposition   
// 명제   
   
// 참과 거짓을 구별할 수 있는 문장이나 수학적 식을 명제라고 함   
- A statement or mathematical expression that distinguishes true from false is called a proposition   
   
// 명제의 진리값   
// - 참, True, T : 명제가 타당한 경우   
// - 거짓, False, F : 명제가 타당하지 않은 경우   
- Truth value   
  - True, T : If the proposition is valid   
  - False, F : If the proposition is not valid   
   
// 명제의 예시   
// 1. 다음 문장이 명제인지 아닌지 구분하시오.   
// ① 6은 2의 배수다   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 명제이다. 진리값이 참임.   
// ② 철수는 공부를 잘한다   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 명제가 아니다. 기준에 따라서 철수는 공부를 잘 할 수도 있고, 못 할 수도 있다.   
// ③ 2 + 3 = 7   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 명제이다. 진리값이 거짓임.   
// ④ x + 2 = 0   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 명제가 아니다. 명제함수이다. x의 값에 따라서 참일 수도 있고, 거짓일 수도 있다.   
// 2. 다음 명제의 진리값을 구하시오.   
// ① 2, 3, 6는 소수이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 거짓. F.   
// ② 소수의 개수는 무한하다.   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 참. T.   
// ③ 126 = 2⁶   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 거짓. F.   
// ④ 지구에서 가장 높은 산은 에베레스트이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ 참. T.   
- Example of a proposition   
  1. Distinguish whether the following sentence is a proposition or not.   
    ① Six is a multiple of two   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ It's a proposition. Truth is true.   
    ② Chulsoo is good at studying   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ It's not a proposition. Depending on the standard, Chul-soo may or may not study well.   
    ③ 2 + 3 = 7   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ It's a proposition. Truth is false.   
    ④ x + 2 = 0   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ It's not a proposition. It's a propositional function. Depending on the value of x, it can be true or false.   
  2. Find the truth value of the following proposition.   
    ① 2, 3 and 6 are prime numbers.   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ false. F.   
    ② The number of prime numbers is infinite.   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ true. T.   
    ③ 126 = 2⁶   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ false. F.   
    ④ The highest mountain on Earth is Everest.   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ true. T.   
   
#### Type of proposition   
// 명제의 종류   
   
// 합성명제   
// 조건명제 (→), 쌍조건명제 (↔)   
// 항진명제, 모순명제   
- Compound proposition   
- Conditional proposition (→), Conditional proposition (↔)   
- Tautology proposition, Contradiction proposition   
   
<br />
### Logical Operation   
// 논리 연산   
   
#### Logical Operator   
// 논리 연산자   
   
// 실수집합   
// - 0.5, √2, x, y, ...   
// - 0.5, √2 --> 상수. 실수상수   
// - x, y --> 변수. 실수변수   
- Real number set   
  - 0.5, √2, x, y, ...   
  - 0.5, √2 --> Constant. Real number constant   
  - x, y --> Variable. Real number variable   
   
// 실수 연산자   
// - +, -, ×, ÷   
- Real number operator   
  - +, -, ×, ÷   
   
// 수식 (실수 연산식)   
// - 실수 연산을 실수집합에 적용하면 성질이 나옴   
// - 실수집합에서 실수상수와 실수변수들을 실수 연산들로 묶어놓으면 수식 (실수 연산식) 이 됨   
// - 예시 : √2x + y   
- Numeric expression (Real number operation expression)   
  - Applying real number operations to real number sets results in properties   
  - In a real number set, real number constants and real number variables are grouped into real number operations, resulting in a numeric expression (Real number operation expression)   
  - Example : √2x + y   
   
// 논리집합   
// - T, F, p, q, ...   
// - T, F --> 상수. 논리상수   
// - p, q --> 변수. 논리변수. 명제   
- Logical set   
  - T, F, p, q, ...   
  - T, F --> Constant. Logical constant   
  - p, q --> Variable. Logical variable. Proposition   
   
// 논리 연산, 논리 연산자   
// - ∨ (or. +), ∧ (and. ×. ·), ~ (not. ~ (﹁). <u>X</u>), ⊕ (xor), ⊙ (xnor)   
// - or, and, not, xor --> 논리 연산   
// - ∨, ∧, ~ (﹁), ⊕, ⊙ --> 논리 연산자   
- Logical Operation, Logical Operator   
  - ∨ (or. +), ∧ (and. ×. ·), ~ (not. ~ (﹁). <u>X</u>), ⊕ (xor), ⊙ (xnor)   
  - or, and, not, xor --> Logical Operation   
  - ∨, ∧, ~ (﹁), ⊕, ⊙ --> Logical Operator   
   
// 합성명제 (논리 연산식)   
// - 논리 연산을 논리집합에 적용하면 성질이 나옴   
// - 논리집합에서 논리상수와 논리변수들을 논리 연산들로 묶어놓으면 합성명제 (논리 연산식) 이 됨   
// - 예시 : p ∨ q   
- Compound Proposition (Logical Operation Expression)   
  - Applying logical operations to logical sets results in properties   
  - In a logical set, when logical numbers and logical variables are grouped into logical operations, it becomes a compound proposition (Logical Operation Expression)   
  - Example : p ∨ q   
   
#### Disjunction (Logical Operation or, Logical Operator ∨)   
// 논리합 (논리 연산 or, 논리 연산자 ∨)   
   
- p ∨ q   
   
Truth Table   
// 진리표   
   
|p|q|p ∨ q|
|:---:|:---:|:---:|
|T|T|T|
|T|F|T|
|F|T|T|
|F|F|F|
   
// 예시   
// 1. 다음 명제의 논리합을 작성하고 진리값을 구하시오.   
// ① p : 3 > 1 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; q : 4 > 8 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p ∨ q --> ∴ T   
// ② p : 2 × 3 = 8 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp; q : 4 - 2 = 3 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp; r : 소크라테스는 살아있다 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p ∨ q ∨ r --> ∴ F   
- Example   
  1. Write the logical sum of the following propositions and find the truth value.   
    ① p : 3 > 1 --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; q : 4 > 8 --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p ∨ q --> ∴ T   
    ② p : 2 × 3 = 8 --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; q : 4 - 2 = 3 --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; r : Socrates is alive --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p ∨ q ∨ r --> ∴ F   
   
#### Conjunction (Logical Operation and, Logical Operator ∧)   
// 논리곱 (논리 연산 and, 논리 연산자 ∧)   
   
- p ∧ q   
   
Truth Table   
// 진리표   
   
|p|q|p ∧ q|
|:---:|:---:|:---:|
|T|T|T|
|T|F|F|
|F|T|F|
|F|F|F|
   
// 예시   
// 1. 다음 명제의 논리곱을 작성하고 진리값을 구하시오.   
// ① p : 홀수와 홀수를 더하면 짝수이다 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; q : 짝수와 홀수를 곱하면 짝수이다 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p ∧ q --> ∴ T   
// ② p : 키보드는 입력장치이다 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; q : USB는 메모리이다 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; r : 모니터는 기억장치이다 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p ∧ q ∧ r --> ∴ F   
- Example   
  1. Write an argument for the following proposition and find the truth value.   
    ① p : Odd plus odd is even number --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; q : An even times an odd is an even number --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p ∧ q --> ∴ T   
    ② p : A keyboard is an input device --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; q : USB is memory device --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; r : A monitor is a memory device --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p ∧ q ∧ r --> ∴ F   
   
#### Negation (Logical Operation Not, Logical Operator ~ (﹁))   
// 부정 (논리 연산 not, 논리 연산자 ~ (﹁))   
   
- ~p   
   
Truth Table   
// 진리표   
   
|p|~p|
|:---:|:---:|
|T|F|
|F|T|
   
#### Exclusive or (Logical Operation XOR, Logical operator ⊕)   
// 배타적 논리합 (논리 연산 xor, 논리 연산자 ⊕)   
   
- p ⊕ q ≡ (p ∧ ~q) ∨ (~p ∧ q)   
   
// p와 q의 진리값이 서로 다르면 T, 같으면 F   
// 'or' 진리표에서 T, T 의 진리값을 F로 바꾼 것   
- If the truth values of p and q are different, it is T, and if it is the same, it is F   
- The change of the truth values of T and T to F in the truth table of 'or'   
   
Truth Table   
// 진리표   
   
|p|q|p ∧ ~q|~p ∧ q|(p ∧ ~q) ∨ (~p ∧ q)|p ⊕ q|
|:---:|:---:|:---:|:---:|:---:|:---:|
|T|T|F|F|F|F|
|T|F|T|F|T|T|
|F|T|F|T|T|T|
|F|F|F|F|F|F|
   
// 예시   
// 1. 합성명제 (p ∧ q) ∨ (p ⊕ q)의 진리표를 작성하시오.   
- Example   
  1. Write a truth table of the compound proposition (p ∧ q) ∨ (p ⊕ q)   
   
|p|q|p ∧ q|p ⊕ q|(p ∧ q) ∨ (p ⊕ q)|
|:---:|:---:|:---:|:---:|:---:|
|T|T|T|F|T|
|T|F|F|T|T|
|F|T|F|T|T|
|F|F|F|F|F|
   
|(p ∧ q) ∨ (p ⊕ q)|p ∨ q|
|:---:|:---:|
|T|T|
|T|T|
|T|T|
|F|F|
   
<br />
### Compound Proposition   
// 합성명제   
   
// 하나 이상의 명제와 논리 연산자 (∨, ∧, ~(﹁), ⊕, ⊙) 그리고 괄호로 이루어진 명제   
- A proposition consisting of one or more propositions and logical operators (∨, ∧, ~(﹁), ⊕, ⊙) and parentheses   
   
<br />
### Conditional Proposition (→)   
// 조건명제 (→)   
   
// 명제 p와 q가 있을 때, 명제 p가 조건의 역할을 수행하고 명제 q가 결론의 역할을 수행하는 경우   
- In the presence of propositions p and q, if the proposition p serves as a condition and the proposition q serves as a conclusion   
   
// p → q (p ⇒ q)   
// - p는 q의 충분조건   
// - q는 p의 필요조건   
- p → q (p ⇒ q)   
  - p is a sufficient condition of q   
  - q is the necessity condition of p   
   
Truth Table   
// 진리표   
   
|p|q|p → q|
|:---:|:---:|:---:|
|T|T|T|
|T|F|F|
|F|T|T|
|F|F|T|
   
// 예시   
// 1. 다음의 명제에 대하여 조건명제의 진리값을 구하시오.   
// ① 1 + 2 = 3 이면, 10 - 2 = 8 이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; 1 + 2 = 3 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; 10 - 2 = 8 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ T   
// ② 1 + 2 = 3 이면, 10 - 2 = 7 이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; 1 + 2 = 3 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; 10 - 2 = 7 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ F   
// ③ 프랑스의 수도가 런던이라면, 이탈리아의 수도는 로마이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; 프랑스의 수도가 런던이라면 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp;  이탈리아의 수도는 로마이다 --> ∴ T   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ T   
// ④ 프랑스의 수도가 런던이라면, 한국의 수도는 콜롬보이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; 프랑스의 수도가 런던이라면 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp;  한국의 수도는 콜롬보이다 --> ∴ F   
// &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ T   
- Example   
  1. Find the truth value of the conditional proposition for the following statement.   
    ① If 1 + 2 = 3, then 10 - 2 = 8.   
      &nbsp;&nbsp;&nbsp;&nbsp; 1 + 2 = 3 --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; 10 - 2 = 8 --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ T   
    ② If 1 + 2 = 3, then 10 - 2 = 7.   
      &nbsp;&nbsp;&nbsp;&nbsp; 1 + 2 = 3 --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; 10 - 2 = 7 --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ F   
    ③ If the capital of France is London, the capital of Italy is Rome.   
      &nbsp;&nbsp;&nbsp;&nbsp; If the capital of France is London --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; The capital of Italy is Rome --> ∴ T   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ T   
    ④ If the capital of France is London, the capital of Korea is Colombo.   
      &nbsp;&nbsp;&nbsp;&nbsp; If the capital of France is London --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; The capital of Korea is Colombo --> ∴ F   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p → q --> ∴ T   
   
<br />
### Conditional Proposition (↔)   
// 쌍조건명제 (↔)   
   
// 명제 p와 q가 있을 때, 명제 p와 q가 조건의 역할과 결론의 역할을 동시에 수행하는 경우   
- In the presence of propositions p and q, if the propositions p and q play both the role of conditions and the role of conclusions   
   
- p ↔ q (p ⇔ q)   
  - (p → q) ∧ (q → p)   
   
Truth Table   
// 진리표   
   
|p|q|p → q|q → p|p ↔ q|
|:---:|:---:|:---:|:---:|:---:|
|T|T|T|T|T|
|T|F|F|T|F|
|F|T|T|F|F|
|F|F|T|T|T|
   
- p ↔ q ≡ ~(p ⊕ q)   
   
Truth Table   
// 진리표   
   
|p ↔ q|(p ⊕ q)|~(p ⊕ q)|
|:---:|:---:|:---:|
|T|F|T|
|F|T|F|
|F|T|F|
|T|F|T|
   
// 예시   
// 1. 다음의 쌍조건명제는 참인가?   
// ① 사람이 살아있다 ↔ 사람이 호흡을 한다   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T ↔ T   
// ② 1 + 2 = 9 ↔ 1 × 2 = 9   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T ↔ T   
- Example   
  1. Is the following conditional proposition true?   
    ① A man is alive ↔ A man breathes   
      &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T ↔ T   
    ② 1 + 2 = 9 ↔ 1 × 2 = 9   
      &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T ↔ T   
   
<br />
### Logical Equivalence (≡)   
// 논리적 동치 (≡)   
   
// 두 명제 p와 q가 논리적으로 동등하면 논리적 동치라고 하고, p ≡ q로 표시함   
// - 논리적으로 동등하다는 말은 두 명제가 항상 동일한 진리값을 가진다는 의미   
- If two propositions p and q are logically equivalent, we call them logical equivalents, and we denote them with 'p ≡ q'   
  - Logically equivalent means that two propositions always have the same truth value   
   
- p ≡ q (== p ↔ q, p ⇔ q)   
   
#### Converse, Inverse, Contraposition   
// 역, 이, 대우   
   
// 조건명제 p → q   
// - 역 : q → p   
// - 이 : ~p → ~q   
// - 대우 : ~q → ~p   
- Conditional Proposition p → q   
  - Converse : q → p   
  - Inverse : ~p → ~q   
  - Contraposition : ~q → ~p   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/DiscreteMathematicsEquivalence.png)
   
// 예시   
// 1. 다음 두 명제가 서로 논리적 동치관계임을 보이시오.   
// ① p ∨ (q ∧ r)   
// ② (p ∨ q) ∧ (p ∨ r)   
// &nbsp;&nbsp;&nbsp;&nbsp; 증명은 진리표를 작성함으로써 가능함   
// &nbsp;&nbsp;&nbsp;&nbsp; (※ 분배법칙)   
- Example   
  1. Show that the following two propositions are logically equivalent to each other.   
    ① p ∨ (q ∧ r)   
      &nbsp;&nbsp;&nbsp;&nbsp; --> p ∨ (q ∧ r) ⇔ (p ∨ q) ∧ (q ∧ r)   
    ② (p ∨ q) ∧ (p ∨ r)   
      &nbsp;&nbsp;&nbsp;&nbsp; Proof is possible by drawing up a truth table   
      &nbsp;&nbsp;&nbsp;&nbsp; (※ Distributive law)   
   
Truth Table   
// 진리표   
   
|p|q|r|q ∧ r|p ∨ (q ∧ r)|p ∨ q|p ∨ r|(p ∨ q) ∧ (p ∨ r)|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|T|T|T|T|T|T|T|T|
|T|T|F|F|T|T|T|T|
|T|F|T|F|T|T|T|T|
|T|F|F|F|T|T|T|T|
|F|T|T|T|T|T|T|T|
|F|T|F|F|F|T|F|F|
|F|F|T|F|F|F|T|F|
|F|F|F|F|F|F|F|F|
   
#### The law of Logical Equivalence   
// 논리적 동치법칙   
   
// 교환법칙   
1 . Commutative law   
- p ∨ q ≡ q ∨ p   
- p ∧ q ≡ q ∧ p   
- p ↔ q ≡ q ↔ p   
   
// 결합법칙   
2 . Associative law   
- (p ∨ q) ∨ r ≡ p ∨ (q ∨ r)   
- (p ∧ q) ∧ r ≡ p ∧ (q ∧ r)   
   
// 분배법칙   
3 . Distributive law   
- p ∨ (q ∧ r) ≡ (p ∨ q) ∧ (p ∨ r)   
- p ∧ (q ∨ r) ≡ (p ∧ q) ∨ (p ∧ r)   
   
// 항등법칙   
4 . Identity law   
- p ∨ F ≡ p   
- p ∧ T ≡ p   
   
|p|p ∨ F|
|:---:|:---:|
|T|T|
|F|F|
   
// 지배법칙   
5 . Domination law   
- p ∨ T ≡ T   
- p ∧ F ≡ F   
   
// 부정법칙   
6 . Negation law   
- ~T ≡ F   
- ~F ≡ T   
- p ∨ (~p) ≡ T   
- p ∧ (~p) ≡ F   
   
// 이중 부정 법칙   
7 . Double negation law   
- ~(~p) ≡ p   
   
// 멱등법칙 : 몇번을 연산하든 p의 값이 진리값임   
8 . Idempotent law : No matter how many operations are repeated, the value of p is the truth value   
- p ∨ p ≡ p   
- p ∧ p ≡ p   
   
// 드 모르간 법칙   
9 . De Morgan's law   
- ~(p ∨ q) ≡ (~p) ∧ (~q) ⇔ (A∪B) ⷭ = A ⷭ∩B ⷭ   
- ~(p ∧ q) ≡ (~p) ∨ (~q) ⇔ (A∩B) ⷭ = A ⷭ∪B ⷭ   
   
// 흡수법칙   
10 . Absorption law   
- p ∨ (p ∧ q) ≡ p   
- p ∧ (p ∨ q) ≡ p   
   
|p|q|p ∧ q|p ∨ (p ∧ q)|
|:---:|:---:|:---:|:---:|
|T|T|T|T|
|T|F|F|T|
|F|T|F|F|
|F|F|F|F|
   
|p|q|p ∨ q|p ∧ (p ∨ q)|
|:---:|:---:|:---:|:---:|
|T|T|T|T|
|T|F|T|T|
|F|T|T|F|
|F|F|F|F|
   
// 함축법칙   
11 . Implication law   
- p → q ≡ ~p ∨ q   
   
|p|q|p → q|~p|~p ∨ q|
|:---:|:---:|:---:|:---:|:---:|
|T|T|T|F|T|
|T|F|F|F|F|
|F|T|T|T|T|
|F|F|T|T|T|
   
// 대우법칙   
12 . Contraposition law   
- p → q ≡ ~q → ~p   
   
|p|q|p → q|~q|~p|~q → ~p|
|:---:|:---:|:---:|:---:|:---:|:---:|
|T|T|T|F|F|T|
|T|F|F|T|F|F|
|F|T|T|F|T|T|
|F|F|T|T|T|T|
   
// 예시   
// 1. 드 모르간 법칙을 사용해 다음 식의 부정을 나타내시오.   
// -2 < x < 3   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ~(-2 < x < 3)   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ~((-2 < x) ∧ (x < 3))   
// &nbsp;&nbsp;&nbsp;&nbsp; --> (~(-2 < x)) ∨ (~(x < 3))   
// &nbsp;&nbsp;&nbsp;&nbsp; --> (-2 ≥ x) ∨ (x ≥ 3)   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ (x ≤ -2) ∨ (x ≥ 3)   
- Example   
  1. Use DeMorgan's law to express the negation of the following expression.   
    -2 < x < 3   
      &nbsp;&nbsp;&nbsp;&nbsp; --> ~(-2 < x < 3)   
      &nbsp;&nbsp;&nbsp;&nbsp; --> ~((-2 < x) ∧ (x < 3))   
      &nbsp;&nbsp;&nbsp;&nbsp; --> (~(-2 < x)) ∨ (~(x < 3))   
      &nbsp;&nbsp;&nbsp;&nbsp; --> (-2 ≥ x) ∨ (x ≥ 3)   
      &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ (x ≤ -2) ∨ (x ≥ 3)   
   
<br />
### Tautology Proposition, Contradiction Proposition   
// 항진명제, 모순명제   
   
// 합성명제를 구성하는 명제의 진리값과 상관없이   
// 1. 항상 참 (T) 인 명제를 항진명제라고 함   
// - p ∨ T   
// 2. 항상 거짓 (F) 인 명제를 모순명제라고 함   
// - p ∧ F   
- Regardless of the truth value of the proposition that makes up the compound proposition   
  1. A proposition that is always true (T) is called an tautology proposition   
      - p ∨ T   
  2. A proposition that is always false (F) is called a contradiction proposition   
      - p ∧ F   
   
<br />
### Predicate Logic   
// 술어논리   
   
#### Predicate Logic and Propositional Function   
// 술어논리와 명제함수   
   
#### Propositional Function   
// 명제함수   
   
// 변수의 값에 의해 함수의 진리값이 결정되는 문장이나 식   
- A sentence or expression in which the truth value of a function is determined by the value of a variable   
   
// 변수의 명세   
// - 변수의 값을 적시   
// - 변수의 범위를 제시 (한정화 : ∀, ∃)   
- Specification of variables   
  - Specify the value of the variable   
  - Present the range of variables (Quantification : ∀, ∃)   
   
// 예시   
// 1. 명제함수 p(x, y) 가 x² + y² = 4 일 때 p(1, 2) 의 진리값은?   
// &nbsp;&nbsp;&nbsp;&nbsp; --> 1² + 2² = 5 --> != 4 --> ∴ F   
- Example   
  1. What is the truth value of p(1, 2) when the propositional function p(x, y) is x² + y² = 4?   
    &nbsp;&nbsp;&nbsp;&nbsp; --> 1² + 2² = 5 --> != 4 --> ∴ F   
   
<br />
### Quantification   
// 한정화   
   
#### Universal Quantifier (∀)   
// 전체한정자 (∀. 임의의)   
   
// 전체한정자는 "모든" 또는 "임의의"를 의미하며, 명제함수 ∀xP(x) 와 같이 사용되었을 경우에는 정의역의 모든 [임의의] x에 대해서 P(x) 가 참 (T) 임을 의미함   
- An entire quantifier means "all" or "any" and, when used in conjunction with the propositional function ∀xP(x), means that P(x) is true (T) for every [any] x in the domain   
   
// '∀x' 는 '임의의 x' 라는 의미   
- '∀x' means 'anything x'   
   
// 예시   
// 1. P(x) 가 "x는 실수이다"이고, x의 정의역이 양수일 경우 ∀xP(x) 는 참이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; --> 양의 실수값은 항상 실수임   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ ∀xP(x) = T   
// 2. P(x) 가 x² + x - 2 > 0 이고, x의 정의역이 실수일 경우 ∀xP(x) 는 거짓이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; --> x² + x - 2 = (x - 1)(x + 2) = 0   
// &nbsp;&nbsp;&nbsp;&nbsp; --> -2 ≤ x ≤ 1 일 때 x² + x - 2 ≤ 0   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ ∀xP(x) = F   
- Example   
  1. If P(x) is "x is real number" and the domain of x is positive, then ∀xP(x) is true.   
    &nbsp;&nbsp;&nbsp;&nbsp; --> Positive real numbers are always real numbers   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ ∀xP(x) = T   
  2. If P(x) is x² + x - 2 > 0, and the domain of x is real number, the ∀xP(x) is false.   
    &nbsp;&nbsp;&nbsp;&nbsp; --> x² + x - 2 = (x - 1)(x + 2) = 0   
    &nbsp;&nbsp;&nbsp;&nbsp; --> If -2 ≤ x ≤ 1, then x² + x -2 ≤ 0   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ ∀xP(x) = F   
   
#### Existential Quantifier (∃)   
// 존재한정자 (∃. 존재한다)   
   
// 존재한정자는 "존재한다"를 의미하며, 명제함수 ∃xP(x) 와 같이 사용되었을 때는 정의역의 어떤 x에 대해서 P(x) 가 참 (T) 임을 의미함   
- An existential quantifier means "exist", and when used with the propositional function ∃xP(x), P(x) means true (T) for any x in the domain   
   
// P(x) 를 참으로 만들어주는 어떤 x가 정의역 안에 하나라도 존재하면 참임   
- There exists some x such that P(x) is true   
   
// 예시   
// 1. P(x) 가 "x는 무리수이다"이고, x의 정의역이 유리수일 경우 ∃xP(x) 는 거짓이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; --> 유리수이면서 무리수인 수는 없음   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ ∃xP(x) = F   
- Example   
  1. If P(x) is "x is irrational number" and the domain of x is rational number, then ∃xP(x) is false.   
    &nbsp;&nbsp;&nbsp;&nbsp; --> A number cannot be rational number and irrational number at the same time   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ ∃xP(x) = F   
   
<br />
### A feasibility test   
// 타당성 검사   
   
#### The validity of a propositional function   
// 명제함수의 타당성   
   
// 벤 다이어그램   
// - 한정자가 사용된 명제함수의 타당성을 직관적으로 검사함   
- Venn Diagram   
  - Venn Diagram intuitively check the validity of the propositional functions used by the quantifier   
   
// 예시   
// 1. 모든 평행사변형은 사각형이다.   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T   
// 2. 삼단논법   
// &nbsp;&nbsp;&nbsp;&nbsp; ① 영희는 서울에 있다   
// &nbsp;&nbsp;&nbsp;&nbsp; ② 서울은 한국에 있다   
// &nbsp;&nbsp;&nbsp;&nbsp; ③ 영희는 한국에 있다   
// &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T   
- Example   
  1. Every parallelogram is a square.   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T   
  2. syllogism   
    ① Young-hee is in Seoul   
    ② Seoul is in Korea   
    ③ Young-hee is in Korea   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T   
   
<br />
### Inference   
// 추론   
   
// 참으로 알려진 명제를 기초로 하여 다른 명제를 유도해 내는 과정을 추론이라고 함   
// - 결론의 근거를 제공하는 알려진 명제를 전제 (premise) 라고 함   
// - 새로 유도된 명제는 결론 (conclusion) 임   
- The process of deriving another proposition based on a proposition known as true is called inference   
  - Known propositions that provide the basis for conclusions are referred to as premises   
  - The newly derived proposition is a conclusion   
   
#### Valid Inference  
// 유효추론   
   
// 전제가 참 (T) 이라고 가정하였을 때 결론이 항상 참 (T) 이 되는 추론   
- Reasoning that the conclusion is always true (T) assuming that the premise is true (T)   
   
- Example   
  1. ((p → q) ∧ (q → r)) → (p → r)   
    &nbsp;&nbsp;&nbsp;&nbsp; --> ∴ T   
    &nbsp;&nbsp;&nbsp;&nbsp; --> Syllogism   
   
#### Rule of Inference   
// 추론규칙   
   
// 기본적인 추론규칙은 논리적 동치 (항진명제) 를 이용함   
- The basic rules of inference use logical equivalence (tautology proposition)   
   
|// 법칙이름<br />Rule name|// 추론법칙<br />Rule of inference|// 항진명제<br />Tautology proposition|
|:---|:---|:---|
|// 선언적 부가<br />Disjunctive addition|p<br />--> ∴ p ∨ q|p → (p ∨ q)<br />※ If p is true, p ∨ q is true|
|// 단순화<br />Simplication|p ∧ q<br />--> ∴ p|(p ∧ q) → p<br />※ If p ∧ q is true, p is true|
|// 긍정논법<br />Modus ponens|p<br />p → q<br />--> ∴ q|(p ∧ (p → q)) → q<br />※ If p and p → q is true, q is true|
|// 부정논법<br />Modus tollens|~q<br />p → q<br />--> ∴ ~p|(~q ∧ (p → q)) → ~p<br />※ If ~q and p → q is true, ~p is true|
|// 선언적 삼단논법 또는 소거<br />Disjunctive syllogism|p ∨ q<br />~p<br />--> ∴ q|((p ∨ q) ∧ ~p) → q<br />※ If p ∨ q and ~p is true, q is true|
|// 가설적 삼단논법 또는 추이<br />Hypothetical syllogism|p → q<br />q → r<br />--> ∴ p → r<br />--> ∴ q|((p → q) ∧ (q → r)) → (p → r)<br />※ If p → q and q → r is true, p → r is true|
   
// 예시   
// 1. 다음 추론이 유효한 추론인지 진리표를 이용하여 보이시오.   
// &nbsp;&nbsp;&nbsp;&nbsp; p → q --> T   
// &nbsp;&nbsp;&nbsp;&nbsp; q --> T   
// &nbsp;&nbsp;&nbsp;&nbsp; ∴ p ? --> T, F --> F   
- Example   
  1. Use the truth table to see if the following inference is valid inference.   
    &nbsp;&nbsp;&nbsp;&nbsp; p → q --> T   
    &nbsp;&nbsp;&nbsp;&nbsp; q --> T   
    &nbsp;&nbsp;&nbsp;&nbsp; ∴ p ? --> T, F --> F   
   
|// 결론<br />Conclusion|// 전제<br />Premise|// 전제<br />Premise|
|:---:|:---:|:---:|
|p|q|p → q|
|T|T|T|
|T|F|F|
|F|T|T|
|F|F|T|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
