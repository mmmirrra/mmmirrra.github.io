---
layout: post
title:  "Programming Language Theory: Program Operation Principles"
date:   2024-03-30 09:00:00 +0900
categories: [Programming Language Theory]
---

### Computer Structure and Program Operation Principles   
// 컴퓨터 구조와 프로그램 동작 원리   
   
#### Computer structure   
// 컴퓨터 구조   
   
// CPU와 메모리, 저장장치 등이 BUS로 연결   
// 다양한 입출력 장치도 BUS에 연결될 수 있음   
- CPU, memory, storage, etc. connect to BUS   
- Various I/O devices can also be connected to the BUS   
   
#### Principles of Computer Operation   
// 컴퓨터 동작 원리   
   
// 전원 : 운영체제 적재(저장장치 → 메모리) → 수행   
// CPU는 인출-해석-실행 주기를 반복하여 메모리의 명령어를 실행   
- Power : Load the operating system (storage device → memory) → Running   
- The CPU running instructions in memory by repeating the read-interpret-execute cycle   
   
<br />
### Why programming language implementation is necessary   
// 프로그래밍 언어 구현이 필요한 이유   
   
#### Machine language   
// 기계어   
   
// CPU가 이해하고 수행하는 명령어   
// 이진수 형태의 명령어를 사람이 이해하는 것은 매우 난해   
- Commands that the CPU understands and performs   
- It's very difficult for a person to understand a binary form of command   
   
#### Assembly   
// 어셈블리어   
   
// 기계어에 거의 일대일 대응하는 형태의 기호 언어   
// CPU에 종속적 → 이식성이 거의 0   
- Symbolic language in a nearly one-to-one correspondence to machine language   
- CPU dependent → Near zero portability   
   
#### High-level programming language   
// 고급 프로그래밍 언어   
   
// 사람에 가까운 표현으로 프로그램을 나타냄   
// 특정 기계에 종속적이지 않음   
// 프로그램을 CPU가 알아듣는 기계어로 표현해 주어야 함   
- representing a program in a close-to-human expression   
- Not dependent on a particular machine   
- The program must be expressed in machine language that the CPU understands   
   
// 소스 프로그램 : 프로그래머가 작성한 프로그램   
// 목적 프로그램 : 컴퓨터 하드웨어가 수행할 수 있는 프로그램   
- Source programs: Programs written by programmers   
- Purpose Program : Programs that computer hardware can perform   
   
<br />
### How the program implements the language   
// 프로그램이 언어의 구현 방법   
   
#### Interpreter   
// 인터프리터   
   
// 프로그래밍 언어로 작성된 고수준의 명령을 하나씩 해석하여 수행하는 프로그램   
// 인터프리터는 CPU의 인출-해석-실행 주기를 흉내 냄   
- A program that interprets and executes high-level commands one by one written in a programming language   
- Interpreter mimics the CPU's withdrawal-interpretation-execution cycle   
   
#### Compiler   
// 컴파일러   
   
// 프로그램을 CPU가 수행할 수 있는 형태로 바꾸어서 CPU가 실행   
// 인터프리터가 하는 해석 과정을 미리 모두 수행(효율적)   
// 상용 프로그램은 컴파일 방식으로 번역한 후 판매   
- CPU runs by changing the program to a form that the CPU can perform   
- Performs all the interpretation processes of the interpreter in advance (efficiently)   
- Commercial programs are translated into compilation and sold   
   
#### Hybrid Implementation   
// 하이브리드 구현   
   
// 인터프리터 방식과 컴파일러 방식을 조합한 방식   
// 중간코드까지 컴파일한 후 인터프리터를 통해 해석   
- A combination of interpreter and compiler methods   
- Compile up to intermediate code and interpret through interpreter   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
