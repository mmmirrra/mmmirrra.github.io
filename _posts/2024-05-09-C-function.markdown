---
layout: post
title:  "C: Function"
date:   2024-05-09 09:00:00 +0900
categories: [C]
---

### What is a function?   
// 함수란?   
   
// 함수란 특정한 작업 (기능) 을 수행하도록 설계된 독립적인 프로그램   
// 이러한 함수들이 정해진 순서에 따라 실행됨으로써 프로그램의 기능을 수행   
- A function is an independent program designed to perform a particular task (function)   
- Performs the function of the program by executing these functions in a predetermined order   
   
<br />
### Program C consists of functions   
// C 프로그램은 함수들로 구성   
   
// 전체의 실행 내용을 몇 개의 모듈 (module) 로 분류   
// 각각의 모듈에 해당하는 내용을 함수로 작성   
// 실행순서에 따라 그 함수들을 차례로 호출하여 실행   
- Classify the entire execution into several modules   
- Write the corresponding contents of each module as a function   
- Run the functions by calling them in order   
   
// 함수의 특성   
// - 함수들은 서로 자유로이 호출 가능   
// - 모든 함수는 서로 독립적   
- Characteristics of a function   
  - Functions can be called freely from each other   
  - All functions are independent of each other   
   
// 함수의 장점   
// - 프로그램의 수정이 용이함   
// - 함수 재사용으로 코드 중복을 최소화 함   
// - 프로그램의 기능을 한 눈에 파악할 수 있게 해줌으로써 유지관리가 쉬움   
- Strengths of a function   
  - Easy to modify programs   
  - Function reuse minimizes code redundancy   
  - Easy to maintain by providing a quick view of the program's functionality   
   
// 단위 프로그램을 하나의 함수에 기술한 경우   
// - 함수의 길이가 커짐   
// - 프로그램의 가독성 문제   
// - 수정의 어려움   
// - 일부분만 재호출 어려움   
- If a unit program is described in one function   
  - The length of the function increases   
  - Problems with the readability of the program   
  - Difficulty in modification   
  - Difficult to recall only part of   
   
<br />
### Function in the C language   
// C 언어에서의 함수   
   
// 표준함수 : C 언어 자체에서 제공하는 함수   
// 사용자 정의 함수 : 사용자가 정의하여 사용하는 함수   
- Standard Function : Functions provided by the C language itself   
- User-defined function : Functions defined and used by the user   
   
<br />
### Standard Function   
// 표준함수   
   
// 표준함수의 원형은 헤더파일에 정의   
// 표준함수의 실체는 라이브러리 파일에 수록   
// 표준함수를 사용하려면 원형이 선언되어 있는 헤더파일을 '#include' 시켜 주어야 함   
- The prototype of the standard function is defined in the header file   
- The substance of a standard function is included in the library file   
- To use the standard function, the header file in which the prototype is declared must be '#include'   
   
#### Example of a prototype of a standard function   
// 표준함수의 원형 예시   
   
// printf(), scanf() 함수의 원형   
// - 헤더파일에 정의되어 있음 : `stdio.h`   
// - 표준함수를 사용하려면 `stdio.h` 를 '#include' 시켜주어야 함   
- Prototype of printf(), scanf() function   
  - Defined in header file : `stdio.h`   
  - To use the standard function, `stdio.h` must be '#include'   
   
```c
int printf(const char *format, ...);
int scanf(const char *format, ...);
```
   
// sin(), cos() 함수의 원형   
// - 헤더파일에 정의되어 있음 : `math.h`   
// - 표준함수를 사용하려면 `math.h` 를 '#include' 시켜주어야 함   
- Prototype of sin(), cos() function   
  - Defined in header file : `math.h`   
  - To use the standard function, `math.h` must be '#include'   
   
```c
double sin(double x);
double cos(double x);
```
   
#### Example of a standard function in language C   
// C 언어에서의 표준함수 예시   
   
