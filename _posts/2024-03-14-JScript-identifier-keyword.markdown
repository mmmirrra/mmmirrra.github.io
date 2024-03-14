---
layout: post
title:  "JScript: Identifier, Keyword"
date:   2024-03-14 09:00:00 +0900
categories: [JScript]
---

### JScript reservation word   
// JScript 예약어   
   
// JScript에는 여러 개의 예약어가 있음   
// 이들 단어는 JScript 예약어, 예비 예약어, 그리고 피해야 할 단어 등 세 종류로 나뉨   
- JScript has multiple reserved words   
- These words are divided into three types: JScript reserved words, preliminary reserved words, and words to avoid   
   
### JScript keywords   
// JScript 키워드   
   
```javascript
break   false   in  this    void
continue    for     new     true    while
delete  function    null    typeof  with
else    if  return  var
```
   
### JScript preliminary keywords   
// JScript 예비 키워드   
   
```javascript
case    debugger    export  super
catch   default     extends     switch
class   do      finally     throw
const   enum    import  try
```
   
### a word to avoid   
// 피해야 할 단어   
   
// JScript 내부 개체나 함수의 이름 등 이미 있는 이름은 모두 피해야 할 단어에 속함   
// String이나 parseInt와 같은 단어도 여기에 해당함   
- Any name that already exists, such as the name of an object or function inside JScript, belongs to a word to avoid   
- Words like String and paradeInt also apply to this   
   
// 처음 두 가지 범주에서 키워드를 사용하면 스크립트를 처음 로드할 때 컴파일 오류가 발생함   
// 세번째 범주에 해당하는 예약어를 사용하면 같은 스크립트에서 이름이 같은 변수와 원래 항목을 모두 사용하려고 할 때 동작에 이상을 일으킬 수 있음   
// 예를 들어 다음과 같은 스크립트는 예기치 못한 결과를 나타냄   
- Using keywords in the first two categories results in compilation errors when first loading the script   
- Using a third category of reserved words might cause behavior problems when trying to use both variables and original items with the same name in the same script   
- For example, the following script shows unexpected results   
   
```javascript
var String;
var text = new String("String object");
```
   
// 이 경우에는 String이 개체가 아니라는 내용의 오류 메시지가 표시됨   
// 대부분의 경우 기존의 식별자를 사용하면 이와 같이 명확하지 않음   
- In this case, an error message indicating that the String is not an object is displayed   
- In most cases, using an existing identifier is not as clear as this   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
