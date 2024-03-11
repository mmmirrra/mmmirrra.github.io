---
layout: post
title:  "Java: Operator Precedence"
date:   2024-03-10 09:00:00 +0900
categories: [Java]
---

### Type of Operator   
// 연산자의 종류   
   
Symbols for performing specific operations   
// 특정 연산을 수행하기 위한 기호   
   
|Type|Operator|Number of operands|Calculated value|Description|
|:---:|:---:|:---:|:---:|:---|
|arithmetic operator|+|2|number|// 덧셈 연산<br />- Addition operation|
|arithmetic operator|-|2|number|// 뺄셈 연산<br />- Subtraction operation|
|arithmetic operator|*|2|number|// 곱셈 연산<br />- Multiplication operation|
|arithmetic operator|/|2|number|// 왼쪽 피연산자를 오른쪽 피연산자로 나눗셈 연산<br />- Dividing left operand by right operand|
|arithmetic operator|%|2|number|// 왼쪽 피연산자를 오른쪽 피연산자로 나눈 나머지를 구하는 연산<br />- Operations to find the remainder of the left operand divided by the right operand|
|code operator<br />(arithmetic operator)|+|1|number|// 음수 부호 : 피연산자의 부호 유지<br />- Negative sign : Retain the sign of the operand|
|code operator<br />(arithmetic operator)|-|1|number|// 양수 부호 : 피연산자의 부호 변경<br />- Positive sign : Change the sign of the operand|
|increase operator<br />(arithmetic operator)|++operand|1|number|// 다른 연산 수행 전 1만큼 증가<br />- Increase by 1 before performing other operations|
|decrease operator<br />(arithmetic operator)|--operand|1|number|// 다른 연산 수행 전 1만큼 감소<br />- Decrease by 1 before performing other operations|
|increase operator<br />(arithmetic operator)|operand++|1|number|// 다른 연산 수행 후 1만큼 증가<br />- Increase by 1 before performing other operations|
|decrease operator<br />(arithmetic operator)|operand--|1|number|// 다른 연산 수행 후 1만큼 감소<br />- Decrease by 1 before performing other operations|
|string|+|2|character|// 두 문자를 연결<br />- Connecting two characters|
|comparison operator|a > b|2|boolean|// 피연산자a가 큰지 검사<br />- Check if operand a is large|
|comparison operator|a >= b|2|boolean|// 피연산자a가 크거나 같은지 검사<br />- Check operand a for greater or equal|
|comparison operator|a < b|2|boolean|// 피연산자a가 작은지 검사<br />- Check if operand a is small|
|comparison operator|a <= b|2|boolean|// 피연산자a가 작거나 같은지 검사<br />- Check if operand a is small or equal|
|comparison operator|==|2|boolean|// 두 피연산자의 값이 같은지 검사<br />- Check if the values of the two operands are the same|
|comparison operator|!=|2|boolean|// 두 피연산자의 값이 다른지 검사<br />- Check if the values of the two operands are the different|
|comparison operator|instanceof|2|boolean|// 값의 비교<br />- Comparison of values|
|logical operator|!|1|boolean|// 논리적 NOT 논리부정 연산 : 피연산자 논리값 변경(true->false, false->true)<br />- Logical NOT (logical denial) operation : Change operand logic value|
|logical operator|&|2|boolean|// 논리적 AND 논리곱 연산 : 피연산자 모두가 true일 경우에만 연산 결과가 true, 아니면 false<br />- Logical AND : The result of the operation is true only if all operands are true|
|logical operator|\||2|boolean|// 논리적 OR 논리합 연산 : 피연산자 중 하나만 true 이면 연산 결과는 true, 아니면 false<br />- Logical OR : If only one of the operands is true, the result of the operation is true|
|logical operator|^|2|boolean|// 논리적 XOR 배타적 논리합 연산 : 피연산자가 하나는 true이고 다른 하나가 false일 경우에만 연산 결과가 true, 아니면 false<br />- Logical XOR : The result of the operation is true only if one operand is true and the other is false|
|logical operator|&&|2|boolean|// 논리적 AND 논리곱 연산 : 피연산자 모두가 true일 경우에만 연산 결과가 true, 아니면 false<br />- Logical AND : The result of the operation is true only if all operands are true|
|logical operator|\|\||2|boolean|// 논리적 OR 논리합 연산 : 피연산자 중 하나만 true 이면 연산 결과는 true, 아니면 false<br />- Logical OR : If only one of the operands is true, the result of the operation is true|
|condition operator<br />(logical operator)|(Condition)? A value or operation function : B value or operation function|3|various|// 조건식에 따라 참이면 A, 거짓이면 B<br />- Based on the results of the conditional expression, calculate A if true and B if false|
|bit logic<br />(bit operator)|~|1|number|// 비트 NOT 논리부정 연산 : 1을 0으로, 0을 1로<br />- Bit NOT (logical denial) operation : 1 to 0 and 0 to 1|
|bit logic<br />(bit operator)|a & b|2|number|// 비트 AND 논리곱 연산 : 두 비트 모두 1이면 1, 아니라면 0<br />- Bit AND : Both bits are 1 if they are 1, and 0 if they are not|
|bit logic<br />(bit operator)|a \| b|2|number|// 비트 OR 논리합 연산 : 두 비트 모두 0이면 0, 아니라면 1<br />- Bit OR : Both bits are 0 if they are 0, and 1 if they are not|
|bit logic<br />(bit operator)|a^b|2|number|// 비트 XOR 배타적 연산 : 두 비트가 다르면 1, 같으면 0<br />- Bit XOR : If the two bits are different, it's 1 and if it's the same, it's 0|
|move the bit<br />(bit operator)|a＜＜b|2|number|// 산술적 시프트 : a의 각 비트를 b번 왼쪽으로 이동, 오른쪽 빈자리는 0으로 채움, 2를 b번 곱한 결과<br />- Arithmetic shift : Move each bit of a to the left b times, and fill the right blank with zero. The result of multiplying 2 by b times|
|move the bit<br />(bit operator)|a＞＞b|2|number|// 산술적 시프트 : a의 각 비트를 b번 오른쪽으로 이동, 왼쪽 빈자리는 최상위 부호비트와 같은 값으로 채움, 2를 b번 나눈 결과<br />- Arithmetic shift : Move each bit of a to the right b times, and fill the left blank with the same value as the most higtest code bit. The result of dividing 2 by b times|
|move the bit<br />(bit operator)|a ＞＞＞ b|2|number|// 논리적 산술적 시프트 : a의 각 비트를 b번 오른쪽으로 이동, 왼쪽 빈자리는 0으로 채움<br />- Logical Arithmetic shift : Move each bit of a to the right b times and fill the left blank with zero|
|substitution operator|+, +=, -=, *=, /=, %=, &=, ^=, \|=, ＞＞=, ＜＜=, ＞＞＞=|2|various|// 우변의 값을 좌변의 변수에 대입<br />- Substitute the value of the right variable into the left variable|
|Type conversion operator|(Data type)|1|converted data type|// 지정된 자료형으로 변환<br />- Converting to specified data type|
|etc.|[], (), .||||
   
