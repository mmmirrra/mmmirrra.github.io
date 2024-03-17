---
layout: post
title:  "JScript: Script Troubleshooting"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

// 어떤 프로그래밍 언어에서나 주의하지 않으면 문제가 발생하는 경우가 반드시 있고, 언어마다 이런 경우가 다름   
// null 값의 경우에도 JScript에서 null 값은 C 또는 C++ 언어에서의 null 값과 다르게 작용함   
- Problems may occur if you do not use it carefully in any programming language. This case varies from language to language   
- Even for null values, null values in JScript act differently from null values in C or C++ languages   
   
<br />
### Syntax error   
// 구문 오류   
   
// 프로그래밍 언어의 구문은 일반 언어의 구문보다 훨씬 더 엄격하기 때문에 스크립트를 쓸 때는 세부 사항에도 주의를 기울이는 것이 중요함   
// 예를 들어 특정 매개변수를 문자열로 만들려고 할 경우 매개변수를 입력한 다음 해당 매개변수를 따옴표로 묶는 것을 잊어버리면 구문 오류가 발생함   
- Because the syntax of a programming language is much more stringent than that of a regular language, it is important to pay attention to the details when writing a script   
- For example, if you try to string a particular parameter, you will get a syntax error if you enter it and then forget to quote that parameter   
   
<br />
### Order of Script Interpretation   
// 스크립트 해석 순서   
   
// JScript 해석은 웹 브라우저가 수행하는 HTML 구문 분석 과정의 일부분임   
// 그러므로 문서의 `<HEAD>` 태그 내부에 스크립트를 두면 스크립트는 어떤 `<BODY>` 태그보다도 먼저 해석됨   
// `<BODY>` 태그에서 만들어진 개체들이 있을 경우 그러한 개체들은 `<HEAD>`가 구문 분석되고 있는 시간에는 존재하지 않으며 스크립트에 의해 다루어질 수 없음   
- JScript interpretation is part of the HTML parsing process performed by a web browser   
- Therefore, if you put a script inside the `<HEAD>` tag of the document, the script will be interpreted before any `<BODY>` tag   
- If there are objects created from tags `<BODY>`, they do not exist at the time `<HEAD>` is being parsed and cannot be dealt with by scripts   
   
<br />
### Automatic Type Compulsory Conversion   
// 자동 형식 강제 변환   
   
// JScript는 자동적인 강제 변환이 가능한 비교적 자유로운 형식의 언어임   
// 따라서 아래 예시의 식에서 다른 형식을 가진 값들이 같지 않지만 결과는 true 임   
- JScript is a relatively free-form language with automatic forced conversion   
- Therefore, values with different formats are not the same in the equation in the example below, but the result is true   
   
```javascript
"100" == 100
false == 0
```
   
<br />
### Operator Precedence   
// 연산자 우선 순위   
   
// 특정 연산을 수행할 때 식 계산은 식의 위치보다 연산자 우선 순위와 더 깊은 관련이 있음   
// 따라서 아래 예시에서 뺄셈이 먼저 나와있지만 연산자 우선 순위에 따라 곱셈이 뺄셈보다 먼저 수행됨   
- When performing certain operations, expression calculations are more closely related to operator precedence than to the position of the expression   
- Therefore, subtraction is shown first in the example below, but multiplication is performed before subtraction according to operator precedence   
   
```javascript
theRadius = aPerimeterPoint - theCenterpoint * theCorrectionFactor;
```
   
<br />
### Use objects and for...in loops together   
// 개체와 for...in 루프를 함께 사용   
   
// for...in 루프를 사용하여 개체의 속성을 단계적으로 작업할 경우 개체 필드가 루프 카운터 변수에 지정되는 순서를 예상하거나 제어할 필요는 없음   
// 게다가 다른 언어 구현에서는 그 순서가 달라질 수도 있음   
- When working on an object's properties stepwise with a for...in loop, it is not necessary to anticipate or control the order in which the object fields are assigned to the loop counter variable   
- In addition, the order may vary in other language implementations   
   
<br />
### with Keyword   
// with 키워드   
   
// with문은 지정된 개체에 이미 존재하는 속성을 처리하는 데는 편리하지만, 속성을 개체에 추가하는데 사용할 수는 없음   
// 개체에서 새로운 속성을 만들려면 개체를 구체적으로 참조해야 함   
- With statements are convenient to handle attributes that already exist in a given object, but they cannot be used to add attributes to an object   
- To create a new property in an object, you must specifically reference the object   
   
<br />
### this Keyword   
// this 키워드   
   
// 개체 자체를 참조하기 위하여 개체 정의의 내부에는 this 키워드를 사용할 수 있지만, 해당 함수가 개체 정의가 아닐 경우 일반적으로 this 키워드 또는 이와 유사한 키워드를 사용하여 현재 실행되고 있는 함수를 참조할 수 없음   
// 함수를 하나의 메서드로 개체에 지정하면 개체를 참조하기 위하여 this 키워드를 함수 내부에서 사용할 수 있음   
- To refer to the object itself, you can use this keyword inside the object definition. However, if the function is not an object definition, it is generally impossible to refer to the currently running function using this keyword or similar keyword   
- Specifying a function to an object as a method allows the use of this keyword inside the function to reference the object   
   
<br />
### Writing scripts to create scripts   
// 스크립트를 작성하는 스크립트 쓰기   
   
// 해석기가 `</SCRIPT>` 태그와 마주치게 되면 이 태그는 현재의 스크립트를 종료시킴   
// `</SCRIPT>` 자체를 나타내려면 이것을 `</SCR`과 `IPT>`와 같이 2개 이상의 문자열로 다시 써야 함   
// 그러면 이 문자열을 사용하는 문에서 2개의 문자열 `</SCR`과 `IPT>`을 연결할 수 있음   
- When the interpreter encounters the tag `</SCRIPT>`, it ends the current script   
- To represent `</SCRIPT>` itself, it must be rewritten with two or more strings, such as `</SCR` and `IPT>`   
- The statement using this string can then connect two strings `</SCR` and `IPT`   
   
<br />
### Implicit window reference   
// 함축적인 창 참조   
   
// 창은 동시에 두 개 이상 열릴 수 있기 때문에 명시적으로 창 참조를 나타내지 않는 한 모두 현재의 창을 가리키게 됨   
// 현재의 창이 아닌 다른 창에 대해서는 명시적 참조를 사용해야 함   
- Because more than one window can be opened at the same time, all point to the current window unless explicitly representing a window reference   
- Explicit references should be used for windows other than the current window   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
