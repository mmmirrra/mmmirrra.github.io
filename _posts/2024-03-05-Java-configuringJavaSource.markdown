---
layout: post
title:  "Java: Configuring Java Source"
date:   2024-03-05 09:00:00 +0900
categories: [Java]
---

### Comment   
// 주석   
   
```java
/* ... */
// 실행과 무관함
- Not related to running
```
   
```java
/** ... */
// 소스 코드 맨 앞에 전반적 설명을 작성하는 주석이며, 자동으로 소스 코드의 매뉴얼 생성을 가능하게 함
// Javadoc 명령
- Comment that creates an overall description at the beginning of the source code, which enables the creation of a source code manual automatically
- Javadoc Command
```
   
```java
// ...
// 같은 라인에서 이후에 나오는 내용은 실행과 무관함
- What follows from the same line is irrelevant to running
```
   
<br />
### Class definition, the format of the main() method   
// 클래스 정의와 main() 메소드의 형식   
   
// main() 메소드의 형식은 정해져 있는 그대로 작성해야 함   
The format of the main() method must be written as it is   
   
```java
package com;

public class Main {
    public static void main(String[] args) {
        // ...
    }
}
```
   
// public class의 이름이 A이면, A.java 파일에 저장되어야 함   
If the name of the public class is A, it must be saved in the A.java file   
   
```java
package Apkg;

public class A {
    ...
}
```
   
<br />
### Java Application Simple Example   
// 간단한 Java 어플리케이션 예제   
   
#### Hello Application   
// Hello 어플리케이션   
   
// 1. Java 소스 작성   
// - 대소문자 구분됨   
// - 주석, public class, main() 메소드, 출력문을 가진 프로그램   
// 이 파일의 이름은 'Main.java' 임   
   
1 . Create Java source   
- Case sensitive   
- Program with comment, public class, main() method, and output statement   
This file is named 'Main.java'   
   
```java
package com;

/**
 * The Hello class implements an application that
 * simply prints "Hello, Java Application!" to standard output.
 */
public class Main {
    public static void main(String[] args) { // main method
        /* Display the string */
        System.out.println("Hello, Java Application!");
    }
}
```
   
// 2. 실행   
// - 실행 버튼 선택하여 실행 또는 'Run' 메뉴 선택하여 실행 또는 'Ctrl + F11' 눌러 실행   
   
2 . Run   
- Run by selecting the Run button or by selecting the 'Run' menu or by pressing 'Ctrl + F11'   
   
// 3. 배포   
// - 개발된 Java 프로그램을 묶어서 외부에서 실행 가능하게 내보내는 것   
// -- 실행에 필요한 클래스 파일을 묶어서 .jar 파일을 만들 수 있음   
// - 프로젝트에서 마우스 오른쪽 버튼으로 'Export...' 선택   
// -- export 유형 (Runnable JAR file), jar 파일의 경로와 이름 등을 지정   
// - 명령프롬프트에서 jar 파일 실행   
   
3 . Export   
- To bundle and export a developed Java program so it can run externally   
  - Create .jar file by grouping the class files required to run   
- Right-click on Project to select 'Export...'   
  - Specify the export type (Runnable JAR file), path and name of the jar file, etc   
- Execute jar file from command prompt   
   
```cmd
C:\Java>dir 디렉터리
2024-01-11  오후 11:15  <DIR>   .
2024-01-11  오후 11:15  <DIR>   ..
2024-01-11  오후 11:15      768 my_project.jar
            1개 파일        768 바이트
            2개 디렉터리        23,705,800,704 바이트 남음
C:\Java>java -jar my_project.jar
Hello, Java Application!

C:\Java>
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