### Operator Precedence   
// 연산자 우선 순위   
   
Operator has priority and direction of application   
// 연산자는 우선 순위가 있으며, 적용 방향이 있음   
   
|Precedence|Operator|Description|Associativity|
|:---:|:---:|:---|:---|
|1|()|parentheses|Left-to-right|
|1|[]|array access|Left-to-right|
|1|.|member access|Left-to-right|
|2|++|unary post-increment|Left-to-right|
|2|--|unary post-decrement|Left-to-right|
|3|+|unary plus|Right-to-left|
|3|-|unary minus|Right-to-left|
|3|!|unary logical NOT|Right-to-left|
|3|~|unary bitwise NOT|Right-to-left|
|3|++|unary pre-increment|Right-to-left|
|3|--|unary pre-decrement|Right-to-left|
|4|()|cast|Right-to-left|
|4|new|object creation|Right-to-left|
|5|*|multiplicative|Left-to-right|
|5|/|multiplicative|Left-to-right|
|5|%|multiplicative|Left-to-right|
|6|+|additive|Left-to-right|
|6|-|additive|Left-to-right|
|6|+|string concatenation|Left-to-right|
|7|＜＜|shift|Left-to-right|
|7|＞＞|shift|Left-to-right|
|7|＞＞＞|shift|Left-to-right|
|8|<|relational|Left-to-right|
|8|<=|relational|Left-to-right|
|8|>|relational|Left-to-right|
|8|>=|relational|Left-to-right|
|8|instanceof|relational|Left-to-right|
|9|==|equality|Left-to-right|
|9|!=|equality|Left-to-right|
|10|&|bitwise AND|Left-to-right|
|11|^|bitwise XOR|Left-to-right|
|12|\||bitwise OR|Left-to-right|
|13|&&|logical AND|Left-to-right|
|14|\|\||logical OR|Left-to-right|
|15|? :|ternary|Right-to-left|
|16|=|assignment|Right-to-left|
|16|+=|assignment|Right-to-left|
|16|-=|assignment|Right-to-left|
|16|*=|assignment|Right-to-left|
|16|/=|assignment|Right-to-left|
|16|%=|assignment|Right-to-left|
|16|&=|assignment|Right-to-left|
|16|^=|assignment|Right-to-left|
|16|\|=|assignment|Right-to-left|
|16|＜＜=|assignment|Right-to-left|
|16|＞＞=|assignment|Right-to-left|
|16|＞＞＞=|assignment|Right-to-left|
|17|->|assignment|Right-to-left|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
