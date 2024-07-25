---
layout: post
title:  "Introduction to Data Analysis: Continuous data"
date:   2024-05-06 09:00:00 +0900
categories: [Data Analysis]
---

<style>
    .characterOverline {
        text-decoration : overline;
    }
</style>

### Organizing continuous data   
// 연속형 자료의 정리   
   
// 중심측도 : 평균, 표본평균, 중앙값   
// 산포도측도 : 분산, 표준편차, 사분위수범위   
- Measure of Location : Mean, Sample Mean, Median   
- Measure of Dispersion : Variance, Standard Deviation, Interquartile Range   
   
<br />
### Measure of Location   
// 중심측도   
   
#### Measure of Location : Mean   
// 중심측도 : 평균 (mean)   
   
// 중심위치의 측도 : 평균, 중앙값, 최빈값 등이 있는데 이 중 가장 많이 사용되는 것이 평균(mean) 임   
- Measure of the central location : There are mean, median, and mode, and the most commonly used is mean   
   
// 평균 : 관측한 자료의 값들을 X<sub>1</sub>, X<sub>2</sub>, ..., X<sub>n</sub> 이라 할 때, 다음과 같이 정의됨   
// - 표본평균 <span class="characterOverline">X</span> = <sup>X<sub>1</sub>, X<sub>2</sub>, ..., X<sub>n</sub></sup> / <sub>n</sub> = <sup>∑X<sub>i</sub></sup> / <sub>n</sub>   
// -- 여기서 <span class="characterOverline">X</span>는 '엑스 바아'라고 읽음   
// -- 평균은 어느 한 자료값이 다른 값들보다 아주 크거나 작은 특이값 (outlier; 아웃라이어; 이상치) 의 영향을 많이 받음   
- Mean : When the values of the observed data are X<sub>1</sub>, X<sub>2</sub>, ..., X<sub>n</sub>, defined as follows   
  - Sample mean <span class="characterOverline">X</span> = <sup>X<sub>1</sub>, X<sub>2</sub>, ..., X<sub>n</sub></sup> / <sub>n</sub> = <sup>∑X<sub>i</sub></sup> / <sub>n</sub>   
    - Here, <span class="characterOverline">X</span> is read as 'Exbaa'   
    - The mean is heavily influenced by outliers in which one data value is much larger or smaller than the other   
   
// 예시 1   
// - 자료 : 5, 4, 7, 6, 8, 10, 11, 0, 7, 18 인 경우   
// -- 평균 <span class="characterOverline">X</span> = <sup>5 + 4 + ... + 7 + 18</sup> / <sub>10</sub> = <sup>76</sup> / <sub>10</sub> = 7.6   
- Example 1   
  - Data : 5, 4, 7, 6, 8, 10, 11, 0, 7, 18   
    - Mean <span class="characterOverline">X</span> = <sup>5 + 4 + ... + 7 + 18</sup> / <sub>10</sub> = <sup>76</sup> / <sub>10</sub> = 7.6   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,18)
> sum(aval)
[1] 76
> mean(aval)
[1] 7.6
```
   
// 예시 2   
// - 자료 : 5, 4, 7, 6, 8, 10, 11, 0, 7, 18, 100 인 경우   
// -- 평균 <span class="characterOverline">X</span> = <sup>5 + 4 + ... + 7 + 18 + 100</sup> / <sub>11</sub> = <sup>176</sup> / <sub>11</sub> = 16   
- Example 2   
  - Data : 5, 4, 7, 6, 8, 10, 11, 0, 7, 18, 100   
    - Mean <span class="characterOverline">X</span> = <sup>5 + 4 + ... + 7 + 18 + 100</sup> / <sub>11</sub> = <sup>176</sup> / <sub>11</sub> = 16   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,18,100)
> sum(aval)
[1] 176
> mean(aval)
[1] 16
```
   
#### Measure of Location : Trimmed mean   
// 중심측도 : 절사평균 (trimmed mean)   
   
