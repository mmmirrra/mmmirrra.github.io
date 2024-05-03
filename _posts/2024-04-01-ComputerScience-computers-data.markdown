---
layout: post
title:  "Introduction to Computer Science: Computers and Data"
date:   2024-04-01 09:00:00 +0900
categories: [Computer Science]
---

### Introduction to Computer Science   
// 컴퓨터과학개론   
   
// 컴퓨터과학 분야의 주요 내용을 개괄적으로 소개하는 과목   
// - 컴퓨터와 데이터   
// - 자료구조   
// - 알고리즘   
// - 운영체제   
// - 컴퓨터 구조   
// - 프로그래밍 언어   
// - 데이터베이스   
// - 컴퓨터 네트워크   
// 용어, 개념, 원리, 방법 등을 미리 접해봄으로써 친숙해질 수 있는 기회와 환경을 제공   
// 컴퓨터과학이라는 학문과 각 내용을 올바르게 이해하고 배울 수 있는 적절한 사고의 틀을 제공   
- A subject that outlines the main contents of the field of computer science   
  - Computer and Data   
  - Data Structure   
  - Algorithm   
  - Operating System   
  - Computer Architecture   
  - Programming Language   
  - Database   
  - Computer Network   
- Experiencing terms, concepts, principles, methods, etc. in advance provides an opportunity and environment to become familiar   
- It provides a framework for the study of computer science and appropriate thinking to understand and learn each content correctly   
   
<br />
### Computer   
// 컴퓨터   
   
#### What is a computer?   
// 컴퓨터란 무엇인가?   
   
// 데이터 처리기 (data processor)   
// - (데이터) 입력 → (컴퓨터 : 데이터 처리) 처리 → (결과) 출력   
// - 현대 컴퓨터의 기능적 측명 ("입력-처리-출력") 만 정의   
// -- 너무 포괄적   
// -- 어떤 형태의 작업을 처리할 수 있는지 불분명   
- Data Processor   
  - (data) input → (computer : data processing) processing → (result) output   
  - Define only the functional measure of modern computers ("input-process-output")   
    - Too comprehensive   
    - It's unclear what types of tasks can be handled   
   
// 프로그램이 가능한 데이터 처리기 (programmable data processor)   
// - 입력 → (프로그램 →) 컴퓨터 → 출력   
- Programmable Data Processor   
  - Input → (Program →) Computer → Output   
   
#### Program   
// 프로그램   
   
// 컴퓨터가 데이터를 어떻게 처리할지를 알려주는 일련의 명령어 집합   
// - 처리 가능한 작업의 유형과 연산의 집합을 결정   
// -- 컴퓨터 → 특수 목적의 작업을 처리하는 기계가 아니라, "다양한 형태의 작업을 수행할 수 있는 범용의 기계"   
- A program is a set of instructions that tell the computer how to process data   
  - Determine the type of task that can be handled and the set of operations   
    - Computer → Not a machine that handles special purpose tasks, but a "universal machine that can perform various types of tasks."   
   
// 프로그래밍 과정의 결과물   
// ① 주어진 문제의 해결 방법과 절차를 찾는다 → "알고리즘"   
// ② 그것을 적절한 프로그래밍 언어를 사용해서 컴퓨터가 이해할 수 있는 형태로 표현한다   
- The outcome of a programming process   
  - ① Find solutions and procedures for the given problem → "Algorithm"   
  - ② Express it in a form that a computer can understand using an appropriate programming language   
   
#### Strengths of computers   
// 컴퓨터의 장점   
   
// 신속한 처리   
// - ms (10<sup>-3</sup>초), μs (10<sup>-6</sup>초), ns (10<sup>-9</sup>초), ps (10<sup>-12</sup>초)   
// 처리 결과의 정확성   
// - 유효한 입력과 프로그램이 주어지면 항상 정확한 결과 생성   
// 자동   
// - 프로그램 지시에 따라 자동으로 처리 → 사람의 개입이 불필요   
// 대용량   
// - 대용량의 데이터 저장 및 처리   
- Expedited processing   
  - ms (10<sup>-3</sup>seconds), μs (10<sup>-6</sup>seconds), ns (10<sup>-9</sup>seconds), ps (10<sup>-12</sup>seconds)   
- Accuracy of processing results   
  - Always produce accurate results given valid inputs and programs   
- Automatic   
  - Follow program instructions automatically → No human intervention required   
- Large capacity   
  - Storage and processing of large capacitys of data   
   
<br />
### Computer Science   
// 컴퓨터과학   
   
#### What is computer science?   
// 컴퓨터과학이란 무엇인가?   
   
// 데이터의 표현, 저장, 조작, 검색과 밀접히 관련된 분야   
// - 컴퓨터 : 프로그램을 통해서 데이터를 입력하여 처리, 저장, 검색, 출력하는 전자적 장치   
// - 데이터를 획득 (acquisition), 표현 (representation), 처리 (processing), 저장 (storage), 통신 (communication), 접근 (access) 을 위한 방법들을 실행 가능성, 구조화, 표현, 기계화에 관련된 내용을 다루는 분야   
- Areas closely related to data representation, storage, manipulation, and retrieval   
  - Computer : an electronic device that inputs, processes, stores, retrieves, and outputs data through a program   
  - The area that covers methods for acquisition, representation, processing, storage, communication, and access data related to feasibility, structuring, representation, and mechanization   
   
