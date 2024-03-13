---
layout: post
title:  "JScript: Code Basic"
date:   2024-03-13 09:00:00 +0900
categories: [JScript]
---

// JScript는 텍스트 형식으로 작성되며, 문, 상호관련이 있는 문으로 이루어진 블록 및 주석으로 구성됨   
// 사용자는 문 내에서 변수, 문자열과 숫자와 같은 직접 실행 데이터, 식을 사용할 수 있음   
- JScript is written in text format and consists of blocks and comments consisting of statements, correlated statements   
- Users can use direct execution data or expressions such as variables, strings, and numbers within the statements   
   
### statement   
// 문   
   
// JScript 코드문은 한 줄에 한 개 이상의 항목과 기호로 이루어져 있음   
// 새 줄은 새 문으로 시작하지만 종결문자인 세미콜론(;)을 사용하여 명확히 종결짓는 것을 권장함   
- JScript code statements consist of one or more items and symbols per line   
- A new line begins with a new statement, but it is recommended to end clearly using the terminating character semicolon(;)   
   
// 예시   
- Example   
   
```javascript
aBird = "Robin";
var today = new Data();
```
   
// 중괄호 ({})로 둘러싸인 여러 줄의 JScript문을 블록이라고 함   
// 블록은 함수나 조건문에 사용됨   
- Multiple lines of JScript statements surrounded by brace ({}) are called blocks   
- Blocks are used in functions or conditional statements   
   
// 예시   
// - 첫번째 문은 함수의 정의를 시작하는 문으로, 이 함수는 5개의 문으로 이루어진 블록으로 구성되어 있음   
// - 중괄호를 사용하지 않은 마지막 3개 문은 블록이 아니며 함수의 일부분도 아님   
- Example   
  - The first statement is the statement that starts the definition of a function, which consists of a block of five statements   
  - The last 3 statements without brace are not blocks and are not part of a function   
   
```javascript
function convert(inches) {
    // These three statements are one block
    feet = inches / 12;
    miles = feet / 5280;
    nauticalMiles = feet / 6080;
    cm = inches * 2.54;
    meters = inches / 39.37;
}

// These three statements are not blocks
km = meters / 1000;
kradius = km;
mradius = miles;
```
   
### comment   
// 주석   
   
// 한 줄의 JScript 주석은 슬래시 두 개(//)로 시작함   
// 여러 줄 주석은 슬래시와 별표의 조합( /* )으로 시작하며 시작 표시와는 반대 순서인 별표와 슬래시( */ )로 끝남   
- One line of JScript comment starts with two slashes (//)   
- Multiple line comments begin with a combination of slashes and asterisks ( /*) and end with asterisks and slashes ( */) in the opposite order to the start mark   
   
```javascript
aGoodIdea = "Complete the comments"; // This is a one-line comment.

/*
    // 이것은 코드문을 설명하는 여러줄 주석입니다.
    // 이 문은 aGoodIdea 변수에 값을 지정합니다.
    // 따옴표 사이의 값을 리터럴이라고 합니다.
    // 리터럴은 명시적이고 직접적인 정보를 가지고 있습니다.
    // 다시 말해 정보를 간접적으로 참조하지 않습니다.
    // 따옴표는 리터럴의 일부분이 아닙니다.
    - This is a multi-line comment that describes the code statement
    - This statement specifies a value for the aGoodIdea variable
    - Values between quotes are called literal
    - Literals have explicit and direct information
    - In other words, it does not refer indirectly to the information
    - Quotations are not part of a literal
*/

// 이것은 또다른 여러 줄 주석입니다. 한 줄 주석을 여러 개 썼습니다.
// 문이 실행된 후 다음 문에서와 같이 변수 이름을 사용하여 aGoodIdea 변수의 내용을 참조할 수 있습니다.
// 여기서 문자열 리터럴은 연결에 의해 aGoodIdea 변수에 추가되어 새 변수를 만들어 냅니다.
// This is another line of commentary. Several lines of commentary
// After the statement is executed, you can use the variable name to refer to the contents of the aGoodIdea variable, as shown in the following statement
// The string literal is added to the aGoodIdea variable by connection to create a new variable

var extendedIdea = aGoodIdea + "text";
```
   
### Same as designated   
// 지정과 같음   
   
// JScript에서 등호(=)는 값을 지정하는 동작을 가리킬 때 사용됨   
- In JScript, the equal sign (=) is used to indicate the action of specifying a value   
   
```javascript
anInterger = 3;
```
   
// 이 코드문은 "3이라는 값을 anInteger 변수에 지정하십시오" 또는 "anInteger가 3이라는 값을 갖습니다"라는 의미임   
// 두 값이 같은지 비교할 때 사용하는 기호로는 등호 두개(==)를 사용   
- This code statement means "Specify a value of 3 for the anInteger variable" or "anInteger has a value of 3."   
- Use two equal signs (==) as symbols to compare if two values are equal   
   
### expression   
// 식   
   
// JScript 식은 부울식이나 숫자식으로 읽을 수 있는 것임   
// 식에는 "더하기"와 같은 단어가 아니라 "+"와 같은 기호문자가 포함됨   
// 값, 변수, 연산자 및 식이 적절하게 결합되어 식을 구성함   
- The JScript expression is a Boolean expression or a numeric expression that can be read   
- Expression contains symbols such as "+" rather than words such as "plus"   
- Values, variables, operators, and expressions are properly combined to construct expressions   
   
```javascript
var anExpression = "3 * (4 / 5)";
var aSecondExpression = "MAth.PI * radius * 2";
var aThirdExpression = aSecondExpression + "%" + anExpression;
var aFourthExpression = "(" + aSecondExpression + ") % (" + anExpression + ")";
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
