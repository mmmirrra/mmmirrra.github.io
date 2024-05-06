---
layout: post
title:  "JavaScript Html: html element hyperlink, img map usemap, iframe"
date:   2024-03-08 09:00:00 +0900
categories: [JavaScript Html]
---

### Elements related to hyperlink   
// 하이퍼링크와 관련된 요소   
   
<br />
### a   
   
// 하이퍼링크를 삽입하는 요소   
// 링크의 클릭을 통해 특정한 다른 위치로 이동할 때 사용   
- Elements to insert hyperlink   
- Used to move to a particular different location by clicking on a link   
   
#### Basic format   
// 기본 형식   
   
```html
<a href="Where to Move">Content to link (text, image)</a>
```
   
- href = hyper references   
   
|Property|Description|
|:---|:---|
|href="URL"|// 링크를 통해 이동하려는 곳의 경로/주소<br />- Path/url of the place you want to travel through the link|
|target="windowName"|// 링크를 클릭하였을 때 링크된 내용이 출력될 창 지정<br />// 값 : _blank (새로운창), _self (기본값, 현재창), 창이름 등<br />- Specify a window in which linked content will be output when a link is clicked<br />- Value : _blank (new window), _self (default, current window), window name, etc.|
|download|// href 속성에 지정된 파일을 다운로드해서 저장<br />- Download and save the file specified in the href property|
   
<br />
#### Basic use example of an element a   
   
// a 요소의 기본적인 사용 예제   
   
```html
<a href="http://...">Current window</a>    <!-- targert="_self" omitted -->
<br />
<a href="http://..." target="_blank">New window</a>
<br />
Click on the flower illustration 
<a href="report.hwp" download>
    <img src="flower.jpg" width="100">
</a>
to download the report document
```
   
#### Move to a specific location with id attributes   
// id 속성을 활용한 특정 위치로의 이동   
   
// 동일/다른 페이지의 특정 위치로 이동하는 경우   
// - 링크 부분   
// -- 같은 페이지 내에서 이동하는 경우   
// --- `<a href="#이동할 특정 위치의 이름">내용</a>`   
// -- 다른 페이지의 특정 위치로 이동하는 경우   
// --- `<a href="페이지경로#이동할 특정 위치의 이름">내용</a>`   
// - 이동할 특정 위치   
// -- `<a id="이동할 특정 위치의 이름">내용</a>`   
- Go to a specific location on the same/different page   
  - Link part   
    - Move within the same page   
      - `<a href="#Name of the specific location to move to">content</a>`   
    - Go to a specific location on another page   
      - `<a href="Page path#Name of the specific location to move to">content</a>`   
  - Specific locations to move to   
    - `<a id="Name of the specific location to move to">content</a>`   
   
```html
<h3>Table of Contents</h3>
<a href="#html"></a>HTML Link<br />
<a href="#css"></a>CSS Link<br />
<a href="#js"></a>JS Link<br />
<a href="html5Introduction.html#html5">HTML5 Document Link</a><br />
<br /><br />
<a id="html">HTML</a>
<p>Hyper Text Markup Language</p>
<a id="css">CSS</a>
<p>Cascading Style Sheet</p>
<a id="js">JS</a>
<p>JavaScript</p>
<!-- #top : When selected, it moves to the top of the current screen because the function called top is already promised even if id is not specified -->
<a id="#top">To the top</a>
```
   
#### Apply Source   
   
<h3>Table of Contents</h3>
<a href="#html">HTML Link</a><br />
<a href="#css">CSS Link</a><br />
<a href="#js">JS Link</a><br />
<a href="html5Introduction.html#html5">HTML5 Document Link</a><br />
<br /><br />
<a id="html">HTML</a>
<p>Hyper Text Markup Language</p>
<a id="css">CSS</a>
<p>Cascading Style Sheet</p>
<a id="js">JS</a>
<p>JavaScript</p>
<!-- #top : When selected, it moves to the top of the current screen because the function called top is already promised even if id is not specified -->
<a id="#top">To the top</a>
<br /><br />
   