// 컴퓨터, 데이터, 프로그램, 알고리즘에 대한 분야   
// - 데이터 → (알고리즘 → 프로그램 →) 컴퓨터 → 정보   
// -- 데이터 관련 과목 : 자료구조, 데이터베이스   
// -- 컴퓨터 관련 과목 : 디지털논리회로, 컴퓨터구조   
// -- 프로그램 관련 과목 : 운영체제, 컴파일러, 프로그래밍 언어, 정보통신, 컴퓨터 그래픽스   
// -- 알고리즘 : 이산구조, 선형대수, 알고리즘, 인공지능   
- Areas of computers, data, programs, and algorithms   
  - Data → (Alarm → Program →) Computer → Information   
    - Data-related subjects : Data structure, database   
    - Computer-related subjects : Digital logic circuit, computer structure   
    - Program-related subjects : Operating system, compiler, programming language, information communication, computer graphics   
    - Algorithms : Discrete structure, linear algebra, algorithms, artificial intelligence   
   
// 알고리즘과 관련된 이슈를 다루는 학문   
// - 주어진 문제를 해결하기 위한 처리 과정을 절차적으로 나열한 명령어들의 집합   
// -- 알고리즘의 한계   
// -- 알고리즘의 분석   
// -- 알고리즘의 개발   
// -- 알고리즘의 통신   
// -- 알고리즘의 표현   
// -- 알고리즘의 실행   
// - 알고리즘의 존재 여부 → "컴퓨터의 한계"   
- A study that deals with issues related to algorithms   
  - A set of instructions that procedurally list the process of solving a given problem   
    - The limits of an algorithm   
    - Analysis of algorithms   
    - Development of algorithms   
    - Communication of algorithms   
    - Representation of the algorithm   
    - Execution of the algorithm   
  - The existence of an algorithm → "The limits of the computer"   
   
#### Characteristics of Computer Science   
// 컴퓨터과학의 특성   
   
// 비교적 짧은 역사, 빠른 변화 및 엄청난 영향력   
// 다른 분야와의 밀접한 연관 → 폭 넓은 연구/응용 범위   
// - 수학, 공학, 심리학, 생물학, 언어학, 경영과학, 물리학, 철학, ...   
- Relatively short history, rapid change and enormous influence   
- Close association with other fields → broad research/application   
  - Mathematics, engineering, psychology, biology, linguistics, business science, physics, philosophy, ...   
   
|// 컴퓨터공학<br />Computer Engineering|// 컴퓨터과학<br />Computer Science|
|:---|:---|
|// 가격대비 성능 특성이 좋은 컴퓨팅 엔진을 만들기 위해 하드웨어와 소프트웨어 요소의 조립에 중점<br />- Focus on assembling hardware and software elements to create price-performance computing engines|// 현재의 기술에 덜 의존적인 방식으로 주어진 문제에 대한 해결책을 효율성과 실현 가능성에 보다 중점 → "컴퓨터를 활용한 문제 해결에 대한 학문"<br />- More emphasis on efficiency and feasibility to solve a given problem in a way that is less dependent on current technology → "Academic of problem solving using computers"|
   
<br />
### Computer System   
// 컴퓨터 시스템   
   
#### Components of a computer system   
// 컴퓨터 시스템의 구성 요소   
   
// 하드웨어, 소프트웨어, 데이터, 사용자   
- Hardware, Software, Data, Users   
   
#### Hardware   
// 하드웨어   
   
// 기계를 구성하고 있는 모든 물리적인 기계장치/전자장치   
// 핵심장치 : 폰 노이만 모델에서 제시한 4개의 서브시스템이 해당   
// 폰 노이만 John von Neumaan 모델 : 컴퓨터의 내부 구조와 처리 과정을 정의한 모델   
- all the physical machinery/electronics that make up the machine   
- Core devices : Four subsystems presented in the von Neumann model are applicable   
- John von Neumaan Model : A Model Defining the Internal Structure and Processing Process of a Computer   
   
// (데이터) 입력 → (프로그램 →) 컴퓨터 (산술논리연산장치, 제어장치, 기억장치, 입출력장치) → (데이터) 출력   
- (Data) Input → (Program →) Computer (Arithmetic Logic Computing Device, Control Device, Memory Device, Input/Output Device) → (Data) Output   
   
// 중앙처리장치 (CPU : Central Processing Unit)   
// - 제어장치 (CU : Control Unit)   
// - 산술논리연산장치 (ALU : Arithmetic and Logic Unit)   
// 기억장치 : 주기억장치, 보조기억장치   
// - 처리할 입력 데이터, 처리를 담당하는 프로그램, 중간 결과, 출력할 데이터   
// 산술논리연산장치 : 산술 연산과 수행을 통해 직접적인 데이터 처리가 이루어지는 장치   
// 제어장치 : 컴퓨터의 기억장치, ALU, 입출력장치의 동작을 제어하는 장치   
// 입력장치 : 키보드, 마우스, 마이크 등   
// 출력장치 : 모니터, 프린터, 스피커 등   
- CPU : Central Processing Unit   
  - CU : Control Unit   
  - ALU : Arithmetic and Logic Unit   
- Memory devices : Main memory devices, auxiliary memory devices   
  - Input data to process, programs responsible for processing, intermediate results, data to output   
- Arithmetic logic calculator : A device that performs direct data processing through arithmetic operations and performance   
- Control devices : A device that controls the operation of a computer's memory, ALU, and I/O devices   
- Input devices : Keyboard, mouse, microphone, etc.   
- Output devices : monitors, printers, speakers, etc.   
   
