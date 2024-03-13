---
layout: post
title:  "JScript: Variable"
date:   2024-03-13 09:00:00 +0900
categories: [JScript]
---

// Microsoft JScript에서 변수는 스크립트 내에 값을 저장하는데 사용됨   
// 변수를 사용하면 이름으로 값을 읽고 조작할 수 있음   
// 변수를 효과적으로 사용하면 스크립트를 이해하는데 도움을 줌   
- In Microsoft JScript, variables are used to store values within scripts   
- Variables read and manipulate values by name   
- Effective use of variables helps you understand the script   
   
### variable declaration   
// 변수 선언   
   
// 변수를 사용하기 전에 반드시 변수를 먼저 선언해야 할 필요는 없지만 이렇게 하는 것이 좋음   
// 변수 선언에는 var문을 사용   
// var문을 반드시 사용해야 하는 경우는 함수에 대해 지역 변수를 선언할 때 뿐임   
// 지역 변수란 함수 내에서만 사용되는 변수를 말함   
// 다른 경우에는 var문을 사용하여 변수를 선언해도 특별히 달라지는 것이 없음   
- It is not necessary to declare a variable before using it, but it is recommended that you do this   
- Use var statements for variable declarations   
- The var statement must be used only when declaring a local variable for a function   
- A local variable is one that is only used within a function   
- In other cases, using var statements to declare variables does not change particularly   
   
```javascript
var mim = "People, plans, canals, Panama!";  // The value stored in mim is in String format
// The statement in the quotation marks specified in mim is a string literal

var ror = 3;    // The value stored in the ror is in Number format
var nen = true; // The value stored in nen is in Boolean format
var fif = 2.718281828;   // The value stored in nen is in Number format.
```
   
### naming variable   
// 변수 명명   
   
// JScript에서는 대/소문자를 구분하기 때문에 myCounter와 MYCOUNTER란 변수 이름은 서로 다른 이름임   
- Because JScript is case sensitive, the variable names myCounter and MYCOUNTER are different   
   
// 길이에는 제한이 없지만 변수 이름은 다음 규칙을 따라야 함   
// - 처음 문자로는 영문자(대문자 또는 소문자)나 밑줄(_), 달러 기호($) 중 하나를 사용해야 함   
// - 이어지는 문자로는 영문자, 숫자, 밑줄, 달러 기호를 사용할 수 있음   
// - 예약어와 같은 이름은 변수에 지정할 수 없음   
- There is no limit to length, but variable names must follow the following rules   
- The first character must be either alphabetic (case or lowercase) or underscore (_), or dollar sign ($)   
- Subsequent characters can include English characters, numbers, underscores, and dollar signs   
- Names such as reservation words cannot be specified in variables   
   
// 유효한 변수 이름 예시   
- Valid variable name example   
  - _pagecount   
  - Part9   
  - Number_Items   
   
// 잘못된 변수 이름 예시   
// - 99Balloons --> 숫자로 시작하여 잘못됨   
// - Smith&Wesson   --> 특수문자 앰퍼샌드(&)를 사용하여 잘못됨   
- Invalid variable name example   
  - 99Balloons --> Invalid starting with a number   
  - Smith&Wesson   --> Invalid using special character ampersand (&)   
   
// 특정한 값을 지정하지 않고 변수를 선언하여 초기화할 때는 특정 값으로 null을 지정할 수 있음   
- You can specify null as a specific value when you initialize a variable by declaring it without specifying a specific value   
   
```javascript
var zaz = null;
var notalot = 3 * zaz;  // Here, the notalo is zero
```
   
// 아무런 값도 지정하지 않고 변수를 선언하면 해당 변수는 존재하기는 하지만 undefined 상태가 됨   
- Declaring a variable without specifying any value results in an undefined state, although it exists   
   
```javascript
var godot;
var waitingFor = 1 * godot;     // Specifies the NaN value for waitingFor because the godot value is not defined
```
   
