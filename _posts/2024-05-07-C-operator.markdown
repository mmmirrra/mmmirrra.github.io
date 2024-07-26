---
layout: post
title:  "C: Operator and Precedence"
date:   2024-05-07 09:00:00 +0900
categories: [C]
---

### What is a Operator?   
// 연산자란?   
   
// 임의의 자료에 대해 각종 연산을 수행하도록 하는 기호   
- A symbol for performing various operations on arbitrary data   
   
<br/>
### Type of Operator   
// 연산자의 종류   
   
|Type|Operator|
|:---|:---|
|// 산술 연산자<br />- Arithmetic Operator|+ - * / % ++ --|
|// 관계 연산자<br />- Relational Operator|＞ ＜ ＞= ＜= == !=|
|// 논리 연산자<br />- Logical Operator|& \|\| !|
|// 대입 연산자<br />- Substitution Operator|+= -= *= /= %= ＜＜= ＞＞= != &=|
|// 조건 연산자<br />- Conditional Operator|?:|
|// 비트 연산자<br />- Bit Operator|& \| ∧ ~ ＜＜ ＞＞|
|// 기타 연산자<br />- Other Operators|sizeof() cast & *|
   
<br/>
### Arithmetic Operator   
// 산술 연산자   
   
// 피연산자에 대해 사칙연산을 포함한 각종 산술연산을 수행하는 연산자   
- Operators performing various arithmetic operations, including four arithmetic operations, on operands   
   
|Type|Operator|Function|Example of use|
|:---|:---:|:---|:---:|
|이항 연산자<br />Binary Operator|+ - * /|// 가/감/승/제를 계산<br />- Calculate the elementary arithmetic|i + 5|
||%|// 나눗셈의 나머지 계산<br />- Calculate of the remainder of the division|i % 5|
|단항 연산자<br />Unary Operator|-|// 부호의 반전<br />- Code reversal|-5|
||++|// 1 증가<br />- 1 increase|i++, ++i|
||--|// 1 감소<br />- 1 decrease|i--, --i|
   
// 이항연산자 사용 예시   
- Example of using binary operator   
   
```c
#include <stdio.h>

void main() {
    int x, y;
    x = 10;
    y = 3;
    printf("x=%d, y=%d\n", x, y);
    printf("x+y=%d\n", x + y);
    printf("x/y=%d\n", x / y);
    // '%'문자를 출력하기 위해 %문자를 2개 연속 사용
    // Use two % characters in a row to output '%' characters
    printf("x%%y=%d\n", x % y);
    printf("y%%x=%d", y % x);
}
```
   
- Result   
   
```
x=10, y=3
x+y=13
x/y=3
x%y=1
y%x=3
```
   
// 단항연산자 사용 예시   
- Example of using unary operator   
   
```c
#include <stdio.h>

void main() {
    int x1 = 5, a1, b1;
    /* 수행순서
        1. ++x1 수행 : x1=x1+1 이므로 x1값이 5에서 6이 됨
        2. ++x1*x1 수행 : a1은 36이 됨
        3. x1-- 수행 : x1값이 6에서 다시 5로 됨
        → 최종 x1의 값이 5이므로 b1=50이 됨
    */
    /* Order of perform
        1. Perform ++x1 : x1 value changed from 5 to 6 because x1=x1+1
        2. Perform ++x1*x1 : a1 becomes 36
        3. Perform x1-- : x1 value changed from 6 to 5 again
        → Last x1 has a value of 5, so b1=50
    */
    a1 = ++x1 * x1--;
    b1 = x1 * 10;
    printf("a1=%d b1=%d x1=%d", a1, b1, x1);
}
```
   
- Result   
   
```
a1=36 b1=50 x1=5
```
   
<br/>
### Relational Operator   
// 관계 연산자   
   
// 피연산자에 대해 대, 소 관계를 비교하는 연산자   
- Operators comparing the large/small relations of operands   
   
