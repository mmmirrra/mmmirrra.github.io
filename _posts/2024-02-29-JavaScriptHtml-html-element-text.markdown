---
layout: post
title:  "JavaScript Html: html element text"
date:   2024-02-29 09:00:00 +0900
categories: [JavaScript Html]
---

### Elements related to text   
// 텍스트와 관련된 요소   
   
// 줄 바꾸기 : 종료태그 없이 사용 가능. 편집기에서 엔터키와 동일   
`<br>` : Change the line. Available without end tag. It's the same function as the Enter key in the editor   
   
// 단락 나눔 : 문단을 나누어 독립된 단락을 생성. 단락 구분을 위해 단락 전후에 빈 줄이 자동으로 추가됨. 여러 번 사용해도 한 번 사용한 것과 같은 효과를 가짐   
`<p>...</p>` : Divide paragraphs to create independent paragraphs. Empty lines are automatically added before and after paragraphs to distinguish paragraphs. Multiple uses have the same effect as a single use   
   
// 수평선 그림 : 주제가 변경되는 콘테츠를 구분하는 용도. 자동 줄바꿈됨. 종료태그 없이 사용 가능   
`<hr>` : Add horizontal line. Use to distinguish between content whose subject changes. Automatically change the line. Available without end tag   
   
// 단락의 제목 지정 : 볼드체. 자동 줄바꿈   
`<hn> n=1, ..., 6 --> h1, h2, h3, h4, h5, h6` : Specify the title of the paragraph. Boldface. Automatically change the line.   
   
// 텍스트를 자유롭게 표시 : 편집기에서 문자가 입력된 형태를 그대로 유지하여 출력. pre 안에서 html 요소는 문자로 취급되지 않고 적용됨   
`<pre>...</pre>` : Output text as it is. The format of the characters entered in the editor remains the same and is outputted. Within pre, the html element is applied without being treated as a character   
   
// 인용문 작성 : 상하 빈 줄로 구분되는 인용문 단락의 생성 및 들여쓰기. 들여쓰기 간격의 인위적인 조정은 불가능. cite속성으로 인용된 부분의 URL 지정   
`<blockquote cite="http://abc.com">...</blockquote>` : Writing Quotation statement. Creating and indenting quotation statement separated by upper and lower blank lines. Artificial adjustment of indent interval is not possible. Specify the URL of the part cited by the cite property   
   
<br />
### Enter spaces and special characters   
// 공백 및 특수문자 입력   
   
// 두 칸 이상의 연속된 공백, 예약어로 사용되는 문자, 키보드로 직접 입력할 수 없는 문자 입력   
Enter two or more consecutive spaces. Enter characters used as reservation words. Enter characters that cannot be entered directly by keyboard   
   
```html
<!-- Enter with Unicode -->
&SpecialName;
&#DecimalCode;
&#xHexadecimalCode;

&nbsp; == &#32; == &#x20; == space
&lt; == &#60; == &#x3c; == <
&gt; == &#62; == &#x3e; == >
&amp; == &#38; == &#x26; == &
&quot; == &#34; == &#x22; == "
&rarr; == &#8594; == &#x2129; == →
&copy; == &#169; == &#xa9; == ＠
```
   
<br />
### Styleing Elements of Charaters   
// 글자의 스타일 지정 요소   
   
#### Physical Style Related Elements   
// 물리적 스타일 관련 요소   
   
// 단순히 웹 브라우저에 표시되는 출력 모양만을 지정하는 요소   
Elements that simply specify the appearance of the output displayed in the web browser   
   
```html
<!-- // 주목해야할 단어를 표시 -->
<b>b : Bold - Show the words of interest</b>

<!-- // 보통의 서술과 구분되는 다른 어조/분위기를 갖는 텍스트 -->
<i>i : Italic type - Text with a different tone/ atmosphere than the usual description</i>

<!-- // 더이상 정확하지 않거나 관련이 없는 내용 -->
<s>s : Cancellation Line - Content that is no longer accurate or relevant</s>

<!-- // 철자가 틀린 단어나 불충분한 내용을 표시 -->
<u>u : Underlined - Mark words misspelled or insufficient content</u>

<!-- // 윗첨자 -->
<sup>up : Superscript</sup>

<!-- // 아래첨자 -->
<sub>sub : Subscript</sub>

<!-- // 부수적인 해설이나 이용조건, 법적공지 등 -->
<small>small : Smaller size - Incidental explanations, Terms of use, Legal announcement, etc.</small>
```
   
#### Apply Source   
`
<!-- // 주목해야할 단어를 표시 -->
<b>b : Bold - Show the words of interest</b>

<!-- // 보통의 서술과 구분되는 다른 어조/분위기를 갖는 텍스트 -->
<i>i : Italic type - Text with a different tone/ atmosphere than the usual description</i>

<!-- // 더이상 정확하지 않거나 관련이 없는 내용 -->
<s>s : Cancellation Line - Content that is no longer accurate or relevant</s>

<!-- // 철자가 틀린 단어나 불충분한 내용을 표시 -->
<u>u : Underlined - Mark words misspelled or insufficient content</u>

<!-- // 윗첨자 -->
<sup>up : Superscript</sup>

<!-- // 아래첨자 -->
<sub>sub : Subscript</sub>

<!-- // 부수적인 해설이나 이용조건, 법적공지 등 -->
<small>small : Smaller size - Incidental explanations, Terms of use, Legal announcement, etc.</small>
`
   
<br />
#### Logical Style Related Elements   
// 논리적 스타일 관련 요소   
   
