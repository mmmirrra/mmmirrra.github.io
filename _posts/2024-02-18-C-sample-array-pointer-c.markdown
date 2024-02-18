---
layout: post
title:  "C: sample_array_pointer.c"
date:   2024-02-18 09:00:00 +0900
categories: [C]
---

solution 'CPrjs'   
project 'Sample_Array_Pointer'   
   
### sourceFile list - .c   
#### main() sourceFile   
`sample_array_pointer.c` : C practice project main function   
   
```c
#include <stdio.h>

#pragma warning(disable:4996)

/* 2차원 배열이 함수의 매개변수로 사용된 예제 - 1. 원형 prototype 선언 */
void score_sum6(int gr6[][5], int, int);

void main() {

	/* 1차원 배열 예제 */
	int array1[4] = { 10, 20, 30, 40 };			// 기억 클래스 auto 생략됨 : 자동변수. 지역변수
	int array2[] = { 10, 20, 30, 40 };
	int array3[4] = { 10, 20 };
	int array4[4] = { 1 };
	int i1;
	for (i1 = 0; i1 <= 3; i1++)
		printf("array1[%d]=%d\t", i1, array1[i1]);	// 출력결과 --> array1[0]=10 \t array1[1]=20 \t array1[2]=30 \t array1[3]=40
	printf("\n");
	for (i1 = 0; i1 <= 3; i1++)
		printf("array2[%d]=%d\t", i1, array2[i1]);	// 출력결과 --> array2[0]=10 \t array2[1]=20 \t array2[2]=30 \t array2[3]=40
	printf("\n");
	for (i1 = 0; i1 <= 3; i1++)
		printf("array3[%d]=%d\t", i1, array3[i1]);	// 출력결과 --> array3[0]=10 \t array3[1]=20 \t array3[2]=0 \t array3[3]=0
	printf("\n");
	for (i1 = 0; i1 <= 3; i1++)
		printf("array4[%d]=%d\t", i1, array4[i1]);	// 출력결과 --> array4[0]=1 \t array4[1]=0 \t array4[2]=0 \t array4[3]=0
	printf("\n");

	static int x2[] = { 1, 2, 3, 4 };			// 기억 클래스 static 사용 : 정적변수. 전역변수
	static int y2[] = { 10, 20, 30, 40 };
	int i2, z2[4];
	for (i2 = 0; i2 < 4; ++i2)
		z2[i2] = x2[i2] + y2[3 - i2];
	printf("Sum of array elements in opposite positions\n");
	for (i2 = 0; i2 < 4; ++i2)
		printf("%d+%d=%d\n", x2[i2], y2[3 - i2], z2[i2]);	// 출력결과 --> 1 + 40 = 41 \n 2 + 30 = 32 \n 3 + 20 = 23 \n 4 + 10 = 14

	/* 2차원 배열 예제 */
	static int score3[4][3] = { {90, 90, 90},
                                      {80, 80, 80},
                                      {70, 70, 70},
                                      {60, 60, 60} };
	int sum3, i3, j3;
	printf("Number\tKorean\tMath\tEnglish\tSum\n");
	for (i3 = 0; i3 < 4; ++i3) {
		sum3 = 0;
		printf("%3d", i3 + 1);					// 출력결과 --> 1 2 3 4
		for (j3 = 0; j3 < 3; j3++) {
			printf("\t%3d", score3[i3][j3]);		// 출력결과 --> \t 90 \t 90 \t 90 80 \t 80 \t 80 \t 70 \t 70 \t 70 \t 60 \t 60 \t 60 \t
			sum3 += score3[i3][j3];
		}
		printf("\t%3d\n", sum3);				// 출력결과 --> \t 270 \n \t 240 \n \t 210 \n \t 180 \n
	}

	/* char형 배열 예제 */
	char name4[] = "HONG GIL DONG";
	char adrs1[6] = { 'S', 'E', 'O', 'U', 'L', '\0' };
	char adrs2[6] = { 'S', 'E', 'O', 'U', 'L' };			// 마지막 요소를 \0으로 하지 않음. 기억공간을 6보다 적게 할 경우 문자 뒤에 이상한 값이 자동 추가됨
	printf("\n name4 : %s\n", name4);				// 출력결과 --> name4 : HONG GIL DONG
	printf("\n adrs1 : %s\n", adrs1);				// 출력결과 --> adrs1 : SEOUL
	printf("\n adrs2 : %s\n", adrs2);				// 출력결과 --> adrs2 : SEOUL 

	char string5[50];
	int i5 = 0;
	printf("Enter a string less than 49 characters.\n");
	scanf("%s", string5);
	printf("Input string: %s\n", string5);
	printf("Output on a character basis: \n");
	while (string5[i5] != '\0') {					// \0 null 문자인 경우 종료
		printf("%c\n", string5[i5]);
		i5++;
	}

	/* 2차원 배열이 함수의 매개변수로 사용된 예제 - 2. 호출 - 가장 높은 차원의 크기 생략 가능 */
	int score6[2][5] = { {10, 20, 30, 40, 50},
                         {10, 10, 10, 10, 10} };
	score_sum6(score6, 2, 5);					// 출력결과 --> sum6[0]=150 \n sum6[1] = 50

	/* 포인터변수 pointer 개념 예제 1 - 변수의 주소 */
	int days7 = 365;
	int month7 = 12;
	int Table7[5] = { 1, 2, 3, 4, 5 };
	printf("The address of days7 is %x\n", &days7);			// 포인터 주소가 16진수로 표기됨
	printf("The address of month7 is %x\n", &month7);
	printf("The address of the array name Table7 is %x\n", Table7);
	printf("The address of the first element of the array name Table7 is %x\n", &Table7[0]);
	printf("The address of the second element of the array name Table7 is %x\n", &Table7[1]);

	/* 포인터변수 pointer 개념 예제 2 - 변수의 사용 */
	int a8, b8;					// 일반변수 선언
	int* p8;					// 포인터변수 선언
	a8 = 5000;					// 일반변수 초기값 설정 : 값 5000 치환
	p8 = &a8;					// 포인터변수 초기값 설정 : a8의 주소를 치환
	b8 = *p8;					// 일반변수 초기값 설정 : 포인터변수 p8이 가리키는 주소인 a8이 가진 값 5000을 b8에 치환

	int* p9, i9 = 4;
	p9 = &i9;					// 포인터변수 초기값 설정 : i9의 주소를 치환
	*p9 = 10;					// 포인터변수 p9가 가리키는 주소인 i9의 값을 10으로 치환
	printf("i9=%d\n", i9);				// 출력결과 --> i9=10

	/* 포인터변수 pointer 개념 예제 3 - 변수의 참조 */
	int* p10, i10 = 3, j10;
	p10 = &i10;					// 포인터변수 초기값 설정 : i10의 주소를 치환
	j10 = *p10;					// 포인터변수 p10이 가리키는 주소인 i10이 가진 값 3을 j10에 치환
	j10++;
	printf("*p10=%d\n", *p10);			// 출력결과 --> *p10=i10의 값 3
	printf("p10=%x\n", p10);			// 출력결과 --> p10=i10의 주소 16진수
	printf("j10=%d\n", j10);			// 출력결과 --> j10=4

	/* 포인터변수 pointer 개념 예제 4 - 실행중 자료형이 결정되는 void형 포인터변수 - void *포인트명 */
	int a11 = 100;
	char b11 = 'B';
	void* p11 = NULL;
	p11 = (int*)&a11;				// 치환 시 int로 명시적 형변환
	printf("*p11=%d\n", *(int*)p11);		// 출력 시 int로 명시적 형변환 : 출력결과 --> *p11=100
	p11 = (char*)&b11;				// 치환 시 char 로 명시적 형변환
	printf("*p11=%c\n", *(char*)p11);		// 출력 시 char 로 명시적 형변환 : 출력결과 --> * p11=B

	/* 포인터변수 연산 예제 */
	int* p12, a12[] = { 10, 20, 30, 40, 50 };
	p12 = &a12[0];
	printf("*p12   == %d\n", *p12);			// 출력결과 --> *p12   == 10
	printf("*p12++ == %d\n", *p12++);		// 값을 출력 후 주소를 1(4byte) 증가 : 출력결과 --> *p12++ == 10
	printf("*++p12 == %d\n", *++p12);		// 주소를 1(4byte) 증가 후 값을 출력 : 출력결과 --> *++p12 == 30
	p12 = p12 + 2;					// 주소를 2(8byte) 증가
	printf("*p12   == %d\n", *p12);			// 출력결과 --> *p12   == 50
	printf("a12[2] == %d\n", a12[2]);		// 출력결과 --> a12[2] == 30
	printf("*p12+2 == %d\n", *p12 + 2);		// 값 + 2 : 출력결과 --> *p12+2 == 52

	int* p13, * q13;
	int a13[] = { 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 };
	p13 = &a13[3];
	printf("*p13     == %d\n", *p13);		// == a13[3] 값 : 출력결과 --> * p13 == 40
	printf("*(p13+3) == %d\n", *(p13 + 3));		// == a13[6] 값 : 출력결과 --> * (p13 + 3) == 70
	q13 = p13 + 3;
	printf("*q13     == %d\n", *q13);		// == a13[6] 값 : 출력결과 --> * q13 == 70
	printf("p13-q13  == %d\n", p13 - q13);		// == &a13[3] - &a13[6] : 출력결과 --> p13 - q13 == -3
	printf("q13-p13  == %d\n", q13 - p13);		// == &a13[6] - &a13[3] : 출력결과 --> q13 - p13 == 3
	// printf("q13+p13 == %d\n", q13 + p13);	// 포인터변수의 + 연산은 오류

	/* char 포인터변수 예제 */
	char* cp14 = "COMPUTER";			// 문자열을 포인터변수에 초기화 설정
	int i14 = 0;
	do
		printf("*(cp14+%d) : %c\n", i14, *(cp14 + i14));	// 출력결과 --> *(cp14+0) : C \n *(cp14+1) : O \n *(cp14+2) : M \n *(cp14+3) : P \n *(cp14+4) : U \n *(cp14+5) : T \n *(cp14+6) : E \n *(cp14+7) : R \n *(cp14+8) : \n
	while (*(cp14+i14++) != 0);

	/* 포인터변수를 이용한 1차원 배열 참조 예제 */
	static int a15[] = { 10, 20, 30, 40, 50 };
	int* pt15, b15, c15, d15;
	pt15 = a15;
	b15 = *pt15 + *(pt15 + 3);
	pt15++;
	c15 = *pt15 + *(pt15 + 3);
	d15 = *pt15 + 3;
	printf("b15=%d, c15=%d, d15=%d\n", b15, c15, d15);	// 출력결과 --> b15=50, c15=70, d15=23

	/* 포인터변수를 이용한 2차원 배열 참조 예제 */
	static a16[3][3] = { {1, 2, 3},
                              {4, 5, 6},
                              {7, 8, -9} };
	int* pt16;
	pt16 = a16[0];
	while (*pt16 != -9) {
		printf("%d\n", *pt16);				// 출력결과 --> 1 \n 2 \n 3 \n 4 \n 5 \n 6 \n 7 \n 8 \n
		pt16++;
	}

	/* 포인터변수와 배열의 호환 예제 */
	char A17[] = "ARRAY";
	char* p17 = "POINTER";
	int i17;
	for (i17 = 0; i17 < 5; i17++)
		printf("*(A17+%d) : %c\n", i17, *(A17 + i17));	// 출력결과 --> *(A17+0) : A \n * (A17+1) : R \n * (A17+2) : R \n * (A17+3) : A \n * (A17+4) : Y \n
	for (i17 = 0; i17 < 7; i17++)
		printf("p17[%d] : %c\n", i17, p17[i17]);	// 출력결과 --> p17[0] : P \n p17[1] : O \n p17[2] : I \n p17[3] : N \n p17[4] : T \n p17[5] : E \n p17[6] : R

	/* 포인터변수 배열 예제 */
	int a18[] = { 1, 2, 3, 4 };
	int b18[] = { 5, 6, 7, 8 };
	int* PA18[2];
	PA18[0] = a18;
	PA18[1] = b18;
	printf("*(PA18[0])=%d\n", *(PA18[0]));			// 출력결과 --> *(PA18[0])=1
	printf("*(PA18[0]+1)=%d\n", *(PA18[0] + 1));		// 출력결과 --> *(PA18[0]+1)=2
	printf("*PA18[1]=%d\n", *PA18[1]);			// 출력결과 --> *PA18[1]=5
	printf("*PA18[1]+15=%d\n", *PA18[1] + 15);		// 출력결과 --> *PA18[1]+15=20

	/* 이중포인터 Pointer to pointer 예제 */
	char a19 = 'A', * p19, ** pp19;
	p19 = &a19;
	pp19 = &p19;
	printf("**pp19=%c\n", **pp19);				// 출력결과 --> **pp19=A
}

/* 2차원 배열이 함수의 매개변수로 사용된 예제 - 3. 정의 */
void score_sum6(int gr6[][5], int row, int column) {		// 가장 높은 차원의 크기 생략 가능
	int sum6[2] = { 0 };
	int i6, j6;
	for (i6 = 0; i6 < row; i6++) {
		for (j6 = 0; j6 < column; j6++)
			sum6[i6] += gr6[i6][j6];		// 행별 합계 계산됨
		printf("sum6[%d]=%d\n", i6, sum6[i6]);
	}
}
```