|Header File|Function Prototype Type|Example of a Function|
|:---:|:---|:---|
|stdio.h|Input/output Function|printf(), scanf(), getchar(), putchar(), ...|
|stdio.h|File related Functions|fopen(), fclose(), fprintf(), ...|
|conio.h|Console Input/Output Function|putch(), cputs(), cprintf(), getch(), getche(), cscanf(), ...|
|string.h|String processing Function|strcat(), strcmp(), strcpy(), strlen(), strncat(), strncpy(), ...|
|math.h|Mathematical Function|sqrt(), sin(), cos(), tan(), log(), exp(), pow(), abs(), asin(), acos(), atan(), cosh(), ...|
|ctype.h|Character form discrimination Function|isalpha(), isdigit(), islower(), ...|
|ctype.h|Character conversion Function|tolower(), toupper()|
|stdlib.h|Numerical transformation Function|atoi(), itoa()|
|stdlib.h|Function related to Random Number|rand(), srand()|
|stdlib.h|Sort/Alignment/Search Function|qsort(), lfind()|
   
#### Example 1 of using a standard function   
// 표준함수의 사용 예시 1   
   
```c
// 입출력 함수를 처리하기 위한 헤더파일
// Header file for processing input/output functions
#include <stdio.h>
// 수학 함수를 처리하기 위한 헤더 파일
// Header file for processing mathematical functions
#include <math.h>

void main() {
    double x1 = 12.34;
    int i1 = 5, j1 = 2;
    int a1, b1, c1;
    a1 = ceil(x1);
    b1 = floor(x1);
    c1 = pow(4, j1);

    // 절대값
    // Absolute value
    printf("abs(-5)=%d\n", abs(i1));

    // 주어진 값 이상의 최소 정수값
    // Minimum integer value greater than or equal to the given value
    printf("ceil(12.34)=%d\n", a1);

    // 코사인
    // Cosine
    printf("cos(10)=%f\n", cos(10));

    // 지수값
    // Exponent value
    printf("exp(2)=%.f\n", exp(j1));

    // 주어진 값 미만의 최대 정수값
    // Maximum integer value below the given value
    printf("floor(12.34)=%d\n", b1);
    printf("sqrt(2)=%5f\n", sqrt(j1));

    // X의 Y승 값
    // The Y-square root of X 
    printf("pow(4,2)=%d", c1);
}
```
   
- Result   
   
```
abs(-5)=5
ceil(12.34)=13
cos(10)=-0.839072
exp(2)=7
floor(12.34)=12
sqrt(2)=1.414214
pow(4,2)=16
```
   
#### Example 2 of using a standard function   
// 표준함수의 사용 예시 2   
   
```c
#include <stdio.h>
// 문자열 처리함수 (strlen) 를 위한 헤더파일
// Header file for string processing function (strlen)
#include <string.h>
// 문자형태 판별함수 (isalpha, isdigit) 를 위한 헤더파일
// Header file for character type discrimination functions (isalpha, isdigit)
#include <ctype.h>
#pragma warning(disable:4996)

void main() {
    int i2, alp2 = 0, no2 = 0, et2 = 0;
    char s2[20];
    printf("Enter a Character\n");
    scanf("%s", s2);
    // strlen() : 문자열 길이를 구하는 함수
    // strlen() : Function to find string length
    for (i2 = 0; i2 < strlen(s2); i2++) {
        // isalpha() : 영문자 여부를 판별하는 함수
        // isalpha() : Function to determine whether it is English or not
        if (isalpha(s2[i2]))
            alp2++;
        // isdigit() : 숫자 여부를 판별하는 함수
        // isdigit() : Function to determine whether it is Number or not
        else if (isdigit(s2[i2]))
            no2++;
        else
            et2++;
    }
    printf("Alphabet=%d\n", alp2);
    printf("Number=%d\n", no2);
    printf("ETC=%d", et2);
}
```
   
- Result   
   
```
Enter a Character KNOU1234567890-#*?$ [Enter]
Alphabet=4
Number=10
ETC=5
```
   
<br />
### User-defined function   
// 사용자 정의 함수   
   
