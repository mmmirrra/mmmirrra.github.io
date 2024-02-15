---
layout: post
title:  "C: Operator Precedence"
date:   2024-02-15 09:00:00 +0900
categories: [C]
---

|Pre<br />cedence|Operator|Description|Associativity|
|:---:|:---|:---|:---|
|1|++ --<br />()<br />[]<br />.<br />-><br />(type){list}|Suffix/postfix increment and decrement<br />Function call<br />Array subscripting<br />Structure and union member access<br />Structure and union member access through pointer<br />Compound literal|Left-to-right|
|2|++ --<br />+<br />-<br />!<br />~<br />(type)<br />*<br />&<br />sizeof<br />_Alignof|Prefix increment and decrement<br />Unary plus<br />Unary minus<br />Logical NOT<br />Bitwise NOT<br />Cast<br />Indirection (dereference)<br />	Address-of<br />Size-of<br />Alignment requirement|Right-to-left|
|3|*<br />/<br />%|Multiplication<br />Division<br />Remainder|Left-to-right|
|4|+<br />-|Addition<br />Subtraction|Left-to-right|
|5|&#60;&#60;<br />&#62;&#62;|Bitwise left shift<br />Bitwise right shift|Left-to-right|
|6|&#60;<br/>&#60;=<br/>&#62;<br/>&#62;=|Relational operators < <br />Relational operators ≤ <br />Relational operators > <br />Relational operators ≥ |Left-to-right|
|7|== <br />!=|Relational = <br />Relational ≠ |Left-to-right|
|8|&|Bitwise AND|Left-to-right|
|9|^|Bitwise XOR (exclusive or)|Left-to-right|
|10|&#124;|Bitwise OR (inclusive or)|Left-to-right|
|11|&&|Logical AND|Left-to-right|
|12|&#124;&#124;|Logical OR|Left-to-right|
|13|?:|Ternary conditional|Right-to-left|
|14|=<br />+=<br />-=<br />*=<br />/=<br />%=<br />&#60;&#60;=<br />&#62;&#62;=<br />&=<br />^=<br />&#124;=|Simple assignment<br />Assignment by sum<br />Assignment by difference<br />Assignment by product<br />Assignment by quotient<br />Assignment by remainder<br />Assignment by bitwise left shift<br />Assignment by bitwise right shift<br />Assignment by bitwise AND<br />Assignment by bitwise XOR<br />Assignment by bitwise OR|Right-to-left|
|15|,|Comma|Left-to-right|
