---
layout: post
title:  "Html CSS JavaScript: html structure"
date:   2024-02-26 09:00:00 +0900
categories: [Html CSS JavaScript]
---

### Components of HTML documents   
// HTML 문서의 구성 요소   
   
#### HTML documents   
// HTML 문서 : 다양한 요소들의 조합   
A combination of various elements   
   
elements == Start Tag + Content + End Tag   
   
```html
<!-- Start Tag == <tagName propertyName="propertyValue" ...> -->
<!-- Content == content -->
<!-- End Tag == </tagName> -->
<!-- Property == propertyName="propertyValue" -->
<tagName propertyName="propertyValue" ...>content</tagName>

<!-- Example -->
<p>HTML5</p>
<a href="abc.com" target=_blank>abc</a>
```
   
Tags used without end tags : `<br>`, `<img>`, etc.   
   
<br />
### Guidelines for Writing HTML Documents   
// HTML 문서 작성 시 주의사항   
   
// 요소명과 속성명은 대소문자를 구분하지 않음   
// - 소문자 표기를 권고   
- The element name and property name are not case sensitive   
  - Lowercase characters recommended   
  - `<TITLE> == <Title> == <title>`   
   
// 파일명 지정 : '파일명.htm' 또는 '파일명.html'   
- File name specification : 'fileName.htm' or 'fileName.html'   
   
// 화이트스페이스는 입력한 의도대로 적용되지 않음   
// - 두 칸 이상의 연속된 공백은 하나의 공백으로 처리됨   
- Whitespace does not apply as intended   
  - Two or more consecutive spaces are treated as one space   
   
// 요소 안에 다른 요소 포함 가능 : 포함 관계 주의   
- Possible inclusion of other elements within an element : Care must be taken in the inclusion relationship   
  - `<tag1> ... <tag2> ~~ </tag2> ... </tag1>`   
   
<br />
### Basic structure of HTML documents   
// HTML 문서의 기본 구조   
   
```html
<!DOCTYPE html>
<html>
  <head>
    document title, meta data, javaScript, CSS (style, link), etc.
  </head>
  <body>
    The body content of the document (text, image, link, table, etc.)
    javaScript insertable
  </body>
</html>
```
   
```html
<!DOCTYPE html>
<!-- 
  // 브라우저에게 페이지를 올바르게 표시할 수 있도록 문서 형식을 알려주는 지시어
  // 반드시 첫 줄에 위치
  - Instructions that tell the browser the type of document so that the page can be displayed correctly
  - Must be located in the first line 
-->
```
   
```html
<html> ... </html>
<!-- 
  // 웹 페이지의 루트 요소 : HTML 문서의 시작과 끝을 알려줌
  - Web page root element : Indicates the start and end of HTML documents
-->
```
   
```html
<head> ... </head>
<!-- 
  // 웹 문서에 대한 메타 정보를 포함 : 화면에 표시되지 않음
  - Include meta information for web documents : Not displayed on screen
  - meta information : title, link, style, script, meta, base, etc.
-->
```
   
```html
<body> ... </body>
<!-- 
  // 브라우저 화면에 실제로 출력해서 보여주려는 문서의 본문에 해당하는 모든 내용을 포함하는 부분 
  - The part that contains all the content that corresponds to the body of the document you want to actually show on the browser screen
-->
```
   
```html
<!-- -->
<!-- 
  // 주석문 : 문서 소스 내에 간단한 설명을 추가할 때 사용
  // 브라우저에 출력되지 않으므로 소스에서만 확인 가능
  // 문서의 어느 곳에든 위치 가능
  // '<! --'와 '-- >'는 하나의 문자임 : 각 문자 사이에 공백 불가
  // 주석 내용으로 '<', '>', '--'는 사용하지 말아야 함
  - Comment : Used to add a brief description within a document source
  - Not output to browser so can only be seen by source
  - Can be located anywhere in the document
  - '<! --' and '-- >' are one character : No spaces between each character
  - '<', '>', '--' should not be used for comment
-->
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
