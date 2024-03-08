---
layout: post
title:  "JavaScript Html: html element image"
date:   2024-03-08 09:00:00 +0900
categories: [JavaScript Html]
---

### Elements related to image   
// 이미지와 관련된 요소   
   
### img   
// 이미지를 삽입하는 요소   
// 웹 페이지에 이미지를 삽입할 때 사용   
// - 종료태그 없이 사용   
- Elements to insert images   
- Used to insert images into web pages   
  - Available without end tag   
   
|Property|Description|
|:---|:---|
|src="URL of the file"|// (필수) 문서에 표시할 이미지 파일의 경로/이름<br />(Required) Path/Name of the image file to be displayed in the document|
|width="number"|// 이미지의 폭(픽셀, %)<br />Width of image (pixel, %)|
|height="number"|// 이미지의 높이(픽셀, %)<br />Height of the image (pixel, %)|
|alt="text"|// 이미지가 표시되지 않을 때 대체 표시될 텍스트<br />Text to be displayed as an alternative when the image is not displayed|
|usemap="#mapName"|// 클라이언트 측의 이미지 맵<br />Client side image map|
   
#### Properties of width, height   
// width, height 속성   
   
// 이미지의 폭과 높이 지정 : 기본크기 = 원본 크기   
// 값 : 픽셀, %(브라우저 화면 크기에 대한 상대적인 크기)   
// 폭과 높이 중 하나의 크기만 지정되면 나머지 하나의 값은 원본 크기에 비례해서 자동 지정   
- Specify the width and height of the image : Default Size = Source Size   
- Value: Pixel, % (relative size to browser screen size)   
- Automatically specify the other value in proportion to the original size if only one of width and height is specified   
   
#### Properties of alt   
// alt 속성   
   
// 이미지에 대해 대체 표시될 텍스트 지정   
// - 이미지 화면에 표시되지 않거나 깨지는 경우를 대비해서 사용   
- Specify the text to be displayed alternatively for the image   
  - Use it in case it doesn't show on the image screen or breaks   
   
```html
<body>
    <img src="flower.jpg"><br />
    <img src="flower.jpg" width="100" height="100">
    <img src="flower.jpg" width="100" border="1">
    <img src="flower.jpg" widht="30%" border="5">
    <img src="flower.jpg" alt="It's flower" border="3">
</body>
```
   
#### Apply Source   
`
<body>
    <img src="flower.jpg"><br />
    <img src="flower.jpg" width="100" height="100">
    <img src="flower.jpg" width="100" border="1">
    <img src="flower.jpg" widht="30%" border="5">
    <img src="flower.jpg" alt="It's flower" border="3">
</body>
`
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
