---
layout: post
title:  "JavaScript Html: html element list - ul, ol, dl"
date:   2024-03-08 09:00:00 +0900
categories: [JavaScript Html]
---

### Elements related to list   
// 리스트와 관련된 요소   
   
|Type|Description|
|:---|:---|
|// 순서 없는 리스트<br />unordered list|// - 글머리기호(·)를 붙여 리스트의 항목을 표시<br />// - 사용 요소 : ul ~ li<br />- Display items in the list with bullet points (·)<br />- Using Elements : ul ~ li|
|// 순서 있는 리스트<br />ordered list|// - 순서(1, 2, 3)를 매겨서 리스트의 항목을 표시<br />// - 사용 요소 : ol ~ li<br />- Show items in the list in order (1, 2, 3)<br />- Using Elements : ol ~ li|
|// 서술 리스트<br />description list|// - 어떤 용어나 이름에 대해서 서술하는 형식<br />// - 사용 요소 : dl ~ dt/dd<br />- A form of description of a term or name<br />- Using Elements : dl ~ dt/dd|
   
<br />
### ul   
   
// 순서 없는 리스트를 지정 : 각 항목 앞에 순서를 나타내지 않는 기호를 붙여서 표시   
// 기호 변경 : CSS list-style-type 속성   
- Specify an unordered list : Mark each item with an unordering symbol before it   
- Symbol Change : CSS list-style-type property   
  - Type of 'list-style-type' : none, disc(●), circle(○), square(■)   
   
```html
<ul>
    <li>item 1</li>
    <li>item 2</li>
    ...
    <li>item n</li>
</ul>
```
   
#### Apply Source   
`
<ul>
    <li>item 1</li>
    <li>item 2</li>
    ...
    <li>item n</li>
</ul>
`
   
<br />
### li   
   
// ul, ol 요소 내에서 공통으로 사용되는 자식 요소   
// 리스트에서 각 항목의 내용을 표시할 때 사용   
// - 들여쓰기   
// - 자동 줄바꿈   
// - 종료태그 없이 사용 가능   
- Common child elements within ul, ol elements   
- Used to display the contents of each item in the list   
  - Indentation   
  - Automatically change the line   
  - Available without end tag   
   
```html
<body>
    <h3>Unordered List</h3>
    <ul>
        <li>item 1
        <li>item 2
        ...
        <li>item n
    </ul>
</body>
```
   
#### Apply Source   
`
<body>
    <h3>Unordered List</h3>
    <ul>
        <li>item 1
        <li>item 2
        ...
        <li>item n
    </ul>
</body>
`
   
<br />
### ol   
   
// 순서 있는 리스트를 지정 : 각 항목 앞에 순서를 나타내는 기호를 붙여서 표시   
// 순서 있는 기호 : 숫자(기본값), 영문자, 로마자 등   
- Specify an ordered list : Mark each item with an order symbol before it   
- An ordered symbol : Numbers (default), English characters, Roman characters, etc.   
   
```html
<ol>
    <li>item 1</li>
    <li>item 2</li>
    ...
    <li>item n</li>
</ol>
```
   
#### Apply Source   
`
<ol>
    <li>item 1</li>
    <li>item 2</li>
    ...
    <li>item n</li>
</ol>
`
   
#### Properties of ol Elements   
// ol 요소의 속성   
   
// type= value" : 순서가 부여된 기호의 유형 지정   
// start="number" : 항목의 시작 번호 지정   
// reversed : 항목의 번호를 역순으로 지정   
- type="value" : Specify the type of ordered symbol   
  - Type of 'value' : 1(1, 2, 3, 4, ...(default)), a(a, b, c, d, ...), A(A, B, C, D, ...), ⅰ(ⅰ, ⅱ, ⅲ, ⅳ, ...), Ⅰ(Ⅰ, Ⅱ, Ⅲ, Ⅳ, ...)   
- start="number" : Specify the starting number of the item   
- reversed : Number items in reverse order   
   
#### Properties of li elements within ol elements   
// ol 요소 내의 li 요소의 속성   
   
// value="number" : 항목 번호를 중간에 바꿀 때 사용   
// - ol 요소 내의 li 에서만 사용됨   
- value="number" : Used to change item numbers in between   
  - Only used in li within ol element   
   
```html
<body>
    <h3>ordered List</h3>
    <ol reversed>
        <li>item 1
        <li>item 2
        ...
        <li>item n
    </ol>
</body>
```
   
#### Apply Source   
`
<body>
    <h3>ordered List</h3>
    <ol reversed>
        <li>item 1
        <li>item 2
        ...
        <li>item n
    </ol>
</body>
`
   
```html
<body>
    <h3>Characteristics of elements</h3>
    <ol type="a" start="2">
        <li>item 1
        <li value="6">item 2
        ...
        <li>item n
    </ol>
</body>
```
   
#### Apply Source   
`
<body>
    <h3>Characteristics of elements</h3>
    <ol type="a" start="2">
        <li>item 1
        <li value="6">item 2
        ...
        <li>item n
    </ol>
</body>
`
   
<br />
### dl   
   
// 용어/이름을 정의하고, 이에 대한 설명을 제공하는 리스트   
- A list that defines a term/name and provides an explanation for it   
   
#### dt   
// dt 요소 : 용어/이름을 나열   
// - 자동 줄바꿈   
- dt : List terms/names   
  - Automatically change the line   
   
#### dd   
// dd 요소 : 나열된 용어/이름에 대한 설명을 제공할 때 사용   
// - 자동 줄바꿈   
// - 자동 들여쓰기   
- dd : Used to provide a description of the terms/names listed   
  - Automatically change the line   
  - Automatic indentation    
   
```html
<dl>
    <dt>name 1</dt>
    <dd>description 1</dd>
    <dt>name 2</dt>
    <dd>description 2</dd>
    ...
    <dt>name n</dt>
    <dd>description n</dd>
</dl>
```
   
#### Apply Source   
`
<dl>
    <dt>name 1</dt>
    <dd>description 1</dd>
    <dt>name 2</dt>
    <dd>description 2</dd>
    ...
    <dt>name n</dt>
    <dd>description n</dd>
</dl>
`
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
