---
layout: post
title:  "C: Standard Input/Output Function and Conversion Character"
date:   2024-05-07 09:00:00 +0900
categories: [C]
---

### What is a function?   
// 함수란?   
   
// 특정한 작업 (기능) 을 수행하도록 설계된 독립적인 프로그램   
- An independent program designed to perform a particular task (function)   
   
// C 언어에서의 함수   
// - 표준함수 : C 언어 자체에서 제공하는 함수   
// - 사용자 정의 함수 : 사용자가 정의하여 사용하는 함수   
- Functions in C language   
  - Standard Function : Functions provided by C language itself   
  - User-defined function : Function defined and used by the user   
   
<br />
### Standard Input/Output Function   
// 표준 입출력 함수   
   
#### Types of standard I/O function   
// 표준 입출력 함수의 종류   
   
|Standard Output Function|Function|
|:---:|:---|
|printf()|// 화면 (monitor) 에 여러 종류의 자료를 출력<br />- Output different types of data on  monitor|
|putchar()|// 화면에 1개의 문자를 출력<br />- Output 1 character on monitor|
|puts()|// 화면에 문자열을 출력<br />- Output a string on monitor|
   
|Standard Input Function|Function|
|:---:|:---|
|scanf()|// 키보드를 통해 여러 종류의 자료를 입력 받음<br />- Multiple types of materials are entered through keyboard|
|getchar()|// 키보드를 통해 1개의 문자를 입력 받음<br />- 1 character entered through keyboard|
|gets()|// 키보드를 통해 문자열을 입력 받음<br />- String entered through keyboard|
   
<br />
### printf() function   
   
- Formats   
   
```c
printf("Output form", Variable 1, Variable 2, ...);
```
   
// 기능   
// - 주어진 출력 양식으로 자료를 출력함   
- Function   
  - Outputs data in a given output form   
   
// 사용 예시   
- Example of Use   
   
```c
printf("This is an example\n");
printf("A = %d, B = %c\n", a, b);
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    char c = 'A';
    int i = 10, j = 20, k = 30;
    // printf()문의 인용부호 내 문자가 화면에 출력
    // The characters in the quotation mark of printf() are displayed on the screen
    printf("a simple output program\n");
    // 변수 c는 순서대로 %c와 %d에 대응
    // Variables c correspond to %c and %d in order
    printf("c=%c, The value of the ASCII code in c is %d\n", c, c);
    // 변수 i, j, k는 순서대로 %문자와 대응
    // Variables i, j, and k correspond to % characters in order
    printf("i=%d, j=%d, k=%d", i, j, k);
}
```
   
- Result   
   
```
a simple output program
c=A, The value of the ASCII code in c is 65
i=10, j=20, k=30
```
   
#### Output Form Conversion Character   
// 출력 양식 변환 기호   
   
|Conversion Character|Displays Argument (Variable’s Contents) As|Data Type of the Argument|
|:---|:---|:---|
|%c<br />%C|Single character|Integer type, Character type|
|%d|Signed decimal integer (int)|Integer type, Character type|
|%e<br />%E|Signed floating-point value in E notation|Real number type|
|%f|Signed floating-point value (float)|Real number type|
|Example %5.2f|Total digits are printed up to 5 digits, decimal places up to 2 digits (float)|Real number type|
|%g<br />%G|Signed value in %e or %f format, whichever is shorter||
|%i|Signed decimal integer (int)||
|%o|Unsigned octal (base 8) integer (int)|Integer type, Character type|
|%s|String of text|String pointer|
|%u|Unsigned decimal integer (int)|Integer type, Character type|
|%x|Unsigned hexadecimal (base 16) integer (int) - 'a' ~ 'f'|Integer type, Character type|
|%X|Unsigned hexadecimal (base 16) integer (int) - 'A' ~ 'F'|Integer type, Character type|
|%p|Address value of the pointer - hexadecimal (base 16)||
|%%|percent character||
   
#### Example of use of form conversion character   
// 양식 변환 기호의 사용 예시   
   
