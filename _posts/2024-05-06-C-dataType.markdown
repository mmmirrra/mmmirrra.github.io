---
layout: post
title:  "C: Data Type - Constants and Variables"
date:   2024-05-06 09:00:00 +0900
categories: [C]
---

### Data type   
// 자료형   
   
// 프로그램에서 사용하는 자료의 형태   
// 자료형은 상수와 변수로 구분하여 사용함   
- Types of data used by programs   
- Data type are divided into constant and variable   
   
// 프로그램에서 자료 (data) 처리를 위해서는   
// - 자료의 생성과 저장, 처리과정이 필요함   
- To process data in the program   
  - Data creation, storage, and processing are required   
   
// C 프로그램은   
// - 수많은 명령어와 자료들로 구성됨   
// - 이들 자료의 정확한 처리와 효율적인 활용이 필요   
- C program is   
  - Consists of numerous commands and datas   
  - Need accurate processing and efficient use of these data   
   
// C 언어는 여러 가지 종류의 자료형 (data type) 을 지원함   
- Language C supports many types of data types   
   
<br />
### Constant   
// 상수   
   
// 상수는 항상 고정되는 값을 갖는 자료임   
- Constant is a data that always has a fixed value   
   
// 값이 한번 정해지면 프로그램 도중에 그 값을 변경할 수 없는 수   
// - 정수형 상수   
// - 실수형 상수   
// - 문자형 상수   
// - 문자열 상수   
- Number of values that cannot be changed during the program once a value is determined   
  - integer type   
  - floating-point type   
  - character type   
  - string type   
   
#### integer type   
// 정수형 상수   
   
// 10진수, 8진수, 16진수로 표현   
- Expressed in decimal, octal, hexadecimal   
   
#### floating-point type   
// 실수형 상수   
   
// 부동소수점 형 상수   
// double형을 기본 자료형으로 사용   
- Floating-point constant   
- Use double as the default data type   
   
#### character type   
// 문자형 상수   
   
// 단일 인용부호 (' ') 로 묶여 있는 1개의 영문자나 숫자문자   
// 내부적으로는 해당 문자의 ASCII 코드값이 사용   
// - 예를 들어 'A'는 내부적으로 65 (ASCII 코드값) 가 사용됨   
// Escape 문자 : 키보드에 나타나 있지 않은 문자   
- One English character or numeric character enclosed by a single quotation mark ('')   
- Internally, the ASCII code value for that character is used   
  - For example, 'A' is used internally with 65 (ASCII code value)   
- Escape characters : Characters not shown on the keyboard   
   
|Escape characters|Function|
|:---:|:---|
|`\a`|alert sound output|
|`\b`|back space|
|`\f`|form feed|
|`\n`|new line<br />(Change the line at the time of output)|
|`\r`|carriage return<br />(Move the cursor to the start position of the row)|
|`\t`|horizontal tab|
|`\0`|null character<br />(Character with ASCII code value of 0)|
   
#### string type   
// 문자열 상수   
   
// 이중 인용부호 (" ") 로 묶여 있는 복수개의 영문자나 숫자   
// 기억공간에 보관될 때는 문자열 끝에 null 문자 (`\0`) 가 추가   
- Multiple English characters or numbers enclosed by double quotation marks ("")   
- When stored in storage, a null character (`\0`) is added at the end of the string   
   
<br />
### Variable   
// 변수   
   
// 변할 수 있는 값   
- A changeable value   
   
// 변수는 프로그램 실행 도중 변할 수 있는 값이 저장되는 기억공간임   
// - 예를 들어 `i = 10;` 은 i 는 변수 (변수명) 이고, 10이란 값을 i라는 이름으로 정의된 기억공간에 저장한다는 의미임   
- Variable is a storage space where values that can change during program execution are stored   
  - For example, `i = 10;` means that i is a variable (variable name), and 10 means that the value is stored in a memory space defined by the name i   
   
// 이러한 변수 속에 들어가는 값은 수시로 변경될 수 있음   
- Values within these variables may change from time to time   
   
