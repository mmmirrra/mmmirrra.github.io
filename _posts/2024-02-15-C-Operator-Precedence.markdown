---
layout: post
title:  "C: Operator Precedence"
date:   2024-02-15 09:00:00 +0900
categories: [C]
---

let md = new window.markdownit();
md.use(window.markdownitMergeCells);

let result = md.render(`
|1|1|3|4|5|
|-|-|-|-|-|
|1|1|2|2|6|
|1|1|2|2|7|
|1|4|3|5|5|
`)

|Precedence|Operator|Description|Associativity|
|:---:|:---:|:---|:---|
|1|++ --|Suffix/postfix increment and decrement|Left-to-right|
|^|()|Function call|Left-to-right|
|1|[]|Array subscripting|Left-to-right|
|1|.|Structure and union member access|Left-to-right|
|1|->|Structure and union member access through pointer|Left-to-right|
|1|(type){list}|Compound literal|Left-to-right|
|2|++ --|Prefix increment and decrement|Right-to-left|
|2|+|Unary plus|Right-to-left|
|2|-|Unary minus|Right-to-left|
|2|!|Logical NOT|Right-to-left|
|2|~|Bitwise NOT|Right-to-left|
|2|(type)|Cast|Right-to-left|
|2|*|Indirection (dereference)|Right-to-left|
|2|&|Address-of|Right-to-left|
|2|sizeof|Size-of|Right-to-left|
|2|_Alignof|Alignment requirement|Right-to-left|
|3|*|Multiplication|Left-to-right|
|3|/|Division|Left-to-right|
|3|%|Remainder|Left-to-right|
|4|+|Addition|Left-to-right|
|4|-|Subtraction|Left-to-right|
|5|&#60;&#60;|Bitwise left shift|Left-to-right|
|5|&#62;&#62;|Bitwise right shift|Left-to-right|
|6|&#60;|Relational operators <|Left-to-right|
|6|&#60;=|Relational operators ≤|Left-to-right|
|6|&#62;|Relational operators >|Left-to-right|
|6|&#62;=|Relational operators ≥|Left-to-right|
|7|==|Relational =|Left-to-right|
|7|!=|Relational ≠|Left-to-right|
|8|&|Bitwise AND|Left-to-right|
|9|^|Bitwise XOR (exclusive or)|Left-to-right|
|10|&#124;|Bitwise OR (inclusive or)|Left-to-right|
|11|&&|Logical AND|Left-to-right|
|12|&#124;&#124;|Logical OR|Left-to-right|
|13|?:|Ternary conditional|Right-to-left|
|14|=|Simple assignment|Right-to-right|
|14|+=|Assignment by sum|Right-to-right|
|14|-=|Assignment by difference|Right-to-right|
|14|*=|Assignment by product|Right-to-right|
|14|/=|Assignment by quotient|Right-to-right|
|14|%=|Assignment by remainder|Right-to-right|
|14|&#60;&#60;=|Assignment by bitwise left shift|Right-to-right|
|14|&#62;&#62;=|Assignment by bitwise right shift|Right-to-right|
|14|&=|Assignment by bitwise AND|Right-to-right|
|14|^=|Assignment by bitwise XOR|Right-to-right|
|14|&#124;=|Assignment by bitwise OR|Right-to-right|
|15|,|Comma|Left-to-right|
