---
layout: post
title:  "Programming Language Theory: Programming Language Paradigm"
date:   2024-05-03 09:00:00 +0900
categories: [Programming Language Theory]
---

### What is a paradigm?   
// 패러다임이란 무엇인가?   
   
// 한 시대의 견해나 사고를 규정하는 양식, 규범, 체계 등을 통칭하는 말   
// 토머스 새뮤얼 쿤 (Thomas Samuel Kuhn) 은 과학 분야의 발전에 따라 이전의 믿음과 체계가 흔들리고 새로운 체계로 대체되는 과정에 주목   
// 패러다임 전환   
// - 천동설 → 지동설   
// - 저축이 미덕 → 소비가 미덕   
- A term collectively referred to as a style, norm, system, etc. that defines the views or thoughts of an era   
- Thomas Samuel Kuhn noted the process by which previous beliefs and systems falter and are replaced by new systems as the scientific field develops   
- A paradigm shift   
  - Geocentrism → Heliocentrism   
  - Saving is a virtue → Consumption is a virtue   
   
<br />
### Programming Paradigm   
// 프로그래밍 패러다임   
   
// 프로그램을 작성하는 전형적인 방식   
// 특정 언어에 종속적인 것이 아닌 프로그래머가 추구하는 프로그램 작성 방식   
- A typical way of coding a program   
- The method of writing a program that is not dependent on a particular language and is pursued by a programmer   
   
#### A shift in the programming paradigm   
// 프로그래밍 패러다임의 변화   
   
// 주어진 데이터에 어떤 연산을 어떤 순서로 할지 결정하는 것이 중요   
// - 명령형 프로그래밍 패러다임 등장   
// 복잡한 데이터 처리를 위해 데이터 처리 방식 자체를 잘 정리하는 것이 중요   
// - 절차형 프로그래밍 패러다임 등장   
// 데이터가 저장된 메모리를 관리하는 것이 어려운 문제로 대두   
// - 함수형 프로그래밍 패러다임 등장   
// 계산 절차를 문제의 조건을 명시하는 규칙으로 생각   
// - 논리 프로그래밍 패러다임 등장   
// - 선언적 프로그래밍 패러다임의 한 종류   
// 같은 데이터에 대해 다른 처리 절차를 여러 개 명시해야 하는 경우가 흔히 발생   
// - 객체지향 프로그래밍 패러다임 등장   
- It's important to decide in which order to perform the operations on the given data   
  - Emergence of the command-type programming paradigm   
- It's important to organize the data processing method itself for complex data processing   
  - Emergence of the procedural programming paradigm   
- Managing the memory where the data is stored has become a challenge   
  - Emergence of the Functional Programming Paradigm   
- Think of the calculation procedure as a rule specifying the conditions in question   
  - Emergence of the logical programming paradigm   
  - A type of declarative programming paradigm   
- It is often necessary to specify multiple different processing procedures for the same data   
  - Emergence of the Object-oriented Programming Paradigm   
   
#### Background of programming paradigm shift   
// 프로그래밍 패러다임 변화의 배경   
   
// 응용 도메인의 변화   
// - 요구사항의 변화   
// - 계산 분야 → 다양한 응용 분야   
// 프로그램 구성 방식의 변화   
// - 명령어 나열 → 존재하는 모듈의 조합   
// 계산 모델의 변화   
// - 튜링기계 모델 → 새로운 방식의 계산 모델   
- Change of application domain   
  - Changes in requirements   
  - Calculations → Various Applications   
- A change in the way a program is organized   
  - List Commands → Combination of existing modules   
- A change in the computational model   
  - Turing machine model → a new computational model   
   
<br />
### Programming Language Paradigm   
// 프로그래밍 언어 패러다임   
   
#### Programming Paradigm VS Programming Language Paradigm   
// 프로그래밍 패러다임 VS 프로그래밍 언어 패러다임   
   
// 프로그래밍 패러다임   
// - 프로그램을 작성하는 방식이나 스타일   
// 프로그래밍 언어 패러다임   
// - 해당 프로그래밍 언어가 지원하는 프로그래밍 패러다임   
// - 일반적으로 프로그래밍 언어는 여러 프로그래밍 패러다임을 지원   
- Programming Paradigm   
  - The way or style of coding a program   
- Programming Language Paradigm   
  - Programming paradigm supported by that programming language   
  - In general, programming languages support multiple programming paradigms   
   
#### Programming Paradigm of Major Languages   
// 주요 언어의 프로그래밍 패러다임   
   
