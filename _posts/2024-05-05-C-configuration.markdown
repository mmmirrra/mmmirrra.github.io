---
layout: post
title:  "C: Configuration of C program"
date:   2024-05-05 09:00:00 +0900
categories: [C]
---

### Basic Structure of C Program   
// C 프로그램의 기본 구조   
   
// 도입부 + main() 함수 + 호출된 함수()   
- Introduction + main() function + called function ()   
   
// 도입부   
// - 프로그램 전체에 적용되는 사항을 기술   
- Introduction   
  - Describe what's applicable throughout the program   
   
// main() 함수   
// - main() 함수는 가장 먼저 호출되는 함수로서 모든 프로그램에 반드시 존재   
- main() function   
  - The main() function is the first function to be called and must exist in all programs   
   
```c
void main()
{
    declaration statement
    substitution statement
    control statement
    function call
    ...
}
```
   
// 호출된 함수()   
// - main() 함수에서 호출되는 함수에 대한 정의   
- called function ()   
  - Definition of the function called in the main() function   
   
```c
called function ()
{
    ...
}
```
   
<br />
### Characteristics of C Program Basic Structure   
// C 프로그램 기본 구조의 특성   
   
// C 프로그램은 반드시 하나 이상의 함수를 포함해야 함   
// main() 함수가 반드시 존재해야 함   
// 함수의 시작과 끝을 알리는 중괄호 {} 를 사용해야 함   
// 중괄호 안에는 변수선언문, 치환문, 연산문, 함수 등의 명령을 기입해야 함   
// 선행처리기 (preprocessor) 를 제외하고 문장의 끝에는 세미콜론 (;) 을 붙임   
- C program must contain at least one function   
- main() function must exist   
- C programs must use brackets {} to indicate the beginning and end of a function   
- In brackets, commands such as variable declarations, substitution statements, operations statements, functions, etc. must be entered   
- Put a semicolon (;) at the end of the sentence except for the preprocessor   
   
<br />
### Components of Program C   
// C 프로그램의 구성 요소   
   
// 예약어 : int, char, if, for, ...   
// 명칭 : 변수, 배열, 함수, ... 등의 이름   
// 상수 : 값이 불변인 자료   
// 연산자 : =, -, *, /, ++, ...   
// 설명문 (주석문) : 프로그램에 대한 주석   
- Reserved word : int, char, if, for, ...   
- Identifier : Identifier of variable, array, function, ..., etc...   
- Constant : Data with a constant value   
- Operators : =, -, *, /, ++, ...   
- Comment : Comment on the program   
   
#### Reserved word   
// 예약어   
   
// 자료형 관련 예약어   
// - char, int, float, short, long, double, unsigned, union, enum, void, ...   
// 기억 관련 예약어   
// - auto, static, extern, register, ...   
// 제어 관련 예약어   
// - if ~ else, for, while, do ~ while, switch ~ case, break, continue, return, ...   
// 기타 예약어   
// - main, sizeof, include, ...   
- Reserved word related to data types   
  - char, int, float, short, long, double, unsigned, union, enum, void, ...   
- Reserved word related to memory   
  - auto, static, extern, register, ...   
- Reserved word related to control   
  - if ~ else, for, while, do ~ while, switch ~ case, break, continue, return, ...   
- Other reserved words   
  - main, sizeof, include, ...   
   
#### Identifier   
// 명칭   
   
// 명칭을 만들 때의 규칙   
// - 영문자와 숫자의 조합으로 만듦   
// - 명칭의 첫 문자는 영문자나 밑줄 ( _ ) 이어야 함   
// - 특수문자를 사용해서는 안됨 (단, 밑줄 ( _ ) 사용 가능)   
// - 문자 사이에 공백이 있어서는 안됨   
// - 예약어를 사용할 수 없음   
// - 영문자 대문자와 소문자는 서로 구별하여 사용함   
// - 명칭의 길이는 컴파일러에 따라 차이가 있음 (일반적으로 32자까지 인식 가능)   
- Rules for naming names   
  - Made from a combination of English letters and numbers   
  - The first letter of the name must be English or underscore ( _ )   
  - Do not use special characters (but underline ( _ ) is available)   
  - There must be no spaces between characters   
  - Reservation word not available   
  - Use uppercase and lowercase letters separately   
  - The length of the name varies depending on the compiler (usually up to 32 characters)   
   
// 사용자 정의 명칭의 예   
- Example of a custom name   
   
|correct name|notes|
|:---:|:---|
|sun10|English and numeric combinations available|
|SUN10|Name different from sun10|
|For|Different from the reserved word for|
|_sum|Underline ( _ ) Available|
   
|misnomer|notes|
|:---:|:---|
|2m|Can't start with numbers|
|KBS@TV|Special characters not allowed|
|for|Reservation word unavailable|
|SUN 10|Spaces between characters not allowed|
   
#### Constant   
// 상수   
   
// 수치 상수, 문자 상수, 문자열 상수   
- numerical constant, character constant, string constant   
   
#### Operators   
// 연산자   
   
// 연산자를 사용하여 각종 연산 수행   
// 다른 언어에 비해 많은 연산자   
- Performing various operations using operators   
- More operators than other languages   
   
#### Comment   
// 설명문 (주석문)   
   
// 여러 줄에 걸친 설명문을 넣기 위해서는 `/*` 와 `*/`을 사용   
// 한 줄짜리 설명문을 넣기 위해서는 보통 `//`을 사용   
// 프로그램의 어느 부분에도 위치할 수 있음   
// 2개 이상의 라인으로 계속될 수 있음   
- Use `/*` and `*/` to put multiple lines of comment   
- Usually `//` is used to put a single-line explanation   
- Can be located in any part of the program   
- Can continue with more than one line   
   
```c
/* A program that receives two numbers, 
adds them, and outputs them */
#include <stdio.h>
void main() {
    int x, y, sum;    // variable declaration
    /* Enter variables x, y */
    scanf("%d ", &x);
    scanf("%d ", &y);
    // Add two numbers and store them in the variable sum
    sum = x + y;
    /* Output the results to the screen */
    printf("sum = %d ", sum);
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
