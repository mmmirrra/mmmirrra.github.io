---
layout: post
title:  "JScript: Operator Precedence"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

### Type of Operator   
// 연산자의 종류   
   
// JScript에서는 산술, 논리, 비트 및 지정 연산자와 같은 모든 범위의 연산자 뿐만 아니라 기타 연산자들도 사용할 수 있음   
- JScript allows you to use a full range of operators, such as arithmetic, logic, bits, and designated operators, as well as other operators   
   
|Type|Operator|Description|
|:---:|:---:|:---:|
|arithmetic operator|-|1 term, Not|
|arithmetic operator|++|Increase|
|arithmetic operator|--|Decrease|
|arithmetic operator|*|Multiplication|
|arithmetic operator|/|Division|
|arithmetic operator|%|Remainder|
|arithmetic operator|+|Addtion|
|arithmetic operator|-|Subtraction|
|logical operator|!|Logical NOT|
|logical operator|<|Check if operand is small|
|logical operator|>|Check if operand is large|
|logical operator|<=|Check if operand is smaller or equal|
|logical operator|>=|Check operand for greater or equal|
|logical operator|==|Relational = : Check if the values of the two operands are the same|
|logical operator|!=|Relational ≠ : Check if the values of the two operands are the differen|
|logical operator|&&|Logical AND|
|logical operator|\|\||Logical OR|
|logical operator|? A : B|Based on the results of the conditional expression, calculate A if true and B if false (trinomial)|
|logical operator|,|Comma|
|logical operator|===|Equivalence|
|logical operator|!==|Not Equivalence|
|bit operator|~|Bit NOT|
|bit operator|＜＜|Move the bit to the left|
|bit operator|＞＞|Move the bit to the right|
|bit operator|＞＞＞|Move right without sign|
|bit operator|&|Bit AND|
|bit operator|∧|Bit XOR|
|bit operator|\||Bit OR|
|specified operator|=|Assignment|
|specified operator|OP=|Compound Assignment|
|etc. operator|delete|Delete|
|etc. operator|typeof|Type|
|etc. operator|void|No return value|
   
<br />
### Operator Precedence   
// 연산자 우선 순위   
   
// JScript에서 사용되는 연산자들은 일정한 순서에 의해 실행되는데 이러한 순서를 연산자 우선순위라고 함   
// 같은 줄에 있는 연산자들은 왼쪽에서 오른쪽 순서로 계산됨   
// 괄호는 계산 순서를 바꾸기 위해 사용함. 괄호 안에 있는 식은 완전히 계산된 다음에 문의 다른 부분에서 사용됨   
// 우선순위가 높은 연산자들은 우선순위가 낮은 연산자들보다 먼저 계산됨   
- Operators used in JScript are executed in a given order, which is called operator precedence   
- Operators in the same row are calculated in order of left to right   
- Parentheses are used to change the order of calculation. The expression in parentheses is fully calculated and then used in other parts of the statement   
- Higher-precedence operators are computed before lower-precedence operators   
   
`z = 78 * (96 + 3 + 45)`   
// 이 식에서 =, *, (), +, + 라는 다섯 개의 연산자가 존재함   
// 이 연산자들은 연산자 우선 순위에 따라 (), *, +, +, = 의 순서로 계산됨   
// 1. 괄호 안에 있는 연산자가 먼저 계산됨. 괄호 안에 있는 두 개의 덧셈 연산자는 동일한 우선 순위를 가지므로 먼저 96에 3을 더하고 그 값에 다시 45가 더해져서 값은 144가 됨   
// 2. 그 다음에 곱셈 연산이 수행됨. 즉 78과 144가 곱해져서 11232가 됨   
// 3. 마지막으로 지정 연산이 수행되어 11232라는 값이 z에 지정됨   
   
`z = 78 * (96 + 3 + 45)`   
- There are five operators in this equation : =, *,(), +, +   
- These operators are calculated in the order of (), *, +, +, = based on operator precedence   
1. The operator in parentheses is calculated first. Because the two addition operators in parentheses have the same precedence, they first add 96, then add 3, and then add 45, so the value is 144   
2. Multiplication operations are then performed. That is, 78 and 144 are multiplied to 11232   
3. Finally, a specified operation is performed, with the value 11232 specified in z   
   
|Precedence|Operator|Description|
|:---:|:---:|:---|
|1|. [] ()|// 필드 엑세스, 배열 인덱스, 함수 호출<br />Field Access, Array Index, Function Call|
|2|++ -- - ~ ! typeof new void delete|// 단일 연산자, 데이터 형식 변환, 개체 작성, 정의되지 않은 값<br />Single Operator, Data Format Conversion, Object Creation, Undefined Value|
|3|* / %|// 곱셈, 나눗셈, 나머지 연산<br />Multiplication, Division, and the Remainder of the Operation|
|4|+ - +|// 덧셈, 뺄셈, 문자열 연결<br />Addtion, Subtraction, String Association|
|5|＜＜ ＞＞ ＞＞＞|// 비트 이동<br />Move the Bit|
|6|< <= > >=|// 보다 작다, 작거나 같다, 보다 크다, 크거나 같다<br />Small, Smaller or Equal, Large, Greater or Equal|
|7|== != === !==|// 같음, 같지 않음, 동치, 동치가 아님<br />Equal, Not the Equal, Equivalent, Not Equivalent|
|8|&|// 비트 논리곱<br />Bit AND|
|9|∧|// 비트 배타적 논리합<br />Bit XOR|
|10|\||// 비트 논리합<br />Bit OR|
|11|&&|// 논리곱<br />Logical AND|
|12|\|\||// 논리합<br />Logical OR|
|13|? A : B|// 조건<br />Based on the results of the conditional expression, calculate A if true and B if false (trinomial)|
|14|= OP=|// 지정, 복합 지정<br />Assignment, Compound Assignment|
|15|,|// 다중 연산<br />Comma|
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
