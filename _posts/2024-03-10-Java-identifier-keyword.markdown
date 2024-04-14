---
layout: post
title:  "Java: Identifier, Keyword"
date:   2024-03-10 09:00:00 +0900
categories: [Java]
---

### Identifier   
// 식별자   
   
// 프로그래머가 작명하는 이름   
// 클래스, 변수, 메소드, 레이블 등의 이름   
- Name created by programmer   
- Names of classes, variables, methods, labels, etc.   
   
<br />
### The rules for naming identifiers   
// 식별자 작명 규칙   
   
// 대소문자 구분, 길이에 제한 없음   
// 영문 대소문자, 한글, 숫자, '_', '$'를 사용   
// 숫자로 시작할 수 없음   
// 키워드, true, false, null은 불가   
- Case sensitive, length free   
- Use alphabetic characters, Korean, numerals, '_', '$'   
- Can't start with a number   
- Keywords, true, false, null are not allowed   
   
// 잘못 작명된 식별자의 예   
- Example of a misnamed identifier   
  - 2002WorldCup   
  - my#class   
  - class   
  - World Cup   
  - lee@abc   
   
<br />
### Conventions for creating identifiers   
// 식별자를 만들 때의 관례   
   
#### class   
// 클래스   
   
// 첫 자는 대문자   
// 단어의 첫 글자는 대문자   
// 나머지는 소문자   
// 예시 : `Car, HelloWorld, MyClass, String`   
- The first character is capital character   
- The first character of the word is capital character   
- The rest are lowercase characters   
- Example : `Car, HelloWorld, MyClass, String`   
   
#### method, variable (field)   
// 메소드, 변수 (필드)   
   
// 첫 자는 소문자   
// 단어의 첫 글자는 대문자   
// 나머지는 소문자   
// 변수 예시 : `speed, myCar`   
// 메소드 예시 : `gearArea()`   
- The first character is lowercase   
- The first character of the word is capital character   
- The rest are lowercase characters   
- Example of a variable : `speed, myCar`   
- Example of a method : `gearArea()`   
   
// 변수의 경우 자료형을 표시하기 위한 접두어를 붙이기도 함   
// - 헝가리안 표기법   
// - 예시   
// -- int형 자료형을 표시하기 위해 변수명 앞에 n을 붙임 : `int nSpeed;`   
// -- String형 자료형을 표시하기 위해 변수명 앞에 sz를 붙임 : `String szStr1;`   
- For variables, prefixes are also attached to indicate the type of data   
  - Hungarian notation   
  - Example   
    - n before variable names to display int-type data types : `int nSpeed;`   
    - sz before variable names to display String-type data types : `String szStr1;`   
   
#### constant   
// 상수   
   
// 모든 문자를 대문자로 표기하고, 단어 사이에 '_'를 넣어 구분   
// 예시 : `static final int NUM_GEARS = 6;`   
- Capitalize all characters and distinguish them by placing '_' between words   
- Example : `static final int NUM_GEARS = 6;`   
   
<br />
### keyword   
// 키워드   
   
// 의미가 미리 정해진 단어   
// 프로그램에서 정해진 의미로만 사용해야 함   
- a word with a predetermined meaning   
- Must be used only in the meaning set by the program   
   
```java
abstract    continue    for   new   switch
assert***   default   goto*   package   synchronized
boolean   do    if    private   this
break   double    implements    protected   throw
byte    else    import    public    throws
case    enum****    instanceof    return    transient
catch   extends   int   short   try
char    final   interface   static    void
class   finally   long    strictfp**    volatile
const*    float   native    super   while
```
   
// goto, const는 현재 사용하지 않음   
// strictfp는 java2부터 사용할 수 있음   
// assert는 java3부터 사용할 수 있음   
// enum은 java4부터 사용할 수 있음   
- goto, const is not currently used   
- strictfp is available from java2   
- assert is available from java3   
- enum is available from java4   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
