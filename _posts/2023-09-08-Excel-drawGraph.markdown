---
layout: post
title:  "Excel: Draw Graph"
date:   2023-09-08 09:00:00 +0900
categories: [Excel]
---

<style>
    .characterOverline {
        text-decoration : overline;
    }
    .characterSpacing {
        letter-spacing : -0.6em;
    }
</style>

### The role of graph in statistical analysis   
// 통계분석에서 그래프의 역할   
   
// 데이터가 갖고 있는 정보를 요약하여 시각적으로 명확하게 보여줌   
- Summarize the information in the data and present it visually and clearly   
   
// 잘못 표현된 그래프는 정보와 그 의미를 왜곡해서 전달할 수 있음   
// - 데이터 특성과 분석 목적에 따라 사용할 수 있는 그래프 종류가 달라짐   
// - 데이터에 알맞은 그래프를 선택하는 것이 중요함   
// - 정량적 데이터 (quantitative data : 비율척도, 구간척도) 이냐 정성적 데이터 (qualitative data : 순서척도, 명목척도) 이냐에 따라 사용 가능한 그래프도 달라짐   
- Misrepresented graphs can distort information and its meaning   
  - Depending on data characteristics and analysis purpose, the types of graphs available vary   
  - It's important to choose the right graph for data   
  - The graph available depends on whether it is quantitative (ratio scale, interval scale) or qualitative data (ordinal scale, nominal scale)   
   
<br />
### Pie chart   
// 원 그래프, 원형 차트   
   
// 각 항목이 차지하는 비율과 원 그래프에서의 면적의 비율을 같게 만든 그래프   
- Graphs that equalize the proportion of each item and the proportion of the area in the pie graph   
   
// 원 그래프를 그릴 때 참고할 사항들   
// - 원 그래프의 조각은 8개 조각보다 작게 할 것   
// -- 작은 비율의 항목은 묶어서 '기타' 로 처리   
// - 특정 조각의 강조   
// -- 나머지 부분과 분리, 어둡거나 밝은 색 또는 무늬 이용   
- Notes for drawing a pie graph   
  - Pieces of a pie graph must be smaller than 8 pieces   
    - Small percentages of items are grouped together and treated as 'others'   
  - Emphasis on a particular piece   
    - Separate from the rest, or use dark or bright colors or patterns   
   
// `[삽입] 탭 - [차트] 그룹 - [원형 또는 도넛형 차트 삽입]` 선택   
// 만들어진 그래프 선택 후 `[차트도구] 탭 - [레이아웃] 그룹 - [차트제목]` 선택하여 그래프 제목 입력   
// `[데이터 레이블]` 선택하여 그래프의 표현 양식 수정 가능   
- Select `[Insert] tab - [Chart] group - [Insert pie or donut chart]`   
- After selecting the graph created, enter the graph title by selecting the `[Chart tools] tab - [Layout] group - [Chart subject]`   
- Select `[Data label]` to modify the expression form of the graph   
   
<br />
### Bar chart   
// 사각형 그래프, 띠 그래프, 막대 그래프   
   
// 주로 질적 데이터를 분석하기 위해 사용됨   
// 항목별 비중을 나타내는 데이터 (모든 항목을 합한 전체가 100%인 데이터) 에 대한 그래프를 표현하는데 많이 쓰임   
// 집단별 차이를 살펴서 비교하는데 효과적임   
// 그룹간 비교, 시간의 흐름에 따른 변화 파악에 적합함   
- It is mainly used to analyze qualitative data   
- It is often used to represent graphs of item-specific weighting data (data that adds up to 100% of all items)   
- It is effective in examining and comparing the differences between groups   
- It is suitable for comparing groups and identifying changes over time   
   
// `[삽입] 탭 - [차트] 그룹 - [세로 또는 가로 막대형 차트 삽입]` 선택   
- Select `[Insert] tab - [Chart] group - [Insert vertical or horizontal bar chart]`   
   
<br />
### Broken line graph   
// 꺽은선 그래프   
   
// 시계열 데이터   
// - 시간의 흐름에 따라 측정치를 측정하여 얻은 데이터   
// - 예시 : 대기 오염도, 주가 또는 환율 동향, 수출입 동향, 월별 판매량, 실업률 등   
- Time series data   
  - Data obtained by measuring measurements over time   
  - Example : Air pollution, stock price or exchange rate trends, import and export trends, monthly sales, unemployment, etc   
   
