---
layout: post
title:  "Programming Language Theory: Introduction"
date:   2024-03-29 09:00:00 +0900
categories: [Programming Language Theory]
---

### What is a programming language?   
// 프로그래밍 언어란 무엇인가?   
   
#### Definition of programming language   
// 프로그래밍 언어의 정의   
   
// 언어란 무엇인가?   
// - 의사 전달 수단   
// - 한 사람의 생각을 다른 사람에게 전달하는데 사용   
// - 자연어는 크게 말과 글, 두 가지 형태로 존재   
// - 하지만 사람도 고려해야 함   
- What is language?   
  - a means of communication   
  - Use to communicate one's thoughts to others   
  - Natural language exists in two main forms : speech and writing   
  - But people should also be considered   
   
// 프로그래밍 언어란 무엇인가?   
// - 프로그램 작성에 사용되는 언어   
// - 역시 의사 전달 수단   
// - 주로 사람의 생각을 기계에 전달하는데 사용   
// - 하지만 사람도 고려해야 함   
- What is a programming language?   
  - Language used to write programs   
  - As expected, a means of communication   
  - Mainly used to communicate people's thoughts to machines   
  - But people should also be considered   
   
// 프로그램 : 컴퓨터가 수행할 명령어를 순서대로 나열해 둔 것   
- Program : a sequential list of instructions to be executed by a computer   
   
// 프로그래밍 언어의 정의   
// - 프로그래밍 언어는 컴퓨터가 수행할 수 있고 사람이 읽을 수 있는 형태로 계산을 나타내는 표기 체계임   
- Definition of programming language   
  - A programming language is a notation system that represents computation in a computer-executable and human-readable form   
   
#### Characteristics of Programming Language   
// 프로그래밍 언어의 특징   
   
||// 자연어<br />Natural language|// 프로그래밍 언어<br />programming language|
|:---:|:---:|:---:|
|// 형식<br />Type|// 말과 글<br />speech and writing|// 주로 글<br />Mainly writing|
|// 내용<br />content|// 모호, 함축<br />ambiguity, connotation|// 엄밀한 규칙, 정확한 의도<br />strict rules, precise intentions|
|// 방향성<br />directionality|// 양방향<br />two-way|// 단방향<br />one-way|
   
#### Why should I learn a programming language   
// 프로그래밍 언어를 배워야 하는 이유   
   
// 프로그래밍에 대한 사고 능력을 확장시켜 줌   
// 문제 해결자로서 현명하게 언어를 선택할 수 있도록 해 줌   
// 언어 사용자로서 언어를 자세히 배울 수 있도록 해줌   
// 현명한 관리자, 현명한 설계자가 될 수 있도록 함   
// 체계적으로 생각하는 방법을 가르쳐 줌   
// 변화를 표현하는 방법을 가르쳐 줌   
- Expanding your thinking skills for programming   
- Allowing you to choose your language wisely as a problem solver   
- As a language user, it allows you to learn the language in detail   
- Be a Smart Manager, Smart Architect   
- It teaches you how to think systematically   
- It teaches you how to express change   
   
<br />
### Function of programming languages   
// 프로그래밍 언어의 기능   
   
#### Basic functions of programming languages   
// 프로그래밍 언어의 기본 기능   
   
// 작성력 : 프로그래머의 의도를 나타낼 수 있도록 하는 기능   
// 가독성 : 프로그램을 쉽게 해독할 수 있도록 하는 기능   
// 실행 가능성 : 컴퓨터에서 실행될 수 있도록 하는 기능   
- Creativity : Ability to express the programmer's intentions   
- Readability : the ability to easily decode a program   
- viability : the ability to run on a computer   
   
#### Additional functions of programming languages   
// 프로그래밍 언어의 부가 기능   
   
// 추상화 : 어떤 대상을 간략하게 추려 나타내는 방법   
// 모듈화 : 복잡한 대상을 나누어 구성할 수 있는 방법   
- Abstract : A brief summary of an object   
- Modularization : How complex object can be divided up   
   
#### Characteristics of Programming Languages   
// 프로그래밍 언어의 특성   
   
