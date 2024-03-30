---
layout: post
title:  "Programming Language Theory: Requirements and Design Principles of Programming Languages"
date:   2024-03-30 09:00:00 +0900
categories: [Programming Language Theory]
---

### Requirement   
// 요구사항   
   
// 표현 풍부성 (expressiveness)   
// - 프로그래머의 아이디어를 표현할 수 있어야 함   
// 유지 보수성 (maintainability)   
// - 변화에 쉽게 대처할 수 있어야 함   
// 실행 가능성 (executability)   
// - 컴퓨터에서 실행할 수 있어야 함   
- Expressiveness   
  - Must be able to express the ideas of the programmer   
- Maintainability   
  - Need to be able to cope with change easily   
- Executability   
  - Must be able to run on computer   
   
<br />
### Design Principles   
// 설계 원칙   
   
// 규칙석 (regularity)   
// - 언어의 기능이 잘 조합될 수 있어야 함   
// - 일반성, 직교성, 일관성   
// 추상화 지원 (support of abstraction)   
// - 실세계의 대상을 추상화하여 나타낼 수 있고 이를 대상으로 어떤 연산을 수행할 수 있어야 함   
// - 데이터 추상화, 제어 추상화, 추상 데이터 타입 정의   
// 복잡도 제어 (complexity control)   
// - 복잡한 대상 및 처리 방법을 제어할 수 있어야 함   
// - 캡슐화, 모듈화   
- Regularity   
  - The functionality of the language must be well combined   
  - Generality, Orthogonality, Consistency   
- Support of abstraction   
  - Programming languages must be able to abstract and represent real-world objects and perform certain operations on them   
  - Data abstraction, control abstraction, defining abstract data types   
- Complexity control   
  - Programming languages must be able to control complex targets and how they are handled   
  - Encapsulation, modularization   
   
<br />
### Criteria for evaluating programming languages   
// 프로그래밍 언어의 평가 기준   
   
// 작성력 : 프로그램 수식이나 문장, 기능을 쉽게 표현할 수 있는가   
// 가독성 : 작성된 프로그램을 보고 쉽게 이해할 수 있도록 하는가   
// 신뢰성 : 작성된 프로그램이 오류에 빠지는 가능성을 줄이는가   
// 직교성 : 언어 기능이 서로 간섭하지 않고 자유롭게 조합될 수 있는가   
// 일관성 : 유사한 기능을 같은 형태로 나타낼 수 있는가   
// 확장성 : 사용자가 원하는 새로운 기능을 추가할 수 있는가   
// 효율성 : 작성된 프로그램이 효율적으로 수행될 수 있도록 하는가   
// 유연성 : 프로그래머가 표현하고 싶은 내용을 유연하게 수용하는가   
// 이식성 : 프로그램을 다른 실행 환경으로 이전할 수 있는가   
- Writing ability : Is it easy to express program formulas, sentences, and functions   
- Readability : Does it make it easier to see and understand the written program   
- Reliability : Does the written program reduce the likelihood of falling into error   
- Orthogonality : Can language functions be freely combined without interfering with each other   
- Consistency : Can similar functions be represented in the same form   
- Scalability : Can users add new features they want   
- Efficiency : Does the written program work efficiently   
- Flexibility : Are programmers flexible in accepting what they want to express   
- Portability : Can programs be transferred to a different execution environment   
   
#### Evaluation Criteria and Requirements for Programming Languages   
// 프로그래밍 언어의 평가 기준과 요구사항   
   
||Expressiveness|Maintainability|Executability|
|:---:|:---:|:---:|:---:|
|Writing ability|O|O||
|Readability||O||
|Reliability||O|O|
|Orthogonality|O|O||
|Consistency|O|O||
|Scalability|O|O||
|Efficiency||O|O|
|Flexibility|O|O||
|Portability||O|O|
   
#### A trade-off between the evaluation criteria of a programming language   
// 프로그래밍 언어의 평가 기준 사이의 절충   
   
|// 프로그램 사용자 측면<br />Program User Aspects||||// 프로그램 개발자 측면<br />Program Developers Aspects|
|:---|:---:|:---:|:---:|---:|
|// 검사 비용을 줄여야 함<br />Need to reduce inspection costs|// 효율성<br />Efficiency|↔|// 신뢰성<br />Reliability|// 더 많이 검사해야 함<br />Need to inspect more|
|// 간단한 기능을 이해하기 쉬움<br />Easy to understand simple features|// 가독성<br />Readability|↔|// 작성력<br />Writing ability|// 복잡하더라도 많은 기능이 지원되어야 함<br />Many features need to be supported, even if it's complicated|
|// 안전을 위해 더 많은 제약을 가해야 함<br />Need to impose more restrictions for safety|// 신뢰성<br />Reliability|↔|// 유연성<br />Flexibility|// 프로그램 작성 시 제약이 적어야 함<br />There should be fewer restrictions when writing a program|
   
<br />
### Criteria for selecting a programming language   
// 프로그래밍 언어의 선택 기준   
   
// 해당 프로그래밍 언어를 사용하는 커뮤니티가 활발하고 호의적인 언어   
// 특정 응용 분야가 존재하는 프로그래밍 언어   
// 접해 보지 못한 프로그래밍 패러다임을 지원할 수 있는 프로그래밍 언어   
- Select a language that has an active and favorable community using that programming language   
- Select a programming language with a specific application   
- A programming language that can support a programming paradigm you have never encountered   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