// C 프로그램에서의 함수   
// - main() 함수 안에 표준함수를 사용하는 형태   
// - 그러나 동일 블록 내의 프로그램 길이가 길어지면 전체 프로그램은 복잡해지고 이해하기가 어려워짐   
// - 따라서 전체 프로그램을 짧은 길이의 단위 프로그램으로 나누어 정의함으로써 프로그램의 작성과 이해를 쉽게 할 필요가 있음   
- Functions in program C   
  - A form that uses a standard function within the main() function   
  - However, longer program lengths within the same block make the entire program more complex and harder to understand   
  - Therefore, it is necessary to make it easier to write and understand the program by dividing the entire program into short-length unit programs   
   
// 사용자 정의 함수   
// - 사용자가 단위 프로그램을 함수로 정의하여 사용   
- User-defined function   
  - User defines a unit program as a function and uses it   
   
#### Example of a user-defined function in a C program   
// C 프로그램에서 사용자 정의 함수의 예시   
   
```c
#include <stdio.h>
#pragma warning(disable:4996)

int sum3(int a3, int b3);

void main() {
    int x3, y3, c3;
    printf("Enter the number twice.\n");
    scanf("%d %d", &x3, &y3);

    printf("sum3(x3, y3)==%d\n", sum3(x3, y3));
    c3 = sum3(10, 20);
    printf("sum3(10, 20)==%d", c3);
}

int sum3(int a3, int b3) {
    int d3;
    d3 = a3 + b3;
    return(d3);
}
```
   
- Result   
   
```
Enter the number twice. 5 6 [Enter]
sum3(x3, y3)==11
sum3(10, 20)==30
```
   
<br />
### Definition of function   
// 함수의 정의   
   
#### Structure of function definition   
// 함수 정의의 구조   
   
```c
// 함수 헤더
// Header of a function
// 반환자료형 함수명 (자료형 매개변수 1, 자료형 매개변수 2, ...)
ReturnDataType functionName (dataType parameter 1, dataType parameter 2, ...)
// 함수 시작
// Start a function
{
    // 함수 몸체
    Body of a function
// 함수 끝
// end of function
}
```
   
- Example   
   
```c
int sum (int a, int b) {
    int d;
    d = a + b;
    return(d);
}
```
   
// 함수 헤더 (반환자료형)   
// - 함수에서 계산된 결과값을 호출한 함수에 되돌려 줄 때의 자료형   
// - 사용될 수 있는 자료형은 C 언어에서 사용 가능한 모든 자료형   
// - 생략이 가능하며, 생략할 경우 자료형은 int형으로 간주   
// - 반환값이 없는 함수인 경우는 void형으로 선언   
- Header of a function (Return data type)   
  - The data type when the result value calculated from the function is returned to the called function   
  - The data types that can be used are all data types available in language C   
  - It can be omitted, and if it is omitted, the data type is considered int type   
  - Declare void type if function with no return value   
   
// 함수 헤더 (함수명, 매개변수)   
// - 함수명   
// -- 변수명을 정하는 규칙과 동일한 방식으로 함수명을 정함   
// -- 의미 있는 함수명을 정하는 것이 함수를 이해하는데 도움을 줌   
// - 자료형과 매개변수   
// -- 자료형은 매개변수의 자료형을 나타냄   
// -- 매개변수는 호출 함수와 피호출 함수 사이에 자료를 주고받기 위해 사용   
// -- 매개변수는 해당 함수 내에서 변수처럼 사용   
// -- 매개변수가 여러 개일 경우에는 콤마 ( , ) 로 구분   
// -- 매개변수가 없으면 void형으로 사용   
- Header of a function (Function name, Parameter)   
  - Function name   
    - Specify function names in the same way as the rule for naming variables   
    - Setting a meaningful function name can help you understand the function   
  - Data type and parameter   
    - Data type represents the data type of a parameter   
    - Parameters are used to send and receive data between calling and called functions   
    - Use a parameter like a variable within that function   
    - Separate multiple parameters with a comma ( , )   
    - If there is no parameter, use it as void type   
   
// 함수 몸체   
// - 함수가 하는 일을 정의하는 부분   
// - 중괄호 ({ }) 를 이용하여 함수의 시작과 끝을 나타냄   
// - C 언어의 기본구조와 동일   
- Body of a function   
  - The part that defines what a function does   
  - Use brackets ({ }) to indicate the beginning and end of a function   
  - Same as the basic structure of the C language   
   