// 꺽은선 그래프는 시계열 데이터의 시간 흐름에 따른 경향 파악에 유용함   
// 데이터 수집 간격이 일정하지 않거나 기간 구분이 없는 데이터의 추세나 변화는 '꺽은선형' 보다 '분산형' 그래프를 작성하는 것이 효과적임   
- Broken line graphs are useful for identifying trends over time in time series data   
- For trends or changes in data with irregular data collection intervals or no period division, it is more effective to create a scatter plot rather than a broken line graph   
   
// `[삽입] 탭 - [차트] 그룹 - [꺽은선형 또는 영역형 차트 삽입]` 선택   
- Select `[Insert] tab - [chart] group - [Insert broken line chart or area chart]`   
   
// 꺽은선 그래프를 작성할 때 주의할 사항   
// - Y 축의 눈금을 얼마나 세분하는가에 따라 그래프의 의미가 다르게 해석될 수 있음   
// -- 눈금을 작게 잡으면 변화 경향을 뚜렷하게 보여줌   
// -- 눈금을 크게 잡으면 변화가 거의 없는 것처럼 보임   
// - X 축의 시작점에 따라 그래프의 의미가 다르게 해석될 수 있음   
// -- 변화가 큰 축을 제외하고 시작점을 잡으면 변화가 거의 없어 보일 수 있음   
// -- 시계열 데이터에서 X 축의 시작 시점을 무엇으로 정하는가에 따라서 그래프의 해석이 달라짐   
- Precautions when creating a broken line graph   
  - The meaning of the graph can be interpreted differently depending on how much the scale of the Y-axis is subdivided   
    - Shrinking the scale clearly shows the trend of change   
    - When the scale is large, there appears to be little change   
  - Depending on the starting point of the X-axis, the meaning of the graph can be interpreted differently   
    - If the starting point is set aside from the axis with large changes, little change may appear   
    - The interpretation of the graph varies depending on what the starting point of the X-axis is in the time series data   
   
// 그래프는 효과적인 정보 전달도 가능하지만, 어떻게 작성했는가에 따라 왜곡된 정보를 전달할 수도 있음   
- Graphs can deliver effective information, but they can also deliver distorted information depending on how they are written   
   
<br />
### Frequency distribution table   
// 도수분포표   
   
// 겹치지 않는 몇 개의 범위 즉, 계급에 속한 관측치의 개수를 요약하여 작성한 표   
// 정성적 데이터뿐만 아니라 정량적 데이터에도 적용할 수 있음   
// 정량적 데이터에 대한 도수분포표를 작성할 때는 사용되는 범주 (계급) 정의에 세심한 고려가 필요함   
- A table summarizing the number of observations in the class (a few non-overlapping ranges)   
- Can be applied to quantitative data as well as qualitative data   
- When creating a frequency distribution table for quantitative data, careful consideration is required in the definition of the category (class) used   
   
#### How to create a frequency distribution table   
// 도수분포표 작성 방법   
   
// ① 데이터 수를 세고 데이터의 최대값과 최소값을 구함   
// ② 계급의 수 결정 : √n ± 2 ~ 3 (보통 5 ~ 20개)   
// ③ 계급의 폭 결정   
// - 계급의 폭 = <sup>(최대값 - 최소값)</sup> / <sub>계급의 수</sub>   
// ④ 계급의 경계값과 중앙값을 구함   
// - 첫 번째 하한경계값 = 최소값 - (<sup>측정의 최소단위</sup> / <sub>2</sub>)   
// - 첫 번째 상한경계값 = 하한경계값 + 계급의 폭   
// - 계급값 = <sup>(하한경계값 + 상한경계값)</sup> / <sub>2</sub>   
// ⑤ 도구분포표 작성   
- ① Count the number of data, obtain the maximum and minimum values of the data   
- ② Determining the number of classes : √n ± 2 ~ 3 (usually 5 to 20)   
- ③ the determination of the breadth of the class   
    - The breadth of the class = <sup>(maximum - minimum)</sup> / <sub>Number of classes</sub>   
- ④ Obtain the boundary and median values of the rank   
    - First lower bound = minimum - (<sup>minimum unit of measurement</sup> / <sub>2</sub>)   
    - First upper bound = lower bound + the breadth of the class   
    - Class value = <sup>(lower bound + upper bound)</sup> / <sub>2</sub>   
- ⑤ Create a frequency distribution table   
   
<br />
### Histogram   
// 히스토그램   
   