// 폰 노이만 모델의 주요 개념   
// - 내장 프로그램 (stored program)   
// -- 실행될 프로그램은 메모리에 저장되어야 함   
// --- 초기 컴퓨터에서는 데이터만 메모리에 저장되고, 프로그램은 컴퓨터 외부에 표현   
// -- "프로그램과 데이터가 동일한 형식 (비트 패턴) 으로 메모리에 표현된다"는 의미를 내포   
// - 프로그램은 유한 개의 명령어의 나열임   
// -- 미리 정의된 기본 명령어의 유한 개의 조합으로 구성됨   
// -- 메모리에서 한번에 하나씩 명령어를 가져와서 해석하고 실행함   
// -- 명령어의 재사용 → 프로그래밍 작업이 간단해짐   
- Key Concepts of the von Neumann Model   
  - stored program   
    - Programs to run must be stored in memory   
      - In early computers, only data is stored in memory, and programs are represented outside the computer   
    - It implies that "programs and data are represented in memory in the same format (bit pattern)"   
  - A program is a list of finite instructions   
    - Consists of a finite combination of predefined basic commands   
    - Obtain, interpret and execute commands one at a time from memory   
    - Reuse of commands → Simplifies programming operations   
   
#### Software   
// 소프트웨어   
   
// 모든 종류의 프로그램을 총체적으로 표현하는 용어   
// - 컴퓨터가 데이터를 어떻게 처리할 것인가를 규정하는 명령어들의 나열   
// - 컴퓨터가 이해할 수 있도록 표현된 알고리즘   
- a term that collectively expresses all kinds of programs   
  - a list of instructions that define how a computer processes data   
  - algorithms expressed so that the computer can understand them   
   
// 소프트웨어 분류   
// - 시스템 소프트웨어   
// -- 컴퓨터 자체의 작업 관리와 특정 기능의 수행을 통해 컴퓨터의 전체적인 운영을 담당   
// --- 운영체제, 컴파일러, ...   
// - 응용 소프트웨어   
// -- 사용자가 요구하는 작업을 직접적으로 수행하는 프로그램   
// --- 워드프로세서, 그래픽 프로그램, 데이터베이스 프로그램, ...   
- Software classification   
  - System Software   
    - Responsible for the overall operation of the computer through the management of its own tasks and the performance of certain functions   
      - Operating system, compiler, ...   
  - Application software   
    - A program that directly performs the tasks that the user requires   
      - Word processor, graphics program, database program, ...   
   
#### Data   
// 데이터   
   
// 모든 데이터는 유형에 관계 없이 비트 패턴으로 표현   
// - 비트 패턴 → 이진 상태를 나타내는 비트인 0과 1이 나열된 형태   
// -- 폰 노이만 모델에서는 데이터의 표현 및 저장 형태에 대해서 정의하지 않음   
// - 데이터의 입출력을 위해서는 적절한 형태로의 변환이 필요   
// -- 데이터 → (변환) → 컴퓨터 → (변환) → 결과   
- All data is expressed in bit patterns, regardless of type   
  - Bit Pattern → Listed with bits 0 and 1 representing binary status   
    - The von Neumann model does not define how data is represented and stored   
  - Data input/output requires conversion to the appropriate format   
    - Data → (Conversion) → Computer → (Conversion) → Results   
   
#### Users   
// 사용자   
   
// 사용자, 오퍼레이터   
// - 컴퓨터의 설계부터 효율적인 이용에 이르기까지 전반적인 데이터 처리 과정에서 유능하고 지식이 풍부한 사람의 적극적인 개입이 필요   
- Users, Operators   
  - The overall data processing process, from computer design to efficient use, requires active involvement by competent and knowledgeable people   
   
<br />
### Data and information   
// 데이터와 정보   
   
#### The relationship between data and information   
// 데이터와 정보의 관계   
   
// I = P(D)   
// 데이터 D → 처리기 P (데이터 처리, 정보 처리) → 정보 I   
// - 데이터 D : 현실 세계로부터 관찰이나 측정을 통해 단순히 얻어지는 값/사실   
// - 정보 I : 어떤 상황에 대해 적절한 의사결정을 수행할 수 있게 하는 지식   
- I = P(D)   
- Data D → Processor P (Data processing, information processing) → Information I   
  - Data D : Values/facts obtained simply from observations or measurements from the real world   
  - Information I : Knowledge that enables you to make appropriate decisions about a situation   
   
#### The form of representation of the data   
// 데이터의 표현 형태   
   
// 데이터의 유형과 무관하게 일관된 표현 방식   
// - 문자, 정수/실수, 이미지, 오디오, 비디오 등   
// - "비트 패턴"   
// - 메모리에 저장된 데이터 유형에 맞는 해석과 처리가 필요   
// -- 입출력 장치나 프로그램의 책임   
- Consistent representation regardless of the type of data   
  - Characters, integers/real number, images, audio, video, etc.   
  - "Bit pattern"   
  - Requires interpretation and processing to match the type of data stored in memory   
    - Responsibility of I/O devices or programs   
   
#### Representation unit of data   
// 데이터의 표현 단위   
   
