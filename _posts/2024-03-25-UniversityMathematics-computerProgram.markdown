---
layout: post
title:  "University Mathematics: Mathematics and Computer Programs"
date:   2024-03-25 09:00:00 +0900
categories: [University Mathematics]
---

### CAS   
   
// 수학 문제를 코드로 풀어가는 소프트웨어   
- software for solving math problems with code   
- major program   
  - free : Maxima, SageMath   
  - paid : Mathematica, Maple, Wolflam Alpha   
   
- Maxima : Software created in 1987 based on Macsyma   
- wxMaxima : Software in the form of graphical user interfaces (GUI) to make Maxima easy to use   
   
#### wxMaxima practice   
   
```
(%i2)	3·2+5;
(%o2)	11
(%i3)	%+sqrt(2);
(%o3)	sqrt(2)+11
(%i4)	float(%);
(%o4)	12.414213562373096
(%i5)	%pi;
(%o5)	%pi
(%i6)	float(%);
(%o6)	3.141592653589793
(%i7)	float(%e);
(%o7)	2.718281828459045
(%i8)	(3·a+b)+2·(2·a-b);
(%o8)	b+2*(2*a-b)+3*a
(%i9)	ratsimp(%);
(%o9)	7*a-b
(%i10)	factor(x²-3·x+2);
(%o10)	(x-2)*(x-1)
(%i12)	limit((1+1/n)^n, n, inf);
(%o12)	%e
(%i14)	wxplot2d(%e^-x^2, [x, -5,5]);
(%t14)	 (Graphics) 
(%o14)	
(%i15)	wxplot2d(%e^(-x^2), [x, -5,5]);
(%t15)	 (Graphics) 
(%o15)	
(%i16)	wxplot2d(x^2+1, [x, -4, 4]);
(%t16)	 (Graphics) 
(%o16)	
(%i17)	load(draw);
(%o17)	"C:/maxima-5.47.0/share/maxima/5.47.0/share/draw/draw.lisp"
(%i18)	wxdraw2d(implicit(9 = x^2 + y^2, x, -6, 6, y, -4, 4));
(%t18)	 (Graphics) 
(%o18)	
(%i19)	wxdraw3d(explicit(x^2-y^2, x, -5, 5, y, -5, 5));
(%t19)	 (Graphics) 
(%o19)	
(%i20)	solve([x^2-1=0], [x]);
(%o20)	[x=-1,x=1]
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