// main() 함수의 함수 몸체 예시   
// - 반환자료형에서 void는 반드시 명시 (생략 시 int로 처리)   
// - 매개변수 (void) 와 ( ) 는 동일한 의미   
- Example of body of a function of the main() function   
  - In return data type, voids must be specified (if omitted, treated as int)   
  - Parameters (void) and ( ) have the same meaning   
   
```c
// 반환자료형이 있는 경우 return값 명시
// Specify the return value if there is a return data type
int main(void) {
    printf("Definition of function\n");
    return(d);
}
```
   
```c
// 반환자료형이 void인 경우 return값 생략
// If the return data type is void, the return value is omitted
void main() {
    printf("Definition of function\n");
}
```
   
// 사용자 정의 함수의 함수 몸체 예시   
// - return 값 d는 sum 함수를 호출한 함수로 반환   
- Example of a function body of a user-defined function   
  - The return value d returns the sum function to the function it called   
   
```c
int sum (int a, int b) {
    // 함수 내에서 새로 사용되는 변수 선언
    // Declare a newly used variable within a function
    int d;
    d = a + b;
    // 값을 되돌려 줄 때 사용
    // Use to return value
    return(d);
}
```
   
<br />
### Use of a function   
// 함수의 사용   
   
// 함수를 사용하기 위해서는 아래와 같이 구성   
// ① 함수의 원형 선언   
// ② 함수의 호출   
// ③ 함수의 정의   
- To use the function, configure as below   
  ① Declaration of prototype of function   
  ② Function call   
  ③ Definition of function   
   
```c
#include <stdio.h>
#pragma warning(disable:4996)

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
int sum3(int a3, int b3);

void main() {
    int x3, y3, c3;
    printf("Enter the number twice.\n");
    scanf("%d %d", &x3, &y3);

    /* 2. 함수의 호출 */
    /* 2. Function call */
    printf("sum3(x3, y3)==%d\n", sum3(x3, y3));
    c3 = sum3(10, 20);
    printf("sum3(10, 20)==%d", c3);
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
int sum3(int a3, int b3) {
    int d3;
    d3 = a3 + b3;
    return(d3);
}
```
   
// 함수의 원형 선언   
// - 함수는 변수와 같이 사용되기 전에 미리 선언   
// - 함수의 원형 선언은 일반적으로 main() 함수 이전에 함   
// - 원형 선언은 함수 정의 부분의 헤더 부분에 세미콜론 ( ; ) 만 추가하면 됨   
// - 함수 원형 선언은 함수와 관련된 3가지 성질을 선언   
// -- 함수의 반환형   
// -- 매개변수의 개수   
// -- 매개변수의 자료형   
- Declaration of prototype of function   
  - A function is declared in advance before being used with a variable   
  - Proclamation of the prototype of a function is usually done before the main() function   
  - The prototype declaration only requires the addition of semicolons ( ; ) to the header part of the function definition part   
  - The declaration of prototype of function declares three properties related to the function   
    - Return type of a function   
    - Number of parameters   
    - Data type of parameters   
   
#### Example 1 declaration of prototype of function (If a prototype declaration is required)   
// 함수 원형 선언 예시 1 (원형 선언이 필요한 경우)   
   
```c
#include <stdio.h>

// 함수의 원형 선언이 필요
// Requires a declaration of prototype of function
int sum3(int a3, int b3);

void main() {
    printf("sum3==%d", sum3(10, 20));
}

// 피호출 함수가 main() 함수 뒤에 선언된 경우
// Case where the called function is declared after the main() function
int sum3(int a3, int b3) {
    return(a3 + b3);
}
```
   
- Result   
   
```
sum3==30
```
   
#### Example 2 declaration of prototype of function (If a prototype declaration is not required)   
// 함수 원형 선언 예시 2 (원형 선언이 필요 없는 경우)   
   
```c
#include <stdio.h>

// 피호출 함수가 main() 함수 이전에 선언된 경우로서 함수의 원형 선언이 필요 없음
// When the called function was declared before the main() function, no prototype declaration of the function is required
int sum3(int a3, int b3) {
    return(a3 + b3);
};

void main() {
    printf("sum3==%d", sum3(10, 20));
}
```
   
- Result   
   
