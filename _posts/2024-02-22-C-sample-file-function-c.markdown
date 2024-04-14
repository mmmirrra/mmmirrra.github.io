---
layout: post
title:  "C: sample_file_function.c"
date:   2024-02-22 09:00:00 +0900
categories: [C]
---

solution 'CPrjs'   
project 'Sample_File_Function'   
   
### sourceFile list - .c   
#### main() sourceFile   
`sample_file_function.c` : C practice project main function   
   
```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#pragma warning(disable:4996)

void main() {

	/* 파일 입출력 프로그램의 구조 예제 */
	char ch1;
	FILE* fp1;						// 파일포인터 선언 - 파일형 (구조체형) 포인터변수를 선언
	fp1 = fopen("sample1.txt", "w");			// 파일 open - 스트림 stream 통로 생성됨 - 기존 파일이 없는 경우 프로젝트와 동일 폴더에 파일 생성됨

	for (ch1 = 'A'; ch1 <= 'Z'; ch1++)
		fputc(ch1, fp1);
	fclose(fp1);						// 파일 close - 스트림 stream 통로 소멸됨
	printf("fp1 close\n");

	/* 파일 열리지 않는 경우에 대한 예외 처리 예제 */
	char ch2;
	FILE* fp2;						// 파일포인터 선언 - 파일형 (구조체형) 포인터변수를 선언
	if ((fp2 = fopen("sample2.txt", "w")) == NULL) {	// 파일 open - 스트림 stream 통로 생성됨
		puts("Unable to open file!\n");
		exit(1);					// 프로그램을 종료할 때 사용하는 함수
	} else {
		printf("fp2 open\n");
		for (ch2 = 'C'; ch2 <= 'Z'; ch2++)
			fputc(ch2, fp2);
		fclose(fp2);					// 파일 close - 스트림 stream 통로 소멸됨
	};

	/* 순차파일 putc() 함수 예제 - 문자를 파일로 출력 */
	char c3;
	FILE* fp3;						// 파일포인터 선언
	fp3 = fopen("sample3.dat", "w");			// 파일 open - 텍스트파일, 쓰기모드로 개방
	if (fp3 == NULL) {					// 파일 개방 에러 체크
		printf("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	printf("Enter a character. Enter 'ctrl+Z' to end the input\n");
	while ((c3 = getchar()) != EOF)			// 문자 출력의 끝을 판별 - ctrl + Z 입력 시 끝이라고 판별함
		putc(c3, fp3);					// 문자를 파일로 출력
	fclose(fp3);						// 파일 close

	/* 순차파일 fputs() 함수 예제 - 문자열을 파일로 출력 */
	char name4[64];
	FILE* fp4;						// 파일포인터 선언
	if ((fp4 = fopen("sample4.dat", "w")) == NULL) {	// 파일 open - 텍스트파일, 쓰기모드로 개방 - 파일 개방 에러 체크
		puts("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	printf("Enter a string. Enter 'end' to end the input\n");
	gets(name4);
	while (strcmp(name4, "end")) {				// 문자열 출력의 끝을 판별 - end 입력 시 끝이라고 판별함
		strcat(name4, "\n");				// 하나의 문자열에 다른 것 ('\n') 을 추가 - 레코드의 끝을 추가
		fputs(name4, fp4);				// 문자열을 파일로 출력
		gets(name4);
	}
	fclose(fp4);						// 파일 close

	/* 순차파일 fprintf() 함수 예제 - 여러 항목의 복합적인 자료로 구성된 레코드를 파일로 출력 */
	char no5[10], name5[10];
	int mid5, term5, rep5, att5, i5;
	FILE* fp5;						// 파일포인터 선언
	fp5 = fopen("sample5.dat", "w");			// 파일 open - 텍스트파일, 쓰기모드로 개방
	if (fp5 == NULL) {					// 파일 개방 에러 체크
		printf("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	fprintf(stdout, "Enter student number, name, middle score, final score, report score, and attendance score\n");		// stdout : 모니터를 가리키는 특수한 파일포인터
	for (i5 = 0; i5 < 5; ++i5) {
		scanf("%s %s %d %d %d %d", no5, name5, &mid5, &term5, &rep5, &att5);			// 레코드 값을 입력 받음
		fprintf(fp5, "%10s %8s %3d %3d %3d %3d\n", no5, name5, mid5, term5, rep5, att5);	// 출력 형식대로 레코드를 파일로 출력
	}
	fclose(fp5);						// 파일 close

	/* 순차파일 getc() 함수 예제 - 파일을 문자 단위로 읽기 */
	printf("read - sample3.dat\n");
	char c6;
	FILE* fp6;						// 파일포인터 선언
	fp6 = fopen("sample3.dat", "r");			// 파일 open - 텍스트파일, 읽기모드로 개방
	if (fp6 == NULL) {					// 파일 개방 에러 체크
		printf("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	while ((c6=getc(fp6)) != EOF)				// 파일의 끝까지 읽음 - getc() 함수에 의해 한 문자씩 읽어와 c6에 전달
		putchar(c6);					// 표준출력함수 putchar() - 모니터에 출력
	fclose(fp6);						// 파일 close
	
	/* 순차파일 fgets() 함수 예제 - 파일을 문자열 단위로 읽기 */
	printf("read - sample4.dat\n");
	char name7[20];;
	FILE* fp7;						// 파일포인터 선언
	if ((fp7 = fopen("sample4.dat", "r")) == NULL) {	// 파일 open - 텍스트파일, 읽기모드로 개방 - 파일 개방 에러 체크
		puts("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	while ((fgets(name7, 20, fp7)!= NULL))			// 파일의 끝까지 문자열 길이 20만큼 읽음 - fgets() 함수에 의해 문자열 읽어와 name7에 전달
		printf("%s", name7);				// 모니터에 출력
	fclose(fp7);						// 파일 close

	/* 순차파일 fscanf() 함수 예제 - 여러 항목의 복합적인 자료로 구성된 레코드 파일을 읽기 */
	printf("read - sample5.dat\n");
	char no8[10], name8[10];
	int mid8, term8, rep8, att8;
	FILE* fp8;						// 파일포인터 선언
	fp8 = fopen("sample5.dat", "r");			// 파일 open - 텍스트파일, 읽기모드로 개방
	if (fp8 == NULL) {					// 파일 개방 에러 체크
		printf("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	printf("student number, name, middle score, final score, report score, and attendance score\n");
	while (!feof(fp8)) {					// 파일의 끝까지 읽음
		fscanf(fp8, "%10s %8s %3d %3d %3d %3d", no8, name8, &mid8, &term8, &rep8, &att8);	// 파일의 레코드 값을 입력 받음
		printf("%-10s %-8s %4d %4d %4d %4d\n", no8, name8, mid8, term8, rep8, att8);		// 입력 형식대로 레코드를 모니터로 출력
	}
	fclose(fp8);						// 파일 close

	/* 순차파일 레코드 추가 예제 */
	FILE* fp9;
	fp9 = fopen("sample6.dat", "a");			// 파일 open - 텍스트파일, 추가모드로 개방 - 기존 파일이 없는 경우 프로젝트와 동일 폴더에 파일 생성됨
	fputs("Cho DS\n", fp9);
	fputs("Han JK\n", fp9);
	fputs("Kang MH\n", fp9);
	fclose(fp9);						// 파일 close

	printf("read - sample6.dat\n");
	char name10[20];;
	FILE* fp10;						// 파일포인터 선언
	if ((fp10 = fopen("sample6.dat", "r")) == NULL) {	// 파일 open - 텍스트파일, 읽기모드로 개방 - 파일 개방 에러 체크
		puts("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	while ((fgets(name10, 20, fp10) != NULL))		// 파일의 끝까지 문자열 길이 20만큼 읽음 - fgets() 함수에 의해 문자열 읽어와 name7에 전달
		printf("%s", name10);				// 모니터에 출력
	fclose(fp10);						// 파일 close

	/* 랜덤파일 fwrite() 함수 예제 */
	char name11[10];
	FILE* fp11;						// 파일포인터 선언
	if ((fp11 = fopen("sample7.dat", "wb")) == NULL) {	// 파일 open - 2진파일, 쓰기모드로 개방 - 파일 개방 에러 체크
		puts("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	printf("Enter a string. Enter 'end' to end the input\n");
	gets(name11);
	while (strcmp(name11, "end")) {			// 문자열 출력의 끝을 판별 - end 입력 시 끝이라고 판별함
		fwrite(name11, 10, 1, fp11);			// fwrite (저장자료변수, 레코드길이, 레코드개수, 파일포인터); - 2진 파일 쓰기
		gets(name11);
	}
	fclose(fp11);						// 파일 close

	/* 랜덤파일 fread() 함수 예제 */
	printf("read - sample7.dat\n");
	char name12[10];
	FILE* fp12;						// 파일포인터 선언
	if ((fp12 = fopen("sample7.dat", "rb")) == NULL) {	// 파일 open - 2진파일, 읽기모드로 개방 - 파일 개방 에러 체크
		puts("Unable to open file!\n");
		exit(1);					// 프로그램을 끝냄
	}
	while (1) {						// 파일의 끝까지 읽음
		if (fread(name12, 10, 1, fp12) != 1)		// fwrite (읽을자료변수, 레코드길이, 레코드개수, 파일포인터); - 2진 파일 읽기
			break;					// 레코드 개수가 1이 아닌 경우 (== 읽을 레코드가 없는 경우 == 파일의 끝인 경우) while 종료
		puts(name12);					// 문자열을 모니터에 출력
	}
	fclose(fp12);						// 파일 close

	/* 랜덤파일 fseek() 함수 예제 */
	char str13[10];
	FILE* fp13 = fopen("sample8.txt", "wt");
	fputs("1234567890", fp13);
	fclose(fp13);

	printf("read - sample8.txt\n");
	fp13 = fopen("sample8.txt", "rt");
	fseek(fp13, 7, SEEK_SET);
	fgets(str13, 4, fp13);
	printf("Outputs 3 characters from the 7th character: %s \n", str13);					// 7번째 글자부터 3글자 출력 - 출력결과 --> 890
	fseek(fp13, -2, SEEK_CUR);
	fgets(str13, 3, fp13);
	printf("Outputs 2 characters to 2 characters in front of the current location: %s \n", str13);		// 현재 위치에서 앞에 2글자부터 2글자 출력 - 출력결과 --> 90
	fseek(fp13, -9, SEEK_END);
	fgets(str13, 6, fp13);
	printf("Outputs 5 characters from the beginning of the 9th character at the end: %s \n", str13);	// 맨 뒤에서 9번째 앞부터 5글자 출력 - 출력결과 --> 23456
	fclose(fp13);
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