#### Specify different types of links   
// 다양한 형태의 링크 지정   
   
```html
Send an email
<p><a href="mailto:adc@abc.com">Send an email</a></p><hr />

Running JavaScript Code
<p><a href="javascript:alert('Hello! World!');">Running JavaScript Code</a></p><hr />

Connecting Music Files
<p><a href="song.mp3">Connecting Music Files</a></p><hr />

Connecting a video file
<p><a href="video.wmv">Connecting a video file</a></p><hr />

Download Compressed File (Execution File)
<p><a href="files.zip">Download Compressed File (Execution File)</a></p><hr />
```
   
#### Apply Source   
   
Send an email
<p><a href="mailto:adc@abc.com">Send an email</a></p><hr />

Running JavaScript Code
<p><a href="javascript:alert('Hello! World!');">Running JavaScript Code</a></p><hr />

Connecting Music Files
<p><a href="song.mp3">Connecting Music Files</a></p><hr />

Connecting a video file
<p><a href="video.wmv">Connecting a video file</a></p><hr />

Download Compressed File (Execution File)
<p><a href="files.zip">Download Compressed File (Execution File)</a></p><hr />
<br /><br />
   
<br />
### Image Map   
   
// 이미지맵   
   
// 하나의 이미지를 여러 개의 영역으로 나누어 각 영역마다 링크를 지정하는 것   
- To divide an image into multiple regions and specify a link for each region   
   
```html
<img src="URL" usemap="#mapName1">
<map name="mapName1">
    <area
        shape="The shape of each region in the image map(default, rect, circle, poly)"
        coords="The coordinate values that make up each region"
        href="URL"
        target="Window where the link will open"
        download="Download a file designated href"
        alt="Alternate Text Content">
    <!-- 영역의 개수만큼 area 요소를 반복 사용 -->
</map>
```
   
#### Example   
   
```html
<img src="flower.jpg" width="350" usemap="#mapName2">
<map name="mapName2">
    <area
        shape="rect"
        coords="5, 5, 100, 50"
        href="http://html..."
        title="example1"
        target="_blank">
    <area
        shape="circle"
        coords="100, 100, 50"
        href="http://html..."
        title="example2"
        target="_blank">
    <area
        shape="poly"
        coords="100, 50, 230, 40, 250, 150"
        href="http://html..."
        title="example3"
        target="_blank">
</map>
```
   
<br />
### iframe   
   
// 새로운 창을 삽입하는 iframe 요소   
// 현재의 웹 페이지 안에서 다른 웹 페이지를 표시하는 창을 삽입할 때 사용   
- iframe element to insert a new window   
- Used to insert windows that display other web pages within the current web page   
   
|Property|Description|
|:---|:---|
|name="name"|// 창의 이름<br />// target 속성의 값으로 사용<br />- The name of the window<br />- Use as a value for target property|
|src="URL"|// 창에 표시될 문서의 URL<br />- The URL of the document to be displayed in the window|
|srcdoc="HTML code"|// 창에서 보여줄 HTML 콘텐츠<br />// srcdoc 속성이 지정되면 src 속성은 무시됨<br />- HTML content to show in the window<br />- When srcdoc attribute is specified, src attribute is ignored|
|width="width"|// 창의 폭 (픽셀)<br />- Window width (pixel)|
|height="height"|// 창의 높이 (픽셀)<br />- Window height (Pixel)|
   
```html
<iframe src="http://html..."
    name="view"
    width="600"
    height="300"
    srcdoc="<p>Window created with iframe elements to display other web pages within the current web page</p>"
>
<!-- 'src' attribute is ignored when 'srcdoc' attribute is added -->

<a href="http://html..." target="view">iframe</a>
<!-- When a link is selected, the link URL opens in the iframe area -->
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
