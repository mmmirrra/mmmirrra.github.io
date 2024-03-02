---
layout: post
title:  "Data Structure: Concept"
date:   2024-03-02 09:00:00 +0900
categories: [Data Structure]
---

### Data & Information   
// 자료와 정보   
   
Information = Process(Data)   
I = P(D)   
P(D) → I   
   
// 자료의 가공 결과는 정보임   
// 자료 → 처리 (컴퓨터) → 정보   
- The result of processing the data is information   
- Data → Processing (Computer) → Information   
   
<br />
### Data   
// 자료   
   
// 현실 세계에서 관찰이나 측정을 통해서 수집된 값(value)이나 사실(fact)   
// 관찰이나 측정을 통해 얻은 수치, 문자 형태로 표현할 수 있는 질적(quality) 또는 양적(quantity) 값   
// 우리의 생활에서 실제로 만질 수 있거나 볼 수 있는 것(길이, 무게 부피 등을 측정할 수 있는 대상)에 대하여 물리적인 단위로 표현하여 얻어낼 수 있는 내용   
- Values or fact collected through observation or measurement in the real world   
- Numerical values obtained by Observation or Measurement, or a qualitative or quantitative value that can be expressed in characters   
- What can be achieved by expressing in physical units what we can actually touch or see in our lives (the object that can measure length, weight volume, etc.)   
   
<br />
### Information   
// 정보   
   
// 어떤 상황에 대해서 적절한 의사결정을 할 수 있게 하는 지식으로서 자료의 유효한 해설이나 자료 상호 간의 관계를 표현하는 내용   
// 어떠한 상황에 적절한 결정이나 판단에 사용될 수 있는 형태로 가공되거나 분류되기 위해 '처리과정'을 거쳐서 정리하고 정돈된 '자료'의 2차 처리 결과물   
// 정보는 자료를 처리해서 얻어진 유용한 결과라고 할 수 있음   
- Content that expresses the effective interpolation of data or the relationship between data as knowledge that enables appropriate decision-making on a situation   
- The results of secondary processing of 'data' organized and organized through a 'processing process' in order to be processed or classified into a form that can be used for decision or judgment appropriate to any situation   
- Information can be said to be a useful result obtained by processing data   
   
<br />
### Abstraction   
// 추상화   
   
// 공통적인 개념을 이용하여 같은 종류의 다양한 객체를 정의하는 것   
// 추상화를 통해 간결하게 말하는 사람의 의사를 전달할 수 있게 되는 것   
// 물리적이며 전기적인 동작과는 무관하게 자료를 생각하고 바라보는 사람의 상상   
- Defining different objects of the same kind using common concepts   
- To be able to convey the speaker's intentions concisely through abstraction   
- the imagination of a person thinking and looking at data, regardless of physical and electrical motion   
   
#### Abstraction of Data   
// 자료의 추상화   
   
// 자료 사이의 논리적 관계를 컴퓨터나 프로그램에 적용하기 위해서는 자료의 추상화가 필요함   
// 추상화를 통해 자료의 논리적 관계를 구조화한 것을 자료구조라고 함   
// 다양한 대상을 컴퓨터에서 저장하고 처리하기 위해 그 대상들의 의미와 구조에 대해서 공통의 특징만을 뽑아 정의한 것   
// 컴퓨터 내부의 이진수의 표현 방법, 저장 위치 등은 포함되지 않고 단순하게 개발자의 머릿속에 그림을 그리는 것처럼 개념화한 것   
// 개발자들 사이의 의사를 전달하기 위해 사용되는 방법   
- Abstracting data is necessary to apply the logical relationship between data to computers or programs   
- Structuring the logical relationship of data through abstraction is called a data structure   
- In order to store and process various objects on a computer, it is defined by extracting only common characteristics of the meaning and structure of the objects   
- It is conceptualized as if drawing a picture in the developer's head without including the method of expressing binary numbers inside the computer, storage location, etc.   
- Methods used to communicate among developers   
   
<br />
### Data Structure   
// 자료구조   
   
// 자료 → 자료의 추상화 → 자료구조   
// 추상화를 통해 알고리즘에서 사용할 자료의 논리적 관계를 구조화한 것   
// 자료의 추상화와 구조화가 적절히 이루어지지 못하면 소프트웨어는 비효율적으로 수행되거나 소프트웨어의 확장성에 문제가 생길 수 있음   
- Data → Abstraction of Data → Data Structure   
- Structured the logical relationship of the data to be used in the Algorithm through abstraction   
- If data is not properly abstracted and structured, software can be performed inefficiently or software scalability can be problematic   
   
<br />
### Algorithm   
// 알고리즘   
   