// 기계적 : 기계적으로 처리할 수 있어야 함   
// - 엄밀한 규칙에 따라 정의   
// 구조적 : 복잡한 구조를 나타낼 수 있어야 함   
// - 자료 구조, 제어 구조   
// 가변적 : 시대의 필요에 따라 바뀔 수 있음   
// - Python : 명령어 언어 → 객체지향 개념 탑재   
- Mechanical : Must be able to handle mechanically   
  - Definition according to strict rules   
- Structural : Must be able to represent complex structures   
  - data structure, control structure   
- Variable : May change according to the needs of the times   
  - Python : Command language → Object-oriented concept   
   
#### Programming language spectrum   
// 프로그래밍 언어 스펙트럼   
   
// 저급 언어   
// - 기계에 종속적인 언어   
// - 기계어, 어셈블리어   
- a low-level language   
  - machine-dependent language   
  - machine language, assembly   
   
// 고급 언어   
// - 기계 독립적으로 정의되고 실행될 수 있는 언어   
// - C, Java, Python 등   
- a high-level language   
  - Language that can be machine-independent defined and executed   
  - C, Java, Python, etc.   
   
<br />
### Components of a programming language   
// 프로그래밍 언어의 구성 요소   
   
#### data   
// 데이터   
   
// 자료를 프로그램이 처리할 수 있는 형태로 나타낸 것   
// 수, 문자, 문자열, 멀티미디어 등   
- Representation of data in a form that can be processed by a program   
- Numbers, characters, strings, multimedia, etc.   
   
// 데이터의 분류   
// - 이진 데이터 : 이진수의 나열로 이루어진 데이터   
// - 텍스트 데이터 : 문자열을 나타내는 데이터   
- Classification of data   
  - Binary data : data consisting of a binary list   
  - text data : data representing a string   
   
#### operation   
// 연산   
   
// 데이터 처리 방법   
// 연산 적용 후 새로운 데이터를 결과로 얻음   
- How to process data   
- Obtain new data as a result after application of the operation   
   
// 용어 정의   
// - 연산자 : 특별한 연산을 수행하는 함수   
// - 변수 : 연산 결과를 저장하는 이름   
- Terminology definition   
  - Operator : a function that performs a special operation   
  - Variables : Name that stores the operation results   
   
// 연산 표현 구조   
// - 수식 : 값을 나타내는 표현   
// - 문장 : 처리를 나타내는 표현   
- operational representation structure   
  - numeric expression : an expression that represents a value   
  - statement : Expressions representing processing   
   
#### command   
// 명령어   
   
// 특정 작업을 지시하는 단어   
// if, while 등   
- a word that directs a particular task   
- if, while, etc.   
   
#### Operations and commands   
// 연산 및 명령어   
   
// 대부분의 프로그래밍 언어는 다양한 연산자와 명령어를 통해 수식과 문장을 구성   
- Most programming languages use a variety of operators and commands to construct numeric expressions and statements   
   
// 연산의 종류   
// - 원시연산 : 언어가 기본적으로 제공하고 있는 연산   
// - 사용자정의연산 : 프로그래머가 추가로 정의한 연산   
// - 라이브러리 : 사용자가 자주 사용할만한 연산을 미리 정의해둔 것   
- Types of operations   
  - Raw operations : operations that the language provides by default   
  - User-defined operations : operations additionally defined by programmers   
  - Library : pre-defined operations that users can use frequently   
   
#### Subprogram   
// 서브프로그램   
   
// 전체 프로그램을 이루는 작은 코드 블록에 이름을 붙인 것   
// 서브루틴이라고 부르기도 함   
- The name of a small block of code that makes up the whole program   
- It's sometimes called a subroutine   
   
// 서브프로그램 분류   
// - 함수 : 연산 수행 결과 값을 반환하는 서브프로그램   
// - 프로시저 : 결과 값을 반환하지 않는 서브프로그램   
- Subprogram Classification   
  - Function : Subprogram that returns the value of the result of performing the operation   
  - procedure : a subprogram that does not return a result value   
   
