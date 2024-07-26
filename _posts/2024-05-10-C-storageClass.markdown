---
layout: post
title:  "C: Storage Class"
date:   2024-05-10 09:00:00 +0900
categories: [C]
---

### Storage Class   
// 기억클래스   
   
// 기억클래스   
// - 변수를 기억공간의 특정 영역에 할당하는 방법   
// - 각 변수의 유효범위와 존속기간을 설정   
- Storage class   
  - How to assign a variable to a specific area of storage space   
  - Set the effective range and duration of each variable   
   
<br />
### Depending on where the variable is used   
// 변수의 사용 위치에 따라   
   
// 지역변수   
// - 특정 범위 내에서만 통용되는 변수   
// - 선언된 블록이나 함수 내에서만 사용 가능   
// - 함수에서 사용되는 매개 변수도 해당   
- Local variable   
  - Variable used only within a specific scope   
  - Only available within a declared block or function   
  - Parameters used in the function are also local variable   
   
// 전역변수   
// - 함수 밖이나 외부파일에서 선언되어 프로그램 전체에 걸쳐 사용될 수 있는 변수   
- Global variable   
  - Variable that are declared outside the function or in external files and used throughout the program   
   
<br />
### Effective range of local and global variables   
// 지역변수와 전역변수의 유효범위   
   
```c
// 변수 x, y는 프로그램 전체에서 사용 가능한 전역변수 (함수 외부에서 선언됨)
// Variables x, y are the global variables available throughout the program (Declared outside the function)
int x, y;

// 변수 m, n은 fcn1() 함수 내에서만 사용 가능한 지역변수
// Variables m, n are local variables that are only available within the fcn1() function
long fcn1(int m, int n) {
    ...
    x++, y--;
    m++, n--;
    ...
}

void fcn2() {
    // 변수 m, n은 fcn2() 함수 내에서만 사용 가능한 지역변수
    // Variables m, n are local variables that are only available within the fcn2() function
    int m, n;
    ...
}

void main() {
    // 변수 m, n은 main() 함수 내에서만 사용 가능한 지역변수
    // Variables m, n are local variables that are only available within the main() function
    int m, n;
    long x;
    ...
    x = fcn1(10, 20);
    fcn2();
    ...
}
```
   
#### Example 1 use of local Variable   
// 지역변수의 사용 예시 1   
   
```c
#include <stdio.h>

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
void fcn8();

void main() {
    // 변수 i8는 main() 함수 내부에서 선언되어 main() 함수에서만 사용 가능한 지역변수
    // Variable i8 is a local variable that is declared inside the main() function and is available only in the main() function
    int i8 = 10;
    printf("\nmain i8=%d\n", i8);

    /* 2. 함수의 호출 */
    /* 2. Function call */
    fcn8();
    printf("\nmain i8=%d\n", i8);
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
void fcn8() {
    // 변수 i8는 fcn8() 함수 내부에서 선언된 지역변수로서 main() 함수의 변수 i8과는 별개로 사용됨
    // Variable i8 is a local variable declared inside the fcn8() function and is used separately from variable i8 of the main() function
    int i8;
    i8 = 20;
    printf("\nfcn8 i8=%d\n", i8);
}
```
   
- Result   
   
```
main i8=10
fcn8 i8=20
main i8=10
```
   
#### Example 2 use of local Variable   
// 지역변수의 사용 예시 2   
   
```c
#include <stdio.h>

void main() {
    // 블록 A : 블록 A의 x8, y8의 유효범위
    // Block A : x8, y8 valid range of block A
    int x8 = 2, y8 = 4;
    printf("A : x8=%d, y8=%d\n", x8, y8);
    {
        // 블록 B : 블록 B의 x8, y8의 유효범위
        // Block B : x8, y8 valid range of block B
        int x8;
        x8 = 5;
        y8++;
        printf("B : x8=%d, y8=%d\n", x8, y8);
    }
    printf("A : x8=%d, y8=%d", x8, y8);
}
```
   
- Result   
   
```
A : x8=2, y8=4
B : x8=5, y8=5
A : x8=2, y8=5
```
   
#### Example of use of global variable   
// 전역변수의 사용 예시   
   
