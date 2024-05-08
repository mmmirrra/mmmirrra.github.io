---
layout: post
title:  "C: Preprocessor"
date:   2024-05-06 09:00:00 +0900
categories: [C]
---

### Preprocessor   
// 선행처리기   
   
// 컴파일에 앞서 프로그램 선두에 선언된 지시자들을 미리 처리하는 역할을 수행   
- Preprocesses the indicators declared at the beginning of the program prior to compilation   
   
#### Types of Preprocessors   
// 선행처리기의 종류   
   
|Preprocessor|Function|
|:---|:---|
|#include|Include files|
|#define|Macro Definition|
|#if, #else, #elif, #endif|Conditional compilation|
   
#### What to watch out for when using a preprocessor   
// 선행처리기를 사용할 때 주의할 점   
   
// 반드시 '#'으로 시작해야 함   
// 명령문 끝에는 세미콜론 ( ; ) 을 붙이지 않음   
// 한 줄에 하나의 명령만 씀   
// 소스 프로그램의 첫 부분에 위치함   
- Must start with '#'   
- Do not put a semicolon ( ; ) at the end of the command   
- Only one command in a line   
- Located at the beginning of the source program   
   
<br />
### '#include'   
   
// '#include'는 C언어에서 제공되는 헤더파일 (*.h) 를 자신의 소스파일에 읽어 들여 함께 컴파일 하고자 할 때 사용   
- '#include' is used to read the header file (*.h) provided in the C language into one's own source file and compile it together   
   
// C 프로그램에서 표준함수인 printf(), scanf() 등을 사용하려면   
// - 이 함수들의 원형 (prototype) 이 선언되어 있는 표준 입출력 헤더파일인 'stdio.h'를 '#include' 시켜야 함   
- To use standard functions such as printf(), scanf(), etc. in a C program   
  - The standard I/O header file 'stdio.h' in which the prototype of these functions is declared must be '#include'   
   
// 형식   
- Formats   
   
```c
#include <File name>
#include "File name"
```
   
// 사용 예시   
- Examples of Use   
   
```c
#include <stdio.h>
#include "stdio.h"
#include "\tc\lib\math.h"
```
   
// 기능   
// - '#include' 다음에 제시된 파일을 현재 프로그램에 포함시킴   
// -- `<파일명>`은 표준 디렉토리 (보통 include 디렉토리) 에서 파일을 찾아 포함시킴   
// -- `"파일명"`은 현재 사용중인 디렉토리나 지정된 디렉토리에서 파일을 찾아 포함시키거나, 또는 드라이브나 경로를 사용   
- Function   
  - Include the file presented after '#include' in the current program   
    - `<File name>` finds and includes files in standard directories (usually include directory)   
    - `"File name"` refers to finding and including files in the current or designated directory, or using a drive or path   
   
<br />
### '#define'   
   
// '#define'은 매크로를 정의할 때 사용   
- '#define' is used to define macros   
   
// 매크로   
// - 선행처리기 '#define'을 사용하여 단순 치환되는 자료   
// - 프로그램 작성 시에 명령이나 수식 또는 상수값이 자주 사용될 때 이들을 대표하는 이름을 붙여 사용하는 대상   
- macro   
  - Data that is simply replaced using preprocessor '#define'   
  - When commands, expressions, or constant values are frequently used when writing a program, they are named to represent them   
   
// 매크로 정의   
// - 매크로 상수 정의   
// - 매크로 함수 정의   
- Macro Definition   
  - Macro Constant Definition   
  - Macro Function Definition   
   
#### Macro Constant Definition   
// 매크로 상수 정의   
   
// 형식   
- Formats   
   
```c
/* Define macro constants : #define macroName data
   Undefining macro constants : #undef macroName */
/* 
   */
#define macroName data
#undef macroName
```
   
// 사용 예시   
- Examples of Use   
   
```c
#define PI 3.141592
// 이는 프로그램 내의 PI는 3.141592로 치환하라는 것
// This means that PI in the program should be replaced by 3.141592
```
   
// 기능   
// - 프로그램에 나오는 매크로명을 지정한 자료로 치환한 후 컴파일하거나 ('#define'), 정의를 해제('#undef') 라 함   
- Function   
  - Compile after replacing the macro name in the program with the specified data ('#define'), or undefined ('#undef')   
   
- Example   
   
```c
#include <stdio.h>
#define ARRD "seoul jongro 86"
#define TEL "o1o-1111-oooo"

void main() {
    printf("address : %s \n", ADDR);
    printf("phone : %s \n", TEL);
}
```
   
- Result   
   
```
address : seoul jongro 86
phone : o1o-1111-oooo
```
   
#### Macro Function Definition   
// 매크로 함수 정의   
   
// 형식   
- Formats   
   
```c
#define macroName(argument) (expression)
#define macroName(argument, argument) (expression)
```
   
// 사용 예시   
- Examples of Use   
   
```c
#define AREA(x) (3.141592*(x)*(x))
#define Hap1(x,y) x+y
```
   
// 장점   
// - 선행처리기에 의한 단순 치환 방식이므로, 전달 인자의 자료형을 명시할 필요가 없고, 또 어떠한 자료형 변수를 인자로 전달해도 잘 동작함   
// - 한 두 줄의 코드인 경우 함수로 정의하는 것보다 속도가 빠름   
- Strength   
  - Since it is a simple substitution method by a preprocessor, there is no need to specify the data type of the transfer argument, and it works well no matter what data type variable is delivered as a argument   
  - For a line or two of code, it is faster than it is defined as a function   
   
- Example   
   
```c
#include <stdio.h>
#define Hap1(x,y) x+y
#define Hap2(x,y) ((x)+(y))
#define Gop1(x,y) x*y
#define Gop2(x,y) ((x)*(y))

void main() {
    int h1, h2, g1, g2;
    h1 = 10 * Hap1(3, 4);
    h2 = 10 * Hap2(3, 4);
    g1 = Gop1(1 + 2, 3 + 4);
    g2 = Gop2(1 + 2, 3 + 4);
    printf("h1=%d, h2=%d\n", h1, h2);
    printf("g1=%d, g2=%d\n", g1, g2);
}
```
   
- Result   
   
```
h1=34, h2=70
g1=11, g2=21
```
   
<br />
### '#if, #else, #elif, #endif'   
   
// 조건에 따라 프로그램을 컴파일하는 명령   
// 최적의 코드로 프로그램을 작성할 수 있기 때문에 시스템의 성능 향상   
- Commands to compile programs according to conditions   
- Improve system performance by allowing programs to be written with optimal code   
   
// '#if, #elif' 다음에는 컴파일 여부를 결정하는 조건문 필요   
// - 조건문은 선행처리과정에서 진위 여부를 판단할 수 있어야 함   
// - 변수 지정이나 함수 호출 불가   
// - 주로 매크로 값이 사용   
- '#if, #elif' requires a conditional statement to determine whether to compile or not   
  - Conditional statements must be able to determine authenticity in the preprocessor   
  - Unable to specify variables or call functions   
  - Mainly macro values are used   
   
- Example   
   
```c
#include <stdio.h>
#define CONDITION 1

void main() {
#if CONDITION
    printf("\n Compiling Program A \n");
#else
    printf("\n Compiling Program B \n");
#endif
}
```
   
// 조건이 참이므로 실제 컴파일 되는 프로그램은   
- Because the condition is true, the program that is actually compiled is   
   
```c
void main() {
    printf("\n Compiling Program A \n");
}
```
   
- Result   
   
```
Compiling Program A
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