|Paradigm/Language|Command-type type|Procedural type|Functional type|Logic type|Object orientation type|
|:---:|:---:|:---:|:---:|:---:|:---:|
|BASIC|○|○||||
|C|○|○||||
|C++|○|○|○||○|
|Haskell|○||○||○|
|Java|○|○|○||○|
|JavaScript|○|○|○||○|
|LISP||○|○|||
|Prolog||○||○||
|Python|○|○|○||○|
|Smalltalk|○|○|||○|
|Visual Basic|○|○|||○|
   
#### Compatibility of the Programming Paradigm   
// 프로그래밍 패러다임의 양립성   
   
// 다양한 프로그래밍 패러다임은 서로 양립할 수 있음   
// 새로운 패러다임의 등장으로 이전에 있던 패러다임이 더욱 공고히 완성   
// 주류 프로그래밍 패러다임이 바뀜에 따라 이를 언어가 수용하는 형태로 변화   
// 예시 : Python   
// - 명령형 패러다임, 절차형 패러다임 지원 → 함수형 패러다임, 객체지향 패러다임을 포함   
- Different programming paradigms are compatible with each other   
- With the advent of a new paradigm, the previous paradigm is more solidified   
- As major programming paradigms change, they change into a form that languages accept   
- Example : Python   
  - Command-type paradigm, Procedural paradigm support → Functional paradigm, Object-oriented paradigm included   
   
<br />
### Example of programs of different kinds of paradigms   
// 여러 패러다임의 프로그램 예시   
   
#### Command-type programming   
// 명령형 프로그래밍   
   
// 프로그램   
// - 일련의 명령어 나열   
// 장점   
// - 프로그램을 쉽게 이해할 수 있음   
// 단점   
// - 프로그램이 복잡한 경우 효과적으로 다루지 못함   
- Program   
  - List a set of commands   
- Strength   
  - Easy to understand programs   
- Weakness   
  - If the program is complicated, it will not be handled effectively   
   
// BASIC 언어로 만들어진 프로그램 : 유클리드 알고리즘을 BASIC으로 표현하여 최대공약수를 구하는 예시   
- A program created in the BASIC language : Example of finding the maximum common divisor by representing the Euclidean algorithm in BASIC   
   
```basic
10 HOME
20 INPUT "Enter A: ";A : INPUT "Enter B: ";B
30 IF A < B THEN C = A : A = B : B = C
40 REM C = A MOD B (A modulo B)
50 LET C = A - INT(A/B)*B
60 LET A = B : B = C
70 IF B > 0 GOTO 40
80 PRINT "GCD is ";A
90 END
```
   
- Result   
   
```
Enter A: 126 [Enter]
Enter B: 312 [Enter]
GCD is 6
```
   
#### Procedural programming   
// 절차형 프로그래밍   
   
// 프로그램   
// - 서브루틴이라는 절차의 집합   
// 장점   
// - 재귀호출을 사용하여 프로시저를 간단하게 정의   
- Program   
  - Set of subroutine procedures   
- Strength   
  - Simply define the procedure using recursive calls   
   
// Algol 언어로 만들어진 프로그램 : 유클리드 알고리즘을 Algol로 표현하여 최대공약수를 구하는 예시   
- A program created in the Algol language : Example of finding the maximum common divisor by representing the Euclidean algorithm in Algol   
   
```algol
PROC gcd = (INT a, b) INT: (
    IF b = 0 THEN
        a
    ELSE
        gcd(b, a MOD b)
    FI
);
main:(
    INT a = 126, b = 312;
    printf(($x"The gcd of"g" and "g" is "gl$,a,b,gcd(a,b)))
)
```
   
- Result   
   
```
The gcd of +126 and +312 is +6
```
   
#### Structured programming   
// 구조화 프로그래밍   
   
// goto 없이 프로그램을 작성하는 방법   
// 블록과 서브루틴을 이용   
// 구조화된 제어문을 이용 (중첩된 제어문)   
- How to coding a program without goto   
- Use blocks and subroutines   
- Use structured control statements (overlapped control statements)   
   
// C 언어로 만들어진 프로그램 : 유클리드 알고리즘을 C로 표현하여 최대공약수를 구하는 예시   
- A program created in the C language : Example of finding the maximum common divisor by representing the Euclidean algorithm in C   
   
```c
#include <stdio.h>

int main() {
    int a, b, c;

    printf("Enter a and b: ");
    scanf("%d %d", &a, &b);
    do {
        c = a % b;
        a = b;
        b = c;
    } while (b > 0);
    printf("gcd: %d\n", a);

    return 0;
}
```
   