// 변수에 값을 지정하여 변수를 함축적으로 선언(var를 사용하지 않음)할 수 있음   
// 하지만 선언되지 않은 변수를 사용할 수는 없음   
// 선언하지 않은 변수를 사용하면 런타임 오류가 발생   
- Variables can be implicitly declared (without var) by specifying values for them   
- But, undeclared variables cannot be used   
- Runtime error when using undeclared variables   
   
```javascript
let = "";   // Implicit declaration of variable let
var aMess = vyv + zez;  // Error occurs because vyv and zez do not exist
```
   
### forced conversion   
// 강제 변환   
   
// JScript는 느슨한 형식의 언어이기 때문에 JScript 내의 변수는 기술적으로 고정된 형식이 없음   
// 변수의 형식은 변수에 포함되어 있는 값의 형식과 같음   
// 변수 또는 데이터의 일부를 다른 형식으로 자동 변환(강제)하는 경우도 있을 수 있음   
// 숫자는 문자열에 쉽게 포함될 수 있지만, 문자열은 직접 숫자에 포함될 수 없기 때문에 명시적 변환 함수 parseInt()와 parseFloat()를 사용함   
- Because JScript is a loose format language, variables within JScript are not technically fixed   
- The format of a variable is the same as the format of the value contained in the variable   
- JScript may automatically convert (enforce) a variable or part of the data into another format   
- Numbers can easily be included in strings, but strings cannot be included in direct numbers, so explicit transformation functions paradeInt() and paradeFloat() are used   
   
```javascript
var theFrom = 1;
var theTo = 10;
var doWhat = "The calculation is from ";
doWhat += theFrom + "to " + theTo + ".";
```
   
// 이 코드를 실행하면 doWhat 변수에 "The calculation is from 1 to 10."가 포함됨   
// 숫자 데이터가 문자열 형식에 강제로 포함된 것임   
- Running this code will include "The calculation is from 1 to 10" in the doWhat variable   
- Number data is forcibly included in string format   
   
```javascript
var nowWhat = 0;
nowWhat += 1 + "10";
// 이 경우 "10"이 문자열이기 때문에 "+=" 연산자는 두 문자열을 연결함
// In this case, the "+=" operator connects the two strings because "10" is a string
```
   
// 이 코드를 실행하면 nowWhat 변수에 "0110"이 포함됨   
// 이러한 결과가 나오려면 다음과 같은 단계를 거침   
// 1. 1과 "10"의 형식을 봄. "10"은 문자열이고 1은 숫자이기 때문에 숫자를 문자열로 변환함   
// 2. + 연산자 양쪽에 모두 문자열이 있으므로 문자열을 결합함. 결과값은 "110"   
// 3. += 연산자 양쪽에 있는 값의 형식을 봄. nowWhat에는 숫자가 포함되어 있고, "110"은 문자열이기 때문에 숫자를 문자열로 변환함   
// 4. += 연산자 양쪽에 모두 문자열이 있으므로 문자열을 결합함. 결과값은 "0110"   
// 5. 이 결과를 nowWhat에 저장   
- Running this code will include "0110" in the nowWhat variable   
- To achieve these results, take the following steps   
  - 1. Look at the format of 1 and "10". Translate numbers into strings because "10" is a string and 1 is a number   
  - 2. + Combine strings because there are strings on both sides of the operator. The result is "110"   
  - 3. += View the format of the value on both sides of the operator. 
NowWhat contains a number, and "110" is a string, so we convert a number into a string   
  - 4. += Combine strings because there are strings on both sides of the operator. The result is "0110"   
  - 5. Save this result to nowWhat   
   
```javascript
var nowThen = 0;
nowThen += 1 + parseInt("10");  // In this case, "+=" runs the addition
```
   
// 이 코드를 실행하면 nowThen 변수에 정수값 11이 포함됨   
- Running this code will include an integer value of 11 in the nowTen variable   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
