---
layout: post
title:  "JavaScript Html: html element semantic"
date:   2024-05-06 09:00:00 +0900
categories: [JavaScript Html]
---

### Elements related to semantic   
// 시맨틱과 관련된 요소   
   
// 시맨틱 요소?   
// - semantic : "의미 있는", "의미의"   
- Semantic elements?   
  - semantic : "meaningful", "signification"   
   
// 표현 중심이 아닌 의미 있는 구조의 문서 작성을 위한 요소   
- Elements for creating meaningful structured documents rather than expression-oriented   
   
// HTML 문서에 의미 부여가 가능   
// - 사람이 읽고 이해하는 것이 용이   
// - 검색 엔진, 문서 해석기 등에 의한 자동적인 문서 처리, 해석도 가능   
- Allows HTML documents to be meaningful   
  - It's easy for people to read and understand   
  - Automatic document processing and interpretation by search engines, document interpreters, etc.   
   
// 문서 구조화   
- Document structuring   
  - header, nav, section, article, aside, footer   
   
// 블록 요소   
- Block element   
  - main, figure ~ figcaption, details ~ summary   
   
// 인라인 요소   
- Inline element   
  - time, meter, progress, ruby ~ rt, wbr   
   
<br />
### Document structuring   
// 문서 구조화   
   
#### Traditional document structuring methods   
// 기존의 문서 구조화 방식   
   
// 헤더 영역, 메뉴 영역, 콘텐츠 영역, 사이드 영역, 푸터 영역   
// div 요소 사용   
- Header Area, Menu Area, Content Area, Side Area, Footer Area   
- Use div element   
   
```html
<div id="header">
<div id="menu">
<div id="contents">
    <div id="article">
    <div id="article">
    <div id="article">
<div id="r-side">
<div id="footer">
```
   
#### Elements for document structuring   
// 문서 구조화를 위한 요소   
   
// header : 머리말 (로고, 사이트 이름 등) 을 나타내는 요소   
// nav : 메뉴 영역을 나타내는 요소   
// section : 제목/주제별로 나눌 수 있는 문서의 내용 영역을 구성하는 요소   
// article : 개별 콘텐츠를 나타내는 요소   
// aside : 좌우측의 보조 콘텐츠 영역을 나타내는 요소   
// footer : 꼬리말 (제작자 정보 및 저작권 정보 등) 을 나타내는 요소   
- header : Elements representing a header (logo, site name, etc.)   
- nav : Elements representing the menu area   
- section : Elements that make up the content area of a document that can be divided by title/topic   
- article : Elements representing individual content   
- aside : Elements representing sub content areas on the left and right sides   
- footer : Elements representing a tail (producer information and copyright information, etc.)   
   
// HTML5 요소를 이용한 문서 구조화   
- Document Structuring Using HTML5 Elements   
   
```html
<header>
<nav>
<section>
    <article>
    <article>
    <article>
<aside>
<footer>
```
   
<br />
### header and footer elements that including the head and tail   
// 머리과 꼬리말을 담는 header, footer 요소   
   
// header 요소   
// - 머리말 : 사이트 이름, 로고와 소개 정보 등   
- header element   
  - Head : Site name, logo and introduction information, etc.   
   
// footer 요소   
// - 꼬리말 : 제작자 정보, 저작권 정보, 연락처 등   
- footer element   
  - Tail : Producer information, copyright information, contact information, etc.   
   
```html
<header>Head</header>
<section>
    <h1>Title</h1>
    <p>Body content</p>
</section>
...
<footer>Tail</footer>
```
   
// 위치 무관   
// 내용 중간 (section, article) 에서 사용되는 경우 머리글, 바닥글 역할을 함   
// header, footer 안에 section, header, footer 요소를 포함하는 것은 불가   
- Location irrelevant   
- Serves as a header and footer when used in sections or articles of content   
- It is not possible to include section, header and footer elements in header or footer   
   
<br />
### nav and aside element containing menu and supplementary content   
// 메뉴와 보조 콘텐츠를 담는 nav, aside 요소   
   
// nav 요소   
// - navigational links 영역   
// -- 주로 웹 페이지 전체에 적용되는 상단의 메뉴를 표시하기 위한 링크를 모아 놓는 곳 : 페이지의 모든 링크를 포함하는 것은 아님   
- nav element   
  - navigational links area   
    - A place where links are gathered to display the menu at the top, which is usually applied to the entire web page : Not all links on the page   
   