- Result   
   
```
Enter a and b: 126 312 [Enter]
gcd: 6
```
   
#### Object-oriented programming   
// 객체지향 프로그래밍   
   
// 프로그램   
// - 서로 통신할 수 있는 객체 (object) 의 집합   
// GUI 개발에 큰 획 (Smalltalk)   
// 프로그램 재사용 편의로 S/W 생산성에 크게 기여   
- Program   
  - A set of object that can communicate with each other   
- A big stroke in GUI development (Smalltalk)   
- Program reuse convenience contributes significantly to S/W productivity   
   
// 객체의 개념   
// - 상태를 유지하며 외부의 요청에 반응하는 데이터   
// - 상태 - 필드 (멤버 변수), 반응 - 메소드 (멤버 함수)   
// - 상태는 외부에 숨기고 메소드는 외부에 공개   
- The concept of an object   
  - Data that remains in state and responds to external requests   
  - Status - Field (member variable), Response - Method (member function)   
  - Hiding the status and revealing the method to the outside   
   
// Smalltalk 언어로 만들어진 프로그램 : 유클리드 알고리즘을 Smalltalk으로 표현하여 최대공약수를 구하는 예시   
- A program created in the Smalltalk language : Example of finding the maximum common divisor by representing the Euclidean algorithm in Smalltalk   
   
```smalltalk
igcd := [ :a :b |
    |u v|
        u := a. v := b.
        [ v > 0 ]
            whileTrue: [ |t|
                t := u.
                u := v.
                v := t rem: v
        ].
    u abs
].

(igcd value: 126 value: 312) printN1.
```
   
- Result   
   
```
6
```
   
#### Functional programming   
// 함수형 프로그래밍   
   
// 데이터는 값으로, 명령어는 함수로 취급   
// - 명령어가 데이터를 바꿀 수 없음   
// 대입문과 반복문 없음   
// 함수 자체도 값으로 취급 가능   
- Treat data as values and commands as functions   
  - Command cannot change data   
- No substitution statement and iteration statement   
- Functions themselves can also be treated as values   
   
// Haskell 언어로 만들어진 프로그램 : 유클리드 알고리즘을 Haskell으로 표현하여 최대공약수를 구하는 예시   
- A program created in the Haskell language : Example of finding the maximum common divisor by representing the Euclidean algorithm in Haskell   
   
```haskell
module Main (main) where

main :: IO ()
main = putStrLn (show (igcd 126 312))

igcd a 0 = abs a
igcd a b = igcd (abs b) (a `mod` (abs b))
```
   
- Result   
   
```
6
```
   
#### Declarative programming and logical language   
// 선언적 프로그래밍과 논리 언어   
   
// 프로그램   
// - 논리식 집합   
// 논리식은 명제나 술어로 나타냄   
// - 술어는 인수를 받을 수 있음   
- Program   
  - Logical set   
- A logical expression is represented by a proposition or predicate   
  - Predicate can take argument   
   
// Prolog 언어로 만들어진 프로그램 : 강아지가 안전하다면 애완견이라고 정의하고, 해당 정의를 이용해 X가 어떤건지 찾는 예시   
- A program created in the Prolog language : If a dog is safe, define it as a pet dog, and use that definition to find out what X is   
   
```prolog
puppy(happy).
safe(happy).
pet(X) :- puppy(X), safe(X).
```
   
- Result   
   
```
?- pet(X).
X = happy.
```
   
// Prolog 언어로 만들어진 프로그램 : 유클리드 알고리즘을 Prolog로 표현하여 최대공약수를 구하는 예시   
- A program created in the Prolog language : Example of finding the maximum common divisor by representing the Euclidean algorithm in Prolog   
   
```prolog
gcd(U, 0, U).
gcd(U, V, X) :- V > 0, Y is U mod V, gcd(V, Y, X).
```
   
- Result   
   
```
?- gcd(126, 312, X).
X = 6
```
   
<br />
### Characteristics of the Programming Paradigm   
// 프로그래밍 패러다임의 특징   
   
// 객체지향 패러다임   
// - 객체 사이의 통신을 통해 계산을 표현   
// 함수형 패러다임   
// - 함수의 적용을 통해 계산을 표현   
// 논리 패러다임   
// - 논리식의 진위를 증명하는 과정을 통해 계산을 표현   
- Object-oriented paradigm   
  - Express computation through communication between objects   
- Functional paradigm   
  - Expression of computation through application of functions   
- Logical paradigm   
  - Express calculation through the process of proving the authenticity of a logical expression   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
