---
layout: post
title:  "JavaScript Html: html element table"
date:   2024-03-08 09:00:00 +0900
categories: [JavaScript Html]
---

### Elements related to table   
// 테이블과 관련된 요소   
   
<br />
### Default format of table   
// 테이블의 기본 형식   
   
```html
<table>
    <tr>
        <td>1 row, 1 column</td>
        <td>1 row, 2 column</td>
        ...
    </tr>
    <tr>
        <td>2 row, 1 column</td>
        <td>2 row, 2 column</td>
        ...
    </tr>
    ...
</table>
```
   
#### Example   
   
```html
<table border="1">
    <caption>score by subject</caption>
    <tr>
        <th>Subject</th>
        <th>an interim examination</th>
        <th>a final examination</th>
    </tr>
    <tr>
        <td>Machine learning</td>
        <td>30</td>
        <td>46</td>
    </tr>
    <tr>
        <td>Algorithm</td>
        <td>28</td>
        <td>50</td>
    </tr>
</table>
```
   
#### Apply Source   
   
<table border="1">
    <caption>score by subject</caption>
    <tr>
        <th>Subject</th>
        <th>an interim examination</th>
        <th>a final examination</th>
    </tr>
    <tr>
        <td>Machine learning</td>
        <td>30</td>
        <td>46</td>
    </tr>
    <tr>
        <td>Algorithm</td>
        <td>28</td>
        <td>50</td>
    </tr>
</table>
<br /><br />
   
<br />
### Basic Elements for Table Creation   
// 테이블 생성을 위한 기본 요소   
   
#### table element   
// table 요소   
   
// HTML에서 테이블을 정의하는 요소   
// - m행 X n열 : m개의 tr 요소, 각 tr내에서 n개의 td 요소   
// - 테이블의 테두리 지정   
// -- border 속성   
// -- 테두리 스타일 지정은 CSS 사용   
- Element that define tables in HTML   
  - m row X n column : m tr elements, n td elements within each tr   
  - specify the border of the table   
    - border Properties   
    - use CSS to style border   
   
#### tr element (table row)   
// tr 요소 (table row)   
   
// 테이블에서 하나의 줄에 해당하는 행을 정의하는 요소   
// - td 요소 (또는 th 요소) 를 포함해야만 사용 가능   
- Element that define rows corresponding to one row in the table   
  - Only available if td element (or th element) is included   
   
#### td element (table data)   
// td 요소 (table data)   
   
// 데이터 (텍스트, 이미지, 테이블 등) 를 표시하는 표준 셀을 정의   
// - 반드시 tr 요소 내에서 사용   
// - 셀 내용 : 왼쪽 정렬   
- Define standard cells that display data (text, images, tables, etc.)   
  - Must be used within tr element   
  - Cell content : Left alignment   
   
#### th element (table header)   
// th 요소 (table header)   
   
// 테이블 내부에서 행, 열의 제목을 표시하는 헤더 셀을 정의   
// - td 요소의 위치에서 선택적으로 사용   
// - 셀 내용 : 진하게 가운데 정렬   
- Define a header cell that displays the title of a row, column inside the table   
  - Optionally use at the location of the td element   
  - Cell details : Strong center alignment   
   
#### catption element   
// catption 요소   
   
// 테이블 전체에 대한 제목을 표시할 때 사용   
// - 테이블의 레이아웃에는 아무런 영향 없음   
// - 반드시 table 요소의 시작태그 바로 다음에 위치시킴   
// -- tr/td 요소 내에서 사용되면 caption 요소는 무시됨   
// - 테이블 상단에 진하게 가운데 정렬   
// -- CSS 속성 (caption-side, text-align) 으로 변경 가능   
- Use to display titles for the entire table   
  - No effect on the layout of the table   
  - The capture element must be placed immediately after the start tag of the table element   
    - Caption element are ignored when used within tr/td element   
  - Align dark center at the top of the table   
    - Changeable to CSS properties (caption-side, text-align)   
   
<br />
### Merging Cells   
// 셀의 병합   
   
// 인접한 여러 셀을 합쳐서 하나의 셀로 만드는 경우   
// - 보다 비정형적인 다양한 모양의 테이블 생성 가능   
- When several adjacent cells are combined to form one cell   
  - Create tables of various shapes that are more atypical   
   
#### rowspan property, colspan property   
// rowspan 속성, colspan 속성   
   
// td 또는 th 요소 내에서만 사용   
// rowspan="n"   
// - 현재 셀 위치에서 인접한 n개의 행을 병합 : 세로 방향의 병합   
// colspan="n"   
// - 현재 셀 위치에서 인접한 n개의 열을 병합 : 가로 방향의 병합   
- Use only within td or th element   
- rowspan="n"   
  - Merge n adjacent rows at the current cell location : Merge longitudinally   
- colspan="n"   
  - Merge n adjacent columns from the current cell location : Merge in the lateral direction   
   
#### Example   
   
```html
<table border="1">
    <tr>
        <td>1-1</td>
        <td>1-2</td>
        <td>1-3</td>
        <td>1-4</td>
    </tr>
    <tr>
        <td>2-1</td>
        <td>2-2</td>
        <td>2-3</td>
        <td>2-4</td>
    </tr>
    <tr>
        <td>3-1</td>
        <td>3-2</td>
        <td>3-3</td>
        <td>3-4</td>
    </tr>
</table>
```
   