```c
#include <stdio.h>

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
void fcn9();
// - 전역변수, 가급적 프로그램 선두에 위치하는 것이 좋음
// - 전역변수는 초기화 안하면 0으로 자동 초기화
// Global variable, preferably at the forefront of the program
// The global variable automatically initializes to zero if not initialized
int x9;

void main() {
    printf("1) x9=%d\n", x9);

    /* 2. 함수의 호출 */
    /* 2. Function call */
    fcn9();
    // - x9는 전역변수이므로 변화된 값으로 복귀
    // Since x9 is a global variable, it returns to the changed value
    printf("2) x9=%d", x9);
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
void fcn9() {
    // - 전역변수이므로 어디서나 사용 가능
    // It's a global variable, so it can be used anywhere
    x9++;
}
```
   
- Result   
   
```
1) x9=0
2) x9=1
```
   
#### Comparison of global and local variables   
// 전역변수와 지역변수의 비교   
   
// 동일 범위 내에서는 지역변수가 우선   
// 전역변수의 선언은 프로그램 선두에 위치   
// 가급적 지역변수를 사용하는 것이 효율적임   
// - 함수의 독립성 향상   
// - 디버깅 효율 향상   
// - 기억 공간 절약   
- Within the same range, local variable take precedence   
- The declaration of global variable is at the forefront of the program   
- It is efficient to use local variable as much as possible   
  - Improving the independence of functions   
  - Improved debugging efficiency   
  - Save memory   
   
<br />
### Storage class type of variable   
// 변수의 기억클래스 종류   
   
#### Declaring variable using storage Class   
// 기억클래스를 이용한 변수 선언   
   
// 형식   
- Formats   
   
```c
// 기억클래스 자료형 변수명;
storageClass dataType variableName;
```
   
// 기능   
// - 기존의 변수 선언문에 기억클래스만 기입   
// - 선언된 변수에 저장된 자료는 해당 기억영역에 놓이게 됨   
- Function   
  - Write only storage class in existing variable declarations   
  - The data stored in the declared variable is placed in the corresponding storage area   
   
// 사용 예시   
- Example of Use   
   
```c
auto int a;
static int b;
extern int c;
register int d;
```
   
#### Depending on the initialization, duration and scope of validity of the variable   
// 변수의 초기화, 지속기간 및 유효범위에 따라   
   
|Type of storage class for a variable|Example of use|Description|
|:---|:---|:---|
|// 자동변수<br />`auto` variable|auto int a;<br />int a;|Created at the run of the function, and removed storage space at the end of the run.<br />You can skip "auto".<br />It's a local variable.<br />Initialization required.|
|// 정적변수<br />`static` variable|static int a;|Storage space is maintained until the end of the program.<br />It's a global variable.<br />The value of the variable continues during program run.<br />Initialized to 0 if no initialization|
|// 외부변수<br />`extern` variable|extern int a;|Declared outside of the function.<br />It's a global variable.<br />Values of variables declared as external variables can be referenced in other files.<br />Initialized to 0 if no initialization.|
|// 레지스터변수<br />`register` variable|register int a;|Used to store data in registers within the CPU.<br />Property is the same as the auto variable.<br />Used to increase the run speed of a program.<br />Mainly used as counter variable in Loop statement.|
   
#### Example of using an automatic variable   
// 자동변수의 사용 예시   
   
```c
#include <stdio.h>

void main() {
    // - 함수 내 자동변수 선언
    // - main() 함수 내에서만 사용 가능
    // - auto 생략
    // Declare automatic variable in a function
    // Available within the main() function only
    // auto is omitted
    int i10 = 1;
    auto int j10 = 2;
    {
        /* 블록 1 */
        /* Block 1 */
        // - 자동변수로서 블록 1 에서만 사용 가능
        // As an automatic variable, only available in block 1
        int i10 = 3;
        /* 블록 2 */
        /* Block 2 */
        {
            // - 자동변수로서 블록 2 에서만 사용 가능
            // As an automatic variable, only available in block 2
            int i10 = 4;
            printf("i10 in block 2 is %d\n", i10);
            printf("j10 in block 2 is %d\n", j10);
        }
        printf("i10 in block 1 is %d\n", i10);
    }
    printf("i10 in void main() function is %d", i10);
}
```
   
- Result   
   
```
i10 in block 2 is 4
j10 in block 2 is 2
i10 in block 1 is 3
i10 in void main() function is 1
```
   
#### Example 1 using static variable   
// 정적변수의 사용 예시 1   
   
