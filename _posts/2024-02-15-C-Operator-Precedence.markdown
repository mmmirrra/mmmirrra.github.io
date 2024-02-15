---
layout: post
title:  "C: Operator Precedence"
date:   2024-02-15 09:00:00 +0900
categories: [C]
---

[cols="^,^,^,^"]
|===
|Precedence |Operator |Description |Associativity
|:---: |:---: |:--- |:---

.6+^|1 |++ -- |Suffix/postfix increment and decrement |Left-to-right
|() |Function call |Left-to-right
|[] |Array subscripting |Left-to-right
|. |Structure and union member access |Left-to-right
|-> |Structure and union member access through pointer |Left-to-right
|(type){list} |Compound literal |Left-to-right
.10+^|2 |++ -- |Prefix increment and decrement |Right-to-left
|+ |Unary plus |Right-to-left
|- |Unary minus |Right-to-left
|! |Logical NOT |Right-to-left
|~ |Bitwise NOT |Right-to-left
|(type) |Cast |Right-to-left
|* |Indirection (dereference) |Right-to-left
|& |Address-of |Right-to-left
|sizeof |Size-of |Right-to-left
|_Alignof |Alignment requirement |Right-to-left
.3+^|3 |* |Multiplication |Left-to-right
|/ |Division |Left-to-right
|% |Remainder |Left-to-right
.2+^|4 |+ |Addition |Left-to-right
|- |Subtraction |Left-to-right
.2+^|5 |&#60;&#60; |Bitwise left shift |Left-to-right
|&#62;&#62; |Bitwise right shift |Left-to-right
.4+^|6 |&#60; |Relational operators < |Left-to-right
|&#60;= |Relational operators ≤ |Left-to-right
|&#62; |Relational operators > |Left-to-right
|&#62;= |Relational operators ≥ |Left-to-right
.2+^|7 |== |Relational = |Left-to-right
|!= |Relational ≠ |Left-to-right
|8 |& |Bitwise AND |Left-to-right
|9 |^ |Bitwise XOR (exclusive or) |Left-to-right
|10 |&#124; |Bitwise OR (inclusive or) |Left-to-right
|11 |&& |Logical AND |Left-to-right
|12 |&#124;&#124; |Logical OR |Left-to-right
|13 |?: |Ternary conditional |Right-to-left
.11+^|14 |=|Simple assignment |Right-to-right
|+= |Assignment by sum |Right-to-right
|-= |Assignment by difference |Right-to-right
|*= |Assignment by product |Right-to-right
|/= |Assignment by quotient |Right-to-right
|%= |Assignment by remainder |Right-to-right
|&#60;&#60;= |Assignment by bitwise left shift |Right-to-right
|&#62;&#62;= |Assignment by bitwise right shift |Right-to-right
|&= |Assignment by bitwise AND |Right-to-right
|^= |Assignment by bitwise XOR |Right-to-right
|&#124;= |Assignment by bitwise OR |Right-to-right
|15 |, |Comma |Left-to-right
|===