// 10% 절사평균은 표본에서 가장 작은 값 10%와 가장 큰 값 10%를 빼고 계산된 평균을 말함   
- The 10% trimmed mean the mean calculated by subtracting the smallest values of 10% and largest values of 10% from the sample   
   
// 예시   
// - 자료 : 5, 4, 7, 6, 8, 10, 11, 0, 7, 18 인 경우   
// -- 자료를 크기순으로 정렬 : 0, 4, 5, 6, 7, 7, 8, 10, 11, 18   
// -- 10% 절사평균 <span class="characterOverline">X</span><sub>10</sub> = <sup>4 + 5 + 6 + 7 + 7 + 8 + 10 + 11</sup> / <sub>8</sub> = 7.25   
// -- 20% 절사평균 <span class="characterOverline">X</span><sub>20</sub> = <sup>5 + 6 + 7 + 7 + 8 + 10</sup> / <sub>6</sub> = 7.166667   
// -- 절사평균은 특이치에 영향을 덜 받는 효과   
- Example   
  - Data : 5, 4, 7, 6, 8, 10, 11, 0, 7, 18   
    - Sorting data in order of size : 0, 4, 5, 6, 7, 7, 8, 10, 11, 18   
    - 10% trimmed mean <span class="characterOverline">X</span><sub>10</sub> = <sup>4 + 5 + 6 + 7 + 7 + 8 + 10 + 11</sup> / <sub>8</sub> = 7.25   
    - 20% trimmed mean <span class="characterOverline">X</span><sub>20</sub> = <sup>5 + 6 + 7 + 7 + 8 + 10</sup> / <sub>6</sub> = 7.166667   
    - The trimmed mean is less susceptible to outliers   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,18)
> mean(aval, trim=0.10)
[1] 7.25
> mean(aval, trim=0.20)
[1] 7.166667
```
   
#### Measure of Location : Median   
// 중심측도 : 중앙값 (median)   
   
// 자료를 크기 순서로 나열할 때 중앙에 놓이는 값   
// 자료의 수를 n이라 할 때 <sup>(n + 1)</sup> / <sub>2</sub> 번째의 값을 중앙값으로 함   
// 이상치에 영향을 덜 받음 (robust to outlier)   
- Values center when listing data in order of size   
- When the number of data is n, the median value is <sup>(n + 1)</sup> / <sub>2</sub>   
- Less affected by outliers (Robust to outlier)   
   
// 예시 1   
// - 자료 : 5, 4, 7, 6, 8, 10, 11, 0, 7, 12, 13, 18, 14 인 경우 (n = 13)   
// -- 크기순 정렬 : 0, 4, 5, 6, 7, 7, 8, 10, 11, 12, 13, 14, 18   
// -- 중앙값 : <sup>(13 + 1)</sup> / <sub>2</sub> = 7 → 7번째 값은 8   
- Example 1   
  - Data : 5, 4, 7, 6, 8, 10, 11, 0, 7, 12, 13, 18, 14 \| (n = 13)   
    - Sort by size : 0, 4, 5, 6, 7, 7, 8, 10, 11, 12, 13, 14, 18   
    - Median : <sup>(13 + 1)</sup> / <sub>2</sub> = 7 → The 7th value is 8   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,12,13,18,14)
> median(aval)
[1] 8
```
   
// 예시 2   
// - 자료 : 5, 4, 7, 6, 8, 10, 11, 0, 7, 12, 13, 18, 14, 20 인 경우 (n = 14)   
// -- 크기순 정렬 : 0, 4, 5, 6, 7, 7, 8, 10, 11, 12, 13, 14, 18, 20   
// -- 중앙값 : <sup>(14 + 1)</sup> / <sub>2</sub> = 7.5 → 7번째와 8번째 값의 평균 값 <sup>(8 + 10)</sup> / <sub>2</sub> = 9   
- Example 2   
  - Data : 5, 4, 7, 6, 8, 10, 11, 0, 7, 12, 13, 18, 14, 20 \| (n = 14)   
    - Sort by size : 0, 4, 5, 6, 7, 7, 8, 10, 11, 12, 13, 14, 18, 20   
    - Median : <sup>(14 + 1)</sup> / <sub>2</sub> = 7.5 → The mean value of the 7th and 8th values is <sup>(8 + 10)</sup> / <sub>2</sub> = 9   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,12,13,18,14,20)