// aside 요소   
// - 주요 콘텐츠 이외에 남아 있는 콘텐츠나 참고가 되는 콘텐츠 등을 나타낼 때 사용   
// -- 본문과는 직접 관련이 없지만 링크나 관련 정보를 표현   
// -- 주로 웹 페이지의 왼쪽 또는 오른쪽에 위치   
- aside element   
  - Used to indicate the remaining content or reference content other than the main content   
    - Not directly related to the text, but expressing links or related information   
    - Mainly located to the left or right of a web page   
   
```html
<header>Head</header>
<nav>menu</nav>
Content Area
...
<aside>Side</aside>
<footer>Tail</footer>
```
   
#### nav element   
// nav 요소   
   
```html
<body>
    <nav>
        <ol>
            <li><a href="...">mail</a></li>
            <li><a href="...">cafe</a></li>
            <li><a href="...">blog</a></li>
            <li><a href="...">map</a></li>
        </ol>
    </nav>
</body>
```
   
#### Apply Source   
   
<body>
    <nav>
        <ol>
            <li><a>mail</a></li>
            <li><a>cafe</a></li>
            <li><a>blog</a></li>
            <li><a>map</a></li>
        </ol>
    </nav>
</body>
<br /><br />
   
<br />
### Content area section element, Individual content article element   
// 내용 영역 section, 개별 콘텐츠 article 요소   
   
```html
<section>
    <h1>culture</h1>
    <article>
        <h3>'Web drama' ...</h3>
        <p>These days, teenage stars ...</p>
    </article>
    <article>
        <h3>'It's okay if it's weird' ...</h3>
        <p>New imagination ...</p>
    </article>
</section>
``` 
   
#### Apply Source   
   
<section>
    <h1>culture</h1>
    <article>
        <h3>'Web drama' ...</h3>
        <p>These days, teenage stars ...</p>
    </article>
    <article>
        <h3>'It's okay if it's weird' ...</h3>
        <p>New imagination ...</p>
    </article>
</section>
<br /><br />
   
#### section element   
// section 요소   
   
// 하나의 주제로 구성된 문서의 내용 영역을 표현   
// - 하나의 section 요소에는 오직 하나의 헤딩 요소 (h1 ~ h6) 만 사용   
- Expressing the content area of a document that consists of a single topic   
  - Only one heading element (h1 ~ h6) is used for one section element   
   
// 하나의 주제 안에 다른 세부 주제가 존재하는 경우   
- If there are other sub topics within one topic   
   
```html
<section>
    <h1>Main title<h1>
    <section>
        <h2>Sub title 1<h2>
            Body content of sub title 1
    </section>
    <section>
        <h2>Sub title 2<h2>
            Body content of sub title 2
    </section>
</section>
```
   
// 하나의 요소에 2개 이상의 헤딩 요소가 사용된 경우   
// - 헤딩 요소의 레벨에 따라 묵시적으로 결정   
- If more than one heading element is used   
  - Implicit determination based on the level of the heading element   
   
// 1. 같은 레벨의 헤딩 요소 사용   
// - 같은 레벨의 section 요소로 구분되어 해석됨   
    1. Using the same level of heading elements   
        - Interpreted as section elements of the same level   
   
```html
<section>
    <h1>Title 1<h1>
    Body content of title 1
    <h1>Title 2<h1>
    Body content of title 2
</section>
```
   
```html
<section>
    <h1>Title 1<h1>
    Body content of title 1
</section>
<section>
    <h1>Title 2<h1>
    Body content of title 2
</section>
```
   
// 2. 다른 레벨의 헤딩 요소 사용   
// - 중첩된 section 요소로 구분   
    2. Use other levels of heading elements   
        - Separated by nested section elements   
   
```html
<section>
    <h1>Title 1<h1>
    Body content of title 1
    <h2>Title 2<h2>
    Body content of title 2
</section>
```
   
```html
<section>
    <h1>Title 1<h1>
    Body content of title 1
    <section>
        <h2>Title 2<h2>
        Body content of title 2
    </section>
</section>
```
   
#### article element   
// article 요소   
   
// 독립적으로 분배 및 재사용이 가능한 개별 콘텐츠 (뉴스 기사, 블로그 포스트 등) 을 나타낼 때 사용   
// - section 요소와 분리하여 개별적으로 사용 가능   
// -- article 요소 안에 section 또는 article 요소 포함 가능   
- Used to represent individual content (news articles, blog posts, etc.) that can be distributed and reused independently   
  - Can be used separately from section elements   
    - Section or article can be included in the article element   
   
<br />
### Semantic Block element   
// 시맨틱 블록 요소   
   
// 주요 콘텐츠 블록을 지정하는 main 요소   
- The main element that specifies the main content block   
   