// 따라서 변수는 사용 전에 반드시 선언하여 컴파일러가 기억공간에서 일정공간을 확보할 수 있도록 해야 함   
- Therefore, variables must be declared before use so that the compiler can free up a certain amount of space in memory   
   
#### Characteristics of Variable   
// 변수의 특징   
   
// 모든 변수는 이름이 있음 (변수명)   
// 모든 변수는 정해진 자료형이 있음   
// 모든 변수는 할당된 값을 갖음   
- All variables have names (variable names)   
- All variables have predetermined data types   
- All variables have assigned values   
   
#### Rules for defining variable names   
// 변수명의 정의 규칙   
   
// 모든 변수는 사용되기 전에 선언되어야 함   
// 변수명은 반드시 영문자나 밑줄 (_) 로 시작해야 함   
// 변수명은 중간에 숫자, 밑줄 (_) 을 섞어서 명명할 수 있음   
// 변수명은 중간에 밑줄 (_) 이외의 특수문자 ($, #, ?, ...) 를 섞어서 명명할 수 없음   
// 변수명은 대소문자를 구별하여 사용해야 함   
// 변수명은 예약어들을 사용할 수 없음   
- All variables must be declared before they are used   
- Variable names must begin with an English or an underscore (_)   
- Variable names can be named by mixing numbers and underscores (_) in the middle   
- Variable names cannot be mixed with special characters ($, #, ?, ...) other than the underscore (_) in the middle   
- Variable names must be case sensitive   
- Variable names cannot use reserved words   
   
<br />
### Declaration of Data Types and Variables   
// 자료형과 변수 선언   
   
// 변수   
// - 자료를 저장할 기억공간을 확보하고 이 공간에 이름을 붙여준 것   
// 변수 선언   
// - 확보된 기억공간에 이름을 부여하는 것   
// 이러한 변수 선언을 위해 자료형이 필요함   
- Variable   
  - Having a memory space to store the data and naming it   
- Declaration of Variable   
  - Giving a name to a secured memory space   
- Data types are required for these variable declarations   
   
#### Type of data type   
// 자료형의 종류   
   
// 자료형의 종류에는 기본형과 확장형이 있음   
- Types of data type include Basic type and Extended type   
   
#### Basic type   
// 기본형   
   
// 정수형   
// - 운영체제에 따라 표현범위가 다름   
- integer type   
  - Expression range varies depending on operating system   
  - `int` (4byte)   
  - `short int` (2byte)   
  - `long int` (4byte)   
  - `unsigned int` (4byte)   
  - `unsigned short int` (2byte)   
  - `unsigned long int` (4byte)   
   
// 실수형   
- floating-point type   
  - `float` (4byte)   
  - `double` (8byte)   
  - `long double` (8byte)   
  - default : `double`   
   
// 문자형   
- character type   
  - `char` (1byte)   
  - `unsigned char` (1byte)   
   
// `char`   
// - -128 ~ 127까지의 값으로 ASCII 코드를 사용하여 처리. 실제 저장은 숫자로 저장됨   
- `char`   
  - Processed using ASCII code with values from -128 to 127. saved as a number   
   
// `unsigned char`   
// - 0 ~ 255까지의 값으로 ASCII 코드를 사용하여 처리. 실제 저장은 숫자로 저장됨   
- `unsigned char`   
  - Processed using ASCII code with values from 0 to 255. saved as a number   
   
- Example   
   
```c
#include <stdio.h>
void main() {
    char ch;    // Declare a character type ch
    int in;    // Declare a integer type in
    ch = in = 'A';    // Actually the ASCII code value of 'A' is used
    printf("ch = %d\n", ch);
    printf("in = %d\n", in);
    ch = in = 100;
    printf("\n ch = %c\n", ch);
    printf("in = %c\n", in);
}
```
   
- Result   
   
```c
ch = 65
in = 65

ch = d
ch = d
```
   
// 열거형   
// - 숫자 대신 단어를 사용   
// - enum 태그명 {열거자1, 열거자2, ...}   
- enumerated type   
  - Use words instead of numbers   
  - `enum tagName {SUN, MON, TUE, WED, ...} e1`   
    - e1 = SUN; ---> e1 == 0   
    - SUN == 0, MON == 1, TUE == 2, WED == 3, ...   
   
- Example   
   
```c
#include <stdio.h>
void main() {
    enum day1 {SUN, MON, TUE, WED, THU, FRI, SAT} d1;
    enum day2 {sun = 2, mon, tue, wed, thu, fri, sat} d2;
    d1 = WED;
    d2 = wed;
    printf("The value stored in enumeration d1 is %d \n", d1);
    printf("The value stored in enumeration d2 is %d \n", d2);
}
```
   
- Result   
   
```c
The value stored in enumeration d1 is 3
The value stored in enumeration d2 is 5
```
   
// 형 없음   
- `void`   
   
#### Extended type   
// 확장형   
   
// 배열형   
// 함수형   
// 포인터형   
// 구조체형   
- array type   
- function type   
- pointer type   
- structure type   
   
<br />
### Declaration of Variable   
// 변수 선언   
   
// 변수명과 변수가 가질 자료형을 지정하여 변수를 위한 기억공간을 할당하는 것   
- Assigning storage space for a variable by specifying the variable name and the type of data the variable will have   
   
```c
Formats : Datatype VariableName;
Examples of Use
    integer → int VariableName;
    short integer → short int VariableName;
    long integer → long int VariableName;
    floating-point → double VariableName;
    character → char VariableName;
    string → char VariableName[Number of characters + 1];
```
   
#### Considerations when declaring variables   
// 변수 선언 시 고려 사항   
   
// 변수에 저장될 값의 크기 (범위)   
// 변수의 선언 위치   
// 변수의 초기화   
- Size of the value to be stored in the variable (range)   
- Declaration Location of Variables   
- Initialization of variables   
   
#### Size of the value to be stored in the variable (range)   
// 변수에 저장될 값의 크기 (범위)   
   
- Example   
   
```c
#include <stdio.h>
void main() {
    short int num1, num2;
    num1 = 32767+1;
    num2 = -32768-1;
    printf("num1 = %d\n", num1);
    printf("num2 = %d\n", num2);
}
```
   
- Result   
   
```c
num1 = -32768
num2 = 32767
```
   
- Example   
   
```c
#include <stdio.h>
void main() {
    int num1, num2;
    num1 = 32767+1;
    num2 = -32768-1;
    printf("num1 = %d\n", num1);
    printf("num2 = %d\n", num2);
}
```
   
- Result   
   
```c
num1 = 32768
num2 = -32769
```
   
#### Declaration Location of Variables   
// 변수의 선언 위치   
   
// 변수를 함수 외부에 선언한 예시   
- Example of declaring a variable outside a function   
   
```c
// 전역변수로 선언, 프로그램 어디서나 사용 가능
// Declare as a global variable, can be used anywhere in the program
int num;
void main() {
    ...
}

sub() {
    ...
}
```
   
// 변수를 함수 내부에 선언한 예시   
- Example of declaring a variable inside a function   
   
```c
void main() {
    // 지역변수로 선언, main 함수 내에서만 사용 가능
    // Declared as a local variable, only within the main function
    int i;
    ...
}

sub1() {
    // sub1 함수 내에서만 사용 가능, main 함수 내의 변수 i와는 별개
    // Available only within sub1 function, separate from variable i in the main function
    int i, j;
    ...
}
```
   
- Example   
   
```c
#include <stdio.h>
int a = 100;
void func() {
    int a = 200;
    printf("the value of a in func() ==> %d \n", a);
}
int main() {
    printf("the value of a in main() ==> %d \n", a);
    func();
}
```
   
- Result   
   
```c
the value of a in main() ==> 100
the value of a in func() ==> 200
```
   
#### Initialization of variables   
// 변수의 초기화   
   
```c
#include <stdio.h>
void main() {
    int i, sum;
    for(i = 1; i <= 10; i++)    // Initialize variable i
        sum = sum + i;    // No initialization of variable sum
    printf("sum from 1 to 10 = %d \n", sum);
}
```
   
- Result   
   
```c
sum from 1 to 10 = 4556
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