> median(aval)
[1] 9
```
   
// 예시 3   
// - 자료 : 5, 4, 7, 6, 8, 10, 11, 0, 9, 14 인 경우 (n = 10)   
// -- 크기순 정렬 : 0, 4, 5, 6, 7, 8, 9, 10, 11, 14   
// -- 중앙값 : <sup>(10 + 1)</sup> / <sub>2</sub> = 5.5 → 5번째와 6번째 값의 평균 값 <sup>(7 + 8)</sup> / <sub>2</sub> = 7.5   
- Example 3   
  - Data : 5, 4, 7, 6, 8, 10, 11, 0, 9, 14 \| (n = 10)   
    - Sort by size : 0, 4, 5, 6, 7, 8, 9, 10, 11, 14   
    - Median : <sup>(10 + 1)</sup> / <sub>2</sub> = 5.5 → The mean value of the 5th and 6th values is <sup>(7 + 8)</sup> / <sub>2</sub> = 7.5   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,9,14)
> median(aval)
[1] 7.5
```
   
// 예시 4   
// - 자료 : 5, 4, 7, 6, 8, 10, 11, 0, 9, 14, 100 인 경우 (n = 11)   
// -- 크기순 정렬 : 0, 4, 5, 6, 7, 8, 9, 10, 11, 14, 100   
// -- 중앙값 : <sup>(11 + 1)</sup> / <sub>2</sub> = 6번째 값은 8   
- Example 4   
  - Data : 5, 4, 7, 6, 8, 10, 11, 0, 9, 14, 100 \| (n = 11)   
    - Sort by size : 0, 4, 5, 6, 7, 8, 9, 10, 11, 14, 100   
    - Median : <sup>(11 + 1)</sup> / <sub>2</sub> = The 6th value is 8   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,9,14,100)
> median(aval)
[1] 8
```
   
#### Measure of Location : Mode   
// 중심측도 : 최빈값 (mode)   
   
// 자료 중 가장 빈도가 많은 값   
// 최빈값은 이산형 자료일 경우 도수분포표만 살펴보면 쉽게 구할 수 있음   
// 연속형 자료일 경우 자료를 몇 개의 계급구간으로 나누어 가장 도수가 높은 계급의 중간값을 최빈값으로 정하기도 함   
- The most frequent value of the data   
- The mode can be easily obtained by looking at the frequency distribution table for discrete data   
- In the case of continuous data, the data is divided into several class sections to set the median value of the highest class as the mode value   
   
// 예시   
// - 자료 : 13, 18, 13, 16, 14, 21, 13   
// -- 최빈값 mode = 13   
- Example   
  - Data : 13, 18, 13, 16, 14, 21, 13   
    - Mode = 13   
   
<br />
### Measure of Dispersion   
// 산포도측도   
   
// 자료가 흩어진 정도를 수치로서 측정하는 것을 산포도의 측도 (measure of dispersion) 라고 함   
// 대표적인 산포도의 측도 : 분산 및 표준편차   
// - 이 외에도 변동계수, 범위, 사분위수범위 등이 이용됨   
- Measure of dispersion is a measurement of the extent to which data is scattered   
- Representative measure of dispersion : Variance and standard deviation   
  - In addition, coefficient of variation, range, interquartile range, etc. are used   
   
#### Measure of Dispersion : Variance, Standard Deviation   
// 산포도측도 : 분산, 표준편차   
   
// 분산 (variance) : 각 자료값과 평균과의 거리를 제곱하여 합을 구한 후 이를 자료의 수로 나눈 측도   
// - 표본분산 s² = <sup>∑(x<sub>i</sub> - <span class="characterOverline">X</span>)²</sup> / <sub>n - 1</sub>   
// 자료가 평균에서 많이 흩어져 있으면 분산이 커지고, 자료가 평균 주위에 몰려 있으면 분산이 작게 됨   
- Variance : The sum is obtained by squaring the distance between each data value and the mean, and the result is divided by the number of data, a measure   
  - Sample Variance s² = <sup>∑(x<sub>i</sub> - <span class="characterOverline">X</span>)²</sup> / <sub>n - 1</sub>   
- If the data is scattered a lot from the mean, the variance increases, and if the data is concentrated around the mean, the variance becomes smaller   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,18)
> var(aval)
[1] 22.93333
```
   