// 삽입 그림을 블록화하는 figure 요소   
// - 하위 요소 : figcaption   
- The figure element that contains the insert picture as a block   
  - Sub-elements : figcaption   
   
// 세부정보를 선택적으로 표시하는 details 요소   
// - 하위 요소 : summary   
- Details element that selectively displays details   
  - Sub-elements : summary   
   
#### The main element that specifies the main content block   
// 주요 콘텐츠 블록을 지정하는 main 요소   
   
// 문서 body 영역의 주요 콘텐츠 블록을 지정할 때 사용   
- Used to specify key content blocks in the document body area   
   
// 문서 전체에서 반복적으로 사용되는 콘텐츠는 포함 불가   
// - 사이드바, 내비게이션 링크, 저작권 정보, 사이트 로고, 검색 폼 등 포함 불가   
// 문서에서 유일한 부분을 의미 : 오직 한번만 사용   
// 문서의 전체적인 레이아웃에는 아무런 영향을 주지 않음   
// article, aside, header, footer, nav 요소의 하위 요소로 사용 불가   
- Do not include content that is used repeatedly throughout the document   
  - Sidebar, navigation link, copyright information, site logo, search form, etc. not included   
- Meaning the only part of a document : Use only once   
- No impact on the overall layout of the document   
- Cannot be used as a sub-element of an article, aside, header, footer, nav element   
   
```html
<body>
    <main>
        <section>
            <h1>Web page components</h1>
            <p>HTML, CSS, JavaScript</p>
            <article>
                <h3>HTML</h3>
                <p>version 5, 2014</p>
            </article>
            <article>
                <h3>CSS</h3>
                <p>Module 3, 2012</p>
            </article>
            <article>
                <h3>JavaScript</h3>
                <p>ES6, 2015</p>
            </article>
        </section>
    </main>
</body>
```
   
#### Apply Source   
   
<body>
    <main>
        <section>
            <h1>Web page components</h1>
            <p>HTML, CSS, JavaScript</p>
            <article>
                <h3>HTML</h3>
                <p>version 5, 2014</p>
            </article>
            <article>
                <h3>CSS</h3>
                <p>Module 3, 2012</p>
            </article>
            <article>
                <h3>JavaScript</h3>
                <p>ES6, 2015</p>
            </article>
        </section>
    </main>
</body>
<br /><br />
   
#### The figure element that contains the insert picture as a block   
// 삽입 그림을 블록화하는 figure 요소   
   
// 본문에서 삽입된 독립적인 콘텐츠 (그림, 다이어그램, 사진, 소스 코드, 동영상 등) 를 하나로 묶어 블록을 형성하고, 캡션을 포함시켜 서로의 관계를 명확히 구조화시킬 때 사용   
// - 요소의 위치는 주요 콘텐츠와 독립적   
// -- 삭제하더라도 문서의 흐름에는 아무런 영향을 주지 않음   
- Use to form blocks by combining independent content (pictures, diagrams, photos, source code, videos, etc.) inserted in the content, and to clearly structure each other's relationship by including captions   
  - The location of the elements is independent of the main content   
    - Deletion does not affect the flow of documents   
   
// figcaption 요소   
// - fogure 요소에 대한 캡션을 표시하는 자식 요소   
// - 위치 : figure 요소 바로 다음 또는 맨 마지막   
- figcaption element   
  - Child element displaying captioning for the fogure element   
  - Location : Immediately next to or last to the figure element   
   
```html
<body>
    <p>figure elements are used to block independent content, such as pictures, diagrams, photos, source codes, videos, etc., inserted into the content</p>
    <figure>
        <img src="flower.jpg" alt="Yellow Tulip" width="300" height="200">
        <figcaption>Figure 1. Pretty Yellow Tulips</figcaption>
    </figure>
</body>
```
   
#### Apply Source   
   
<body>
    <p>figure elements are used to block independent content, such as pictures, diagrams, photos, source codes, videos, etc., inserted into the content</p>
    <figure>
        <img src="flower.jpg" alt="Yellow Tulip" width="300" height="200">
        <figcaption>Figure 1. Pretty Yellow Tulips</figcaption>
    </figure>
</body>
<br /><br />
   
#### Details element that selectively displays details   
// 세부정보를 선택적으로 표시하는 details 요소   
   
