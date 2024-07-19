---
layout: post
title:  "C: Control Structure - if / switch...case / for / while / do...while / goto / break / continue"
date:   2024-05-08 09:00:00 +0900
categories: [C]
---

### Control Structure of programming language   
// 프로그램 언어의 제어 구조   
   
1. Sequence Control Structure : Control Structure performed from top to bottom unless otherwise specified   
2. Selection or Decision Control Structure (Conditional Statement) : Branch Control Structure to move performance to specific parts under given conditions   
 - `if`, `else`, `else if`   
3. Case Control Structure   
 - `switch ~ case` : Branch to one of several locations according to the given value   
4. Repetition Control Structure : Repeated Control Structure that repeats a specific part a certain number of times   
 - `for`   
 - `while`   
 - `do ~ while`   
5. Jump Statement   
 - `goto` : Unconditionally move to the specified Label   
 - `break` : Terminate Statement (for, while, do ~ while, switch ~ case)   
 - `continue` : Move back to Statement. Go to the beginning of the control statement and restart (for, while, do ~ while) (switch ~ case excluded)   
   
<br />
### Selection Control Statement   
// 선택 제어문   
   
// 선택 제어문의 종류   
- Type of Selection Control Statement   
  - if   
  - switch ~ case   
  - goto   
   
<br />
### if   
   
#### Simple if statement (Simple control)   
// 단순 if문 (단순제어)   
   
// 형식   
- Formats   
   
```c
if (Condition)
    Command Statement 1;
    Command Statement 2;
```
   
```c
if (Condition) {
    Command Statement 1;
	...
    Command Statement n;
}
...
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int a1 = 10, b1 = 20;
    // 조건을 만족하지 않으므로 중괄호 밖의 명령문을 수행함
    // Performs an out-of-brace command statement because the condition is not met
    if (a1 > b1) {
        a1 = a1 + 20;
        // 조건에 맞지 않기 때문에 출력 안됨
        // Not output because it does not meet the conditions
        printf("a1=%d", a1);
    }
    b1 = b1 + 20;
    printf("b1=%d", b1);
}
```
   
- Result   
   
```
b1=40
```
   
#### if ~ else   
   
// 형식   
- Formats   
   
```c
if (Condition)
    Command Statement 1;
else
    Command Statement 2;
```
   
// 기능   
// - 주어진 조건이 참일 때는 명령문 1을, 거짓일 때는 명령문 2를 수행함   
- Function   
  - If the given condition is true, do command statement 1 and if false, do command statement 2   
   
- Example   
   
```c
#include <stdio.h>
#pragma warning(disable:4996)

void main() {
    int a2, b2, max2;
    printf("Enter the number twice.\n");
    scanf("%d %d", &a2, &b2);
    // 입력된 a, b를 비교하여 분기
    // branch by comparing input a and b
    if (a2 >= b2)
        max2 = a2;
    else
        max2 = b2;
    // 입력된 값 중 큰 값이 출력됨. 두 값이 같다면 먼저 입력된 값이 출력됨
    // Larger of the entered values is output. If the two values are the same, the entered value is output first
    printf("max2=%d", max2);
}
```
   
- Result   
   
```
Enter the number twice. 2 3 [Enter]
max2=3
```
   
#### Multiple if-else statement   
// 다중 if ~ else 문   
   
// 형식   
- Formats   
   
```c
if (Condition 1)
    if (Condition 2)
        Command Statement 1;
    else
        Command Statement 2;
else
    Command Statement 3;
```
   
// 기능   
// - 조건 1과 조건 2가 참일 때 명령문 1 수행   
// - 조건 1이 참이고 조건 2가 거짓일 때 명령문 2 수행   
// - 조건 1이 거짓일 때 명령문 3 수행   
- Function   
  - Perform command statement 1 when condition 1 and condition 2 are true   
  - Perform command statement 2 when condition 1 is true and condition 2 is false   
  - Perform command statement 3 when condition 1 is false   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int a3;
    printf("Enter a number as negative or positive or zero.\n");
    scanf("%d", &a3);
    if (a3 >= 0)
        if (a3 == 0)
            // 조건 1과 조건 2를 모두 만족할 경우 출력
            // Output if both condition 1 and condition 2 are satisfied
            printf("The value entered is 0");
        else
            // 조건 1을 만족하고, 조건 2를 만족하지 않을 경우 출력
            // Output if condition 1 is met and condition 2 is not met
            printf("The value entered is positive");
    else
        // 조건 1을 만족하지 않을 경우 출력
        // Output if condition 1 is not met
        printf("The value entered is negative");
}
```
   
- Result   
   
```
10 [Enter]
The value entered is positive
```
   
#### Multiple if ~ else if ~ else statement   
// 다중 if ~ else if ~ else 문   
   
// 형식   
- Formats   
   
```c
if (Condition 1)
    Command Statement 1;