// 컴퓨터에게 일을 시키기 위한 (추상화된) 명령어의 연속된 덩어리   
// 사람(개발자)이 컴퓨터에게 일을 시키기 위한 사람의 의도와 명령을 전달해 줄 수 있는 방법(언어/글)   
// 컴퓨터에게 시킬 일   
// 컴퓨터가 수행할 명령어의 유한 집합이 사람의 머리속에 추상화되어 존재하는 것   
// 컴퓨터에게 시킬 일(프로그램)을 머릿속에서 추상화시켜서 대략적으로 상상해 놓은 것   
- A successive set of instructions for making a computer work   
- How a person(developer) can communicate a person's intentions and commands to make a computer do things (language/text)   
- Algorithms are things that you're going to have computers do   
- A finite set of instructions to be performed by a computer is abstracted in the human head   
- Algorithms are an abstraction of a program to be given to a computer in your head and roughly imagining it   
   
#### Conditions of Algorithm   
// 알고리즘의 조건   
   
// 1. 출력 : 알고리즘을 수행하고 나면 적어도 한 가지 결과를 생성해야 함   
// 2. 유효성 : 모든 명령은 컴퓨터에서 수행할 수 있어야 함   
// 3. 입력 : 외부/내부 입력값은 유한해야 하며, 반드시 입력 형태가 정의될 수 있어야 함   
// 4. 명확성 : 각 명령은 모호하지 않고 단순 명확해야 함   
// 5. 유한성 : 한정된 수의 단계를 거친 후에는 반드시 종료함   
1. Output : Algorithms must produce at least one result once done   
2. Effectiveness : All commands must be able to be performed on the computer   
3. Input : The external/internal input must be finite, and the input form must be defined   
4. Clarity : Each command should be unambiguous, simple and clear   
5. Finiteness : It must be terminated after a limited number of steps   
   
<br />
### Performance Analysis   
// 알고리즘의 성능 분석   
   
// 알고리즘을 실행하는데 필요한 시간과 공간을 추정하여 알고리즘의 성능을 분석   
Estimate the time and space required to running an Algorithm to analyze its performance   
   
#### Analyzing the Running Time of the Algorithm   
// 알고리즘의 실행시간 분석   
   
// 알고리즘을 실행하는데 필요한 예측 실행시간을 추정하여 알고리즘의 성능을 분석   
- Estimate the prediction running time required to run the Algorithm to analyze the performance of the Algorithm   
   
// 실행 시간의 예측   
// - 알고리즘의 실행 횟수를 O(n)이라고 표현   
// - 같은 O(n)을 가진다고 해서 같은 실행시간을 갖는 것이 아니라서 실행시간의 유사한 증가 경향에 대해서 표현하는 방법   
- Prediction of Running Time   
  - Express the number of runs of an Algorithm as O(n)   
  - To express a similar trend of increasing run time because having the same O(n) does not mean having the same run time   
   
#### Analyzing the Algorithm's Running Memory   
// 알고리즘의 실행메모리 분석   
   
// 알고리즘을 실행하는데 필요한 공간(메모리)을 추정하여 알고리즘의 성능을 분석함   
- Estimate the space (memory) required to run the Algorithm to analyze its performance   
   
// - 고정공간 : 프로그램의 크기나 입출력의 횟수와 관계없이 컴파일시에 결정되어 프로그램의 실행이 끝날때까지 고정적으로 필요한 메모리 공간   
// - 가변공간 : 프로그램의 실행 과정에서 동적으로 할당되어야 하는 자료구조와 변수들을 위해 필요한 메인메모리 공간   
  - Fixed Space : Memory space determined at the time of compilation, regardless of the size of the program or the number of inputs and outputs, which is fixedly required until the end of the program's running   
  - Variable Space : The main memory space required for data structures and variables that must be dynamically allocated during the running of the program   
   
// 실행 메모리의 예측   
// - 알고리즘의 공간 복잡도는 프로그램을 실행시켜서 완료하는데 필요한 총 메모리 공간   
// - Sp = Sc + Se (공간복잡도 = 고정공간 + 가변공간)   
- Prediction of running memory   
  - The Algorithm's Space Complexity is the total amount of memory required to run a program and complete it   
  - Sp = Sc + Se (Space Complexity = Fixed Space + Variable Space)   
   
<br />
### Performance Measurement   
// 알고리즘의 성능 측정   
   
// 컴퓨터가 실제로 프로그램을 실행하는데 걸리는 시간을 측정하여 알고리즘의 성능을 측정   
- Measure the performance of an Algorithm by measuring how long it takes a computer to actually run a program   
   
#### Measurement of Running Time   
// 실행시간의 측정   
   