// 표준편차 (standard deviation) : 분산의 제곱근   
// - 표본표준편차 s = √s²   
- Standard Deviation : Square root of Variance   
  - Sample Standard Deviation s = √s²   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,18)
> sd(aval)
[1] 4.788876
```
   
#### Measure of Dispersion : Coefficient of Variation, Range   
// 산포도측도 : 변동계수, 범위   
   
// 변동계수 (coefficient of variation) : 자료의 개수나 측정단위가 다른 두 개 이상의 자료에 대한 표준편차를 비교하는 것은 무의미함. 이러한 경우에 사용하는 측도가 표준편차를 평균으로 나눈 표준화 된 표준편차인 변동계수 (coefficient of variation) 를 사용함. 변이계수라고도 함   
// - 변동계수 = <sup>표준편차</sup> / <sub>평균</sub>   
// CV = <sup>s</sup> / <sub><span class="characterOverline">X</span></sub> × 100   
- Coefficient of Variation : It is meaningless to compare the standard deviation of two or more data with different numbers of data and different units of measurement. In this case, the coefficient of variation using a standardized measure that divides the standard deviation by the mean is used   
  - Coefficient of Variation = <sup>Standard Deviation</sup> / <sub>Mean</sub>   
- CV = <sup>s</sup> / <sub><span class="characterOverline">X</span></sub> × 100   
   
```r
> sd(score) / mean(score)
[1] 0.4237972
```
   
// 범위 (Range) : 최대값 - 최소값   
// - 범위는 계산하기가 간편하나 극단점 (특이값, 이상치) 이 있을 경우 올바른 산포의 측도가 되지 못함   
- Range : Maximum - Minimum   
  - Range is simple to calculate, but if there are extreme points (outliers), it does not measure the correct spread   
   
#### Measure of Dispersion : IQR (Interquartile Range)   
// 산포도측도 : 사분위수범위   
   
// p % 백분위수 (percentile) : 자료를 작은 것부터 큰 것까지 순서대로 늘어놓았을 때 p % 번째 자료를 말함   
// - 백분위수 중 25% 백분위수를 제1사분위수 (1st interquartile, Q₁ 로 표시) 라 부름   
// - 백분위수 중 50% 백분위수를 제2사분위수 (2st interquartile, Q₂ 로 표시 : 중앙값) 라 부름   
// - 백분위수 중 75% 백분위수를 제3사분위수 (3st interquartile, Q₃ 로 표시) 라 부름   
- p% percentile : It means the p%th data when the data are arranged in order from small to large   
  - Of the percentiles, the 25% percentile is called the first quartile (expressed in 1st interquartile, Q₁)   
  - Of the percentiles, the 50% percentile is called the second quartile (expressed in 2st interquartile, Q₂ : median)   
  - Of the percentiles, the 75% percentile is called the third quartile (expressed in 3st interquartile, Q₃)   
   
// 사분위수 범위 = 제3사분위수 - 제1사분위수   
- IQR (Interquartile Range) = 3st interquartile Q₃ - 1st interquartile Q₁   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,18)
> IQR(aval)
[1] 4.25
> quantile(aval, probs=c(0.25, 0.5, 0.75))
 25%  50%  75% 
5.25 7.00 9.50 
```
   
