---
layout: post
title:  "Java: Concept"
date:   2024-03-03 09:00:00 +0900
categories: [Java]
---

### Java Language Overview   
// Java 언어 개요   
   
#### Origin of Java Language   
// Java 언어의 기원   
   
// Java를 개발한 사람은 Sun Microsystems 회사의 제임스 고슬링(캐나다의 컴퓨터 과학자)   
// 1990년 그린 프로젝트(소비자용 전자제품의 제어박스 개발 프로젝트 - 하드웨어 플랫폼과 무관하게 동작하는 언어 필요)에서 Oak Language 개발. Oak 언어가 Java로 개명됨   
// 1995년 Java와 HotJava(Java 기반의 웹 브라우저) 발표   
// - www 웹의 확산과 함께 주목을 받음   
// 1996년 1월 JDK 1.0 발표 (JDK는 Java Development Kit 줄임말)   
// - 1998년 Java2 SDK, SE 1.2 (J2SE 1.2부터 Java2라고 함. SE는 Standard Edition 표준판 줄임말)   
// - 2014년 Java Platform(JDK) SE 8   
// - 2023년 9월 Java SE 21 발표   
// 2009년 Oracle이 Sun을 인수함   
- It was James Gosling from Sun Microsystems who developed Java (Canadian computer scientist)   
- Development of Oak Language in the 1990 Green Project (Project to Develop Control Boxes for Consumer Electronics - required a language that operated independently of the hardware platform). Oak Language Renamed to Java   
- 1995 Java and Hot Java (Java-based Web Browser) Announced   
  - With the proliferation of www web, Java also gained attention   
- JDK 1.0 released in January 1996 (JDK stands for Java Development Kit)   
  - 1998 Java2 SDK, SE 1.2 (J2SE 1.2 is referred to as Java2. SE stands for Standard Edition)   
  - 2014 Java Platform (JDK) SE 8   
  - Java SE 21 Announced in September 2023   
- Oracle Acquired Sun in 2009   
   
#### Characteristics of Java Language   
// Java 언어의 특징   
   
// 운영체제와 무관하고 하드웨어 플랫폼에 독립적   
// 완전한 객체지향 프로그래밍 언어   
// 데스크톱 응용 외에 웹 또는 네트워크 프로그래밍이 용이   
// 변수 등의 사용에 있어서 엄격한 자료형의 검사   
// 예외 처리 기능 제공   
// 멀티 스레딩 지원   
- Independent of operating system and independent of hardware platform   
- Perfect object-oriented programming language   
- Can program the web or network in addition to desktop applications   
- a rigorous examination of data types in the use of variables   
- Provides exception handling capabilities   
- Multi-threading support   
   
#### Java Platform   
// Java 플랫폼   
   
// Java 플랫폼은 Java 프로그램의 개발과 실행을 위한 환경   
// 사용중인 운영체제에 맞는 Java 플랫폼을 설치해야 함   
// JDK에 Java 플랫폼이 포함되어 있음   
- Java platform is an environment for the development and execution of Java program   
- Install the Java platform based on the operating system used   
- JDK contains Java platform   
   
// C 프로그램과 Java 프로그램의 차이점   
Differences between C and Java program   
   
|C|Java|
|:---:|:---:|
|<br /><br /><br />Application written with C<br />program.c<br />-------------<br />Operating System<br />(Windows, UNIX, OS X, etc..)<br />-------------<br />Computer System<br />(Hardware)|Application written with Java<br />program.java<br />-------------<br />Java Platform<br />(Java VM, API)<br />-------------<br />Operating System<br />(Windows, UNIX, OS X, etc..)<br />-------------<br />Computer System<br />(Hardware)|
   
#### Configuring Java Platforms   
// Java 플랫폼의 구성   
   
Java VM (Virtual Machine)   
// Java 프로그램의 실행 환경을 제공하는 가상 기계   
// 소프트웨어 플랫폼   
// Java 프로그램의 구동 엔진   
// 실행에 필요한 사항을 관리   
// 메모리 정리를 자동으로 수행   
- Virtual machines that provide the execution environment for Java program   
- Software Platform   
- Java program's drive engine   
- Managing what's needed to run a program   
- Automatically clean up memory   
   