|Operator|Function|Example of use|
|:---:|:---|:---|
|==|// 같은가의 여부를 비교<br />- Compare whether it is the same or not|// a==b : a와 b는 같다<br />a==b : a and b are the same|
|!=|// 다른가의 여부를 비교<br />- Compare of differences|// a!=b : a와 b는 같지 않다<br />a!=b : a and b are not the same|
|＞＞=<br />＜＜=|// 대, 소 관계를 비교<br />- Compare relation large/ small|// a＞=b : a는 b보다 크거나 같다<br />a＞=b : a is greater than or equal to b|
   
// 사용 예시   
- Examples of Use   
   
```c
#include <stdio.h>

void main() {
    int a2 = 4, b2, c2, d2;
    // a2가 2보다 큰가를 비교 → 참
    // Compare whether a2 is greater than 2 → True
    b2 = a2 > 2;
    // 비교 결과가 참이므로 1 출력
    // 1 output because the comparison result is true
    printf("b2=%d\n", b2);
    // a2가 2보다 작은가를 비교 → 거짓
    // Compare whether a2 is less than 2 → False
    c2 = a2 < 2;
    // 비교 결과가 거짓이므로 0 출력
    // 0 output because the comparison result is false
    printf("c2=%d\n", c2);
    // a2가 4인가 비교 → 참
    // Comparison of a2 being equal to 4 → True
    d2 = a2 == 4;
    // 비교 결과가 참이므로 1 출력
    // 1 output because the comparison result is true
    printf("d2=%d", d2);
}
```
   
- Result   
   
```
b2=1
c2=0
d2=1
```
   
<br/>
### Logical Operator   
// 논리 연산자   
   
// 피연산자에 대해 논리 연산을 수행하는 연산자   
- Operator to perform logical operations on operands   
   
|Operator|Function|Example of use|
|:---:|:---|:---:|
|&&|// 논리곱 (AND) : 양쪽 모두 참일 때만 참<br />- Conjunction (AND) : Only when both sides are true|a&&b|
|\|\||// 논리합 (OR) : 양쪽 중 하나라도 참이면 참<br />- Disjunction (OR) : If either of them is true|a\|\|b|
|!|// 논리부정 (NOT) : 오른쪽이 참이면 거짓, 거짓이면 참<br />- Negation (NOT) : If the right side is true, it's false. If the right side is false, it's true.|!a|
   
// 사용 예시   
- Examples of Use   
   
```c
#include <stdio.h>

void main() {
    int a3 = 4, b3 = 7, c3, d3, e3;
    // - 양쪽 모두 참이므로 결과는 참 (논리곱)
    // - 논리곱 && : 참 && 참 == 참
    // Both are true, so the result is true (Conjunction)
    // Conjunction && : true && true == true
    c3 = a3 > 2 && b3 <= 7;
    printf("c3=%d\n", c3);
    // - 한 쪽이 참이므로 결과는 참 (논리합)
    // - 논리합 || : 거짓 || 참 == 참
    // One side is true, so the result is true (Disjucntion)
    // Disjucntion || : false || true == true
    d3 = a3 < 2 || b3 <= 7;
    printf("d3=%d\n", d3);
    // - a3이 참이므로 결과는 거짓 (논리부정)
    // - 논리부정 ! : !참 == 거짓
    // Result is false because a3 is true (Negation)
    // Negation ! : !true == false
    e3 = !a3;
    printf("e3=%d", e3);
}
```
   
- Result   
   
```
c3=1
d3=1
e3=0
```
   
<br/>
### Substitution Operator   
// 대입 연산자   
   
// 연산자의 오른쪽을 왼쪽에 대입하는데 사용   
- Used to substitute the right to the left of the operator   
   