// 비트 (binary digit)   
// - off = 기호 0   
// - on = 기호 1   
// 바이트 (byte)   
// - 8bit   
// - KB (2<sup>10</sup>≒10<sup>3</sup>), MB (2<sup>20</sup>≒10<sup>6</sup>), GB (2<sup>30</sup>≒10<sup>9</sup>), TB (2<sup>40</sup>≒10<sup>12</sup>), PB (2<sup>50</sup>≒10<sup>15</sup>)   
// - EB (2<sup>60</sup>), ZB (2<sup>70</sup>), YB (2<sup>80</sup>)   
// 워드 (word)   
// - 컴퓨터 연산의 기본 단위가 되는 정보의 양 → 32비트, 64비트   
- binary digit   
  - off = symbol 0   
  - on = symbol 1   
- byte   
  - 8bit   
  - KB (2<sup>10</sup>≒10<sup>3</sup>), MB (2<sup>20</sup>≒10<sup>6</sup>), GB (2<sup>30</sup>≒10<sup>9</sup>), TB (2<sup>40</sup>≒10<sup>12</sup>), PB (2<sup>50</sup>≒10<sup>15</sup>)   
  - EB (2<sup>60</sup>), ZB (2<sup>70</sup>), YB (2<sup>80</sup>)   
- word   
  - Amount of information that is the basic unit of computer operation → 32 bits, 64 bits   
   
<br />
### Number System   
// 진법   
   
// 수를 세는 방법 또는 단위   
// - r진수 → 0, 1, ..., (r-1)까지의 숫자만을 사용해서 표현한 수   
- A method or unit of counting   
  - r number → A number expressed using only the numbers 0, 1, ..., and (r-1)   
   
|// 진법<br />number system|// 사용하는 수<br />Numbers used for number system|// 표기방법<br />Indication method|
|:---|:---|:---|
|// 2진법<br />binary system|0, 1|1010<sub>2</sub> 1001<sub>b</sub>|
|// 8진법<br />octal system|0, 1, 2, ..., 7|720<sub>8</sub> 257<sub>o</sub>|
|// 10진법<br />decimal system|0, 1, 2, ..., 9|99<sub>10</sub> 123<sub>d</sub>|
|// 16진법<br />hexadecimal system|0, 1, 2, ..., 9, A, B, C, D, E, F|2CF<sub>16</sub> FF30<sub>h</sub>|
   
// 각 위치에 따른 서로 다른 가중치 (자릿값) 가 존재   
- Different weights (place values) exist for each location   
   
// 예시   
// - '123' (일이삼) : 일백이십삼 (= 1 x 10<sup>2</sup> + 2 x 10<sup>1</sup> + 3 x 10<sup>0</sup>)   
- Example   
  - '123' (one two three) : One hundred and twenty-three (= 1 x 10<sup>2</sup> + 2 x 10<sup>1</sup> + 3 x 10<sup>0</sup>)   
   
|Binary system|1|0|1|1|1|.|0|1|1|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|weight|2<sup>4</sup>|2<sup>3</sup>|2<sup>2</sup>|2<sup>1</sup>|2<sup>0</sup>|.|2<sup>-1</sup>|2<sup>-2</sup>|2<sup>-3</sup>|
   
#### Binary → Decimal   
// 2진수 → 10진수   
   
// 10진수 = (각 비트값 x 해당 비트 위치의 가중치) 의 합   
- Decimal = sum of (each bit value x the weight of that bit position)   
   
|...|2<sup>4</sup>|2<sup>3</sup>|2<sup>2</sup>|2<sup>1</sup>|2<sup>0</sup>|.|2<sup>-1</sup>|2<sup>-2</sup>|2<sup>-3</sup>|2<sup>-4</sup>|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|...|16|8|4|2|1|.|<sup>1</sup>/<sub>2</sub>|<sup>1</sup>/<sub>4</sub>|<sup>1</sup>/<sub>8</sub>|<sup>1</sup>/<sub>16</sub>|
   
// 예시   
// - 이진수 101.1001 → 십진수 5.5625   
- Example   
  - Binary 101.1001 → Decimal 5.5625   
   
|Binary system|1|0|1|.|1|0|0|1|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|weight|1 x 2<sup>2</sup>|0 x 2<sup>1</sup>|1 x 2<sup>0</sup>|.|1 x 2<sup>-1</sup>|0 x 2<sup>-2</sup>|0 x 2<sup>-3</sup>|1 x 2<sup>-4</sup>|
   
#### Octal, Hexadecimal → Decimal   
// 8진수, 16진수 → 10진수   
   
// 10진수 = (각 숫자값 x 해당 위치의 가중치) 의 합   
- Decimal = Sum of (each numeric value x the weight of the location)   
   
// 예시   
- Example   
  - 3456<sub>8</sub> = 3 x 8<sup>3</sup> + 4 x 8<sup>2</sup> + 5 x 8<sup>1</sup> + 6 x 8<sup>0</sup> = 1838   
  - AE7<sub>16</sub> = A x 16<sup>2</sup> + E x 16<sup>1</sup> + 7 x 16<sup>0</sup> = 10 x 16<sup>2</sup> + 14 x 16<sup>1</sup> + 7 x 16<sup>0</sup> = 2791   
   
#### Decimal → R number (r = 2, 8, 16)   
// 10진수 → r진수 (r = 2, 8, 16)   
   
// 정수 부분과 소수 부분을 구분하여 각각 처리한 후, 각 결과를 단순히 연결해서 나열   
- After processing each integer part and decimal part separately, simply connect and list each result   
   