#### Type   
// 타입   
   
// 데이터 집합과 연산 집합을 합친 개념   
// 연산의 안전성 보장을 위해 필요   
- The concept of combining data sets and operation sets   
- Required to ensure the safety of the operation   
   
// 타입 안전성   
// - 함수 f의 타입이 f(x):A → B 라면, 모든 a ∈ A에 대해 f(a) ∈ B 여야 함   
- Type Safety   
  - If the type f of function f is f(x):A → B, then for all a ∈ A, it must be f(a) ∈ B   
   
// 프로그래밍 언어의 분류   
// - 강타입 언어 : 타입 오류를 모두 검출하는 언어   
// - 약타입 언어 : 일부 타입 오류를 허용하는 언어   
// - 무타입 언어 : 타입 선언문도 없고 어떤 대상의 타입이 계속 변경될 수 있는 언어   
- Classification of programming languages   
  - Strong Type Language : a language that detects all type errors   
  - Weak Type Language : Language that allows some type of error   
  - Type-free language : a language in which there is no type declaration and the type of an object may change continuously   
   
#### Module   
// 모듈   
   
// 독립적인 프로그램 구성단위   
// 서브프로그램도 모듈의 일종   
- Independent program unit   
- Subprograms are also a type of module   
   
// 특징   
// - 내부와 외부를 구별하며 독자적인 이름 공간을 차지   
// - 변수, 함수, 타입 등 프로그래밍 언어에서 제공하는 거 모든 것을 포함하는 단위   
- Characteristics   
  - Distinguish between inside and outside and occupy a unique name space   
  - A unit that contains everything that a programming language provides, such as variable, function, and type   
   
<br />
### How to learn a programming language   
// 프로그래밍 언어의 학습 방법   
   
#### Two aspects of programming language   
// 프로그래밍 언어의 두 가지 측면   
   
|// 프로그램 형태<br />Program Form|+|// 수행 과정<br />the course of performance|
|:---:|:---:|:---:|
|// 작성한 프로그램<br />// 데이터<br />// 연산<br />- a written program<br />- data<br />- operation|+|// 실행 시 프로세스<br />// 메모리<br />// 수행 흐름<br />- running Processes<br />-  memory<br />- performance Flow|
|// 구문론<br />syntax|+|// 의미론<br />semantics|
   
#### How to learn a programming language   
// 어떻게 프로그래밍 언어를 배워야 하나?   
   
// 좋은 프로그램을 많이 읽어야 함   
// 프로그램을 많이 작성해 봐야 함   
// 직접 실행해 보며 많이 생각해 봐야 함   
- Read a lot of good programs   
- Writing a lot of programs   
- Try it yourself and think a lot about it   
   
#### How to Choose a Programming Language   
// 프로그래밍 언어의 선택 방법   
   
// 초보자   
// - 자신이 조금이라도 아는 언어   
// - 사용해 볼 수 있는 언어   
// - 주위에서 정보를 얻을 수 있는 언어   
// - 프로그램을 관리하기 쉬운 언어   
- Beginner   
  - a language one knows even a little   
  - a language you can use   
  - a language where you can get information from your surroundings   
  - an easy-to-manage language for programs   
   
// 숙련자   
// - 자신의 업무 분야에서 사용되는 언어   
// - 자신이 아는 언어와 유사한 언어   
- a skilled person   
  - language spoken in one's field of work   
  - a language similar to the one one knows   
   
#### the learning tips of programming languages   
// 프로그래밍 언어의 학습 요령   
   
// 눈보다 손   
// 그림으로 생각   
// 점진적으로 변경   
- with hands rather than eyes   
- Thinking through images   
- a gradual change   
   
#### Why to learn programming linguistics   
// 왜 프로그래밍 언어론을 배워야 하나?   
   
// 새로운 프로그래밍 언어를 쉽게 습득하기 위해서   
// 내가 사용하는 언어를 더 잘 이해하기 위해서   
// 현명한 언어 설계자가 되기 위해서   
- To learn a new programming language easily   
- To better understand the language I use   
- To be a smart language architect   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