|Operator|Example of use|Function|
|:---:|:---:|:---|
|=|a=5|// a에 5를 대입<br />- Substitute 5 into a|
|+=|a+=5|// a=a+5 : a에 5를 더한 후 결과를 a에 대입<br />- a=a+5 : After adding 5 to a, substitute the result into a|
|-=|a-=5|// a=a-5 : a에 5를 뺀 후 결과를 a에 대입<br />- a=a-5 : Subtract 5 from a and substitute the result into a|
|*=|a*=5|// a=aㄷ* 5 : a에 5를 곱한 후 결과를 a에 대입<br />- a=a*5 : After multiplying a by 5, substitute the result into a|
|/=|a/=5|// a=a/5 : a에 5를 나누 후 결과를 a에 대입<br />- a=a/5 : Divide 5 into a and substitute the result into a|
|%=|a%=5|// a=a%5 : a에 5를 나눈 후 그 나머지를 a에 대입<br />- a=a%5 : After dividing a by 5, substitute the rest into a|
|&=|a&=5|// a=a&5 : a와 5에 대해 bit 단위의 AND 연산을 한 후 결과를 a에 대입<br />- a=a&5 : After performing AND operation of a and 5 in bit units, substitute the result into a|
|\|=|a\|=5|// a=a\|5 : a와 5에 대해 bit 단위의 OR 연산을 한 후 결과를 a에 대입<br />- a=a\|5 : After performing OR operations of a and 5 in bit units, substitute the result into a|
|∧=|a∧=5|// a=a∧5 : a와 5에 대해 bit 단위의 XOR 연산을 한 후 결과를 a에 대입<br />- a=a∧5 : After performing the bit-wise XOR operation on a and 5, substitute the result into a|
|＜＜=|a＜＜=5|// a=a＜＜5 : a의 값을 5 bit 좌로 이동 후 결과를 a에 대입<br />- a=a＜＜5 : Move the value of a to the left of 5 bits and substitute the result into a|
|＞＞=|a＞＞=5|// a=a＞＞5 : a의 값을 5 bit 우로 이동 후 결과를 a에 대입<br />- a=a＞＞5 : Move the value of a to the right of 5 bits and substitute the result into a|
   
// 사용 예시   
- Examples of Use   
   
```c
#include <stdio.h>

void main() {
    int a4;
    // a4에 5를 대입
    // Substitute 5 into a4
    a4 = 5;
    printf("a4 = 5 --> %d\n", a4);
    // a4 = a4 + 5 : a4에 5를 더한 후 결과를 a4에 대입
    // a4 = a4 + 5 : After adding 5 to a4, substitute the result into a4
    a4 += 5;
    printf("a4 += 5 --> %d\n", a4);
    // a4 = a4 - 5 : a4에 5를 뺀 후 결과를 a4에 대입
    // a4 = a4 - 5 : Subtract 5 from a4 and substitute the result into a4
    a4 -= 5;
    printf("a4 -= 5 --> %d\n", a4);
    // a4 = a4 * 5 : a4에 5를 곱한 후 결과를 a4에 대입
    // a4 = a4 * 5 : After multiplying a4 by 5, substitute the result into a4
    a4 *= 5;
    printf("a4 *= 5 --> %d\n", a4);
    // a4 = a4 / 5 : a4에 5를 나눈 후 결과를 a4에 대입
    // a4 = a4 / 5 : After dividing a4 by 5, substitute the result into a4
    a4 /= 5;
    printf("a4 /= 5 --> %d\n", a4);
    // a4 = a4 % 3 : a4에 3를 나눈 후 그 나머지를 a4에 대입
    // a4 = a4 % 3 : After dividing a4 by 3, substitute the rest into a4
    a4 %= 3;
    printf("a4 %%= 3 --> %d\n", a4);
    // a4 = a4 & 55 : a4와 55에 대한 bit단위의 AND연산을 한 후 결과를 a4에 대입
    // a4 = a4 & 55 : After performing AND operations of a4 and 55 in bit units, substitute the result into a4
    a4 &= 55;
    printf("a4 &= 55 --> %d\n", a4);
    // a4 = a4 | 5 : a4와 5에 대해 bit단위의 OR연산을 한 후 결과를 a4에 대입
    // a4 = a4 | 5 : After performing OR operations of a4 and 5 in bit units, substitute the result into a4
    a4 |= 5;
    printf("a4 |= 5 --> %d\n", a4);
    // a4 = a4 ^ 5 : a4와 5에 대해 bit단위의 XOR연산을 한 후 결과를 a4에 대입
    // a4 = a4 ^ 5 : After performing the bit-wise XOR operation on a4 and 5, substitute the result into a4
    a4 ^= 5;
    printf("a4 ^= 5 --> %d\n", a4);
    // a4 = a4 << 5 : a4의 값을 5bit 좌로 이동 후 결과를 a4에 대입
    // a4 = a4 << 5 : Move the value of a4 to the left of 5 bits and substitute the result into a4
    a4 <<= 5;
    printf("a4 <<= 5 --> %d\n", a4);
    // a4 = a4 >> 5 : a4의 값을 5bit 우로 이동 후 결과를 a4에 대입
    // a4 = a4 >> 5 : Move the value of a4 to the right of 5 bits and substitute the result into a4
    a4 >>= 5;
    printf("a4 >>= 5 --> %d", a4);
}
```
   
