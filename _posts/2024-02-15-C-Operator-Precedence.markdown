---
layout: post
title:  "C: Operator Precedence"
date:   2024-02-15 09:00:00 +0900
categories: [C]
---

|Precedence|Operator|Description|Associativity|
|:---:|:---|:---|:---|
|1|++ --<br />()<br />[]<br />.<br />-><br />(type){list}|Suffix/postfix increment and decrement<br />Function call<br />Array subscripting<br />Structure and union member access<br />Structure and union member access through pointer<br />Compound literal|Left-to-right|
|2|++ --<br />+ -<br />! ~<br />(type)<br />*<br />&<br />sizeof<br />_Alignof|Prefix increment and decrement<br />Unary plus and minus<br />Logical NOT and bitwise NOT<br />Cast<br />Indirection (dereference)<br />	Address-of<br />Size-of<br />Alignment requirement|Right-to-left|
|3|	* / %|Multiplication, division, and remainder|Left-to-right|
|4|+ -|Addition and subtraction|Left-to-right|
|5|<< >>|Bitwise left shift and right shift|Left-to-right|
|6|	< <=<br/>> >=|For relational operators < and ≤ respectively<br />For relational operators > and ≥ respectively|Left-to-right|
|7|== !=|For relational = and ≠ respectively|Left-to-right|
|8|&|Bitwise AND|Left-to-right|
|9|^|Bitwise XOR (exclusive or)|Left-to-right|
|10|&#124;|Bitwise OR (inclusive or)|Left-to-right|
|11|&&|Logical AND|Left-to-right|
|12|&#124;&#124;|Logical OR|Left-to-right|
|13|?:|Ternary conditional|Right-to-left|
|14|=<br />+= -=<br />*= /= %=<br /><<= >>=<br />&= ^= |=|Simple assignment<br />Assignment by sum and difference<br />Assignment by product, quotient, and remainder<br />Assignment by bitwise left shift and right shift<br />Assignment by bitwise AND, XOR, and OR|Right-to-left|
|15|,|Comma|Left-to-right|