```c
#include <stdio.h>

void main() {
    // 문자형 출력
    // Output character type
    printf("%c\n", 'a');
    // 정수형 10진수 출력
    // Output integer decimal number
    printf("%d\n", -123);
    // 정수형 8진수 출력
    // Output integer octal number
    printf("%o\n", 123);
    // 정수형 소문자 16진수 출력
    // Output integer lowercase hexadecimal
    printf("%x\n", 123);
    // 정수형 대문자 16진수 출력
    // Output integer upper case hexadecimal
    printf("%X\n", 123);
    // 실수형 출력
    // Output real number type
    printf("%f\n", 123.456789);
    // 지수형 출력
    // Output exponential type
    printf("%e\n", 123.456789);
    // 문자열형 출력
    // Output string type
    printf("%s", "abcdefg");
}
```
   
- Result   
   
```
a
-123
173
7b
7B
123.456789
1.2345678e+02
abcdefg
```
   
#### Example of editing an output form   
// 출력 양식의 편집 예시   
   
```c
#include <stdio.h>

void main() {
    // 숫자의 길이만큼 출력 폭이 자동 지정됨
    // Output width is automatically specified by the length of the number
    printf("|%d|\n", 123);
    // 총 5자리로 오른쪽부터 채워짐
    // Filled from right with a total of 5 digits
    printf("|%5d|\n", 123);
    // 총 5자리로 왼쪽부터 채워짐
    // Filled from left with a total of 5 digits
    printf("|%-5d|\n", 123);
    // 총 5자리로 오른쪽부터 채워지고, 공백은 0으로 채워짐
    // A total of 5 digits are filled from the right, and the space is filled with zero
    printf("|%05d|\n", 123);
    // 총 6자리 (소수점 포함) 로 채워지고, 소수점 이하는 1자리만 출력됨
    // Filled with a total of 6 digits (including decimals), only 1 digit output for sub-decimal
    printf("|%6.1f|\n", 123.45);
    // 총 7자리 (소수점 포함) 로 채워지고, 공백은 0으로 채워지고, 소수점 이하는 2자리만 출력됨
    // 7 digits total (including decimals), spaces filled with zeros, and only 2 digits below decimals
    printf("|%07.2f|", 123.45);
}
```
   
- Result   
   
```
|123|
|  123|
|123  |
|00123|
| 123.5|
|0123.45|
```
   
<br />
### scanf() function   
   
- Formats   
   
```c
printf("Input form", &Variable1, &Variable2, ...);
```
   
// 기능   
// - 주어진 양식으로 자료를 입력 받아 지정된 기억공간 (변수) 에 저장   
- Function   
  - Enter data in a given form and store it in a designated memory space (variable)   
   
// 사용 예시   
- Example of Use   
   
```c
scanf("%d", &a);
```
   
#### Intput Form Conversion Character   
// 입력 양식 변환 기호   
   
|Conversion Character|Conversion Function|
|:---|:---|
|%d|// 키보드를 통해 정수형을 입력 받음<br />- Enter integer type through keyboard|
|%ld|// 키보드를 통해 long 정수형을 입력 받음<br />- Enter long integer type through keyboard|
|%f|// 키보드를 통해 실수형을 입력 받음<br />- Enter real number type through keyboard|
|%lf|// 키보드를 통해 double 실수형을 입력 받음<br />- Enter double real number type through keyboard|
|%c|// 키보드를 통해 문자형을 입력 받음<br />- Enter character type through keyboard|
|%s|// 키보드를 통해 문자열을 입력 받음<br />- Enter string through keyboard|
   
- Example   
   
```c
#include <stdio.h>
/* 권장하지 않는 함수 사용에 대한 경고 메시지 무시 - scanf */
/* Ignoring warning messages about using a function that is not recommended - scanf */
#pragma warning(disable : 4996)

void main() {
    int jsu1, jsu2;
    float ssu1, ssu2;
    printf("\nEnter the integer twice\n");
    scanf("%d %d", &jsu1, &jsu2);
    printf("\nEnter the real number twice\n");
    scanf("%f %f", &ssu1, &ssu2);
    printf("\ninteger %d %d\n", jsu1, jsu2);
    printf("\nreal number %f %f", ssu1, ssu2);
}
```
   
- Result   
   