else if (Condition 2)
    Command Statement 2;
else if (Condition 3)
    Command Statement 3;
else
    Command Statement 4;
```
   
// 기능   
// - 조건 1이 참이면 명령문 1 수행   
// - (조건 1이) 거짓이면 조건 2를 검사하여 참이면 명령문 2 수행   
// - (조건 1이 거짓이면 조건 2를 검사하여) 거짓이면 조건 3을 검사하여 참이면 명령문 3 수행   
// - (조건 1이 거짓이면 조건 2를 검사하여 거짓이면 조건 3을 검사하여) 거짓이면 명령문 4 수행   
- Function   
  - If condition 1 is true, perform command statement 1   
  - If condition 1 is false, inspect condition 2 and if true, perform command statement 2   
  - If condition 1 is false, inspect condition 2 and if it is false, inspect condition 3 and if it is true, perform command statement 3   
  - (If condition 1 is false, check condition 2 and if it is false, check condition 3) If it is false, perform command statement 4   
   
- Example   
   
```c
#include <stdio.h>
#pragma warning(disable:4996)

void main() {
    int score = 0;
    printf("Enter score:");
    scanf("%d", &score);
    if (score >= 90)
        printf("Grade is A");
    else if (score >= 80)
        printf("Grade is B");
    else if (score >= 70)
        printf("Grade is C");
    else if (score >= 60)
        printf("Grade is D");
    else
        printf("Grade is F");
}
```
   
- Result   
   
```
Enter score: 70 [Enter]
Grade is C
```
   
<br />
### switch ~ case   
   
// 형식   
- Formats   
   
```c
// switch (수식) {
// 	case 값1 : 명령문 1;
// 	case 값2 : 명령문 2;
// 	...
// 	default : 명령문 n;
// }
switch (numeric expression statement) {
	case Value 1 : Command Statement 1;
	case Value 2 : Command Statement 2;
	...
	default : Command Statement n;
}
```
   
// 기능   
// - 주어진 값에 따라 여러 곳 중 한 곳으로 분기하여 실행   
- Function   
  - Run branching to one of several locations according to the given value   
   
- Example   
   
```c
#include <stdio.h>
#pragma warning(disable:4996)

void main() {
    int n4;
    printf("n4=? Enter a number.\n");
    scanf("%d", &n4);
    printf("\n n4%%5=%d\n", n4 % 5);
    // 입력된 수를 5로 나누어 그 나머지에 해당되는 경우로 분기
    // Divide the number entered by 5 and branch to the remaining cases
    switch (n4 % 5) {
        case 0: printf("remainder is 0");
            break;
        case 1: printf("remainder is 1");
            break;
        case 2: printf("remainder is 2");
            break;
        default: printf("remainder is 3 or 4");
            break;
	}
}
```
   
- Result   
   
```
n4=? Enter a number. 10 [Enter]
n4%5=0
remainder is 0
```
   
<br />
### goto statement (Unconditional branching)   
// goto 문 (무조건 분기)   
   
// 형식   
- Formats   
   
```c
Label :

goto Label;
...
```
   
// 기능   
// - 프로그램 수행 도중에 원하는 곳으로 제어를 무조건적으로 옮김   
- Function   
  - goto unconditionally moves control to desired location during program run   
   
- Example   
   
```c
#include <stdio.h>
#pragma warning(disable:4996)

void main() {
    int i5, n5, c5 = 'A';
    while (1) {
        printf("\n How many times?\n");
        scanf("%d", &n5);
        // n5회 반복하는 for 반복문
        // Repeating for repeate statement n5 times
        for (i5 = 1; i5 <= n5; i5++) {
            printf("%c ", c5);
            if (c5 == 'Q')
                // 레이블명 end5로 무조건 실행을 옮김
                // Unconditionally moved run to label name 'end5'
                goto end5;
            c5++;
        }
    }
    // goto가 이동해 올 레이블 Label. 레이블명 뒤에는 콜론 ( : ) 을 붙임
    // Label to be moved by goto. Label name followed by colon ( : )
    end5:
    printf("\n\n The End");
}
```
   
- Result   
   
```
How many times? 6 [Enter]
A B C D E F