- Result   
   
```
a4 = 5 --> 5
a4 += 5 --> 10
a4 -= 5 --> 5
a4 *= 5 --> 25
a4 /= 5 --> 5
a4 %= 3 --> 2
a4 &= 55 --> 2
a4 |= 5 --> 7
a4 ^= 5 --> 2
a4 <<= 5 --> 64
a4 >>= 5 --> 2
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int a5 = 10, b5 = 3, c5 = 11;
    // a5 = a5 * (b5 - 1)
    a5 *= (b5 - 1);
    // b5 = b5 / (1 + 1)
    b5 /= 1 + 1;
    // c5 = c5 + 2
    c5 += 2;
    printf("a5=%d b5=%d c5=%d\n", a5, b5, c5);
}
```
   
- Result   
   
```
a5=20 b5=1 c5=13
```
   
<br/>
### Conditional Operator   
// 조건 연산자   
   
// 주어진 조건의 만족 여부에 따라 지정된 수식을 수행하는 연산자   
- An operator that performs a specified formula based on whether a given condition is satisfied   
   
// 형식   
- Formats   
   
```c
// (조건)? 수식1 : 수식2;
(Condition)? Expression statement 1 : Expression statement 2;
```
   
// 기능   
// - 조건이 성립하면 (참이면) 수식1을 수행하고, 조건이 성립되지 않으면 (거짓이면) 수식2를 수행함   
- Function   
  - If the condition is met (true), perform Expression statement 1, if the condition is not met (false), perform Expression statement 2   
   
// 사용 예시   
- Examples of Use   
   
```c
x=(5>2)? 1 : 0;
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int a6 = 10, b6;
    // 조건을 만족하지 않으므로 (a6 - 1) 을 수행
    // Perform (a6 - 1) because it does not satisfy the conditions
    b6 = (a6 > 15) ? (a6 + 1) : (a6 - 1);
    printf("b6=%d", b6);
}
```
   
- Result   
   
```
b6=9
```
   
<br/>
### Bit Operator   
// 비트 연산자   
   
// 수치에 대해 bit 단위의 연산을 수행하는 연산자   
- An operator that performs bit-wise operations on a numerical value   
   
|Operator|Example of use|Function|
|:---:|:---:|:---|
|&<br />(bit AND)|a&b|// 대응되는 두 bit가 모두 1일 때만 결과는 1<br />- The result is 1 only when both corresponding bits are 1|
|\|<br />(bit OR)|a\|b|// 대응되는 두 bit 중 하나라도 1이면 결과는 1<br />- If either of the two corresponding bits is 1, the result is 1|
|∧<br />(bit XOR)|a∧b|// 대응되는 두 bit가 서로 다를 때만 결과는 1<br />- The result is 1 only when two corresponding bits are different from each other|
|~<br />(bit NOT)|~a|// 1은 0으로, 0은 1로 함<br />- Change 1 to 0 and 0 to 1|
|＜＜<br />(Move the bit to the left)|a＜＜b|// a의 값에 대해 2비트 왼쪽으로 이동<br />- Move 2 bits to the left for the value of a|
|＞＞<br />(Move the bit to the right)|a＞＞b|// a의 값에 대해 2비트 오른쪽으로 이동<br />- Move 2 bits to the right for the value of a|
   
// 사용 예시   
- Examples of Use   
   