// 연속형 데이터에 대하여 데이터의 특징이나 분포 모양을 살펴볼 때 널리 이용되는 그래프   
// 수평축 위에 계급구간을 표시하고 그 위로 각 계급의 상대도수에 비례하는 넓이의 직사각형을 그린 것   
- Graphs that are widely used when looking at the features or distribution of data for continuous data   
- Displaying the class section on the horizontal axis and drawing a rectangle of area proportional to the relative number of classes on it   
   
// `[데이터] 탭 - [분석] 그룹 - [데이터분석] - [분석 도구] - [히스토그램]` 선택   
- Select `[Data] tab - [Analysis] group - [Data analysis] - [Analysis tool] - [Histogram]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelHistogram1.png)
   
// 여러 막대 중 하나를 선택하고 `마우스 오른쪽 단추 선택 - [단축메뉴] - [데이터 계열 서식]` 선택   
- Select one of several bars and select `Right-click selection - [short Menu] - [Data series format]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelHistogram2.png)
   
// `[데이터 계열 서식] - [계열 옵션] - [간격 너비(W)]` 에 0% 입력   
- Enter 0% in `[Data series format] - [Series options] - [Interval width (W)]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelHistogram3.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelHistogram4.png)
   
<br />
### Scatter plot   
// 산점도   
   
// 두 연속형 변수 사이의 관계를 그래프를 통해서 살펴보기 위해서 사용함   
// 두 변수 사이의 연관성 정도를 살펴보기 위한 분석의 첫 단계   
- Use the graph to examine the relationship between two continuous variables   
- The first step in the analysis to examine the degree of association between two variables is Scatter plot   
   
// `[삽입] 탭 - [차트] 그룹 - [분산형(X, Y) 또는 거품형 차트 삽입] - [분산형]` 선택   
- Select `[Insert] tab - [Chart] group - [Insert scatter (X, Y) or bubble chart] - [scatter chart]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelScatterPlot1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelScatterPlot2.png)
   
<br />
### Correlation analysis, Dependence analysis   
// 상관분석   
   
// 상관계수 (correlation)   
// - 두 변수간의 선형관계 (직선관계) 의 정도를 나타내주는 측도   
// - 상관계수 ρ (그리스문자, '로'라고 읽음) 는 -1 과 1 사이의 값을 가짐   
// - `-1 ≥ ρ ≥ 1`   
// -- \|ρ\| 의 값이 1에 가까울수록 두 변수는 강한 선형 연관성   
// -- \|ρ\| 의 값이 0에 가까울수록 두 변수는 약한 선형 연관성. 양의 상관관계   
// -- ρ이 -1 에 가까운 경우 음의 상관관계. 감소하는 성향   
// -- ρ이 1 에 가까운 경우 양의 상관관계. 증가하는 성향   
// -- ρ이 0 에 가까운 경우 상관관계가 거의 없이 골고루 분포되어 있음. 증가/감소 성향이 없음   
- Correlation   
  - A measure of the degree of linear relationship (straight line) between two variables   
  - The correlation coefficient ρ (read 'Roe' in Greek) has a value between -1 and 1   
  - `-1 ≥ ρ ≥ 1`   
    - The closer the value of \|ρ\| is to 1, two variables are strongly linearly associated   
    - The closer the value of \|ρ\| is to 0, the weaker linear associations between the two variables. A positive correlation   
    - Negative correlation if the ρ is close to -1. A decreasing tendency   
    - Positive correlation if the ρ is close to 1. A increasing tendency   
    - When the ρ is close to 0, it is evenly distributed with little correlation. No propensity to increase/decrease   
   
// 상관계수 추정치 계산   
- Calculate correlation coefficient estimates   
   
<span class="characterSpacing">ρ<sup>^</sup></span> &nbsp; = <sup>∑(x₁ - <span class="characterOverline">x</span>) · (y₁ - <span class="characterOverline">y</span>)</sup> / <sub>√∑(x₁ - <span class="characterOverline">x</span>)² · √∑(y₁ - <span class="characterOverline">y</span>)²</sub>
   
#### Correlation analysis procedures   
// 상관분석 절차   
   
// `[데이터] 탭 - [분석] 그룹 - [데이터 분석] - [분석 도구] - [상관 분석]` 선택   
- Select `[Data] tab - [Analysis] group - [Data analysis] - [Analysis tool] - [Correlation Analysis]`   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelCorrelation1.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelCorrelation2.png)
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelCorrelation3.png)
   
<br />
<cite>Source: Department of Computer Science, Korea National Open University</cite>
