---
layout: post
title:  "Java: Data Type"
date:   2024-03-10 09:00:00 +0900
categories: [Java]
---

### variable type and data type   
// 변수의 종류와 자료형   
   
#### variable and Data type   
// 변수와 자료형   
   
// 변수를 선언할 때 저장되는 값의 자료형을 선언   
// 메소드를 선언할 때 파라미터와 반환 값의 자료형을 선언   
// 자료형에 따라 적용 가능한 연산이 다름   
- Declare the data type of the value stored when declaring a variable   
- When declaring a method, declare the parameters and return values data type   
- Applicable operations vary depending on the data type   
   
#### variable type   
// 변수의 종류   
   
|Type|Description|
|:---:|:---|
|// 데이터 필드<br />// - 인스턴스 변수<br />Data Field<br />- Instance Variable|// 클래스 정의에서 non-static 필드<br />// 개별 객체가 소유한 변수<br />- In class definition, non-static fields<br />- Variables owned by individual objects|
|// 데이터 필드<br />// - 클래스 변수<br />// (static 변수, 정적 변수)<br />Data Field<br />- Class Variable<br />(static variable)|// 클래스 정의에서 static 필드<br />// 동종 객체 간 공유 변수(정적 변수)<br />- In class definition, static fields<br />- Shared variables between homogeneous objects (static variable)|
|// 지역 변수<br />Local Variable|// 메소드 내부(또는 블록 내부)에서 선언된 변수<br />- Variables declared inside the method (or inside the block)|
|// 파라미터<br />Parameter|// 메소드 호출 시 전달하는 값을 저장하기 위한 변수<br />- Variables to store the values that are passed on method calls|
   
<br />
### Range of Use of Variables   
// 변수의 사용 범위   
   
#### Local Variable and Parameter   
// 지역 변수와 파라미터   
   
// 선언된 곳부터 해당 블록이 종료될때까지 유효함   
// - 메소드가 실행될 때 만들어지고 종료되면 없어짐   
// 지역 변수는 초기값을 지정한 후 사용해야 함   
// 지역 변수 선언에서는 접근 제어자(access modifier)를 사용하지 않음   
- Valid from where it was declared until the block was terminated   
  - Created when the method runs and disappears when terminated   
- Local variables must be used after initial values are specified   
- Do not use access modifier in local variable declarations   
   
#### Data field (instance variable or class variable)   
// 데이터 필드(인스턴스 변수 or 클래스 변수)   
   
// 선언된 클래스 내부에서 사용 가능   
// 클래스 외부에서의 사용 가능 여부는 접근 제어자(access modifier)에 따라 다름   
// - 예시 : `class Circle { protected int radius; ... }`   
- Available inside declared classes   
- The availability outside the class depends on the access modifier   
  - Example : `class Circle { protected int radius; ... }`   
   
<br />
### Java's default data type   
// Java의 기본 자료형   
   
|Type|Keyword|Length(byte)|The range of values|
|:---:|:---:|:---:|:---|
|character|char<br />(use Unicode)|2|'\u0000' ~ '\uffff'|
|logic|boolean|1|true or false|
|integer|byte|1|-128 ~ 127|
|integer|short|2|-32768 ~ 32767|
|integer|int|4|-2³¹ ~ (2³¹ - 1)|
|integer|long|8|-2&#8310;³ ~ (2&#8310;³ - 1)
|real number|float|4|(+/-)Approximately 1.4E-45 ~ 3.4E38|
|real number|double|8|(+/-)Approximately 4.9E-324 ~ 1.8E308|
   
<br />
### literal   
// 리터럴   
   
#### constants   
// 상수   
   
// 값이 한번 할당되면, 값을 변경할 수 없는 변수   
- Variables that cannot be changed once a value is assigned   
   
// 예시   
// - `final int nConst = 3;` // 선언 시 초기 값을 지정한 경우   
- Example   
  - `final int nConst = 3;` // Specify initial values in declaration   
   
#### literal   
// 리터럴   
   
// 소스 코드에서 사용되는 실제 데이터 값   
- Actual data values used by source code   
   
#### integer literal   
// 정수형 리터럴   
   
// byte, short, int 또는 long형의 실제 값   
// 소문자 i이나 대문자 L로 끝나면 long형, 나머지는 int   
// - byte와 short는 허용 범위 안에서 int와 호환됨   
- Actual value of byte, short, int, or long type   
- If it ends with lowercase i or uppercase L, it's long, and the rest is int   
  - byte and short are compatible with int within acceptable range   
   