```
Enter the integer twice 10 20 [Enter]
Enter the real number twice 3.14 6.28 [Enter]
integer 10 20
real number 3.140000 6.280000
```
   
<br />
### getchar() function   
   
- Formats   
   
```c
getchar();
```
   
// 기능   
// - 한 문자를 키보드를 통해 입력 받음   
- Function   
  - Enter one character through keyboard   
   
// 사용 예시   
- Example of Use   
   
```c
a = getchar();
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    char a;
    printf("Please enter a character\n");
    // 한 문자가 입력되면 문자형 변수 a에 저장
    // If one character is entered, save it in a character variable a
    a = getchar();
    printf("a=%c", a);
}
```
   
- Result   
   
```
Please enter a character S [Enter]
a=S
```
   
<br />
### putchar() function   
   
- Formats   
   
```c
putchar(character);
```
   
// 기능   
// - 한 문자를 화면에 출력   
- Function   
  - Output one character to the screen   
   
// 사용 예시   
- Example of Use   
   
```c
putchar('A');
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    char var = 'A';
    // 함수의 괄호 안에 문자형 변수가 사용됨
    // Character variables are used in parentheses of the function
    putchar(var);
    // 수식이 사용됨
    // expression is used
    putchar(var + 1);
    // escape 문자. 줄바꿈 new line. 화면에 출력되면 것은 없이 줄바꿈만 됨
    // Escape characters. New line. When printed on the screen, there is nothing but a new line
    putchar('\n');
    // 문자형 상수가 사용됨
    // Characteristic constant used
    putchar('K');
    // 수식이 사용됨
    // expression is used
    putchar('K' + 2);
    // \007 == \a --> 화면에 출력되는 것은 없이 경고음 삑 소리만 남
    // \007 == \a --> There is no output on the screen, only a warning tone
    putchar('\007');
}
```
   
- Result   
   
```
AB
KM
(a warning sound)
```
   
<br />
### gets() function   
   
- Formats   
   
```c
gets(Variable);
```
   
// 기능   
// - 문자열을 키보드로부터 입력 받음   
- Function   
  - String received from keyboard   
   
// 사용 예시   
- Example of Use   
   
```c
char s[50];
gets(s);
```
   
- Example   
   
```c
#include <stdio.h>
#pragma warning(disable : 4996)

void main() {
    // 문자열 저장을 위해 배열명 s인 배열 선언
    // To save a string, declare an array with array name s
    char s[50];
    printf("\nEnter a string in gets()?\n");
    // 띄어쓰기 포함된 문자열을 입력하면 문자열 전체가 저장됨
    // If a string containing spaces is entered, the entire string is saved
    gets(s);
    printf("Enter a string in gets() = %s\n", s);
    printf("\nEnter a string in scanf()?\n");
    // 띄어쓰기 포함된 문자열을 입력하면 첫번째 단어만 저장됨. scanf는 띄어쓰기를 데이터를 여러개로 구분하는 것으로 인식함. 변수에 & 생략했으나 오류발생하지 않음
    // Only the first word is saved when a string containing spaces is entered. Scanf recognizes data as being separated by spaces. '&' omitted for variable but no error occurred
    scanf("%s", s);
    printf("Enter a string in scanf() = %s", s);
}
```
   
- Result   
   
```
Enter a string in gets()? 컴퓨터 과학 [Enter]
Enter a string in gets() = 컴퓨터 과학

Enter a string in scanf()? 컴퓨터 과학 [Enter]
Enter a string in scanf() = 컴퓨터
```
   
<br />
### puts() function   
   
- Formats   
   
```c
puts(Variable);
```
   
// 기능   
// - 문자열을 화면에 출력   
- Function   
  - Output a string to the screen   
   
// 사용 예시   
- Example of Use   
   
```c
char s[50] = "seoul";
puts(s);
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    char s1[] = "Computer";
    char s2[] = "Science";
    // 자동 줄바꿈됨
    // Auto-lined
    puts(s1);
    puts(s2);
    // 자동 줄바꿈 안됨
    // No Auto-lined
    printf("%s", s1);
    // 문자열 연결 출력됨
    // String is associated and output
    printf("%s", s2);
}
```
   
- Result   
   
```
Computer
Science
ComputerScience
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