// 예시   
// - 10진수 60.6875 → 2진수 111100.1011   
// -- 60은 정수 부분 → 2진수 111100   
// -- 6875는 소수 부분 → 2진수 .1011   
- Example   
  - Decimal 60.6875 → Binary 111100.1011   
    - 60 is an integer part → Binary 111100   
    - 6875 is a decimal part → Binary .1011   
   
#### Decimal integer part → r number (r = 2, 8, 16) transform algorithm   
// 10진수 정수 부분 → r진수 (r = 2, 8, 16) 변환 알고리즘   
   
```c
// 입력값 = 10진수 (정수 부분);
// i = 0;
// 몫 = 입력값 / r; 나머지 = 입력값 mod r;
// 결과 (i) = 나머지;
// while (몫 ≠ 0)
//     입력값 = 몫;
//     i = i + 1;
//     몫 = 입력값 / r;
//     나머지 = 입력값 mod r;
//     결과 (i) = 나머지
// end
// 출력[결과 (i), 결과 (i - 1), ..., 결과 (0)];
input value = decimal number (integer portion);
i = 0;
share = input value  /r; rest = input value mod r;
results (i) = rest;
while (share ≠ 0)
    input value = share;
    i = i + 1;
    share = input value / r;
    rest = input value mod r;
    results (i) = rest
end
output [result (i), result (i - 1), ..., result (0)];
```
   
// 예시   
// - 10진수 60<sub>10</sub> → 2진수 111100<sub>2</sub>   
// - 10진수 60<sub>10</sub> → 8진수 74<sub>8</sub>   
// - 10진수 60<sub>10</sub> → 16진수 3C<sub>16</sub>   
- Example   
  - Decimal 60<sub>10</sub> → Binary 111100<sub>2</sub>   
  - Decimal 60<sub>10</sub> → Octal 74<sub>8</sub>   
  - Decimal 60<sub>10</sub> → Hexadecimal 3C<sub>16</sub>   
   
#### Decimal decimal part → r number (r = 2, 8, 16) transform algorithm   
// 10진수 소수 부분 → r진수 (r = 2, 8, 16) 변환 알고리즘   
   
```c
// 입력값 = 10진수 (소수 부분);
// i = 0;
// while (입력값 ≠ 0)
//     임시변수 = 입력값 x r;
//     결과 (i) = 임시변수의 정수 부분;
//     i = i + 1;
//     입력값 = 임시변수의 소수 부분;
// end
// 출력[0.결과 (0), 결과 (1), ..., 결과 (i)];
input value = decimal number (decimal part);
i = 0;
while (input value ≠ 0)
    temporary variable = input value x r;
    results (i) = the integer part of the temporary variable;
    i = i + 1;
    input = decimal part of the temporary variable;
end
output [0.result (0), result (1), ..., result (i)];
```
   
// 예시   
// - 10진수 0.6875<sub>10</sub> → 2진수 0.1011<sub>2</sub>   
// - 10진수 0.6875<sub>10</sub> → 8진수 0.54<sub>8</sub>   
// - 10진수 0.6875<sub>10</sub> → 16진수 0.B<sub>16</sub>   
- Example   
  - Decimal 0.6875<sub>10</sub> → Binary 0.1011<sub>2</sub>   
  - Decimal 0.6875<sub>10</sub> → Octal 0.54<sub>8</sub>   
  - Decimal 0.6875<sub>10</sub> → Hexadecimal 0.B<sub>16</sub>   
   
// 계산기 끝나지 않고 무한히 반복되는 경우 적당한 자리에서 종료함. 변환 전의 값과 변환 후의 값이 같지 않음   
- If the calculator does not end and repeats indefinitely, it ends in the appropriate place. The value before conversion and the value after conversion are not the same   
   
// 예시   
// - 10진수 0.6<sub>10</sub> → 2진수 0.1001<sub>2</sub>   
// - ∴ 0.6 ≠ 0.1001   
- Example   
  - Decimal 0.6<sub>10</sub> → Binary 0.1001<sub>2</sub>   
  - ∴ 0.6 ≠ 0.1001   
   
#### Binary ↔ Octal/hexadecimal   
// 2진수 ↔ 8진수/16진수   
   
// 예시   
// - 2진수 1110100101.0011111<sub>2</sub> → 8진수 3645.174<sub>8</sub>   
- Example   
  - Binary 1110100101.0011111<sub>2</sub> → Octal 3645.174<sub>8</sub>   
   
|Binary system|011|110|100|101|.|001|111|100|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Octal system|3|6|4|5|.|1|7|4|
   
// 예시   
// - 2진수 1110100101.0011111<sub>2</sub> → 16진수 7A5.3E<sub>16</sub>   
- Example   
  - Binary 1110100101.0011111<sub>2</sub> → Hexadecimal 7A5.3E<sub>16</sub>   
   
|Binary system|0111|1010|0101|.|0011|1110|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Hexadecimal|7|A|5|.|3|E|
   
<br />
### Integer representation   
// 정수 표현   
   
#### Integer representation method   
// 정수 표현 방법   
   
// 부호 없는 정수   
// - 부호 (+, -) 비트가 없음   
// - n비트 → 0 ~ 2<sup>n-1</sup>   
- An unsigned integer   
  - No sign (+, -) bit   
  - nbit → 0 ~ 2<sup>n-1</sup>   
   
// 부호 있는 정수   
// - 최상위 비트 ⇒ 부호 비트 (0 → 양수, 1 → 음수)   
// - 양의 정수는 모두 동일. 음의 정수는 서로 다른 형태를 가짐   
- A signed integer   
  - Highest bit ⇒ sign bit (0 → positive, 1 → negative)   
  - Positive integers are all the same. Negative integers have different forms   
   
