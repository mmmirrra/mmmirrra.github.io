---
layout: post
title:  "JScript: Data Type"
date:   2024-03-13 09:00:00 +0900
categories: [JScript]
---

### Type of JScript data format   
// JScript 데이터 형식의 종류   
   
// Microsoft JScript에는 6가지 데이터 형식이 있음   
// 중요한 형식 : Number, String, Object, Boolean   
// 나머지 형식 : null, undefined   
- Microsoft JScript has six data formats   
- an important format : Number, String, Object, Boolean   
- the rest of the format : null, undefined   
   
<br />
### String data format   
// String 데이터 형식   
   
// 문자열은 작은따옴표나 큰따옴표를 사용하여 표현   
// 따옴표를 포함한 문자열을 표현하려면 작은따옴표를 사용함   
// JScript에서는 문자열도 개체인데, 특별한 속성을 가지고 있으며 특별한 경우에 사용함   
- A string is represented by a single quotation marks or double quotation marks  
- Use single quotation marks to express a string that contains quotation marks   
- In JScript, strings are also objects, which have special properties and are used in special cases   
   
// 문자열 예시   
- String Example   
   
```javascript
"The cow jumped over the moon"
'"Guys, stop!" cried the technician.'
"42"
```
   
// 문자열은 0개 이상의 유니코드 문자를 포함할 수 있음   
// 문자열이 유니코드 문자를 전혀 포함하고 있지 않을 때 이를 빈 문자열("")이라고 함   
- String can contain more than 0 Unicode characters   
- When a string contains no Unicode characters, it is called an empty string ("")   
   
<br />
### Number data format   
// Number 데이터 형식   
   
// JScript는 정수와 부동 소수점 숫자를 지원함   
// 정수 : 양수, 0, 음수   
// 부동 소수점 숫자 : 소수점 또는 과학적 표기법에서 10의 거듭제곱을 나타내는 "e"(대문자 또는 소문자) 중 하나를 포함하거나 둘 다 포함할 수 있음   
// 숫자 표현은 IEEE 754 표준을 따름   
- JScript supports integer and floating point number   
- integer: positive, 0, negative   
- floating point number : In decimal or scientific notation, it may contain one or both of the "e" (case or lowercase characters) representing a power of 10   
- The numerical representation follows the IEEE 754 standard   
   
// 특별한 숫자 값들   
// - Nan (not a Number) : 숫자가 아님   
// - Positive Infinity : 양의 무한대   
// - Negative Infinity : 음의 무한대   
// Positive 0 : 양의 0   
// Negative 0 : 음의 0   
- special numerical values   
  - Nan : Not a Number   
  - Positive Infinity   
  - Negative Infinity   
- Positive 0   
- Negative 0   
   
// 정수는 10진수, 8진수 및 16진수로 표현될 수 있음   
- integers can be expressed in decimal, octal, and hexadecimal   
   
#### octal   
// 8진수   
   
// 8진수 정수는 "0"으로 시작하며 0부터 7까지의 숫자를 사용함   
// 숫자가 "0"으로 시작되고 숫자 "8" 및 또는 "9"를 포함한다면 그 숫자는 10진수임   
// 8진수이면서 문자 "e"(또는 "E")를 포함하는 숫자는 오류를 일으킴   
- An octal integer starts with "0" and uses a number from 0 to 7   
- If a number starts with "0" and contains numbers "8" and/or "9," the number is decimal   
- Numbers that are octal and contain the character "e" (or "E") cause errors   
   
#### hexadecimal   
// 16진수   
   
// 16진수("hex") 정수는 "0x"("X"는 소문자 또는 대문자)로 시작하며 0부터 9까지의 숫자와 A부터 F(소문자 또는 대문자)까지의 문자를 사용함   
// 16진수 표기법에서는 "e"문자가 허용되지만 지수를 의미하지는 않음   
// A부터 F까지의 문자는 10진수의 10부터 15까지의 숫자를 나타내기 위하여 사용됨   
- The hexadecimal ("hex") integer starts with "0x" (where "X" is a lowercase or uppercase character) and uses numbers from 0 to 9 and characters from A to F (lower case or uppercase character)   
- In hexadecimal notation, an "e" character is allowed, but not an exponent   
- Characters A through F are used to represent decimal numbers 10 through 15   
   
// 예시   
// - 16진수 0xF = 10진수 15   
// - 16진수 0x10 = 10진수 16   
- Example   
  - hexadecimal 0xF = decimal 15   
  - hexadecimal 0x10 = decimal 16   
   
#### floating point number   
// 부동소수점 숫자   
   
// 8진수와 16진수는 음수가 될 수 있지만 분수가 될 수는 없음   
// "0"으로 시작하고 소수점을 포함하는 숫자는 부동 소수점 숫자임   
// "0x" 또는 "00"으로 시작하는 숫자가 소수점을 포함한다면 소수점 오른쪽에 있는 내용은 무시됨   
- Octal and hexadecimal numbers can be negative, but not fractions   
- Numbers that begin with "0" and contain decimal are floating-point numbers   
- If a number that begins with "0x" or "00" contains a decimal point, the content to the right of the decimal point is ignored   
   
// 숫자에 관한 예시   
- Example of a number   
   
```javascript
// 네 개의 부동 소수점 숫자, 모두 같은 숫자입니다
// The four floating-point numbers are all the same
.0001, 0.0001, 1e-4, 1.0e-4

// 부동 소수점 숫자, 345를 의미합니다
// Floating point number 345
3.45e2

// 정수, 42를 의미합니다
// integer 42
42

// 8진수, 255를 의미합니다
// octal 255
0377

// 8진수는 소수 부분을 가질 수 없습니다. 0을 의미합니다
// An octal number cannot have a decimal part. It means 0
00.0001

// 정수, 378을 의미합니다
// integer 378
0378

// 16진수, 255를 의미합니다
// hexadecimal 255
0Xff

// 16진수, 14287을 의미합니다
// hexadecimal 14287
0x37CF

// 16진수, 999를 의미합니다
// hexadecimal 999
0x3e7

// 16진수는 소수 부분을 가질 수 없습니다. 3을 의미합니다
// Hexadecimal cannot have decimal parts. It means 3
0x3.45e2
```

<br />
### Boolean   
// 부울   
   
// 부울값은 true 이거나 false 임   
// 부울값은 특별한 값이며 1과 0으로 사용하지 않음   
- Boolean values are true or false   
- Boolean values are special values and are not used as 1 and 0   
   
```javascript
/* 
    // 비교문에서 값이 0인 표현식은 false로 간주되고, 0이 아닌 숫자로 평가되는 문장은 true로 간주됩니다. 따라서 다음식은 true 입니다.
    - In comparison statement, an expression with a value of 0 is considered false, and a statement with a nonzero number is considered true. Therefore, the following expression is true.
*/
(false == 0)
```
   
<br />
### undefined data format   
// undefined 데이터 형식   
   
// undefined 값은 변수가 작성된 후 변수에 값이 지정되기 전에 단순히 변수에 지정되는 값임   
- The undefined value is simply the value specified in the variable after the variable is created before the value is specified in the variable   
   
<br />
### null data format   
// null 데이터 형식   
   
// null 값은 아무런 값도 가지지 않으며 의미가 없음   
- null value has no value and is meaningless   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