Java API (Application Programming Interface)   
// 프로그램의 개발에 필요한 클래스 라이브러리   
// 패키지(클래스 묶음)들이 계층 구조로 분류되어 있음   
- Class libraries required for program development   
- Packages (class bundles) are categorized into hierarchical structures   
   
#### Running Java Program   
// Java 프로그램의 실행   
   
Java Source File (HelloWorld.java) → Compiler → Java bytecode (HelloWorld.class) → Java VM → Running a Program (Running HelloWorld)   
   
// Java 소스와 바이트코드   
// - Java 소스는 파일 확장자가 .java   
// - 바이트코드는 파일 확장자가 .class인 파일 (클래스 파일)   
// -- Java 소스를 컴파일한 결과물   
// -- Java 플랫폼의 Java VM에서 실행 가능한 코드   
- Java source and bytecode   
  - Java source has a file extension of .java   
  - Bytecode has a file extension of .class (class file)   
    - Results from compiling Java sources   
    - Code executable on Java VM on Java platform   
   
<br />
### Object-Oriented Programming   
// 객체지향 프로그래밍   
   
#### Class and Object   
// 클래스와 객체   
   
// 추상화   
// - 구체적인 모든 사실이 아니라 전형적이고 필요한 부분만을 추려서 사물을 이해하고 표현하는 것   
- Abstraction   
  - To understand and express things by selecting only typical and necessary parts, not all specific facts   
   
// 클래스   
// - 추상화 과정의 결과가 클래스임   
// - 클래스는 객체를 만들기 위한 모형 또는 틀   
// - 공통적인 특징을 가지는 객체들을 추상화하기 위한 수단   
// - 객체의 상태는 필드(데이터)로, 행위는 메소드로 구현됨   
// - 객체는 특정 클래스의 인스턴스임. 클래스의 변수 또는 클래스가 실체화 된 것   
- Class   
  - The result of the abstraction process is class   
  - Class are models or frameworks for creating objects   
  - means for abstracting objects with common characteristics   
  - Object states are implemented as fields (data) and actions are implemented as methods   
  - The object is an instance of a particular class. Object is a class's variable or class materialized   
   
#### Java Program and Class   
// Java 프로그램과 클래스   
   
// 클래스가 프로그램 구성의 기본 단위   
// 객체는 클래스로 만듦   
// 객체의 데이터(필드)와 객체의 기능(메소드)이 클래스 구조로 캡슐화되어 있음   
// 클래스 정의로부터 객체(인스턴스)들이 만들어지고 객체들 간의 상호작용으로 프로그램이 동작함   
- Class is the basic unit of program configuration   
- Create object with class   
- The object's data (fields) and the object's function (methods) are encapsulated in a class structure   
- Objects (instances) are created from class definitions and programs operate as interactions between objects   
   
#### Example of comparing a C Program with a Java Program - Grades Processing Program   
// C 프로그램과 Java 프로그램의 비교 예제 - 성적처리 프로그램   
   
C Program   
   
```c
#include <stdio.h>
int e[2];                 // Variables for English Grade
int m[2];                 // Variables for Math Grade

void input_grade()         // a function that receives English and Math grades
{
  e[0] = 90;              // the first student's English grade
  e[1] = 80;              // the second student's English grade
  m[0] = 85;              // the first student's Math grade
  m[1] = 80;              // the second student's Math grade
}

void output_grade()        // a Function that output total grade
{
  printf("%d,%d", e[0] + m[0], e[1] + m[1]);
}

void main(void) 
{
  input_grade();
  output_grade();
}
```
   
Java Program   
   
```java
class Grade {
  int e;                  // Variables for English Grade
  int m;                  // Variables for Math Grade

  void output_grade()     // a method of calculating the sum of grades
  {
    System.out.println(e + m);
  }
}

public class Main {
  public static void main(String[] args) {
    Grade g1, g2;           // Object for expressing the grades of two people
    g1 = new Grade();       // Creating objects
    g2 = new Grade();
    g1.e = 90;              // Enter the grade
    g1.m = 85;
    g2.e = 80;
    g2.m = 80;

    g1.output_grade();
    g2.output_grade();
  }
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