```
sum3==30
```
   
<br />
### Function call   
// 함수의 호출   
   
// 함수는 일종의 부 프로그램임   
// 따라서 함수의 호출이 있어야 함   
// 함수의 호출 방법   
// - 함수명과 매개변수의 열거   
- A function is a subprogram   
- Therefore, there must be a call of the function   
- How to Call a Function   
  - Enumeration of function names and parameters   
   
#### Parameter   
// 매개변수   
   
// 실 매개변수   
// - 함수를 호출하는 함수 (호출함수) 에 쓰이는 매개변수   
// 형식 매개변수   
// - 호출 당하는 함수 (피호출함수) 에 쓰이는 매개변수   
- Actual parameter   
  - Parameters used for functions that call functions   
- Formal parameter   
  - Parameters used for functions being called (called function)   
   
// 실 매개변수와 형식 매개변수 사이에는 자료형과 변수의 개수가 일치해야 함   
- The number of data types and variables must match between actual and formal parameters   
   
#### Example of parameter   
// 매개변수의 예시   
   
```c
void main() {
    ...
    // 호출함수로서 a, b, c는 실 매개변수
    // As a calling function, a, b, and c are actual parameters
    fcn1(a, b, c);
    ...
}

// 피호출함수로서 x, y, z는 형식 매개변수
// As the called function, x, y, and z are formal parameters
fcn1(int x, float y, double z) {
    ...
}
```
   
// 자료형이 일치하지 않을 경우는 형 변환이 발생함   
// 변수의 개수가 일치하지 않을 경우 컴파일 에러가 발생함   
- Inconsistent data types result in a type conversion   
- Compilation error occurs when the number of variables does not match   
   
#### Return result value (return statement)   
// 결과값 반환 (return 문)   
   
// 형식   
- Formats   
   
```c
// return(수식);
// return 수식;
return(Expression statement);
return Expression statement;
```
   
// 기능   
// - 함수를 끝내고 제어와 함수 수행결과를 호출 함수로 넘김   
- Function   
  - Ends the function and passes control and function performance results to the call function   
   
// 사용 예시   
- Example of Use   
   
```c
// 상수 0 반환 (정상적인 종료를 의미)
// Return constant 0 (meaning normal termination)
return 0;
// 상수 1 반환
// Return constant 1
return 1;
// x값 반환
// Return x value
return x;
// 수식의 결과 값 반환
// Returns the result value of an expression
return (x + y * z);
// 다른 함수 호출
// Call other functions
return (sum(10, 20));
```
   
- Example   
   
```c
#include <stdio.h>

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
int max4(int x4, int y4);
int min4(int x4, int y4);

void main() {
    int i4 = 10, j4 = 20;

    /* 2. 함수의 호출 */
    /* 2. Function call */
    printf("max4(%d, %d)=%d\n", i4, j4, max4(i4, j4));
    printf("min4(%d, %d)=%d", i4, j4, min4(i4, j4));
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
int max4(int x4, int y4) {
    return(x4 > y4 ? x4 : y4);
}

int min4(int x4, int y4) {
    if (x4 > y4)
        return y4;
    else
        return x4;
}
```
   
- Result   
   
```
max4(10, 20)=20
min4(10, 20)=10
```
   
<br />
### Example of different uses of function   
// 함수의 여러 가지 사용 예시   
   
- Example   
   
```c
#include <stdio.h>

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
test5();
int sum5(int, int);

void main() {
    int s5;

    /* 2. 함수의 호출 */
    /* 2. Function call */
    // 단순한 함수호출
    // Simple function call
    test5();
    // 단순한 함수호출
    // Simple function call
    sum5(10, 20);
    // 함수 호출결과를 변수에 반환
    // Return function call result to variable
    s5 = sum5(30, 40);
    printf("sum5 from 30 to 40=%d\n", s5);
    // 호출결과를 직접 사용
    // Use call results directly
    printf("sum5 from 100 to 200=%d", sum5(100, 200));
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
test5() {
    printf("Different ways to use a Function\n");
}

int sum5(int a5, int b5) {
    int i5, s5 = 0;
    for (i5 = a5; i5 <= b5; i5++)
        s5 = s5 + i5;
    return s5;
}
```
   