```html
<table border="1">
    <tr>
        <td colspan="4">1-1 ~ 1-4</td>
    </tr>
    <tr>
        <td rowspan="2">2-1<br />3-1</td>
        <td rowspan="2">2-2<br />3-2</td>
        <td>2-3</td>
        <td>2-4</td>
    </tr>
    <tr>
        <td colspan="2">3-3, 3-4</td>
    </tr>
</table>
```
   
#### Apply Source   
   
<table border="1">
    <tr>
        <td>1-1</td>
        <td>1-2</td>
        <td>1-3</td>
        <td>1-4</td>
    </tr>
    <tr>
        <td>2-1</td>
        <td>2-2</td>
        <td>2-3</td>
        <td>2-4</td>
    </tr>
    <tr>
        <td>3-1</td>
        <td>3-2</td>
        <td>3-3</td>
        <td>3-4</td>
    </tr>
</table>
   
<table border="1">
    <tr>
        <td colspan="4">1-1 ~ 1-4</td>
    </tr>
    <tr>
        <td rowspan="2">2-1<br />3-1</td>
        <td rowspan="2">2-2<br />3-2</td>
        <td>2-3</td>
        <td>2-4</td>
    </tr>
    <tr>
        <td colspan="2">3-3, 3-4</td>
    </tr>
</table>
<br /><br />
   
<br />
### Grouping per-line content   
// 행 단위 콘텐츠의 그룹핑   
   
#### thead, tbody, tfoot element   
// thead, tbody, tfoot 요소   
   
// 테이블에서 행 단위 콘텐츠를 헤더, 몸체, 푸터 부분으로 구분하여 그룹핑하는 요소   
// 테이블 레이아웃에는 아무런 영향을 미치지 않음   
// 요소의 사용 위치   
// - thead, tbody, tfoot 요소는 순서대로 사용   
// - `<table><caption><colgroup><thead><tr><th><td>...</table>`   
- Element that group row-by-row content into header, body, and footer parts in the table   
- No effect on table layout   
- Where an element is used   
  - Use the thead, tbody, and tfoot in order   
  - `<table><caption><colgroup><thead><tr><th><td>...</table>`   
   
#### Example   
   
```html
<table border="1">
    <thead>
        <tr>
            <th>subject</th>
            <th>score</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Korean</td>
            <td>90</td>
        </tr>
        <tr>
            <td>English</td>
            <td>95</td>
        </tr>
        <tr>
            <td>Mathematics</td>
            <td>85</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Average</td>
            <td>90</td>
        </tr>
    </tfoot>
</table>
```
   
#### Apply Source   
   
<table border="1">
    <thead>
        <tr>
            <th>subject</th>
            <th>score</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Korean</td>
            <td>90</td>
        </tr>
        <tr>
            <td>English</td>
            <td>95</td>
        </tr>
        <tr>
            <td>Mathematics</td>
            <td>85</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Average</td>
            <td>90</td>
        </tr>
    </tfoot>
</table>
<br /><br />
   
<br />
### Specify style in column units   
// 열 단위의 스타일 지정   
   
#### colgroup element   
// colgroup 요소   
   
// 하나 이상의 열들을 모아서 한꺼번에 스타일을 지정할 때 사용   
// 요소의 사용 위치   
// - `<table><caption><colgroup><thead><tr><th><td>...</table>`   
- Use to gather one or more columns and style them all at once   
- Where an element is used   
  - `<table><caption><colgroup><thead><tr><th><td>...</table>`   
   
#### col element   
// col 요소   
   
// 지정된 열에 대해서 서로 다른 포매팅을 정의하는 요소   
// colgroup 요소의 자식 요소   
// - 종료태그 없이 사용   
// - span="n" 속성 : 해당 요소의 스타일이 적용되는 열의 개수   
- Element that define different formatting for a given column   
- Child element of a colgroup element   
  - Use without end tag   
  - span="n" property : the number of columns to which the style of the element is applied   
   
#### Example   
   
```html
<style>
    .subject{background-color: lightblue}
    .score{background-color: lightyellow}
    .average{background-color: lightgreen}
</style>

<table border="1">
    <colgroup>
        <col class="subject">
        <col span="2" class="score">
        <col class="average">
    </colgroup>
        <tr>
            <th>Subject</th>
            <th>an interim examination</th>
            <th>a final examination</th>
            <th>Average</th>
        </tr>
        <tr>
            <td>Korean</td>
            <td>90</td>
            <td>95</td>
            <td>92.5</td>
        </tr>
        <tr>
            <td>English</td>
            <td>96</td>
            <td>90</td>
            <td>93.0</td>
        </tr>
        <tr>
            <td>Mathematics</td>
            <td>85</td>
            <td>95</td>
            <td>90.0</td>
        </tr>
</table>
```
   
#### Apply Source   
   
<style>
    .subject{background-color: lightblue}
    .score{background-color: lightyellow}
    .average{background-color: lightgreen}
</style>

<table border="1">
    <colgroup>
        <col class="subject">
        <col span="2" class="score">
        <col class="average">
    </colgroup>
        <tr>
            <th>Subject</th>
            <th>an interim examination</th>
            <th>a final examination</th>
            <th>Average</th>
        </tr>
        <tr>
            <td>Korean</td>
            <td>90</td>
            <td>95</td>
            <td>92.5</td>
        </tr>
        <tr>
            <td>English</td>
            <td>96</td>
            <td>90</td>
            <td>93.0</td>
        </tr>
        <tr>
            <td>Mathematics</td>
            <td>85</td>
            <td>95</td>
            <td>90.0</td>
        </tr>
</table>
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
