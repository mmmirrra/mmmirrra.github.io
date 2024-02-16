---
layout: post
title:  "C: sample_conditional_statement.c : main() sourceFile"
date:   2024-02-16 09:00:00 +0900
categories: [C]
---

solution 'CPrjs'   
project 'Sample_Conditional_Statement'   
   
<br />
### Control Structure   
1. Sequence Control Structure: Control Structure performed from top to bottom unless otherwise specified   
2. Selection or Decision Control Structure (Conditional Statement): Branch Control Structure to move performance to specific parts under given conditions   
 - `if`, `else`, `else if`   
3. Case Control Structure   
 - `switch ~ case` : Branch to one of several locations according to the given value   
4. Repetition Control Structure: Repeated Control Structure that repeats a specific part a certain number of times   
 - `for`   
 - `while`   
 - `do ~ while`   
5. Jump Statement   
 - `goto` : Unconditionally move to the specified Label   
 - `break` : Terminate Statement (for, while, do ~ while, switch ~ case)   
 - `continue` : Move back to Statement. Go to the beginning of the control statement and restart (for, while, do ~ while) (switch ~ case excluded)   
   
<br />
### sourceFile list - main() sourceFile - sample_conditional_statement.c   
   
`sample_conditional_statement.c` : C practice project main function   
   
```c
#include <stdio.h>
#include <math.h>
#pragma warning(disable:4996)

void main() {

	/* if 예제 */
	int a1 = 10, b1 = 20;
	if (a1 > b1) {
		a1 = a1 + 20;
		printf("a1=%d\n", a1);		// 조건에 맞지 않기 때문에 출력 안됨
	}
	b1 = b1 + 20;
	printf("b1=%d\n", b1);			// 출력결과 --> b1=40

	/* if ~ else 예제 */
	int a2, b2, max2;
	printf("Enter the number twice.\n");
	scanf("%d %d", &a2, &b2);
	if (a2 >= b2)
		max2 = a2;
	else
		max2 = b2;
	printf("max2=%d\n", max2);			// 출력결과 --> max2=입력된값 중 큰 값. 두 값이 같다면 먼저 입력된 값

	/* 다중 if ~ else 예제 */
	int a3;
	printf("Enter a number as negative or positive or zero.\n");
	scanf("%d", &a3);
	if (a3 >= 0)
		if(a3 == 0)
			printf("The value entered is 0\n");
		else
			printf("The value entered is positive\n");
	else
		printf("The value entered is negative\n");

	/* 다중 if ~ else if ~ else 예제 */
	int score = 0;
	printf("Enter score:");
	scanf("%d", &score);
	if (score >= 90)
		printf("Grade is A\n");
	else if (score >= 80)
		printf("Grade is B\n");
	else if (score >= 70)
		printf("Grade is C\n");
	else if (score >= 60)
		printf("Grade is D\n");
	else
		printf("Grade is F\n");

	/* switch ~ case 예제 */
	int n4;
	printf("n4=? Enter a number.\n");
	scanf("%d", &n4);
	printf("\n n4%%5=%d\n", n4 % 5);
	switch (n4 % 5) {
		case 0: printf("remainder is 0\n");
			break;
		case 1: printf("remainder is 1\n");
			break;
		case 2: printf("remainder is 2\n");
			break;
		default: printf("remainder is 3 or 4\n");
			break;
	}

	/* goto 예제 - 무조건 분기 */
	int i5, n5, c5 = 'A';
	while (1) {
		printf("\n How many times?\n");
		scanf("%d", &n5);
		for (i5 = 1; i5 <= n5; i5++) {
			printf("%c", c5);
			if (c5 == 'Q')
				goto end5;
			c5++;
		}
	}
	end5:		// goto가 이동해 올 레이블 Label
	printf("\n\n The End \n");

	/* for (초기식; 조건식; 증감식) 예제 */
	int i6, sum6 = 0;
	for (i6 = 0; i6 <= 10; ++i6)
		sum6 = sum6 + i6;
	printf("Sum from 1 to %d=%d\n", i6 - 1, sum6);		// 출력결과 --> Sum from 1 to 10=55

	/* 다중 for 예제 */
	int a7, b7;
	for (a7 = 1; a7 <= 3; ++a7) {
		printf("\na7=%d\n", a7);
		for (b7 = 0; b7 <= 4; b7++)
			printf("b7=%d ", b7);
		putchar('\n\n');
	}

	/* while (조건식) 예제 */
	int i8 = 0;
	int sum8 = 0;
	while (i8 <= 100) {
		sum8 = sum8 + i8;
		i8++;
	}
	printf("Sum from 1 to 100=%d\n", sum8);		// 출력결과 --> Sum from 1 to 100=5050

	/* 다중 while (조건식) 예제 - 구구단 */
	int i9 = 2, j9 = 0;
	while (i9 < 10) {
		j9 = 1;
		while (j9 < 10) {
			printf("%dx%d=%d\n", i9, j9, i9 * j9);		// 출력결과 --> 2x1=2 \n 2x2=4 \n ... 9x8=72 \n 9x9=81
			j9++;
		}
		printf("\n");
		i9++;
	}

	/* do ~ while (조건식) 예제 */
	int i10 = 0, n10;
	int sum10 = 0;
	printf("n10=? Enter a number.\n");
	scanf("%d", &n10);
	do {
		sum10 = sum10 + i10;
		i10++;
	} while (i10 <= n10);				// 맨 뒤에 세미콜론을 꼭 써야 함
	printf("i10=%d\n", i10);
	printf("Sum from Initial value of i10 to %d=%d\n", n10, sum10);

	/* break 예제 */
	int num11, sum11 = 0;
	while (1) {							// 1==참. 무한 while 루프
		printf("num11(End:0)...?");
		scanf("%d", &num11);
		if (num11 == 0)					// num11==0이면 while 루프 종료
			break;
		sum11 = sum11 + num11;
	}
	printf("\n sum11=%d\n", sum11);

	/* continue 예제 - 루프를 다시 시작할 때 사용 - 반복구조에만 사용. switch ~ case 에는 사용 불가 */
	int num12 = 1;
	while (num12 != 0) {
		printf("\n num12(End:0)...? If you enter a prime number, it's an infinite loop.");
		scanf("%d", &num12);
		if (num12 < 0) {
			printf("0 : Negative number !\n");
			continue;
		}
		printf("Square root of %d=%f\n", num12, sqrt(num12));
	}
	printf("\n\n The end \n");
}
```