// - 실제로 실행시간을 시계로 잰다는 것   
// - 실제로 실행될 수 있는 프로그램(실행파일)이 있어야 함   
// - 시스템 시계를 이용   
- Actually clocking the run time   
- Must have a program (executive file) that can actually run   
- Using the system clock   
   
<br />
### Relationship between Data Structure and Algorithm   
// 자료구조와 알고리즘의 관계   
   
// 자료구조는 입력 자료에 대한 추상화된 상태라면, 알고리즘은 컴퓨터가 수행해야 할 명령의 추상화   
- If the data structure is an abstracted state of the input data, the Algorithm is an abstracted state of the instructions that the computer must perform
   
|// 관계<br />Relationship|
|:---:|
|자료구조 → 컴퓨터 → 출력<br />↑<br />알고리즘|
|Data Structure → Computer → Output<br />↑<br />Algorithm|
   
<br />
### Two Aspects of Data Structure   
// 자료구조의 두 가지 측면   
   
// 개발자 → 추상화 → [자료구조] ← 구체화 ← 컴퓨터   
Developer → Abstract → [Data Structure] ← Concrete ← Computer   
   
<br />
### Abstracting/Concrete of Data Structure and Algorithm   
// 자료구조와 알고리즘의 추상화/구체화   
   
// 입력값을 머릿속에서 추상화된 형태(자료구조)로 구조화하고, 수행되어야 할 명령어를 머릿속에서 추상화된 형태(알고리즘)로 체계화됨   
// 프로그래밍 언어 : 자료구조와 알고리즘을 구체화하는 방법   
- Input values should be structured in an abstract form (Data Structure) in the head, and instructions to be performed should be structured in an abstract form (algorithm) in the head   
- Programming Language : How to specify data structure and algorithm   
   
|// 구체화<br />Concrete|
|:---:|
|자료구조 → 입력값 → 컴퓨터 → 출력<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↑<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;프로그램<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↑<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;알고리즘|
|Data Structure → Input → Computer → Output<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↑<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Program<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↑<br />&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Algorithm|
   
<br />
### ADT (Abstract Data Type)   
// 추상 자료형   
   
// 자료구조와 알고리즘의 중간쯤에 있는 자료의 복잡한 논리적 성격을 정의하는 형식   
// 자료값의 집합과 연산 집합에 대한 정의(명세의 집합)로 구성됨   
// 자료구조를 표현하는 가장 대표적인 방법   
- A form that defines the complex logical nature of data halfway between data structure and algorithm   
- Consists of a set of data values and definitions of a set of operations (a set of specifications)   
- The most representative way to express data structure   
   
#### Abstraction and Abstract Data Type   
// 추상화와 추상 자료형   
   
// 추상화 : 그림이나 수식과 같이 의미를 표현하고 전달하는 방법   
// 추상 자료형 : 전산학에서 사용되는 자료구조를 표현하는(공통의 의미를 추출하여 전달하는) 방법   
- Abstraction : A way of expressing and conveying meaning, such as a picture or formula   
- Abstract Data Type : A method of expressing data structures used in computer science (Extracting common meanings and conveying them)   
   
<br />
### Types of Data Structure   
// 자료구조의 구분   
   
// 미리 정의된 자료구조 : 프로그래밍 언어를 개발하는 개발자에 의해 정의되고 추상화되었고, 이를 컴퓨터 내부에서 프로그래밍 언어의 형태로 구현된 자료구조를 의미함   
// '미리 정의된 자료구조'는 프로그래밍 언어 개발자가 프로그램 개발자를 위해 미리 정의하지만, '사용자 정의 자료구조'는 프로그램 개발자가 자신의 프로그램 개발 방향에 따라 프로그래밍 언어로 새롭게 정의하여 사용하는 자료구조임   
- Predefined Data Structure : It is defined and abstracted by developers who develop programming languages, and refers to data structures implemented in the form of programming languages inside computers   
- 'Predefined Data Structure' is predefined by programming language developers for program developers, but 'Custom Data Structure' is a data structure newly defined and used by program developers in programming languages according to their program development direction   
   
|// 미리 정의된 자료구조<br />Predefined Data Structure||// 사용자 정의 자료구조<br />Custom Data Structure|
|:---|:---|:---|
|// 기본 자료구조<br />Basic Data Structure|// 파생된 자료구조<br />Derived Data Structure||
|// 정수<br />Integer<br />// 실수<br />Real Number<br />// 문자<br />Character|// 배열<br />Array<br />// 구조체<br />Structure<br />// 포인터<br />Pointer|// 리스트<br />List<br />// 스택<br />Stack<br />// 큐<br />Queue<br />// 트리<br />Tree<br />// 그래프<br />Graph|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
