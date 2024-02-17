---
layout: post
title:  "C: Storage Class"
date:   2024-02-17 09:00:00 +0900
categories: [C]
---

storage class : How to assign a variable to a specific area of storage space   
   
#### Depending on where the variable is used   
 - local variable   
 - global variable   
   
#### Depending on the initialization, duration and range of validity of the variable   
 : Example of use : storageClass datatype variable;
 - 'auto' // 자동변수 : auto int a; : Created at the execution of the function, and removed storage space at the end of the execution. You can skip "auto". It's a local variable. Initialization required   
 - 'static' // 정적변수 : static int b;   
 - 'extern' // 외부변수 : extern int c;   
 - 'register' // 레지스터변수 : register int d;   



|type|Example of use|Description|
|:---|:---|:---|
|auto<br />// 자동변수|auto int a|Created at the execution of the function, and removed storage space at the end of the execution.<br />You can skip "auto".<br />It's a local variable.<br />Initialization required|
|stdio.h|File related Functions|fopen(), fclose(), fprintf(), ...|
|conio.h|Console Input/Output Function|putch(), cputs(), cprintf(), getch(), getche(), cscanf(), ...|
|string.h|String processing Function|strcat(), strcmp(), strcpy(), strlen(), strncat(), strncpy(), ...|
|math.h|Mathematical Function|sqrt(), sin(), cos(), tan(), log(), exp(), pow(), abs(), asin(), acos(), atan(), cosh(), ...|
|ctype.h|Character form discrimination Function|isalpha(), isdigit(), islower(), ...|
|ctype.h|Character conversion Function|tolower(), toupper()|
|stdlib.h|Numerical transformation Function|atoi(), itoa()|
|stdlib.h|Function related to Random Number|rand(), srand()|
|stdlib.h|Sort/Alignment/Search Function|qsort(), lfind()|