```c
#include <stdio.h>

void main() {
    // 연산을 설명으로 표현
    // Express the operation as a description
    // printf("x의 비트 == 10110011\n");
    // printf("y의 비트 == 01001001 인 경우\n");
    // printf("x&y 결과 == 00000001 (두 비트가 모두 1(참)인 경우만 1(참). 나머지는 0(거짓))\n");
    // printf("x|y 결과 == 11111011 (두 비트 중 하나라도 1(참)인 경우만 1(참). 나머지는 0(거짓))\n");
    // printf("x^y 결과 == 11111010 (두 비트가 서로 다른 경우 경우만 1(참). 나머지는 0(거짓))\n");
    // printf("~x 결과 == 01001100 (1(참)과 0(거짓)을 반대로 변경)\n");
    // printf("x<<2 결과 == 11001100 (비트를 왼쪽으로 2비트 이동. 빈공간에는 00을 채움)\n");
    // printf("x>>2 결과 == 00101100 (비트를 오른쪽으로 2비트 이동. 빈공간에는 00을 채움)");
    printf("bit of x == 10110011\n");
    printf("bit of y == 01001001\n");
    printf("The result of x&y == 00000001 (1 (true) only if both bits are 1 (true). The rest is 0 (false))\n");
    printf("The result of x|y == 11111011 (Only 1 (true) if either bit is 1 (true). The rest is 0 (false))\n");
    printf("The result of x^y == 11111010 (1 (true) only if the two bits are different. The rest is 0 (false))\n");
    printf("The result of ~x == 01001100 (Reverse 1 (true) and 0 (false))\n");
    printf("The result of x<<2 == 11001100 (Move the bit to the left by 2 bits. Fill empty spaces with 00)\n");
    printf("The result of x>>2 == 00101100 (Move the bit to the right by 2 bits. Fill empty spaces with 00)");
}
```
   
<br/>
### Other Operators   
// 기타 연산자   
   
|Operator|Function|
|:---:|:---|
|sizeof()|// 지정한 자료형, 수식, 변수가 차지하는 기억공간의 크기 (byte) 를 구함<br />- Find the size (byte) of memory space occupied by the specified data type, expression statement, and variable|
|cast(conversion of data type)|// 지정한 자료형을 다른 자료형으로 강제적으로 바꿈<br />- Forced to change the designated data type to another data type|
|&|// 주소 연산자로서 피연산자의 주소를 나타냄<br />- An address operator that represents the address of an operand|
|*|// 내용 연산자로서 피연산자의 내용을 가져옴<br />- As a content operator, bring the content of the operand|
   
#### sizeof()   
   
// 형식   
- Formats   
   
```c
// sizeof(자료형 또는 수식 또는 변수 또는 상수)
sizeof(Data type or expression statement or variable or constant)
```
   
// 기능   
// - 지정한 자료형, 수식, 변수, 상수의 기억공간의 크기 (byte) 를 구함   
- Function   
  - Find the size (byte) of memory space occupied by the specified data type, expression statement, and variable   
   
// 사용 예시   
- Examples of Use   
   
```c
sizeof(int)
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    float a7 = 3.14;
    printf("The size of the int type is =%d bytes\n", sizeof(int));
    printf("Size of float type variable a7 is =%d bytes", sizeof(a7));
}
```
   
- Result   
   
```
The size of the int type is =4 bytes
Size of float type variable a7 is =4 bytes
```
   
#### cast operator (conversion of data type operator)   
// cast 연산자 (형변환 연산자)   
   
// 형식   
- Formats   
   
```c
// (형명칭)자료
(Type Name)Data
```
   
// 기능   
// - 이미 지정된 자료의 자료형을 다른 자료형으로 강제적으로 바꿈   
- Function   
  - Forced to change the data type of the already specified data to another data type   
   
// 사용 예시   
- Examples of Use   
   