```c
#include <stdio.h>

void main() {
    // 자동변수 선언
    // Declare automatic variable
    int a11 = 10;
    // 정적변수 선언
    // Declar static variable
    static int b11 = 20;
    {
        // 자동변수로서 이 블록을 벗어나면 값이 소멸됨
        // As an automatic variable, the value is lost when it is out of this block
        int a11 = 5;
        printf("a11=%d b11=%d\n", a11, b11);
    }
    printf("a11=%d b11=%d", a11, b11);
}
```
   
- Result   
   
```
a11=5 b11=20
a11=10 b11=20
```
   
#### Example 2 using static variable   
// 정적변수의 사용 예시 2   
   
```c
#include <stdio.h>

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
test11();

void main() {
    int i11;
    i11 = 0;
    while (i11 < 3) {
        /* 2. 함수의 호출 */
        /* 2. Function call */
        test11();
        i11++;
    }
}

/* 3. 함수의 정의 */
/* 3. Definition of function */
test11() {
    // - a11은 지역변수이므로 함수 호출 시마다 0으로 초기화 됨
    // a11 is a local variable, so it is initialized to 0 with each function call
    auto int a11 = 0;
    // - s11은 전역변수이므로 함수 호출 시 이전 실행 결과값이 유지됨
    // s11 is a global variable, so the previous execution result value is retained when calling the function
    static int s11 = 0;
    printf("auto=%d, static=%d\n", a11, s11);
    ++a11;
    ++s11;
}
```
   
- Result   
   
```
auto=0, static=0
auto=0, static=1
auto=0, static=2

```
   
#### Example 1 use of external variable   
// 외부변수의 사용 예시 1   
   
```c
#include <stdio.h>

int i12 = 10;
int j12 = 20;

void main() {
    // - 외부변수 선언 extern 생략 가능
    // - 변수 i12가 선언되면 선언된 위치 이하부터 그 값이 유효하기 때문임
    // External variable declaration. extern can be omitted
    // If variable i12 is declared, the value is valid below the declared position
    extern int i12;
    // - 외부변수 선언 extern 생략 불가
    // - 변수 k12가 범위 바깥에 있기 때문임
    // External variable declaration. extern cannot be omitted
    // Because variable k12 is out of range
    extern int k12;
    // - 변수 j12 = 20, j12 = 100 이 동시에 있을 경우 자동변수 (지역변수) 가 우선임
    // Automatic variable (local variable) take precedence when variables j12 = 20, j12 = 100 are present at the same time
    int j12 = 100;
    printf("i12=%d j12=%d k12=%d\n", i12, j12, k12);
}

int k12 = 50;
```
   
- Result   
   
```
i12=10 j12=100 k12=50
```
   
#### Example 2 use of external variable   
// 외부변수의 사용 예시 2   
   
```c
#include <stdio.h>
#pragma warning(disable:4996)

/* 1. 함수의 원형 prototype 선언 */
/* 1. Declaration of prototype of function */
void extern_ex13();
// 전역변수 s13 선언
// Declare global variable s13
char s13[100];

void main() {
    printf("Enter a string.\n");
    scanf("%s", s13);
    printf("The input string is %s stored in the global variable s13\n", s13);

    /* 2. 함수의 호출 */
    /* 2. Function call */
    // 외부함수 호출
    // Calling an external function
    extern_ex13();
}
```
   
// 외부변수가 선언된 파일   
- Files with external variables declared   
   
```c
#include <stdio.h>

/* 다른 파일에서 선언된 전역변수 s13을 이 파일에서 사용 */
/* Use global variable s13 declared in another file, in this file */
extern char s13[];

/* 3. 함수의 정의 */
/* 3. Definition of function */
void extern_ex13() {
    // 외부변수 s13 값을 출력
    // Output external variable s13 value
    printf("The value of the extern variable s13 is %s.", s13);
}
```
   
- Result   
   
```
Enter a string. KNOU [Enter]
The input string is KNOU stored in the global variable s13
The value of the extern variable s13 is KNOU.
```
   
#### Example of using a register variable   
// 레지스터변수의 사용 예시   
   
```c
#include <stdio.h>

void main() {
    register int i14;
    int sum14 = 0;
    // register 변수를 반복문의 카운터 변수로 사용
    // Using register variable as counter variable of repeat statement
    for (i14 = 0; i14 <= 10; ++i14)
        sum14 += i14;
    i14 -= 1;
    printf("i14=%d sum14=%d", i14, sum14);
}
```
   
- Result   
   
```
i14=10 sum14=55
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
