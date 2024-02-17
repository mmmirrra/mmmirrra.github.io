---
layout: post
title:  "C: Conversion Character"
date:   2024-02-13 09:00:00 +0900
categories: [C]
---

|Conversion Character|Displays Argument (Variable’s Contents) As|
|:---|:---|
|%c<br />%C|Single character|
|%d|Signed decimal integer (int)|
|%e<br />%E|Signed floating-point value in E notation|
|%f|Signed floating-point value (float)|
|Example %5.2f|Total digits are printed up to 5 digits, decimal places up to 2 digits|
|%g<br />%G|Signed value in %e or %f format, whichever is shorter (auto)|
|%i|Signed decimal integer (int)|
|%o|Unsigned octal (base 8) integer (int)|
|%s|String of text|
|%u|Unsigned decimal integer (int)|
|%x|Unsigned hexadecimal (base 16) integer (int) - 'a' ~ 'f'|
|%X|Unsigned hexadecimal (base 16) integer (int) - 'A' ~ 'F'|
|%p|Address value of the pointer - hexadecimal (base 16)|
|%%|(percent character)|