// 사용자의 요구 (핸들(▶ ▼) 클릭) 에 따라 추가적인 세부정보를 보여주거나 숨기는 형태의 상호작용을 지원하는 요소   
// - 세부정보는 어떤 종류의 콘텐츠도 가능   
// - open 속성 : 세부정보가 사용자에게 보여지도록 지정   
// - summary 요소   
// -- 세부정보에 대한 캡션을 지정하는 details 요소의 자식 요소   
// -- 캡션의 클릭을 통해서도 세부정보의 표시 여부의 선택이 가능   
// -- 미사용하면 "세부정보"라는 기본 제목이 표시됨   
- Elements that support interaction in the form of showing or hiding additional details based on user request (click handle (▶ ▼))   
  - Details can be any kind of content   
  - open property : Specifying that details are visible to the user   
  - summary element   
    - Child element of the details element that captions the details   
    - Click the caption to choose whether to display the details   
    - If not used, the default title "Details" will be displayed   
   
```html
<details>
    <summary>HTML</summary>
    <p>Define the structure and content of a webpage</p>
</details>
<details open>
    <summary>CSS</summary>
    <p>Specify the output appearance of a webpage</p>
</details>
<details>
    <summary>JavaScript</summary>
    <p>Programming the behavior of web pages</p>
</details>
```
   
#### Apply Source   
   
<details>
    <summary>HTML</summary>
    <p>Define the structure and content of a webpage</p>
</details>
<details open>
    <summary>CSS</summary>
    <p>Specify the output appearance of a webpage</p>
</details>
<details>
    <summary>JavaScript</summary>
    <p>Programming the behavior of web pages</p>
</details>
<br /><br />
   
<br />
### Semantic Inline element   
// 시맨틱 인라인 요소   
   
// 시간, 날짜를 지정하는 time 요소   
// 주어진 값이나 비율을 나타내는 meter 요소   
// 작업의 진행률을 나타내는 progress 요소   
// 루비 주석을 지정하는 ruby 요소   
// - 하위 요소 : rt   
// 줄바꿈의 허용 위치를 지정하는 wbr 요소   
- time element that specifies time and date   
- meter element representing a given value or ratio   
- progress element representing the progress of the task   
- ruby element specifying ruby comment   
  - Sub-elements : rt   
- wbr element that specifies the allowable position of the new line   
   
#### time element that specifies time and date   
// 시간, 날짜를 지정하는 time 요소   
   
// datetime 속성 : 시스템이 인식할 수 있도록 정확한 형식의 시간, 날짜를 지정   
- datetime property : Specify the exact format of time and date so that the system can recognize it   
   
```html
<body>
    <p>The wake-up time is <time>07:00</time>,
        The bedtime is <time>23:00</time></p>
    <p>The HTML5 standard was published in <time data="2014-10-28">at the end of 2014</time></p>
</body>
```
   
#### Apply Source   
   
<body>
    <p>The wake-up time is <time>07:00</time>,
        The bedtime is <time>23:00</time></p>
    <p>The HTML5 standard was published in <time data="2014-10-28">at the end of 2014</time></p>
</body>
<br /><br />
   
#### meter element representing a given value or ratio   
// 주어진 값이나 비율을 나타내는 meter 요소   
   
// 일정 범위 안의 측정값이나 분포 비율 등을 표시할 때 사용   
// - "측정기" gauge : 현재 디스크 사용량과 같이 일정 시점에서 주어진 (정적인) 양을 표시   
- Used to display measurements, distribution ratios, etc. within a range   
  - gauge : Displays a given (static) amount at a given point in time, such as the current disk usage   
   
// 속성   
// - value : (필수) 실제로 측정한 현재의 값   
// - main, max : 요소가 인식하는 최소값 (0.0) 과 최대값 (1.0)   
// - low, hight : 허용되는 범위의 최소값, 최대값   
// -- min ≤ low ≤ hight ≤ max   
// optimum : 최적의 값   
- property   
  - value : (Required) Current measured value   
  - main, max : Minimum (0.0) and Maximum (1.0) recognized by the element   
  - low, hight : Minimum and maximum values in the allowed range   
    - min ≤ low ≤ hight ≤ max   
  - optimum : optimum value   
   
```html
<body>
    <p>Disk Utilization <meter max=100 value=70></meter> (Based on 1TB)</p>
    <p>Movie reservation rate <meter min=0 max=100 value=95></meter></p>
    <p>Voter turnout in local elections <meter value=0.35 title="Turnout as of 3 p.m"></meter></p>
</body>
```
   
#### Apply Source   
   
<body>
    <p>Disk Utilization <meter max=100 value=70></meter> (Based on 1TB)</p>
    <p>Movie reservation rate <meter min=0 max=100 value=95></meter></p>
    <p>Voter turnout in local elections <meter value=0.35 title="Turnout as of 3 p.m"></meter></p>
</body>
<br /><br />
   