// 예시   
// - long형 : 26L   
// - int형 : 26(10진수), 0b11010(2진수), 032(8진수), 0x1a(16진수)   
- Example   
  - long type : 26L   
  - int type : 26 (decimal), 0b11010 (binary), 032 (eight), 0x1a (heximal)   
   
#### real number literal   
// 실수형 리터럴   
   
// 소수점이 있는 숫자   
// f나 F로 끝나면 float형, 나머지는 double형   
- a number with a decimal point   
- If it ends in f or F, it's float type, and the rest is double type   
   
// 예시   
// - float형 : 123.4f   
// - double형 : 123.4, 1.234e2   
- Example   
  - float type : 123.4f   
  - double type : 123.4, 1.234e2   
   
#### character literal   
// 문자형 리터럴   
   
// 1개의 문자를 표현하고 16비트 Unicode로 인코딩됨   
// 단일 따옴표를 사용하고 Unicode 사용 가능   
// - '\u0000' ~ '\uffff'   
// - 1개 문자는 (0 ~ 65535)의 수와 호환됨   
- 1 character represented and encoded in 16-bit Unicode   
- Single quotes and Unicode enabled   
  - '\u0000' ~ '\uffff'   
  - One character is compatible with a number of '0 to 65535'   
   
// 예시   
// - 대문자 A 표현 : `(char)65, 'A', '\u0041'`   
// - 한글 가 표현 : `'가', '\uAC00'`   
- Example   
  - uppercase 'A' expression : `(char)65, 'A', '\u0041'`   
  - Expressions in Korean 'A' : `'가', '\uAC00'`   
   
<br />
### reference type   
// 참조형   
   
// 기본형을 제외한 모든 자료형   
// 참조 값(주소 값)을 나타내는 자료형   
- All data types except default types   
- Data type that represents the reference value (address value)   
   
// 참조형 변수는 객체를 가리키는 변수로, 객체의 주소 값(참조 값)을 저장함   
// - 실제 객체는 동적 메모리 공간에 저장됨   
// - 기본형 변수는 저장 공간에 값 자체를 저장함   
- A reference variable is a variable that points to an object and stores the object's address value (reference value)   
  - Real objects are stored in dynamic memory space   
  - The default variable stores the value itself in the storage space
   
// 대표적 참조형은 클래스, 배열, 인터페이스, 열거형 등   
- Representative reference types include classes, arrays, interfaces, enumeration, etc.   
- Example   
  - `Person p1;`   
  - `String szStr;`   
  - `int anArray[];`   
   
<br />
### conversion of data type  
// 자료형의 변환(형변환)   
   
#### conversion of implied data type   
// 묵시적 자료형의 변환   
   
// 작은 타입에서 큰 타입으로의 자동 형변환   
// - byte → short → int → long → float → double   
// - 개발자 → 직원 → 인간 → 포유류   
- Automatic type conversion from small to large type   
  - byte → short → int → long → float → double   
  - Developer → Staff → Human → Mammals   
   
// 예시   
// - `double d = 5;`   
// -- 대입문 : int형인 5가 double형 5.0 으로 자동 형변환 됨   
// - `System.out.println("j = " + 10);`   
// -- 수식 : 문자 'j = '과 숫자 10을 합하여 문자형 'j = 10' 으로 자동 형변환 됨   
// - `double res = Math.sqrt(2);`   
// -- 메소드 호출 시 인자의 유형 : int형인 2가 double형인 2.0 으로 자동 형변환 됨   
- Example   
  - `double d = 5;`   
    - substitute : int type 5 automatically converted to double type 5.0   
  - `System.out.println("j = " + 10);`   
    - method : Automatically converted into character type 'j = 10' by combining letters 'j = 10' and numbers 10   
  - `double res = Math.sqrt(2);`   
    - Type of parameter in method call : Int type 2 is automatically converted to double type 2.0   
   
#### conversion of explicit data type   
// 명시적 자료형의 변환   
   
// 큰 타입에서 작은 타입으로 변환할 때는 명시적 형변환이 필요   
// 명시적 형변환은 강제로 변환하는 것   
// 문법 : `(자료형)피연산자`   
- Explicit type conversion is required when converting from large to small type   
- Explicit conversion is forced conversion   
- Grammar : `(data type) operand`   
   
// 예시   
// - `float f = (float)5.5;`   
// -- double형인 5.5를 float형으로 강제 형변환하여 f에 대입   
- Example   
  - `float f = (float)5.5;`   
    - convert double type 5.5 into float type and substitute it into f   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