|// 부호화-크기<br />sign and magnitude|// 1의 보수<br />ones' complement|// 2의 보수<br />two's complement|
|:---|:---|:---|
|// 절대값으로 표현<br />Expression in absolute value|// 양수에 대한 보수로서 표현<br />Expression as complement for positive numbers|// (1의 보수 + 1) 로 음수 표현<br />Negative expression as (ones' complement + 1)|
|-(2<sup>n-1</sup>-1) ~ +(2<sup>n-1</sup>-1)|-(2<sup>n-1</sup>-1) ~ +(2<sup>n-1</sup>-1)|-2<sup>n-1</sup> ~ +(2<sup>n-1</sup>-1)|
|+0 (00000000)|+0 (00000000)||
|-0 (10000000)|-0 (11111111)||
   
#### An unsigned integer   
// 부호 없는 정수   
   
// 예시   
- Example   
   
|Example Numbers|115|275|
|:---:|:---:|:---:|
|binary conversion|1110011|100010011|
|n-bit allocation (n=8)|[0,1,1,1,0,0,1,1]|[overflow 1][0,0,0,1,0,0,1,1]|
   
#### A signed integer   
// 부호 있는 정수   
   
// n=8 비트인 경우  
- if n = 8bits   
   
// 예시   
// - 양수 124   
// -- [0(부호),1,1,1,1,1,0,0]   
// - 음수 -124   
// -- 부호화-크기 : 절대값 : [1(부호),1,1,1,1,1,0,0]   
// -- 1의 보수 : 0 → 1, 1 → 0 : [1(부호),0,0,0,0,0,1,1]   
// -- 2의 보수 : (1의 보수) + 1 : [1(부호),0,0,0,0,0,1,1] + 1 → [1(부호),0,0,0,0,1,0,0]   
- Example   
  - Positive 124   
    - [0(sign),1,1,1,1,1,0,0]   
  - Negative -124   
    - sign and magnitude : absolute value : [1(sign),1,1,1,1,1,0,0]   
    - ones' complement : 0 → 1, 1 → 0 : [1(sign),0,0,0,0,0,1,1]   
    - two' complement : (ones' complement) + 1 : [1(sign),0,0,0,0,0,1,1] + 1 → [1(sign),0,0,0,0,1,0,0]   
   
#### Application of two's complement method   
// 2의 보수 방식의 응용   
   
// 덧셈만 수행하는 컴퓨터에서는   
// A - B → B에 대한 2의 보수를 취한 후 덧셈 수행 → A + (-B)   
- In a computer that only performs addition   
- A - B → B after two's complement then performing addition → A + (-B)   
   
// 예시   
// - 24 - 17 → 00011000 - 00010001 → 17에 대한 2진수를 2의 보수로 처리 → 00011000 + 11101111 → 100000111 → 맨 앞의 1은 무시하고 나머지만 표기 00000111 → 7   
- Example   
  - 24 - 17 → 00011000 - 00010001 → Treat a binary number for 17 as two's complement → 00011000 + 11101111 → 100000111 → Ignore the first 1 and mark only the rest 00000111 → 7   
   
// 예시   
// - 8비트, 2의 보수 방식을 사용하여 표현한 이진수 10001100를 십진수로 표기하면?   
// -- 10001101 - 1 → 10001100   
// -- 10001100 → 2의 보수 계산 11110011 → 맨 앞자리 기호는 1이므로 -로 표기하고, 나머지는 십진수로 변환 → -115   
- Example   
  - What if the binary number 10001100 expressed using 8-bit and two's complement methods is expressed in decimal?   
    - 10001101 - 1 → 10001100   
    - 10001100 → Calculated with two's complement 110011 → Since the first digit symbol is 1, it is marked as -, and the rest is converted to a decimal number → -115   
   
<br />
### Real number representation   
// 실수 표현   
   
// 과학적 표기법을 활용한 부동소수점 방식으로 표현   
- Expression in a floating-point manner using scientific notation   
   
// 예시   
// - 1,234,000,000,000 → 과학적 표기법 1.234 x 10<sup>12</sup>   
// - -0.0000000005678 → 과학적 표기법 -5.678 x 10<sup>-10</sup>   
- Example   
  - 1,234,000,000,000 → scientific notation 1.234 x 10<sup>12</sup>   
  - -0.0000000005678 → scientific notation -5.678 x 10<sup>-10</sup>   
   
// 과학적 표기법 (-1)<sup>s</sup> x M x B<sup>E</sup>   
// - <sup>s</sup>는 부호를 결정. 0 또는 1   
// - M은 가수   
// - B는 기저   
// - <sup>E</sup>는 지수   
- scientific notation (-1)<sup>s</sup> x M x B<sup>E</sup>   
  - <sup>s</sup> determines the sign. 0 or 1   
  - M is the mantissa (fraction/mantissa)   
  - B is the basis   
  - <sup>E</sup> is the exponent   
   
// 컴퓨터에서 실수는 유효숫자를 사용하는 곱셈 형태의 과학적인 표기법으로 나타냄   
- In computers, real numbers are expressed in scientific notation in the form of multiplication using significant numbers   
   
// 예시   
- Example   
   
||1.234 x 10<sup>12</sup>|-5.678 x 10<sup>-10</sup>|
|:---:|:---:|:---:|
|sign S|0|1|
|mantissa M|1.234|5.678|
|basis B|10|10|
|exponent E|12|-10|
   