#### progress element representing the progress of the task   
// 작업의 진행률을 나타내는 progress 요소   
   
// 작업의 현재 진행 정도를 나타낼 때 사용   
// - 파일 복사, 다운로드 등과 같이 동적으로 변하는 작업의 진행 정도를 표현할 때 유용   
- Use to indicate the current progress of a task   
  - Useful for expressing the progress of dynamically changing tasks such as copying and downloading files   
   
// 속성   
// - value : 완료된 작업의 양을 나타내는 현재 상태의 값   
// -- 0.0 ~ 1.0 또는 0.0 ~ max   
// - max : 작업에 필요한 작업량의 최대값   
// -- 1.0   
- property   
  - value : The value of the current state, which represents the amount of completed task   
    - 0.0 ~ 1.0 or 0.0 ~ max   
  - max : Maximum amount of task required for a task   
    - 1.0   
   
```html
<body>
    File download status : 
    <progress value="25" max="100"></progress>
</body>
```
   
#### Apply Source   
   
<body>
    File download status : 
    <progress value="25" max="100"></progress>
</body>
<br /><br />
   
// 현재 진행 중인 상태의 값 (value) 의 지속적인 업데이트가 필요   
// - 반드시 자바스크립트와의 연동이 필요   
- Requires continuous updates of the value of the current state   
  - Must work with JavaScript   
   
#### ruby element specifying ruby comment   
// 루비 주석을 지정하는 ruby 요소   
   
// 하나 이상의 구문 콘텐츠에 루비 주석을 표시할 때 사용   
- Use to display ruby comments for one or more syntax content   
   
// 루비 주석 : 일본어, 한자의 기본 문자열 주변에 발음법이나 의미를 나타내기 위해 추가되는 짧은 텍스트   
- ruby comment : Short text added to represent pronunciation or meaning around the basic string of Japanese and Chinese characters   
   
// ruby 요소   
// - 하나 이상의 문자로 구성되는 기본 텍스트를 작성   
// rt 요소   
// - ruby 요소의 자식 요소   
// - rt 요소 바로 앞에 오는 하나 이상의 구문에 대한 루비 주석 표시   
- ruby element   
  - Create a primary text consisting of one or more characters   
- rt element   
  - Child element of ruby element   
  - Displays a ruby comment for one or more phrases that precede the rt element   
   
```html
<ruby>韓<rt>かん</rt></ruby>
<ruby>國<rt>こく</rt></ruby>
<ruby>放<rt>ほう</rt></ruby>
<ruby>送<rt>そう</rt></ruby>
<ruby>通信<rt>つうしん</rt></ruby>
<ruby>大學<rt>だいがく</rt></ruby><br /><br />
<ruby>HTML5 Web programming<rt>the first semester of the second year</rt></ruby><br /><br />
<ruby>日本<rt>にほん</rt></ruby>
```
   
#### Apply Source   
   
<ruby>韓<rt>かん</rt></ruby>
<ruby>國<rt>こく</rt></ruby>
<ruby>放<rt>ほう</rt></ruby>
<ruby>送<rt>そう</rt></ruby>
<ruby>通信<rt>つうしん</rt></ruby>
<ruby>大學<rt>だいがく</rt></ruby><br /><br />
<ruby>HTML5 Web programming<rt>the first semester of the second year</rt></ruby><br /><br />
<ruby>日本<rt>にほん</rt></ruby>
<br /><br />
   
#### wbr element that specifies the allowable position of the new line   
// 줄바꿈의 허용 위치를 지정하는 wbr 요소   
   
// 텍스트에서 줄바꿈을 허용할 위치를 지정할 때 사용   
// - "허용 위치" : 줄바꿈이 수행되어도 괜찮은 지점   
// -- 해당 위치에서 실제로 줄바꿈이 무조건 수행되는 것이 아니라 레이아웃의 배치 상황에 따라 결정   
// - 긴 URL 또는 단어/텍스트를 표시할 때 유용   
- Use to specify where to allow line breaks in text   
  - "Allowed position" : point where the line change can be carried out   
    - Determined by layout placement, rather than the actual line modulation at that location is not performed unconditionally   
  - Useful for displaying long URLs or words/texts   
   
```html
<p>This is a veryveryveryveryveryveryveryveryveryveryveryveryvery<wbr>longwordthatwillbreakatspecific<wbr>placeswhenthebrowserwindowisresized</p>
```
   
#### Apply Source   
   
<p>This is a veryveryveryveryveryveryveryveryveryveryveryveryvery<wbr>longwordthatwillbreakatspecific<wbr>placeswhenthebrowserwindowisresized</p>
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
 