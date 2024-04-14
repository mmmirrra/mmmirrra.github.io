---
layout: post
title:  "JScript: Special Character"
date:   2024-03-15 09:00:00 +0900
categories: [JScript]
---

// JScript는 직접 입력할 수 없는 문자를 문자열에 포함시킬 수 있는 특수 문자를 제공함   
// 각 특수 문자는 백슬래시로 시작함   
// 백슬래시는 다음 문자가 특수문자임을 JScript 해석기에 알려주는 데 사용되는 제어문자임   
- JScript provides special characters that can include characters that cannot be entered directly into a string   
- Each special character begins with a backslash   
- Backslash is a control character used to inform the JScript interpreter that the following characters are special characters   
   
|// 제어 시퀀스<br />Control Sequence|// 문자<br />Charactor|
|:---|:---|
|\b|Backspace|
|\f|Paper Supply|
|\n|Change the line|
|\r|Carriage Return|
|\t|Horizontal Tab(Ctrl-I)|
|\'|single quotation marks|
|\"|double quotation marks|
|\ \ |Backslash|
   
// 백슬래시 자체는 제어문자로 사용되므로 스크립트에서 직접 입력할 수 없음   
// 백슬래시를 사용하려면 두 번 입력해야 함 (\ \ )   
- Backslash itself is used as a control character and cannot be entered directly from the script   
- To use a backslash, type twice (\ \ )   
   
```javascript
document.write('The image path is C:\\webstuff\\mypage\\gifs\\garden.gif');
document.write('The caption is "After the snow of \'. Grandma\'s house is covered."');
```
   
// 이들 제어 시퀀스를 사용하면 `<PRE>` 태그와 `<XMP>` 태그 내부의 텍스트 서식을 제어할 수 있으며 내부경고, 프롬프트 및 확인 메시지 상자 내부의 텍스트 서식도 어느 정도 제어할 수 있음   
- Using these control sequences, you can control the `<PRE>` tag and the text format inside the `<XMP>` tag. Some control over text formatting inside internal alerts, prompts, and confirmation message boxes   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