// 컴퓨터는 2진수를 사용하므로 과학적 표기법의 B에 2를 대입 (-1)<sup>s</sup> x M x 2<sup>E</sup>   
// - <sup>s</sup>는 부호를 결정. 0 또는 1   
// - M은 가수   
// - <sup>E</sup>는 지수   
// 비트 표현 시 부호, 지수, 가수 순으로 표현   
// - 부호 1비트, 지수 m비트, 가수 n비트   
// - 지수와 가수의 비트수는 시스템을 사용하는 목적에 따라서 시스템을 설계하는 사람이 결정함   
// -- 지수 : 지수를 크게 하면 수의 범위가 넓어짐   
// --- 초과표기법 excess notation에 대해 알아야 지수를 표현할 수 있음   
// -- 가수 : 가수를 크게 하면 유효숫자의 자리수가 많아지고 정밀도가 높아짐   
// --- 정규화 normalization에 대해 알아야 가수를 표현할 수 있음   
- Computers use binary digits, so substitute 2 into B in scientific notation (-1)<sup>s</sup> x M x 2<sup>E</sup>   
  - <sup>s</sup> determines the sign. 0 or 1   
  - M is the mantissa (fraction/mantissa)   
  - <sup>E</sup> is the exponent   
- When expressing a bit, it is expressed in the order of sign, exponent, and mantissa   
  - sign 1 bit, exponent m bit, and mantissa n bit   
  - The number of bits in the exponent and mantissa is determined by the person designing the system according to the purpose of using the system   
    - exponent : Increasing the exponent widens the range of numbers   
      - You need to know about the excess notation to express the exponent   
    - mantissa : Increasing the mantissa increases the number of significant digits and increases precision   
      - You need to know about normalization to express the mantissa   
   
#### Excess Notation   
// 초과표기법   
   
// 부동소수점 방식의 지수 부분만을 표현하기 위한 방법   
// - 매직 넘버   
// -- m비트 → 매직 넘버는 2<sup>m-1</sup> 또는 2<sup>m-1</sup>-1   
// --- m = 8 인 경우 → 매직 넘버는 2<sup>8-1</sup> = 2<sup>7</sup> = 128 ('초과_128') 또는 2<sup>8-1</sup>-1 = 2<sup>7</sup>-1 = 127 ('초과_127')   
- To express only the exponent part of the floating-point method   
  - Magic number   
    - mbit → magic number is 2<sup>m-1</sup> or 2<sup>m-1</sup>-1   
      - If m = 8, → magic number is 2<sup>8-1</sup> = 2<sup>7</sup> = 128 ('excess_128') or 2<sup>8-1</sup>-1 = 2<sup>7</sup>-1 = 127 ('excess_127')   
   
// 예시   
// - (-1)<sup>0/1</sup> x 1010.0011 x 2<sup>-32</sup> 를 표기하는 방법   
// -- 1비트 (부호) + 지수 (8비트) + 가수 (n비트)   
// --- 1비트 (부호) 자리에 0 또는 1 표기   
// --- 지수 (8비트) 자리에는   
// ---- 매직넘버를 127을 사용하는 경우   
// ---- 지수 <sup>-32</sup> + 매직넘버 127 = 95 → 십진수 95를 이진수로 변환 01011111   
// ---- 이진수로 변환된 값 01011111을 지수 (8비트) 자리에 표기   
// --- 가수 (n비트) 자리에는 정규화를 이용하여 표기   
- Example   
  - How to mark (-1)<sup>0/1</sup> x 1010.0011 x 2<sup>-32</sup>   
    - 1 bit (sign) + exponent (8 bit) + mantissa (n bit)   
      - Mark 0 or 1 in 1 bit (sign) place   
      - In the exponent (8 bit) position   
        - If the magic number is 127   
        - Exponent <sup>-32</sup> + Magic Number 127 = 95 → Decimal 95 converted to binary 01011111   
        - Binary converted value 01011111 in exponential (8-bit) digits   
      - Use normalization to mark in the mantissa (n-bit) position   
   
#### Normalization   
// 정규화   
   
// 가수를 표현할 때 표준화된 형식이 필요   
- Need a standardized format for expressing mantissa   
   
// 예시   
- Example   
  - -1010.00110011 x 2<sup>3</sup>   
  - -10.1000110011 x 2<sup>5</sup>   
  - -101000110.011 x 2<sup>-2</sup>   
  - -0.101000110011 x 2<sup>8</sup>   
    - → Normalization 1.01000110011 x 2<sup>6</sup>   
   
// 예시   
- Example   
  - 0.0000011011 x 2<sup>0</sup> → Normalization 1.1011 x 2<sup>-6</sup>   
  - 10111010.0101 x 2<sup>0</sup> → Normalization 1.01110100101 x 2<sup>7</sup>   
   
#### An example of a real number representation   
// 실수 표현의 예   
   