- Result   
   
```
Different ways to use a Function
sum5 from 30 to 40=385
sum5 from 100 to 200=15150
```
   
<br />
### How to transfer data between parameters   
// 매개변수 사이의 자료전달 방법   
   
// 값에 의한 자료전달 (call by value)   
// - 기본적인 자료전달 방법   
// - 실 매개변수와 형식 매개변수 사이에 값의 전달   
// - 호출한 함수의 실행이 끝난 다음 전달받은 값을 되돌려 받지는 못함   
// 참조에 의한 자료전달 (call by reference)   
// - 호출함수와 피호출함수의 매개변수 값을 서로 교환할 수 있는 자료전달 방법   
// - 값을 전달하는 것이 아니라 실 매개변수의 값이 들어있는 주소 값이 전달됨   
- call by value   
  - Basic data delivery methods   
  - Transfer of values between actual and formal parameters   
  - After the execution of the called function is finished, the value received is not returned   
- call by reference   
  - A method of transferring data that can exchange the parameter values of the calling function and the called function   
  - Address values containing the values of the actual parameters are delivered, not the values   
   
#### call by value   
// 값에 의한 자료전달   
   
```c
// 함수 호출 (실 매개변수) - 자료전달 (값 전달)
// Function call (Actual parameter) - Data transfer (Value transfer)
fcn1(10, 20);
...
// 함수 정의 (형식 매개변수)
// Function definition (Formal parameter)
int fcn1(int x, int y)
```
   
- Example   
   
```c
#include <stdio.h>

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
void swap6(int x6, int y6);

void main() {
    int a6 = 3, b6 = 5;
    printf("Before the call, a6=%d, b6=%d\n", a6, b6);

    /* 2. 함수의 호출 */
    /* 2. Function call */
    swap6(a6, b6);
    printf("After the call, a6=%d, b6=%d", a6, b6);
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
// 두 변수 x6와 y6의 값을 서로 바꿈
// Interchange the values of two variables x6 and y6
void swap6(int x6, int y6) {
    int temp;
    temp = x6;
    x6 = y6;
    y6 = temp;
    printf("in the function, x6=%d, y6=%d\n", x6, y6);
}
```
   
- Result   
   
```
Before the call, a6=3, b6=5
in the function, x6=5, y6=3
After the call, a6=3, b6=5
```
   
// 피호출함수 내에서 형식 매개변수의 값이 바뀌었지만 실 매개변수의 값은 변하지 않음   
- Within the called function, the values of the formal parameters have changed, but the values of the real parameters remain unchanged   
   
#### call by reference   
// 참조에 의한 자료전달   
   
```c
// 함수 호출 (실 매개변수) - 주소 값을 전달
// Function call (Actual parameter) - Forward address values
fcn1(&a, &b);
...
// 함수 정의 (형식 매개변수)
// Function definition (Formal parameter)
int fcn1(int *x, int *y)
```
   
- Example   
   
```c
#include <stdio.h>

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
void swap7(int* x7, int* y7);

void main() {
    int a7 = 3, b7 = 5;
	printf("Before the call, a7=%d, b7=%d\n", a7, b7);

    /* 2. 함수의 호출 */
    /* 2. Function call */
    // 주소 값을 전달하기 위해 실 매개변수 앞에 주소 연산자 &를 붙임
    // To carry the address value, put the address operator & before the actual parameter
	swap7(&a7, &b7);
	printf("After the call, a7=%d, b7=%d", a7, b7);
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
// 두 변수 x7와 y7의 주소의 내용을 서로 바꿈
// 주소 값을 전달받기 위해 포인터변수 int *x7, int *y7를 선언
// Interchange the contents of the addresses of two variables x7 and y7
// Declare pointer variable int *x7, int *y7 to receive address values
void swap7(int* x7, int* y7) {
	int temp;
	temp = *x7;
	*x7 = *y7;
	*y7 = temp;
	printf("in the function, x7=%d, y7=%d\n", *x7, *y7);
}
```
   
- Result   
   
```
Before the call, a7=3, b7=5
in the function, x7=5, y7=3
After the call, a7=5, b7=3
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