How many times? 7 [Enter]
G H I J K L M

How many times? 8 [Enter]
N O P Q

The End
```
   
#### Case where 'goto' statement cannot be used   
// goto 문의 사용될 수 없는 경우   
   
// Label이 특정 루프 안에 있을 경우 루프 바깥쪽에 있는 goto는 루프 안쪽으로 들어갈 수 없음   
// 특정 루프 안에 있는 goto는 다른 루프 안에 있는 Label로 갈 수 없음   
- goto outside the loop cannot enter the loop if the label is in a particular loop   
- goto in a particular loop cannot go to a label in another loop   
   
<br />
### Iteration Control Statement   
// 반복 제어문   
   
// 반복 제어문의 종류   
- Types of iterative control statements   
  - for   
  - while   
  - do ~ while   
   
<br />
### for   
   
// 형식   
- Formats   
   
```c
// for (초기식; 조건식; 증감식) {
//     반복 실행될 문장
// }
for (Initial Expression; Conditional Expression; Increase/Decrease Expression) {
    Statements to be repeated
}
```
   
// 기능   
// - 주어진 조건이 만족되는 동안 루프문을 반복 수행함   
- Function   
  - Repeat loop statements while the given conditions are satisfied   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    // 루프변수 i6은 정수형이어야 함
    // Loop variable i6 must be integer type
    int i6, sum6 = 0;
    for (i6 = 0; i6 <= 10; ++i6)
        // i6값이 11이 되면 조건식이 거짓이 되어 루프를 빠져 나옴
        // If the i6 value becomes 11, the conditional expression becomes false and leaves the loop
        sum6 = sum6 + i6;
    printf("Sum from 1 to %d=%d", i6 - 1, sum6);
}
```
   
- Result   
   
```
Sum from 1 to 10=55
```
   
#### Multiple for statement   
// 다중 for 문   
   
// 형식   
- Formats   
   
```c
// for (초기식; 조건식; 증감식) {
//     for (초기식; 조건식; 증감식) {
//         for (초기식; 조건식; 증감식) {
//             반복 실행될 문자
//         }
//     }
// }
for (Initial Expression; Conditional Expression; Increase/Decrease Expression) {
    for (Initial Expression; Conditional Expression; Increase/Decrease Expression) {
        for (Initial Expression; Conditional Expression; Increase/Decrease Expression) {
            Characters to be repeated
        }
    }
}
```
   
// 기능   
// - 주어진 조건이 만족되는 동안 루프문을 반복 수행함   
- Function   
  - Repeat loop statements while the given conditions are satisfied   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int a7, b7;
    // 외부 for 문의 범위
    // Range of external 'for' statement
    for (a7 = 1; a7 <= 3; ++a7) {
        printf("\na7=%d\n", a7);
        // 내부 for 문의 범위
        // Range of internal 'for' statement
        for (b7 = 0; b7 <= 4; b7++)
            printf("b7=%d ", b7);
        putchar('\n\n');
    }
}
```
   
- Result   
   
```
a7=1
b7=0 b7=1 b7=2 b7=3 b7=4 
a7=2
b7=0 b7=1 b7=2 b7=3 b7=4 
a7=3
b7=0 b7=1 b7=2 b7=3 b7=4 
```
   
<br />
### while   
   
// 형식   
- Formats   
   
```c
// while (조건식) {
//     반복 실행할 문장;
// }
while (Conditional Expression) {
    Sentence to run repeatedly;
}
```
   
// 기능   
// - 주어진 조건이 만족되는 동안 루프문을 반복 수행함   
- Function   
  - Repeat loop statements while the given conditions are satisfied   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int i8 = 0;
    int sum8 = 0;
    // i8 <= 100 을 만족하는 동안 반복 수행
    // Repeat while i8 <= 100 is satisfied
    while (i8 <= 100) {
        sum8 = sum8 + i8;
        i8++;
    }
    printf("Sum from 1 to 100=%d\n", sum8);
}
```
   
- Result   
   
```
Sum from 1 to 100=5050
```
   