```c
(float)i/j
```
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int a8 = 3, b8 = 4;
    double c8;
    // int형인 a8을 double형으로 강제 형변환
    // Force conversion of int type a8 to double type
    c8 = (double)a8 / b8;
    printf("result of division : %f\n", c8);
}
```
   
- Result   
   
```
result of division : 0.750000
```
   
<br />
### Operator Precedence   
// 연산자 우선순위   
   
|Precedence|Operator|Description|Associativity|
|:---:|:---:|:---|:---:|
|1|++ --|Suffix/postfix increment and decrement|Left-to-right|
|1|()|Function call|Left-to-right|
|1|[]|Array subscripting|Left-to-right|
|1|.|Structure and union member access|Left-to-right|
|1|->|Structure and union member access through pointer|Left-to-right|
|1|(type){list}|Compound literal|Left-to-right|
|2|++ --|Prefix increment and decrement|Right-to-left|
|2|+|Unary plus|Right-to-left|
|2|-|Unary minus|Right-to-left|
|2|!|Logical NOT|Right-to-left|
|2|~|Bitwise NOT|Right-to-left|
|2|(type)|Cast|Right-to-left|
|2|*|Indirection (dereference)|Right-to-left|
|2|&|Address-of|Right-to-left|
|2|sizeof|Size-of|Right-to-left|
|2|_Alignof|Alignment requirement|Right-to-left|
|3|*|Multiplication|Left-to-right|
|3|/|Division|Left-to-right|
|3|%|Remainder|Left-to-right|
|4|+|Addition|Left-to-right|
|4|-|Subtraction|Left-to-right|
|5|&#60;&#60;|Bitwise left shift|Left-to-right|
|5|&#62;&#62;|Bitwise right shift|Left-to-right|
|6|&#60;|Relational operators <|Left-to-right|
|6|&#60;=|Relational operators ≤|Left-to-right|
|6|&#62;|Relational operators >|Left-to-right|
|6|&#62;=|Relational operators ≥|Left-to-right|
|7|==|Relational =|Left-to-right|
|7|!=|Relational ≠|Left-to-right|
|8|&|Bitwise AND|Left-to-right|
|9|^|Bitwise XOR (exclusive or)|Left-to-right|
|10|\||Bitwise OR (inclusive or)|Left-to-right|
|11|&&|Logical AND|Left-to-right|
|12|\|\||Logical OR|Left-to-right|
|13|?:|Ternary conditional, Trinomial|Right-to-left|
|14|=|Simple assignment|Right-to-right|
|14|+=|Assignment by sum|Right-to-right|
|14|-=|Assignment by difference|Right-to-right|
|14|*=|Assignment by product|Right-to-right|
|14|/=|Assignment by quotient|Right-to-right|
|14|%=|Assignment by remainder|Right-to-right|
|14|&#60;&#60;=|Assignment by bitwise left shift|Right-to-right|
|14|&#62;&#62;=|Assignment by bitwise right shift|Right-to-right|
|14|&=|Assignment by bitwise AND|Right-to-right|
|14|^=|Assignment by bitwise XOR|Right-to-right|
|14|\|=|Assignment by bitwise OR|Right-to-right|
|15|,|Comma|Left-to-right|
   
#### Example of a computational process based on operator precedence   
// 연산자 우선순위에 따른 연산과정 예시   
   
`z = x + y * 2 - ++x + (y += 3)`   
① : `y += 3`   
② : `++x`   
③ : `y * 2`   
④ : 'x + ③ - ② + ①' == ` x + y * 2 - ++x + (y += 3)`   
⑤ : 'z = ④' == `z = x + y * 2 - ++x + (y += 3)`   
   
- Example   
   
```c
#include <stdio.h>

void main() {
    int a9, b9, c9;
    a9 = 10;
    b9 = 20;
    c9 = 30;
    // a9+(b9*c9)
    printf("a9+b9*c9=%d\n", a9 + b9 * c9);
    // b9+=2*c9 먼저 계산되고 a9=b9가 계산됨
    // b9+=2*c9 is calculated first, and a9=b9 is calculated
    printf("a9=b9+=2*c9 --> a9=%d\n", a9 = b9 += 2 * c9);
    printf("a9=(b9>c9)?b9:c9 --> a9=%d\n", a9 = (b9 > c9) ? b9 : c9);
    printf("a9/b9*c9=%d\n", a9 / b9 * c9);
    // a9=(a9*(b9=(c9+5))) : c9+5가 b9에 저장되고, a9*b9가 a9에 저장됨
    // a9=(a9*(b9=(c9+5))) : c9+5 is stored in b9, a9*b9 is stored in a9
    printf("a9*=b9=c9+5 --> a9=%d", a9 *= b9 = c9 + 5);
}
```
   
- Result   
   
```
a9+b9*c9=610
a9=b9+=2*c9 --> a9=80
a9=(b9>c9)?b9:c9 --> a9=80
a9/b9*c9=30
a9*=b9=c9+5 --> a9=2800
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