#### Example of Measure of Dispersion by R   
// R을 이용한 산포도측도 예시   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> aval = c(5,4,7,6,8,10,11,0,7,18)
> sd(aval)
[1] 4.788876
> IQR(aval)
[1] 4.25
> summary(aval)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   0.00    5.25    7.00    7.60    9.50   18.00 
> quantile(aval, probs=c(0.25, 0.5, 0.75))
 25%  50%  75% 
5.25 7.00 9.50 
```
   
// sd() 는 표준편차   
// IQR() 은 사분위수범위   
// summary() 는 여러가지를 한번에 구함   
// quantile() 는 사분위수 값 개별 산정   
- sd() is standard deviation   
- IQR() is interquartile range   
- summary() finds many things at once   
- quantile() calculates the interquartile values individually   
   
<br>
### Graph of Continuous Data   
// 연속형 자료의 그래프   
   
#### Graph of Continuous Data : Histogram   
// 연속형 자료 그래프 : 히스토그램   
   
// 연속인 자료를 일정한 계급으로 나누어 각 계급에 속한 도수들을 정리한 도수분포표를 이용하여 작성한 그래프   
// 히스토그램은 연속인 자료의 분포를 살펴볼 때 이용되는 그래프로서, 많은 양의 자료에 적합함   
- Graph prepared by dividing continuous data into certain classes and using a frequency distribution table that summarizes the frequencies belonging to each class   
- A histogram is a graph that is used to look at the distribution of consecutive data and is suitable for large amounts of data   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> a = rnorm(200)
> hist(a, col="RED")
> a = rnorm(2000)
> hist(a, col="RED")
```
   
// rnorm() 은 랜덤 넘버를 받음. rnorm(200) 은 랜덤 넘버를 200개 받음   
- rnorm() receives a random number. rnorm(200) receives 200 random numbers   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisHistogram.png)
   
#### Graph of Continuous Data : Stem-and-Leaf Plot   
// 연속형 자료 그래프 : 줄기-잎 그림   
   
// 분포의 대략적인 형태를 살펴보기 위하여 작성되는 그래프로 군집의 존재여부, 집중도가 높은 구간, 대칭성의 여부, 자료의 범위 및 산포, 특이값의 존재 여부 등을 파악하는데 이용됨   
- It is a graph created to examine the approximate shape of the distribution and is used to determine the existence of clusters, sections with high concentration, symmetry, range and distribution of data, and the existence of outliers   
   
// 예시   
// - 점수자료 : 54, 57, 55, 23, 51, 64, 90, 51, 52, 43, 15, 10, 82, 74, 54, 78, 37, 73, 52, 48, 41, 33, 52, 30, 41, 51, 18, 39, 46, 28, 53, 44, 46, 56, 28, 58, 29, 58, 67, 35, 25, 38, 61, 53, 23, 73, 69, 47, 41, 45, 77, 56, 89, 28, 54, 99, 10, 43, 35, 24, 21, 23, 67, 14, 53   
- Example   
  - Score data : 54, 57, 55, 23, 51, 64, 90, 51, 52, 43, 15, 10, 82, 74, 54, 78, 37, 73, 52, 48, 41, 33, 52, 30, 41, 51, 18, 39, 46, 28, 53, 44, 46, 56, 28, 58, 29, 58, 67, 35, 25, 38, 61, 53, 23, 73, 69, 47, 41, 45, 77, 56, 89, 28, 54, 99, 10, 43, 35, 24, 21, 23, 67, 14, 53   
   
// RStudio 에서 실행   
- Run in RStudio   
   
// 파일 업로드하여 실행   
- Upload and run a file   
   
```r
> score = scan("c:/data/dataintro/score.txt")
Read 65 items
> stem(score)

  The decimal point is 1 digit(s) to the right of the |

  1 | 00458
  2 | 1333458889
  3 | 0355789
  4 | 11133456678
  5 | 111222333444566788
  6 | 14779
  7 | 33478
  8 | 29
  9 | 09
> stem(score, scale=2)

  The decimal point is 1 digit(s) to the right of the |

  1 | 004
  1 | 58
  2 | 13334
  2 | 58889
  3 | 03
  3 | 55789
  4 | 111334
  4 | 56678
  5 | 111222333444
  5 | 566788
  6 | 14
  6 | 779
  7 | 334
  7 | 78
  8 | 2
  8 | 9
  9 | 0
  9 | 9
```
   
