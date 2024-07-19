---
layout: post
title:  "C: sample_operator.c"
date:   2024-05-07 09:00:00 +0900
categories: [C]
---

solution 'CPrjs'   
project 'Sample_Operator'   
   
### sourceFile list - .c   
#### main() sourceFile   
`sample_operator.c` : C practice project main function   
   
```c
/* 선행처리기 preprocessor* /
/* 파일 포함 : #include <파일명>, #include "파일명" */
/* 매크로 macro 상수 정의 : #define 매크로명 자료
   매크로 macro 상수 정의 해제 : #undef 매크로명
   매크로 macro 함수 정의 : #define 매크로명(인수) (수식), #define 매크로명(인수, 인수) (수식)
   매크로 macro 함수 특징 : 인자로 전달하는 변수의 자료형은 제한없음 */
/* 조건부 컴파일 : #if, #else, #elif, #endif
   조건부 컴파일 특징 : #if와 #elif 에는 컴파일 여부를 결정하는 조건문 필요. 
                      조건문은 선행처리과정에서 진위 여부를 판단할 수 있어야 함. 
                      조건문에는 변수 지정이나 함수 호출 불가하고, 주로 매크로 값을 사용함 */

/* Preprocessor* /
/* File include : #include <fileName>, #include "fileName" */
/* Defining the macro constant : #define macroName data
   Undefining the macro constant : #undef macroName
   Defining the macro function : #define macroName(argument) (expression statement), #define macroName(argument, argument) (expression statement)
   Macro function feature : No limits on the data type of variables passed as arguments */
/* Conditional compilation : #if, #else, #elif, #endif
   Conditional Compilation Features : #If and #elif require a conditional statement to determine whether to compile or not. 
                      Conditional statements must be able to determine the authenticity of prior processing. 
                      Conditional statements cannot specify variables or call functions, and mainly use macro values */

#include <stdio.h>
#define PI 3.141592
#define TEL "o1o-1111-oooo"
#define AREA(x) (3.141592*(x)*(x))
#define Hap1(x,y) x+y
#define Hap2(x,y) ((x)+(y))
#define Gop1(x,y) x*y
#define Gop2(x,y) ((x)*(y))
#define CONDITION 1

#define _CRT_SECURE_NO_WARNINGS
/* 권장하지 않는 함수 사용에 대한 경고 메시지 무시 - scanf */
/* Ignore warning messages about using a function that is not recommended - scanf */
#pragma warning(disable : 6031)
#pragma warning(disable : 4996)

void main() {

	printf("Hello C Programming\n");

	/* 매크로 macro 함수 정의 예제 */
	/* Example macro function definition */
	int h1, h2, g1, g2;
	h1 = 10 * Hap1(3, 4);
	h2 = 10 * Hap2(3, 4);
	g1 = Gop1(1 + 2, 3 + 4);
	g2 = Gop2(1 + 2, 3 + 4);
	printf("h1=%d, h2=%d\n", h1, h2);	// Output Results --> h1=34, h2=70
	printf("g1=%d, g2=%d\n", g1, g2);	// Output Results --> g1=11, g2=21

	/* 조건부 컴파일 예제 */
	/* Conditional Compilation Example */
#if CONDITION
	printf("\n Compile A program \n");
#else
	printf("\n Compile B program \n");
#endif

	/* printf() 표준출력함수 예제 */
	/* printf() : Standard Output Function Example */
	char c = 'A';
	int i = 10, j = 20, k = 30;
	printf("a simple output program\n");		// Output Results --> a simple output program
	printf("c=%c, The value of the ASCII code of c is %d\n", c, c);	// Output Results --> c=A, The value of the ASCII code of c is 65
	printf("i=%d, j=%d, k=%d\n", i, j, k);		// Output Results --> i=10, j=20, k=30
	printf("%c\n", 'a');				// Character type : Output Results --> a
	printf("%d\n", -123);				// Integer type decimal : Output Results --> -123
	printf("%o\n", 123);				// Integer type octal : Output Results --> 173
	printf("%x\n", 123);				// Integer type hexadecimal lowercase : Output Results --> 7b
	printf("%X\n", 123);				// Integer type hexadecimal uppercase : Output Results --> 7B
	printf("%f\n", 123.456789);			// Real number type : Output Results --> 123.456789
	printf("%e\n", 123.456789);			// Exponent type : Output Results --> 1.2345678e+02
	printf("%s\n", "abcdefg");			// String type : Output Results --> abcdefg

	/* 출력양식 편집 예제 */
	/* Edit Output Form Example */

	// 숫자의 길이만큼 출력 폭이 자동 지정됨
	// Output width is automatically specified by the length of the number
	printf("|%d|\n", 123);		// Output Results --> |123|

	// 총 5자리로 오른쪽부터 채워짐
	// Filled from right with a total of 5 digits
	printf("|%5d|\n", 123);		// Output Results--> |  123|

	// 총 5자리로 왼쪽부터 채워짐
	// Filled from left with a total of 5 digits
	printf("|%-5d|\n", 123);	// Output Results --> |123  |

	// 총 5자리로 오른쪽부터 채워지고, 공백은 0으로 채워짐
	// Filled from right with a total of 5 digits, and spaces filled with zeros
	printf("|%05d|\n", 123);	// Output Results --> |00123|

	// 총 6자리 (소수점 포함) 로 채워지고, 소수점 이하는 1자리만 출력됨
	// Filled with a total of 6 digits (including decimals), only 1 digit below decimals
	printf("|%6.1f|\n", 123.45);	// Output Results --> | 123.5|

	// 총 7자리 (소수점 포함) 로 채워지고, 공백은 0으로 채워지고, 소수점 이하는 2자리만 출력됨
	// Filled with a total of 7 digits (including decimals), spaces filled with zeros, and only 2 digits below decimals
	printf("|%07.2f|\n", 123.45);	// Output Results --> |0123.45|

	/* scanf() 표준입력함수 예제 */
	/* scanf() : Example of a Standard Input Function */
	int jsu1, jsu2;
	float ssu1, ssu2;
	printf("\nEnter an integer twice\n");
	scanf("%d %d", &jsu1, &jsu2);
	printf("\nEnter an real number twice\n");
	scanf("%f %f", &ssu1, &ssu2);
	printf("\nInteger is %d %d\n", jsu1, jsu2);
	printf("\nReal number is %f %f\n", ssu1, ssu2);

	/* getchar() 문자 하나만 입력받는 함수 예제 */
	/* getchar() : Example of a function that receives only one character */
	char a;
	printf("Please enter one character\n");
	a = getchar();
	printf("a=%c\n", a);

	/* putchar() 문자 하나만 출력하는 함수 예제 */
	/* putchar() : Example of a function that outputs only one character */
	char var = 'A';
	putchar(var);		// Output Results --> A
	putchar(var + 1);	// Output Results --> B
	putchar('\n');		// Output Results --> escape : new line
	putchar('K');		// Output Results --> K
	putchar('K' + 2);	// Output Results --> M
	putchar('\007');	// Output Results --> \007 == \a --> Warning sound

	/* gets() 문자열을 입력받는 함수 예제 */
	/* gets() : Example of a function that receives a string */
	char s[50];
	printf("\nEnter a string in gets()?\n");

	// 띄어쓰기 포함된 문자열을 입력하면 문자열 전체가 저장됨
	// If a string with spaces is entered, the entire string is saved
	gets(s);
	printf("Enter string with gets() = %s\n", s);
	printf("\nEnter a string in scanf()?\n");

	/* 띄어쓰기 포함된 문자열을 입력하면 첫번째 단어만 저장됨.
		scanf는 띄어쓰기를 데이터를 여러개로 구분하는 것으로 인식함.
		변수에 & 생략했으나 오류발생하지 않음 */
	/* If a string with spaces is entered, only the first word is saved. 
		Scanf recognizes spacing as dividing data into several. 
		'&' is omitted for variable but no error occurred. */
	scanf("%s", s);
	printf("Enter string with scanf() = %s\n", s);

	/* puts() 문자열을 출력하는 함수 예제 */
	/* puts() : Example of a function that outputs a string */
	char s1[] = "Computer";
	char s2[] = "Science";
	puts(s1);		// Auto-lined : Output Results --> Computer
	puts(s2);		// Auto-lined : Output Results --> Science
	printf("%s", s1);	// No Auto-lined
	printf("%s\n", s2);	// String connection output : Output Results --> ComputerScience

	/* 산술연산자 예제 - 이항연산자 */
	/* Example Arithmetic Operator - Binary Operator */
	int x, y;
	x = 10;
	y = 3;
	printf("x=%d, y=%d\n", x, y);	// Output Results --> x=10, y=3
	printf("x+y=%d\n", x + y);	// Output Results --> x+y=13
	printf("x/y=%d\n", x / y);	// Output Results --> x/y=3
	printf("x%%y=%d\n", x % y);	// Output Results --> x%y=1
	printf("y%%x=%d\n", y % x);	// Output Results --> y%x=3

	/* 산술연산자 예제 - 단항연산자 */
	/* Example Arithmetic Operator - Unary Operator */
	int x1 = 5, a1, b1;
	a1 = ++x1 * x1--;				// Order of run 1. ++x1 --> 2. ++x1*x1 --> 3. x1--
	b1 = x1 * 10;
	printf("a1=%d b1=%d x1=%d\n", a1, b1, x1);	// Output Results --> a1=36 b1=50 x1=5

	/* 관계연산자 예제 */
	/* Example of Relational Operator */
	int a2 = 4, b2, c2, d2;
	b2 = a2 > 2;			// True
	printf("b2=%d\n", b2);		// Output Results --> b2=1
	c2 = a2 < 2;			// False
	printf("c2=%d\n", c2);		// Output Results --> c2=0
	d2 = a2 == 4;			// True
	printf("d2=%d\n", d2);		// Output Results --> d2=1

	/* 논리연산자 예제 */
	/* Logical Operator Example */
	int a3 = 4, b3 = 7, c3, d3, e3;

	// 논리곱 && : 참 && 참 == 참
	// conjunction && : true && true == true
	c3 = a3 > 2 && b3 <= 7;
	printf("c3=%d\n", c3);		// Output Results --> c3=1

	// 논리합 || : 거짓 || 참 == 참
	// disjunction || : false || true == true
	d3 = a3 < 2 || b3 <= 7;
	printf("d3=%d\n", d3);		// Output Results --> d3=1

	// 논리부정 ! : !참 == 거짓
	// negation ! : !true == false
	e3 = !a3;
	printf("e3=%d\n", e3);		// Output Results --> e3=0

	/* 대입연산자 예제 */
	/* Example of substitution operator */
	int a4;

	// a4에 5를 대입
	// Substitute 5 into a4
	a4 = 5;
	printf("a4 = 5 --> %d\n", a4);	// Output Results --> a4 = 5 --> 5

	// a4 = a4 + 5 : a4에 5를 더한 후 결과를 a4에 대입
	// a4 = a4 + 5 : Add 5 to a4 and substitute the result into a4
	a4 += 5;
	printf("a4 += 5 --> %d\n", a4);	// Output Results --> a4 += 5 --> 10

	// a4 = a4 - 5 : a4에 5를 뺀 후 결과를 a4에 대입
	// a4 = a4 - 5 : Subtract 5 from a4 and substitute the result into a4
	a4 -= 5;
	printf("a4 -= 5 --> %d\n", a4);	// Output Results --> a4 -= 5 --> 5

	// a4 = a4 * 5 : a4에 5를 곱한 후 결과를 a4에 대입
	// a4 = a4 * 5 : Multiply a4 by 5 and substitute the result into a4
	a4 *= 5;
	printf("a4 *= 5 --> %d\n", a4);	// Output Results --> a4 *= 5 --> 25

	// a4 = a4 / 5 : a4를 5로 나눈 후 결과를 a4에 대입
	// a4 = a4 / 5 : Divide a4 by 5 and substitute the result into a4
	a4 /= 5;
	printf("a4 /= 5 --> %d\n", a4);	// Output Results --> a4 /= 5 --> 5

	// a4 = a4 % 3 : a4를 3으로 나눈 후 그 나머지를 a4에 대입
	// a4 = a4 % 3 : Divide a4 by 3 and substitute the rest into a4
	a4 %= 3;
	printf("a4 %%= 3 --> %d\n", a4);	// Output Results --> a4 %= 3 --> 2

	// a4 = a4 & 55 : a4와 55에 대한 bit단위의 AND연산을 한 후 결과를 a4에 대입
	// a4 = a4 & 55 : Perform AND operations in bit units for a4 and 55 and substitute the result into a4
	a4 &= 55;
	printf("a4 &= 55 --> %d\n", a4);	// Output Results --> a4 &= 55 --> 2

	// a4 = a4 | 5 : a4와 5에 대해 bit단위의 OR연산을 한 후 결과를 a4에 대입
	// a4 = a4 | 5 : Perform OR operations in bit units for a4 and 5 and substitute the result into a4
	a4 |= 5;
	printf("a4 |= 5 --> %d\n", a4);	// Output Results --> a4 |= 5 --> 7

	// a4 = a4 ^ 5 : a4와 5에 대해 bit단위의 XOR연산을 한 후 결과를 a4에 대입
	// a4 = a4 ^ 5 : Perform XOR operations in bit units for a4 and 5 and substitute the result into a4
	a4 ^= 5;
	printf("a4 ^= 5 --> %d\n", a4);	// Output Results --> a4 ^= 5 --> 2

	// a4 = a4 << 5 : a4의 값을 5bit 좌로 이동 후 결과를 a4에 대입
	// a4 = a4 << 5 : Move the value of a4 to the left of 5 bits and substitute the result into a4
	a4 <<= 5;
	printf("a4 <<= 5 --> %d\n", a4);	// Output Results --> a4 <<= 5 --> 64

	// a4 = a4 >> 5 : a4의 값을 5bit 우로 이동 후 결과를 a4에 대입
	// a4 = a4 >> 5 :  Move the value of a4 to the right of 5 bits and substitute the result into a4
	a4 >>= 5;
	printf("a4 >>= 5 --> %d\n", a4);	// Output Results --> a4 >>= 5 --> 2

	int a5 = 10, b5 = 3, c5 = 11;

	// a5 = a5 * (b5 - 1)
	a5 *= (b5 - 1);

	// b5 = b5 / (1 + 1)
	b5 /= 1 + 1;

	// c5 = c5 + 2
	c5 += 2;
	printf("a5=%d b5=%d c5=%d\n", a5, b5, c5);	// Output Results --> a5=20 b5=1 c5=13

	/* 조건연산자 예제 */
	/* Example Conditional Operator */
	int a6 = 10, b6;
	// 조건을 만족하지 않으므로 (a6 - 1) 을 수행
	// Perform (a6 - 1) because it does not satisfy the conditions
	b6 = (a6 > 15) ? (a6 + 1) : (a6 - 1);
	printf("b6=%d\n", b6);			// Output Results --> b6=9

	/* 비트연산자 예제 */
	/* Example of bit operator */
	printf("a bit of x == 10110011\n");
	printf("a bit of y == if 01001001\n");
	printf("the result of x&y == 00000001 (If both bits are 1 (true), it is 1 (true). The rest is 0 (false))\n");
	printf("the result of x|y == 11111011 (If either bit is 1 (true), it is 1 (true). The rest is 0 (false))\n");
	printf("the result of x^y == 11111010 (Only 1 (true) if the two bits are different. The rest is 0 (false))\n");
	printf("the result of ~x == 01001100 (Reverse 1 (true) and 0 (false))\n");
	printf("the result of x<<2 == 11001100 (Move the bit to the left by 2 bits. Fill empty spaces with 00)\n");
	printf("the result of x>>2 == 00101100 (Move the bit to the right by 2 bits. Fill empty spaces with 00)\n");

	/* 기타연산자 예제 - sizeof(자료형 또는 수식 또는 변수 또는 상수) 
		: 지정한 자료형, 수식, 변수, 상수의 기억공간의 크기 (byte) 를 구함 */
	/* Example of Other Operators - sizeof(Data type or expression statement or variable or constant) 
		: Obtain the size (byte) of the memory space of the specified data type, expression statement, variable, and constant */
	float a7 = 3.14;
	printf("int형의 크기는=%d바이트\n", sizeof(int));		// Output Results --> Int type size is = 4 bytes
	printf("float형 변수 a7의 크기는=%d바이트\n", sizeof(a7));	// Output Results --> Size of float type variable a7 is = 4 bytes

	/* 기타연산자 예제 - cast(형변환) - (형명칭)자료 
		: 지정한 자료형을 다른 자료형으로 강제적으로 바꿈 */
	/* Example of Other Operators - cast(type cast) - (typeName)data 
		: Forced to change the specified data type to another data type */
	int a8 = 3, b8 = 4;
	double c8;
	// int형인 a8을 double형으로 강제 형변환
	// Forced to change of int type a8 to double type
	c8 = (double)a8 / b8;
	printf("나눗셈 결과 : %f\n", c8);	// Output Results --> 나눗셈 결과 : 0.750000

	/* 기타연산자 예제 - & : 주소 연산자로서 피연산자의 주소를 나타냄 */
	/* 기타연산자 예제 - * : 내용 연산자로서 피연산자의 내용을 가져옴 */
	/* Example of Other Operators - & : Address operator represents the address of the operand */
	/* Example of Other Operators - * : Gets the content of the operand as a content operator */

	/* 연산자 우선순위 예제 */
	/* Example of Operator Precedence */
	int a9, b9, c9;
	a9 = 10;
	b9 = 20;
	c9 = 30;

	// a9+(b9*c9)
	printf("a9+b9*c9=%d\n", a9 + b9 * c9);					// Output Results --> a9+b9*c9=610

	// b9+=2*c9 먼저 계산되고 a9=b9가 계산됨
	// b9+=2*c9 calculated first and a9=b9 calculated later
	printf("a9=b9+=2*c9 --> a9=%d\n", a9 = b9 += 2 * c9);			// Output Results --> a9=b9+=2*c9 --> a9=80

	printf("a9=(b9>c9)?b9:c9 --> a9=%d\n", a9 = (b9 > c9) ? b9 : c9);	// Output Results --> a9=(b9>c9)?b9:c9 --> a9=80

	printf("a9/b9*c9=%d\n", a9 / b9 * c9);					// Output Results --> a9/b9*c9=30

	// a9=(a9*(b9=(c9+5))) : c9+5가 b9에 저장되고, a9*b9가 a9에 저장됨
	// a9=(a9*(b9=(c9+5))) : c9+5 saved in b9 and a9*b9 saved in a9
	printf("a9*=b9=c9+5 --> a9=%d\n", a9 *= b9 = c9 + 5);			// Output Results --> a9*=b9=c9+5 --> a9=2800
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