// 예시   
// - 60.6875   
// - 총 4바이트 : 부호 1비트, 지수 8비트 (매직넘버 초과_127), 가수 23비트   
// -- → 부호 1비트는 양수이므로 0 표기   
// -- → 60.6875의 정수 부분과 소수 부분을 각각 2진수로 계산하여 연결 111100.1011   
// -- → 2진수 실수 111100.1011를 정규화 1.111001011 x 2<sup>5</sup>   
// -- → 매직넘버 127 + 지수 5 = 132를 2진수로 변환하여 지수 10000100 표기   
// -- → 1.111001011 중 소수점 밑의 부분만 가수 111001011 표기. 가수의 나머지 빈 비트는 모두 0으로 채움   
// - ∴ 최종 비트 표기 [0(부호),10000100(지수),11100101100000000000000(가수)]   
- Example   
  - 60.6875   
  - 4 bytes in total : sign 1 bit, exponent 8 bits (magic number excess_127), mantissa 23 bits   
    - → 1 bit of sign is positive, so 0 notation   
    - → Connect the integer and decimal parts of 60.6875 by calculating them as binary digits, respectively 111100.1011   
    - → Binary real number 111100.1011 normalized 1.111001011 x 2<sup>5</sup>   
    - → Magic number 127 + exponent 5 = Convert 132 to binary to exponent 10000100   
    - → Only the part below the decimal point is marked with "mantissa 111001011." All the remaining empty bits of the mantissa are filled with zero   
  - ∴ Final bit notation [0(sign),10000100(exponent),11100101100000000000000(mantissa)]   
   
#### IEEE Floating Point Standard Format   
// IEEE 부동소수점 방식의 표준 형식   
   
// 단정도 single precision : 4바이트   
// - 부호 1비트, 지수 8비트 (매직넘버 초과_127), 가수 23비트   
// 배정도 double precision : 8바이트   
// - 부호 1비트, 지수 11비트 (매직넘버 초과_1023), 가수 52비트   
- single precision : 4bytes   
  - 1 bit of sign, 8 bit of exponent (magic number excess_127), 23 bit of mantissa   
- double precision : 8bytes   
  - 1 bit of sign, 11 bit of exponent (magic number excess_1023), 52 bit of mantissa   
   
<br />
### Textual representation   
// 문자 표현   
   
// 키보드를 통해 입력되는 문자로 2진수로 표현되어 처리   
// - 각 문자마다 유일한 값으로써 코드를 할당할 수 있는 약속된 문자 체계가 필요   
- Characters entered through the keyboard in binary terms and processed   
  - Requires a promised character system that allows each character to allocate code as a unique value   
   
// 문자 체계의 종류   
// - ASCII, 유니코드, ...   
- Types of Character Systems   
  - ASCII, Unicode, ...   
   
#### ASCII (American Standard Code for Information Interchange)   
// 아스키코드   
   
// 미국표준협회 (ANSI)   
// 7비트 코드 : 128개 (2<sup>7</sup>) 의 서로 다른 문자 표현   
- American National Standards Institute (ANSI)   
- 7-bit code : 128 (2<sup>7</sup>) different character representations   
   
// 확장된 아스키 Extended ASCII : 1비트 + 7비트   
// - 1비트 : 0 또는 패러티 비트를 표기   
// -- 패러티 비트 (parity bit) : 데이터 전송 시 전송상의 오류가 발생하는 경우 오류를 검출하기 위한 용도로 사용   
// --- 짝수 패러티 : 전송할 데이터 안에 있는 1의 개수를 짝수로 만들어줌. 예시 1001100 → 11001100   
// --- 홀수 패러티 : 전송할 데이터 안에 있는 1의 개수를 홀수로 만들어줌. 예시 1001100 → 01001100   
- Extended ASCII : 1 bit + 7 bit   
  - 1 bit : 0 or parity bit   
    - parity bit : Used to detect errors when transferring data occurs   
      - Even Parity : Makes the number of 1s in the data to be transmitted even. Example 1001100 → 11001100   
      - Odd Parity : Makes the number of 1s in the data to be transmitted an odd number. Example 1001100 → 01001100   
   
#### Unicode   
// 유니코드   
   
// 세계의 모든 문자를 컴퓨터에서 일관되게 표현하고 다룰 수 있도록 설계된 산업 표준   
// - 1990년 애플 컴퓨터, IBM, MS 등의 컨소시엄으로 설립한 유니코드 (Unicode) 가 첫 버전 발표   
// -- 1995년 국제 표준으로 제정. 공식명칭은 ISO/IC 10646-1   
// -- 사용중인 플랫폼, 프로그램, 언어에 무관   
// -- 16비트 코드 체계   
// -- 65,636개 (2<sup>16</sup>의 서로 다른 문자 표현)   
- Industry standards designed to consistently represent and handle all characters in the world on a computer   
  - Unicode, which was established in 1990 as a consortium of Apple computers, IBM and Microsoft, announced its first version   
    - Established as an international standard in 1995. The official name is ISO/IC 10646-1   
    - Regardless of platform, program, or language   
    - a 16-bit code scheme   
    - 65,636 (2<sup>16</sup> different character representations)   
   
#### EBCDIC (Extended Binary Coded Decinal Interchange Code)   
   
// IBM 개발   
// 8비트 코드   
// 실제 사용되는 문자 코드는 127개   
// IBM 메인프레임에서만 사용   
- IBM Development   
- 8-bit code   
- 127 text codes are actually used   
- Use only in IBM mainframe   
   
#### BCD (Binary Coded Decimal)   
   
// 4비트로 구성된 열 개의 코드로 10진수를 표현   
// 8421 코드   
- Ten 4-bit codes represented decimal numbers   
- 8421 Code   
   
// 예시   
// - 십진수 295를 비트로 표기하면 [0010][1001][0101]   
- Example   
  - Decimal 295 in bits is [0010][1001][0101]   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
