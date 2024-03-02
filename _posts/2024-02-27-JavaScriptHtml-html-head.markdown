---
layout: post
title:  "JavaScript Html: html head"
date:   2024-02-27 09:00:00 +0900
categories: [JavaScript Html]
---

### Meta elements included in the head   
// 헤드 부분에 포함되는 메타 요소   
   
### title   
// 브라우저 상단(탭)에 문서의 제목을 표시할 때 사용   
// 즐겨찾기 제목, 검색 엔진의 출력된 결과 페이지 제목으로도 사용   
- Use to display the title of a document at the top of your browser (tab)   
- Favorite title, also used as the title of the results page printed by the search engine   
   
### link   
// CSS 스타일 파일(*.css)을 가져와 웹 문서에 적용할 때 사용   
// 문서의 body 부분에 포함 가능   
- Used to import and apply CSS-style files (*.css) to web documents   
- Can be included in body part of document   
   
```html
<link rel="stylesheet" href="fileName.css">
``` 
   
### style   
// 웹 문서 전체에 적용할 CSS 스타일을 정의할 때 사용   
Use to define the CSS style to apply to the entire web document   
   
```html
<style>
    Define CSS Style (Example : h1{color: red;})
</style>
```
   
### script   
// 자바스크립트 코드를 작성(또는 외부 코드 링크)할 때 사용   
// 바디 부분에 포함 가능   
- Used to write JavaScript code (or link external code)   
- Can be included in body   
   
```html
<script>
    javaScript code
</script>
```
   
```html
<script src="fileName.js"></script>
```
   
### meta   
// 웹 문서에 대한 다양한 메타 데이터를 나타낼 때 사용   
Used to represent different metadata for web documents   
   
- Character encoding method   
   
```html
<meta charset="UTF-8">
```
- Description
   
```html
<meta name="description" content="...">
```
   
- Keywords
   
```html
<meta name="keywords" content="keyword1, keyword2, ...">
```
   
- Author   
   
```html
<meta name="author" content="Author Name">
```
   
### base   
// 1. 웹 문서의 기본 URL 경로 지정   
// - body 요소 내의 상대 경로로 표시된 URL을 절대 경로로 취급   
1. Specify the default URL path for a Web document   
  - Treat URLs marked as relative paths within body elements as absolute paths   
   
```html
<base href="http://abc.com">
<body>
  <a href="ex.html"> ----> <a href="http://abc.com/ex.html">
</body>
```
   
// 2. 웹 페이지가 출력될 타깃 윈도우 지정   
 2. Specify the target window to which the web page will be printed   
   
```html
<base target="_blank">
<body>
  <a href="ex.html"> ----> Open in a new window
</body>
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
