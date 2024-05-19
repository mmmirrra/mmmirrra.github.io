---
layout: post
title:  "C: sample_structure_union.c"
date:   2024-02-20 09:00:00 +0900
categories: [C]
---

solution 'CPrjs'   
project 'Sample_Structure_Union'   
   
### sourceFile list - .c   
#### main() sourceFile   
`sample_structure_union.c` : C practice project main function   
   
```c
#include <stdio.h>
#include <string.h>

#pragma warning(disable:4996)

/* 구조체 structure 예제 - 1. person1형 구조체 선언 */
struct person1 {
	char name[8];
	int age;
	char sex;
};

/* 구조체 배열 포인터변수 structure pointer 사용 예제  - 1. student4형 구조체 선언 */
struct student4 {
	char name[10];
	int kor;
	int math;
};

/* 구조체를 함수의 매개변수로 사용 예제 - 1. num4형 구조제 선언, calc4 원형 선언 */
struct num4 {
	int x;
	int y;
	int sum;
	int mul;
};

struct num4 calc4(struct num4);

/* 구조체 포인터변수를 함수의 매개변수로 사용 예제 - 1. num5형 구조제 선언, calc5 원형 선언 */
struct num5 {
	int x;
	int y;
	int sum;
	int mul;
};

struct num5 calc5(struct num5*);

/* typedef 예제 1 - 1. data6형 구조체 선언, typedef 선언 */
struct data6 {
	int x;
	int y;
};

typedef struct data6 DATA6;

typedef struct data7 {
	int x;
	int y;
} DATA7;

/* typedef 예제 2 - 1. person8형 구조체 선언, typedef 선언 */
struct person8 {
	char name[20];
	char sex;
	int age;
};

typedef struct person8 MAN8;
typedef unsigned char CHAR8;
typedef int* PTR8;

void main() {

	/* 구조체 structure 예제 - 2. person형 구조체 선언과 초기화 */
	struct person1 X1 = { "HONG", 30, 'M' };
	struct person1 Y1;
	strcpy(Y1.name, "LIM");
	Y1.age = 35;
	Y1.sex = 'M';
	printf("X1: %s, %d, %c\n", X1.name, X1.age, X1.sex);			// 출력결과 --> X1 : HONG, 30, M:
	printf("Y1: %s, %d, %c\n", Y1.name, Y1.age, Y1.sex);			// 출력결과 --> Y1 : LIM, 35, M
	printf("sizeof(struct person1) : %d\n", sizeof(struct person1));	// 출력결과 --> sizeof(struct person1) : 16
	printf("sizeof(X1) : %d\n", sizeof(X1));				// 출력결과 --> sizeof(X1) : 16
	printf("sizeof(Y1.name) : %d\n", sizeof(Y1.name));			// 출력결과 --> sizeof(Y1.name) : 8
	printf("sizeof(Y1.age) : %d\n", sizeof(Y1.age));			// 출력결과 --> sizeof(Y1.age) : 4
	printf("sizeof(Y1.sex) : %d\n", sizeof(Y1.sex));			// 출력결과 --> sizeof(Y1.sex) : 1
	/* sex에는 person1의 멤버 중 가장 큰 자료형인 int의 크기인 4바이트가 배정됨 */
	printf("sizeof(Y1) : %d\n", sizeof(Y1));				// 출력결과 --> sizeof(Y1) : 16

	/* 구조체 배열 structure array 예제 */
	struct person2 {
		char* name;
		int age;
		char sex;
	};

	struct person2 X2[3] = { { "HONG", 20, 'M' },
                                  { "HWANG", 22,'F' },
                                  { "LIM", 30, 'M' } };
	int i2, sum2 = 0;
	for (i2 = 0; i2 < 3; i2++) {
		printf("name:%s age:%d sex:%c\n", X2[i2].name, X2[i2].age, X2[i2].sex);		// 출력결과 --> name:HONG age:20 sex:M \n name:HWANG age:22 sex:F \n name:LIM age:30 sex:M
		sum2 = sum2 + X2[i2].age;
	}
	printf("age sum:%d\n", sum2);				// 출력결과 --> age sum:72

	/* 구조체 포인터변수 structure pointer 선언 예제 */
	struct person3 {
		char* name;
		int age;
		char sex;
	};

	struct person3 man3;
	struct person3* pt3;
	pt3 = &man3;

	/* 구조체 배열 포인터변수 structure pointer 사용 예제  - 2. student4형 구조체 선언과 초기화 */
	struct student4 hs4[4] = { { "KIM HG", 90, 95 },
                                    { "LEE SY", 85, 90 },
                                    { "PARK GS", 70, 85 },
                                    { "CHOI HI", 95, 75 } };
	struct student4* p4;
	p4 = hs4;
	printf("%s %d %d\n", p4->name, p4->kor, p4->math);	// 출력결과 --> KIM HG 90 95
	p4 += 3;
	printf("%s %d %d\n", p4->name, p4->kor, p4->math);	// 출력결과 --> CHOI HI 95 75
	p4--;
	printf("%s %d %d\n", p4->name, p4->kor, p4->math);	// 출력결과 --> PARK GS 70 85

	/* 구조체를 함수의 매개변수로 사용 예제 - 2. calc4 호출 */
	struct num4 number4;
	number4.x = 10;
	number4.y = 20;
	number4 = calc4(number4);
	printf("x:%d, y:%d, sum:%d, mul:%d\n", number4.x, number4.y, number4.sum, number4.mul);		// 출력결과 --> x:10, y:20, sum:30, mul:200

	/* 구조체 포인터변수를 함수의 매개변수로 사용 예제 - 2. calc5 호출 */
	struct num5 number5;
	number5.x = 10;
	number5.y = 20;
	calc5(&number5);
	printf("x:%d, y:%d, sum:%d, mul:%d\n", number5.x, number5.y, number5.sum, number5.mul);		// 출력결과 --> x:10, y:20, sum:30, mul:200

	/* typedef 예제 1 - 2. data6형 구조체 선언과 초기화 */
	DATA6 d6 = { 1, 2 };
	printf("d6.x=%d, d6.y=%d\n", d6.x, d6.y);	// 출력결과 --> d6.x=1, d6.y=2

	/* typedef 예제 2 - 2. person8형 구조체 선언과 초기화 */
	MAN8 member8;
	CHAR8 data8;
	PTR8 pt8;
	strcpy(member8.name, "HONG GIL DONG");
	member8.sex = 'M';
	member8.age = 30;
	data8 = 100;
	pt8 = &(member8.age);
	printf("*pt8=%d\n", *pt8);			// 출력결과 --> *pt8=30

	/* 구조체의 비트필드 bit field 예제 */
	struct test9 {					// 전체 비트의 합은 자료형의 크기 (여기에서는 unsigend 이므로 int 4byte) 보다 크기가 작아야 함
		unsigned a : 5;
		unsigned b : 6;
		unsigned c : 6;
		unsigned d : 4;
	};
	struct test9 v9 = { 1, 2, 3, 4 };
	printf("v9.a=%d, v9.b=%d, v9.c=%d, v9.d=%d\n", v9.a, v9.b, v9.c, v9.d);	// 출력결과 --> v9.a=1, v9.b=2, v9.c=3, v9.d=4
	printf("v9 uses %dbyte.\n", sizeof(v9));				// 출력결과 --> v9 uses 4byte.

	/* 공용체 union 예제 */
	union test10 {
		short int i;
		float f;
		double d;
	};

	union test10 u10;
	u10.i = u10.f = u10.d = 0;
	printf("sizeof(u10): %dbyte\n", sizeof(u10));		// 출력결과 --> sizeof(u10):8byte
	u10.i = 100;
	printf("i:%d f:%f d:%f\n", u10.i, u10.f, u10.d);	// 출력결과 --> i:100 f:0.000000 d:0.000000
	u10.f = 0.5;
	printf("i:%d f:%f d:%f\n", u10.i, u10.f, u10.d);	// 출력결과 --> i:0 f:0.500000 d:0.000000
	u10.d = 0.016667;
	printf("i:%d f:%f d:%f\n", u10.i, u10.f, u10.d);	// 출력결과 --> i:-28156 f:109291767575372798867298844672.000000 d:0.016667
}

/* 구조체를 함수의 매개변수로 사용 예제 - 3. calc4 정의 */
struct num4 calc4(struct num4 number) {
	number.sum = number.x + number.y;
	number.mul = number.x * number.y;
	return(number);
}

/* 구조체 포인터변수를 함수의 매개변수로 사용 예제 - 1. num5형 구조제 선언, calc5 원형 선언 */
struct num5 calc5(struct num5* number) {
	(*number).sum = (*number).x + (*number).y;		// (*number).sum == number->sum
	number->mul = number->x * number->y;
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