#### Multiple while statement   
// 다중 while 문   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int i9 = 2, j9 = 0;
    while (i9 < 10) {
        j9 = 1;
        while (j9 < 10) {
            printf("%dx%d=%d\n", i9, j9, i9 * j9);
            j9++;
        }
        printf("\n");
        i9++;
    }
}
```
   
- Result   
   
```
2x1=2
2x2=4
...
2x9=18
3x1=3
...
3x9=27
...
9x1=9
...
9x8=72
9x9=81
```
   
<br />
### do ~ while   
   
// 형식   
// - while (조건식); 맨 뒤에 세미콜론을 꼭 써야 함   
- Formats   
  -  while (Conditional Expression); Make sure to use a semi-colon at the end when using it   
   
```c
// do {
//     반복 실행될 문장;
// } while (조건식);
do {
    Statements to be repeated;
} while (Conditional Expression);
```
   
// 기능   
// - 반복문 내의 명령문을 실행한 후, 주어진 조건을 검사하여 반복 수행 여부를 결정함   
- Function   
  - After executing the command statement in the iteration statement, examine given conditions to determine whether to repeat   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int i10 = 0, n10;
    int sum10 = 0;
    printf("n10=? Enter a number.\n");
    scanf("%d", &n10);
    do {
        sum10 = sum10 + i10;
        i10++;
    } while (i10 <= n10);
    printf("i10=%d\n", i10);
    printf("Sum from Initial value of i10 to %d=%d", n10, sum10);
}
```
   
- Result   
   
```
n10=? Enter a number. 10 [Enter]
i10=11
Sum from Initial value of i10 to 10=55
```
   
<br />
### Other control statements   
// 기타 제어문   
   
// 기타 제어문의 종류   
- Types of other control statements   
  - break   
  - continue   
   
<br />
### break   
   
// break 문은 반복 명령의 실행 도중에 강제적으로 반복문을 빠져 나오는데 사용   
// - for 루프, while 루프, do ~ while 루프, switch 블록 등을 강제로 종료시키고자 할 때 사용   
- break statements are used to force a repeat statement to exit during the run of a repeat command   
  - break can be used to force for loop, while loop, do ~ while loop, switch block and etc.   
   
// break 문은 자신이 포함된 반복문만 빠져 나옴   
- The break statement only comes out of the repetition sentence that contains itself   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int num11, sum11 = 0;
    // 1==참. 무한 while 루프
    // 1 == True. Infinite while loop
    while (1) {
        printf("num11(End:0)...?");
        scanf("%d", &num11);
        // num11==0이면 while 루프 종료
        // When 'num11==0', end the while loop
        if (num11 == 0)
            // 루프 바깥으로 빠져 나감
            // Out of the loop
            break;
        sum11 = sum11 + num11;
    }
    printf("\n sum11=%d", sum11);
}
```
   
- Result   
   
```
num11(End:0)...? 10 [Enter]
num11(End:0)...? 20 [Enter]
num11(End:0)...? 30 [Enter]
num11(End:0)...? 0 [Enter]
sum11=60
```
   
<br />
### continue   
   
// continue 문은 루프 실행 중에 루프를 다시 실행하고자 할 때 사용   
// - switch ~ case 문에서는 사용하지 않고, 반복문에만 국한되어 사용   
- Use the continue statement when you want to run the loop again during loop run   
  - Use only for repeat statements, not for switch ~ case statements   
   
// continue 문은 그 루프의 선두로 제어를 옮겨 다음 반복을 실행   
- The continue statement moves control to the head of the loop and executes the next iteration   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int num12 = 1;
    // num이 0이 아닌 한 계속 반복하는 while 루프
    // While loop that repeats again and again as long as num is not 0
    while (num12 != 0) {
        printf("\n num12(End:0)...? If you enter a prime number, it's an infinite loop.");
        scanf("%d", &num12);
        if (num12 < 0) {
            printf("0 : Negative number !\n");
            // 음수이면 continue 수행, 루프의 선두로 복귀
            // If negative, perform 'continue' and return to the head of the loop
            continue;
        }
        printf("Square root of %d=%f\n", num12, sqrt(num12));
    }
    printf("\n\n The end");
}
```
   
- Result   
   
```
num12(End:0)...? If you enter a prime number, it's an infinite loop. 2 [Enter]
Square root of 2=1.414214

num12(End:0)...? If you enter a prime number, it's an infinite loop. -3 [Enter]
0 : Negative number !

num12(End:0)...? If you enter a prime number, it's an infinite loop. 0 [Enter]
Square root of 0=0.000000

The end
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
