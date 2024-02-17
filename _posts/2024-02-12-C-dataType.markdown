---
layout: post
title:  "C: data type"
date:   2024-02-12 09:00:00 +0900
categories: [C]
---

// 자료형은 상수와 변수로 구분하여 사용함   
Data type are divided into constant and variable   
   
// 상수는 항상 고정되는 값을 갖는 자료임   
Constant is a data that always has a fixed value   
   
// 변수는 프로그램 실행 도중 변할 수 있는 값이 저장되는 기억공간임   
Variable is a storage space where values that can change during program execution are stored   
   
// 자료형의 종류에는 기본형과 확장형이 있음   
Types of data type include Basic type and Extended type   
   
<br />
### Basic type   
// 기본형   
   
// 정수형   
integer type: `int` (4byte), `short int` (2byte), `long int` (4byte), `unsigned int` (4byte), `unsigned short int` (2byte), `unsigned long int` (4byte)   
   
// 실수형   
floating-point type: `float` (4byte), `double` (8byte), `long double` (8byte)   
default: `double`   
   
// 문자형   
character type: `char` (1byte), `unsigned char` (1byte)   
// char : -128 ~ 127까지의 값으로 ASCII 코드를 사용하여 처리. 실제 저장은 숫자로 저장됨   
`char` : Processed using ASCII code with values from -128 to 127. saved as a number   
// unsigned char : 0 ~ 255까지의 값으로 ASCII 코드를 사용하여 처리. 실제 저장은 숫자로 저장됨   
`unsigned char` : Processed using ASCII code with values from 0 to 255. saved as a number   
   
// 열거형: enum 태그명 {열거자1, 열거자2, ...}   
enumerated type: `enum tagName {SUN, MON, TUE, WED, ...} e1`   
e1 = SUN; ---> e1 == 0   
SUN == 0, MON == 1, TUE == 2, WED == 3, ...   
   
// 형 없음   
`void`   
   
<br />
### Extended type   
// 확장형   
   
// 배열형   
array type   
   
// 함수형   
function type   
   
// 포인터형   
pointer type   
   
// 구조체형   
structure type   