// 자료 직접 입력하여 실행   
- Enter and run data directly   
   
```r
> score = c(54, 57, 55, 23, 51, 64, 90, 51, 52, 43, 15, 10, 82, 74, 54, 78, 37, 73, 52, 48, 41, 33, 52, 30, 41, 51, 18, 39, 46, 28, 53, 44, 46, 56, 28, 58, 29, 58, 67, 35, 25, 38, 61, 53, 23, 73, 69, 47, 41, 45, 77, 56, 89, 28, 54, 99, 10, 43, 35, 24, 21, 23, 67, 14, 53)
> stem(score)

  The decimal point is 1 digit(s) to the right of the |

  1 | 00458
  2 | 1333458889
  3 | 0355789
  4 | 11133456678
  5 | 111222333444566788
  6 | 14779
  7 | 33478
  8 | 29
  9 | 09
> ?stem
> stem(score, scale=2)

  The decimal point is 1 digit(s) to the right of the |

  1 | 004
  1 | 58
  2 | 13334
  2 | 58889
  3 | 03
  3 | 55789
  4 | 111334
  4 | 56678
  5 | 111222333444
  5 | 566788
  6 | 14
  6 | 779
  7 | 334
  7 | 78
  8 | 2
  8 | 9
  9 | 0
  9 | 9
```
   
#### Graph of Continuous Data : Box plot   
// 연속형 자료 그래프 : 상자그림   
   
// 다섯숫자요약 (five-number summary) : 최소값, 제1사분위수, 중앙값,  제3사분위수, 최대값   
- Five-number summary : Minimum, 1st interquartile, Median, 3st interquartile, Maximum   
   
// 상자그림 (box plot) : 다섯숫자요약을 특이값과 함께 그래프로 표현한 것으로서 분포의 상태, 특이값의 유무, 여러 집단의 수치자료를 비교하고자 할 때 유용하게 이용됨   
- Box plot : It is a graph of a five-number summary with outliers, and is useful when comparing the state of the distribution, the presence or absence of outliers, and numerical data of several groups   
   
// 상자그림을 그리는 방법   
// ① 다섯숫자요약을 구한다   
// ② 제1사분위수, 제3사분위수에 해당하는 수직선상의 위치에 네모 상자의 양 끝이 오게하고, 상자내의 중앙값에 해당되는 위치에 가로지르는 막대 표시를 한다   
// ③ 안울타리 (inner fence) 값을 구한다   
// - IF<sub>L</sub> = 제1사분위수(Q₁) - 1.5 x IQR   
// - IF<sub>U</sub> = 제3사분위수(Q₃) + 1.5 x IQR   
// - 단, IQR = Q₃ - Q₁   
// ④ 안울타리의 안쪽에 있으면서 경계에 가장 가까운 인접값 (adjacent value, AV) 를 찾아 상자의 양끝을 연결한다   
// ⑤ 안울타리 바깥에 있는 자료점을 특이값으로 간주하고 "O" 또는 "*"으로 표시한다   
- How to draw a box plot   
    - ① Find the five-number summary   
    - ② Both ends of the square box come to the position on the vertical line corresponding to the first and third interquartiles. Mark the bar across the median value in the box   
    - ③ Find the inner fence value   
        - IF<sub>L</sub> = first interquartile (Q₁) - 1.5 x IQR   
        - IF<sub>U</sub> = third interquartile (Q₃) + 1.5 x IQR   
        - However, IQR = Q₃ - Q₁   
    - ④ Connect both ends of the box by finding the nearest adjacent value (AV) that is located inside the fence   
    - ⑤ Consider the data point outside the fence as an outlier and mark it as "O" or "*"   
   
// RStudio 에서 실행   
- Run in RStudio   
   
```r
> boxplot(score)
```
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataAnalysisBoxPlot.png)
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
