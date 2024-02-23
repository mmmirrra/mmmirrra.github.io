---
layout: post
title:  "C: sample_dynamic-allocation.c"
date:   2024-02-23 09:00:00 +0900
categories: [C]
---

solution 'CPrjs'   
project 'Sample_Dynamic-Allocation'   
   
### sourceFile list - .c   
#### main() sourceFile   
`sample_dynamic-allocation.c` : C practice project main function   
   
```c
#include <stdio.h>
#include <stdlib.h>

/* 기억공간 관리함수를 위한 헤더파일 */
#include <mem.h>

#pragma warning(disable:4996)

/* 메모리 정적할당 예제 - 1. 함수 원형 선언 */
void test1(int);
void test2(int);
int a1 = 100;						// 전역변수 - 데이터 영역에 할당 - 프로그램 종료 시 까지 존재

void main() {

	/* 메모리 정적할당 예제 - 2. 함수 호출 */
	int b1 = a1;					// 지역변수 - 스택 영역에 할당 - main() 함수 종료 시 까지 존재
	test1(b1);
	test2(b1);

	/* 메모리 동적할당 malloc() 예제 1 */
	int* a3;					// 동적할당을 위한 포인터변수 선언
	a3 = (int*)malloc(sizeof(int));			// a3과 자료형을 일치시키기 위해 강제 형변환 - 힙 영역에 할당 - free() 함수 실행 전까지 존재
	if (a3 == NULL) {				// 기억공간 할당 성공 여부 판단
		puts("Memory allocation failed!\n");
		exit(1);
	}
	*a3 = 20;
	printf("Variable a3 stored in heap: %d\n", *a3);	// 출력결과 --> Variable a3 stored in heap: 20
	free(a3);					// 할당받은 기억공간 해제

	/* 메모리 동적할당 malloc() 예제 2 */
	int size4;					// 입력받을 문자 수를 저장할 변수 선언
	char* str4;					// 동적할당을 위한 포인터변수 선언
	printf("Enter the size of the string\n");
	scanf("%d", &size4);
	str4 = (char*)malloc(size4 + 1);		// str4와 자료형을 일치시키기 위해 강제 형변환 - 힙 영역에 할당 - free() 함수 실행 전까지 존재
	if (str4 == NULL) {				// 기억공간 할당 성공 여부 판단
		puts("Memory allocation failed!\n");
		exit(1);
	}
	printf("Enter the size of the string\n");
	scanf("%s", str4);				// 동적으로 할당된 기억공간에 문자열 저장
	printf("String stored in dynamically allocated memory: %s\n", str4);
	free(str4);					// 할당받은 기억공간 해제

	/* 메모리 동적할당 calloc() 예제 */
	int i5;
	int* a5;					// 동적할당을 위한 포인터변수 선언
	a5 = (int*)calloc(5, sizeof(int));		// a5와 자료형을 일치시키기 위해 강제 형변환 - 힙 영역에 할당 - free() 함수 실행 전까지 존재
	for (i5 = 0; i5 < 5; i5++) {
		printf("%d\n", a5[i5]);			// 출력결과 --> 0 \n 0 \n 0 \n 0 \n 0 \n
	}
	free(a5);					// 할당받은 기억공간 해제

	/* 메모리 동적할당 realloc() 예제 */
	int* a6;
	a6 = (int*)calloc(5, sizeof(int));		// int형 크기의 기억공간 5개 할당
	a6 = (int*)realloc(a6, 10 * sizeof(int));	// int형 크기의 기억공간 10개 재할당
	free(a6);

	/* 기억공간 관리함수 memcmp() 예제 */
	char* s71 = "aaa";
	char* s72 = "bbb";
	int stat7;
	stat7 = memcmp(s71, s72, 3);			// s71과 s72의 내용을 3byte만큼 비교하여 그 결과를 stat에 저장
	printf("%d\n", stat7);				// 출력결과 --> -1

	/* 기억공간 관리함수 memcpy() 예제 */
	char src8[] = "1234567890";
	char dest8[] = "abcdefghijklmnopqrstuvwxyz";
	char* stat8;
	printf("Data from dest8 before memcpy() runs: %s\n", dest8);		// 출력결과 --> abcdefghijklmnopqrstuvwxyz
	stat8 = (char*)memcpy(dest8, src8, strlen(src8));			// src8의 첫 부분에서부터 문자열의 길이(strlen())만큼의 자료를 dest8에 복사
	if (stat8)
		printf("Data from dest8 after memcpy() runs: %s\n", dest8);	// 출력결과 --> 1234567890klmnopqrstuvwxyz
	else
		printf("Copy failed\n");

	/* 기억공간 관리함수 memset() 예제 */
	char s9[] = "1234567890";
	printf("Data from s9 before memset() runs: %s\n", s9);			// 출력결과 --> 1234567890
	memset(s9, '*', strlen(s9));						// 배열 s9의 데이터를 '*'로 문자열의 길이만큼 (strlen()) 채움
	printf("Data from s9 after memset() runs: %s\n", s9);			// 출력결과 --> **********
}

/* 메모리 정적할당 예제 - 3. 함수 정의 */
void test1(int c) {		// 매개변수 - 스택 영역에 할당 - test1() 함수 종료 시 까지 존재
	int d;			// 지역변수 - 스택 영역에 할당 - test1() 함수 종료 시 까지 존재
	d = c + 10;
	printf("%d\n", d);
}

void test2(int e) {		// 매개변수 - 스택 영역에 할당 - test2() 함수 종료 시 까지 존재
	int f;			// 지역변수 - 스택 영역에 할당 - test2() 함수 종료 시 까지 존재
	f = e + 20;
	printf("%d\n", f);
}
```