// 출력 형태보다는 요소 자체가 의미를 갖고 사용되는 요소   
An element in which an element itself is used to have meaning rather than an output form   
   
```html
<!-- // 책, 시, 그림, 영화 등의 작품 제목을 표시. 이탤릭체 -->
<cite>cite : Display the title of the work of a book, poem, painting, film, etc. Italic type</cite>

<!-- // 컴퓨터 코드를 표시. 다른것과 폰트가 다름 -->
<code>code : Show computer code. The font is different from the other one</code>

<!-- // 프로그램의 샘플 출력을 표시. 다른것과 폰트가 다름 -->
<samp>samp : Display sample output from the program. The font is different from the other one</samp>

<!-- // 변수를 표시. 이탤릭체 -->
<var>var : Show variables. Italic type</var>

<!-- // 용어에 대한 정의를 표시. 이탤릭체 -->
<dfn>dfn : Show definition for term. Italic type</dfn>

<!-- // 강조하는 내용을 표시. 이탤릭체 -->
<em>em : Show highlights. Italic type</em>

<!-- // 중요한 내용을 표시. 진하게 표시 -->
<string>string : Show important content. Bold</string>

<!-- // 축약형을 표시 -->
<abbr>abbr : Display abbreviations</abbr>

<!-- // 실제 우편물 주소를 표시. 이탤릭체. 자동 줄바꿈 -->
<address>address : Display the actual mail address. Italic type. Automatically change the line</address>

<!-- // 키보드로 입력한 내용임을 표시. 다른것과 폰트가 다름 -->
<kbd>kbd : Show that this is entered by keyboard. The font is different from the other one</kbd>

<!-- // 짧은 인용구를 표시. 큰따옴표가 자동으로 추가됨 -->
<q>q : Show short quotes. Double quotation marks added automatically</q>

<!-- // 시각적/의미적으로 특정 문구나 단어를 강조. 형광색 배경 -->
<mark>mark : Emphasize a particular phrase or word visually or meaningfully. The background is fluorescent</mark>
```
   
#### Apply Source   
`
<!-- // 책, 시, 그림, 영화 등의 작품 제목을 표시. 이탤릭체 -->
<cite>cite : Display the title of the work of a book, poem, painting, film, etc. Italic type</cite>

<!-- // 컴퓨터 코드를 표시. 다른것과 폰트가 다름 -->
<code>code : Show computer code. The font is different from the other one</code>

<!-- // 프로그램의 샘플 출력을 표시. 다른것과 폰트가 다름 -->
<samp>samp : Display sample output from the program. The font is different from the other one</samp>

<!-- // 변수를 표시. 이탤릭체 -->
<var>var : Show variables. Italic type</var>

<!-- // 용어에 대한 정의를 표시. 이탤릭체 -->
<dfn>dfn : Show definition for term. Italic type</dfn>

<!-- // 강조하는 내용을 표시. 이탤릭체 -->
<em>em : Show highlights. Italic type</em>

<!-- // 중요한 내용을 표시. 진하게 표시 -->
<string>string : Show important content. Bold</string>

<!-- // 축약형을 표시 -->
<abbr>abbr : Display abbreviations</abbr>

<!-- // 실제 우편물 주소를 표시. 이탤릭체. 자동 줄바꿈 -->
<address>address : Display the actual mail address. Italic type. Automatically change the line</address>

<!-- // 키보드로 입력한 내용임을 표시. 다른것과 폰트가 다름 -->
<kbd>kbd : Show that this is entered by keyboard. The font is different from the other one</kbd>

<!-- // 짧은 인용구를 표시. 큰따옴표가 자동으로 추가됨 -->
<q>q : Show short quotes. Double quotation marks added automatically</q>

<!-- // 시각적/의미적으로 특정 문구나 단어를 강조. 형광색 배경 -->
<mark>mark : Emphasize a particular phrase or word visually or meaningfully. The background is fluorescent</mark>
`
   
<br />   
### Block Element vs Inline Element   
// 블록 요소 vs 인라인 요소   
   
|Block Element|Inline Element|
|:---|:---|
|// 문서 구조 요소<br />Document Structure Element|// 텍스트 요소<br />Text Element|
|// 항상 새로운 줄에서 시작해서 하나의 줄을 전부 차지해서 내용 표시<br />Always start with a new line and occupy all of one line to display the contents|// 입력하는 내용만큼의 공간을 차지해서 내용 표시<br />Display content in as much space as input|
|// 자동으로 줄바꿈 수행<br />Automatically perform a new line|// 줄바꿈 미수행 → 앞뒤 내용이 이어져 한 줄에 쭉 표시<br />Line modification not performed → Front and back contents are connected, displaying in a single line|
|div, p, h1, ...|span, img, strong, ...|
   
<br />
### Container Elements that contain content   
// 콘텐츠 컨테이너 요소   
   
|div|span|
|:---|:---|
|Block Element|Inline Element|
|// HTML 요소를 하나로 묶어서 논리적인 단위의 영역을 구성<br />Organize areas of logical units by grouping HTML elements together|// 텍스트를 위한 컨테이너<br />Containers for text|
|// 논리적으로 구분된 대량의 내용에 대해 CSS 스타일 지정 또는 전체 페이지의 공간을 분할하여 레이아웃을 구성하는데 사용<br />Use to style the CSS for a large amount of logically separated content or to organize the layout by dividing the space of the entire page|// 텍스트의 일부에 대해 CSS 스타일 지정 또는 자바스크립트에서 조작할 때 유용<br />Useful when styling CSS or manipulating in JavaScript for a portion of text|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
