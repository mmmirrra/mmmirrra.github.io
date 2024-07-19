---
layout: post
title:  "C: sample_function_storageClass.c"
date:   2024-05-11 09:00:00 +0900
categories: [C]
---

solution 'CPrjs'   
project 'Sample_Function_StorageClass'   
   
### sourceFile list - .c   
#### main() sourceFile   
// 메인 함수   
`sample_function_storageClass.c` : C practice project main function   
   
```c
#include <stdio.h>
#include <math.h>
#include <string.h>
#include <ctype.h>

#pragma warning(disable:4996)

/* 사용자 정의 함수 예제 - 1. 원형 prototype 선언 */
/* Example of a user-defined function - 1. Declare a prototype */
int sum3(int a3, int b3);

/* return 예제 - 1. 원형 prototype 선언 */
/* Example of return - 1. Declare a prototype */
int max4(int x4, int y4);
int min4(int x4, int y4);

/* 함수 호출 예제 - 1. 원형 prototype 선언 */
/* Example of calling functions - 1. Declare a prototype */
test5();
int sum5(int, int);

/* 매개변수 사이의 자료전달 방법 예제 - 1. 원형 prototype 선언 */
/* Example of how to transfer data between parameters - 1. Declare a prototype */
void swap6(int x6, int y6);
void swap7(int* x7, int* y7);

/* 기억 클래스 storage class 예제 - 1. 원형 prototype 선언 */
/* Example of storage classes - 1. Declare a prototype */
void fcn8();
void fcn9();
int x9;
test11();
int i12 = 10;
int j12 = 20;

/* extern_ex13() 함수 - 1. 원형 prototype 선언 */
/* extern_ex13() function - 1. Declare a prototype */
void extern_ex13();

/* 전역변수 s13 선언 */
/* Declare global variable s13 */
char s13[100];

void main() {

	/* math.h 예제 */
	/* Example of math.h */
	double x1 = 12.34;
	int i1 = 5, j1 = 2;
	int a1, b1, c1;
	a1 = ceil(x1);
	b1 = floor(x1);
	c1 = pow(4, j1);

	// 절대값
	// Absolute value
	printf("abs(-5)=%d\n", abs(i1));	// Output Results --> abs(-5)=5

	// 주어진 값 이상의 최소 정수값
	// Minimum integer value greater than or equal to the given value
	printf("ceil(12.34)=%d\n", a1);		// Output Results --> ceil(12.34)=13

	// 코사인
	// Cosine
	printf("cos(10)=%f\n", cos(10));	// Output Results --> cos(10)=-0.839072

	// 지수값
	// Exponential
	printf("exp(2)=%.f\n", exp(j1));	// Output Results --> exp(2)=7

	// 주어진 값 미만의 최대 정수값
	// Maximum integer value below the given value
	printf("floor(12.34)=%d\n", b1);	// Output Results --> floor(12.34)=12

	// 제곱근
	// square root
	printf("sqrt(2)=%5f\n", sqrt(j1));	// Output Results --> sqrt(2)=1.414214

	// X의 Y승 값
	// The Y-square root of X 
	printf("pow(4,2)=%d\n", c1);		// Output Results --> pow(4,2)=16

	/* string.h, ctype.h 예제 */
	/* Example of string.h, ctype.h */
	int i2, alp2 = 0, no2 = 0, et2 = 0;
	char s2[20];
	printf("Enter a Character\n");
	scanf("%s", s2);
	for (i2 = 0; i2 < strlen(s2); i2++) {
		// 영문자여부 판별
		// Determining whether it is English or not
		if (isalpha(s2[i2]))
			alp2++;
		// 숫자여부 판별
		// Determining whether it is Number or not
		else if (isdigit(s2[i2]))
			no2++;
		else
			et2++;
	}
	printf("Alphabet=%d\n", alp2);
	printf("Number=%d\n", no2);
	printf("ETC=%d\n", et2);

	/* 사용자 정의 함수 예제 - 2. 호출 */
	/* Example of a user-defined function - 2. Calling */
	int x3, y3, c3;
	printf("Enter the number twice.\n");
	scanf("%d %d", &x3, &y3);
	printf("sum3(x3, y3)==%d\n", sum3(x3, y3));		// Output Results --> sum3(x3, y3)==Output of calculation results
	c3 = sum3(10, 20);
	printf("sum3(10, 20)==%d\n", c3);			// Output Results --> sum3(10, 20)==30

	/* return 예제  - 2. 호출 */
	/* Example of return - 2. Calling */
	int i4 = 10, j4 = 20;
	printf("max4(%d, %d)=%d\n", i4, j4, max4(i4, j4));	// Output Results --> max4(10, 20)=20
	printf("min4(%d, %d)=%d\n", i4, j4, min4(i4, j4));	// Output Results --> min4(10, 20)=10

	/* 함수 호출 예제 - 2. 호출 */
	/* Example of calling functions - 2. Calling */
	int s5;

	// 단순한 함수호출
	// Simple function call
	test5();

	// 단순한 함수호출
	// Simple function call
	sum5(10, 20);

	// 함수 호출결과를 변수에 반환
	// Return function call result to variable
	s5 = sum5(30, 40);

	printf("sum5 from 30 to 40=%d\n", s5);			// Output Results --> sum5 from 30 to 40=385

	// 호출결과를 직접 사용
	// Use call results directly
	printf("sum5 from 100 to 200=%d\n", sum5(100, 200));	// Output Results --> sum5 from 100 to 200=15150

	/* 매개변수 사이의 자료전달 방법 예제 1 - 값에 의한 자료전달 call by value - 2. 호출 */
	/* Example 1 of how to transfer data between parameters - call by value - 2. Calling */
	int a6 = 3, b6 = 5;
	printf("Before the call, a6=%d, b6=%d\n", a6, b6);	// Output Results --> Before the call, a6=3, b6=5
	swap6(a6, b6);
	printf("After the call, a6=%d, b6=%d\n", a6, b6);	// Output Results --> After the call, a6=3, b6=5

	/* 매개변수 사이의 자료전달 방법 예제 2 - 참조에 의한 자료전달 call by reference - 2. 호출 */
	/* Example 2 of how to transfer data between parameters - call by reference - 2. Calling */
	int a7 = 3, b7 = 5;
	printf("Before the call, a7=%d, b7=%d\n", a7, b7);	// Output Results --> Before the call, a7=3, b7=5
	swap7(&a7, &b7);
	printf("After the call, a7=%d, b7=%d\n", a7, b7);	// Output Results --> After the call, a7=5, b7=3

	/* 기억 클래스 storage class 예제 1 - 지역변수 local variable */
	/* Example 1 of storage classes - local variable */
	Example of storage classes
	int i8 = 10;
	printf("\nmain i8=%d\n", i8);				// Output Results --> main i8=10
	fcn8();
	printf("\nmain i8=%d\n", i8);				// Output Results --> main i8=10

	int x8 = 2, y8 = 4;
	printf("A: x8=%d, y8=%d\n", x8, y8);			// Output Results --> A: x8=2, y8=4
	{
		int x8;
		x8 = 5;
		y8++;
		printf("B: x8=%d, y8=%d\n", x8, y8);		// Output Results --> B: x8=5, y8=5
	}
	printf("A: x8=%d, y8=%d\n", x8, y8);			// Output Results --> A: x8=2, y8=5

	/* 기억 클래스 storage class 예제 2 - 전역변수 global variable */
	/* Example 2 of storage classes - global variable */
	printf("1) x9=%d\n", x9);				// Output Results --> 1) x9=0
	fcn9();
	printf("2) x9=%d\n", x9);				// Output Results --> 2) x9=1

	/* 기억 클래스 storage class 예제 3 - 자동변수 auto */
	/* Example 3 of storage classes - auto variable */

	// auto 생략
	// auto is omitted
	int i10 = 1;

	auto int j10 = 2;
	{
		int i10 = 3;
		{
			int i10 = 4;
			printf("i10 in block 2 is %d\n", i10);	// Output Results --> i10 in block 2 is 4
			printf("j10 in block 2 is %d\n", j10);	// Output Results --> j10 in block 2 is 2
		}
		printf("i10 in block 1 is %d\n", i10);		// Output Results --> i10 in block 1 is 3
	}
	printf("i10 in void main() function is %d\n", i10);	// Output Results --> i10 in void main() function is 1

	/* 기억 클래스 storage class 예제 4 - 정적변수 static */
	/* Example 4 of storage classes - static variable */
	int a11 = 10;						// auto variable
	static int b11 = 20;					// static variable
	{
		int a11 = 5;
		printf("a11=%d b11=%d\n", a11, b11);		// Output Results --> a11=5 b11=20
	}
	printf("a11=%d b11=%d\n", a11, b11);			// Output Results --> a11=10 b11=20

	int i11;
	i11 = 0;
	while (i11 < 3) {
		test11();					// Output Results --> auto=0, static=0 \n auto=0, static=1 \n auto=0, static=2
		i11++;
	}

	/* 기억 클래스 storage class 예제 5 - 외부변수 extern */
	/* Example 5 of storage classes - extern variable */

	// 외부변수 선언 extern 생략 가능
	// External variable declaration. extern can be omitted
	extern int i12;

	// 외부변수 선언 extern 생략 불가
	// External variable declaration. extern cannot be omitted
	extern int k12;

	int j12 = 100;
	printf("i12=%d j12=%d k12=%d\n", i12, j12, k12);	// Output Results --> i12=10 j12=100 k12=50

	printf("Enter a string.\n");
	scanf("%s", s13);
	printf("The input string is %s stored in the global variable s13\n", s13);

	// extern_ex13() 함수 - 2. 호출 - 전역변수 s13에 입력된 문자열이 출력됨
	// extern_ex13() function - 2. Calling - String entered in global variable s13 is output
	extern_ex13();

	/* 기억 클래스 storage class 예제 6 - 레지스터변수 register */
	/* Example 6 of storage classes - register variable */
	register int i14;
	int sum14 = 0;

	// register변수를 반복문의 카운터 변수로 사용
	// Using register variable as counter variable of repeat statement
	for (i14 = 0; i14 <= 10; ++i14)
		sum14 += i14;

	i14 -= 1;
	printf("i14=%d sum14=%d\n", i14, sum14);		// Output Results --> i14=10 sum14=55
}

/* 사용자 정의 함수 예제 - 3. 정의 */
/* Example of a user-defined function - 3. Definition */
int sum3(int a3, int b3) {
	int d3;
	d3 = a3 + b3;
	return(d3);
}

/* return 예제 - 3. 정의 */
/* Example of return - 3. Definition */
int max4(int x4, int y4) {
	return(x4 > y4 ? x4 : y4);
}

int min4(int x4, int y4) {
	if (x4 > y4)
		return y4;
	else
		return x4;
}

/* 함수 호출 예제 - 3. 정의 */
/* Example of calling functions - 3. Definition */
test5() {
	printf("Different ways to use a Function\n");
}

int sum5(int a5, int b5) {
	int i5, s5 = 0;
	for (i5 = a5; i5 <= b5; i5++)
		s5 = s5 + i5;
	return s5;
}

/* 매개변수 사이의 자료전달 방법 예제 - 3. 정의 */
/* Example of how to transfer data between parameters - 3. Definition */
void swap6(int x6, int y6) {
	int temp;
	temp = x6;
	x6 = y6;
	y6 = temp;
	printf("in the function, x6=%d, y6=%d\n", x6, y6);	// Output Results --> in the function, x6=5, y6=3
}

void swap7(int* x7, int* y7) {
	int temp;
	temp = *x7;
	*x7 = *y7;
	*y7 = temp;
	printf("in the function, x7=%d, y7=%d\n", *x7, *y7);	// Output Results --> in the function, x7=5, y7=3
}

/* 기억 클래스 storage class 예제 - 3. 정의 */
/* Example of storage classes - 3. Definition */
void fcn8() {
	int i8;
	i8 = 20;
	printf("\nfcn8 i8=%d\n", i8);			// Output Results --> fcn8 i8=20
}

void fcn9() {
	x9++;
}

test11() {
	// a11은 지역변수이므로 함수 호출 시마다 0으로 초기화 됨
	// a11 is a local variable, so it is initialized to 0 with each function call
	auto int a11 = 0;

	// s11은 전역변수이므로 함수 호출 시 이전 실행 결과값이 유지됨
	// s11 is a global variable, so the previous execution result value is retained when calling the function
	static int s11 = 0;

	printf("auto=%d, static=%d\n", a11, s11);
	++a11;
	++s11;
}

int k12 = 50;
```
   
<br />
#### etc. sourceFile   
// 외부변수가 선언된 파일   
`externExample.c` : Files with external variables declared   
   
```c
#include <stdio.h>

/* 변수 s13을 외부변수로 선언 - 다른 파일에서 선언된 전역변수 s13을 이 파일에서 사용 */
/* Declare variable s13 as external variable - Use global variable s13 declared in another file, in this file */
extern char s13[];

/* extern_ex13() 함수 - 3. 정의 */
/* extern_ex13() function - 3. Definition */
void extern_ex13() {
	printf("The value of the extern variable s13 is %s.\n", s13);
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
