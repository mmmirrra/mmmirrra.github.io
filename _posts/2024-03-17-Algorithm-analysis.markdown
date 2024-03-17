---
layout: post
title:  "Algorithm: Running time, Asymptotic Analysis, Recurrence Relation"
date:   2024-03-17 09:00:00 +0900
categories: [Algorithm]
---

### Algorithm Analysis   
// 알고리즘 분석   
   
#### Accuracy Analysis   
// 정확성 분석   
   
// 유효한 입력에 대해 유한시간 내에 정확한 결과의 생성 여부   
// - 수학적 기법을 사용한 이론적인 증명 과정   
- Whether to generate accurate results in finite time for valid inputs   
  - A theoretical process of proof using mathematical techniques   
   
#### Efficiency Analysis   
// 효율성 분석   
   
// 알고리즘 수행에 필요한 컴퓨터 자원의 양을 측정/평가   
- Measure/assess the amount of computer resources required to perform an algorithm   
   
// 공간 복잡도   
// - 메모리의 양 = 정적 공간 + 동적 공간   
// 시간 복잡도   
// - 수행시간 = 알고리즘의 실행에서부터 완료까지 걸리는 시간   
- space complexity   
  - Amount of memory = static space + dynamic space   
- time complexity   
  - Running time = The time from execution to completion of the algorithm   
   
<br />
### Time Complexity   
// 시간 복잡도   
   
#### How to run it on a computer to measure the actual running time?   
// 컴퓨터에서 실행시켜 실제 수행시간을 측정하는 방법?   
   
// 실행 환경에 종속적이므로 일반성이 결여된 방법   
// - 컴퓨터 속도, 구현에 사용된 프로그래밍 언어, 프로그램 작성 방법, 컴파일러의 효율성 등에 따라 시간이 달라짐   
- How the execution environment is dependent and therefore lacks generality   
  - Time varies depending on the speed of the computer, the programming language used in the implementation, how the program is written, the efficiency of the compiler, etc.   
   
#### Algorithm running time   
// 알고리즘 수행시간   
   
// 알고리즘 수행시간 = ∑{각 문장(연산)이 수행되는 횟수}   
- Algorithm running time = ∑ {number of times each expression (operation) is performed}   
   
// 수행시간에 영향을 미치는 요인   
// - 입력 크기   
// -- "입력되는 데이터의 크기", "문제가 해결하려는 대상이 되는 개체의 개수"   
// --- 예시 : 리스트 원소의 개수, 행렬의 크기, 그래프의 정점의 수 등   
// - 입력 데이터의 상태   
- Factors affecting running time   
  - Input Size   
    - "Size of data input", "Number of objects the problem is trying to resolve"   
      - For example: the number of list elements, the size of the matrix, the number of vertices in the graph, etc.   
  - Status of input data   
   
#### The larger the input size n, the more time it takes to running   
// 입력 크기 n이 커질수록 수행시간도 증가   
   
// 단순히 단위 연산이 수행되는 개수의 합으로 표현하는 것은 부적절   
// - 입력 크기 n의 함수 f(n)으로 표현   
- It is inappropriate to express simply as the sum of the number of unit operations performed   
  - Expressed as a function f(n) of input size n   
   
#### Dependent on the state of the input data   
// 입력 데이터의 상태에 종속적   
   
// 평균 수행시간 → A(n) = ∑<sub>I∈<i>S</i><sub>n</sub></sub>P(I)t(I)   
// - <i>S</i><sub>n</sub> : 크기 n인 입력들의 집합   
// - P(I) : 입력 I가 발생할 확률   
// - t(I) : 입력 I일 때 알고리즘의 수행시간   
- Average running time → A(n) = ∑<sub>I∈<i>S</i><sub>n</sub></sub>P(I)t(I)   
  - <i>S</i><sub>n</sub> : Set of inputs of size n   
  - P(I) : The probability that input I will occur   
  - t(I) : Time to run the algorithm when input I   
   
// 최선 수행시간 → B(n) = min<sub>I∈<i>S</i><sub>n</sub></sub>t(I)   
- Best running time → B(n) = min<sub>I∈<i>S</i><sub>n</sub></sub>t(I)   
   
// 최악 수행시간 → W(n) = max<sub>I∈<i>S</i><sub>n</sub></sub>t(I)   
- Worst running time → W(n) = max<sub>I∈<i>S</i><sub>n</sub></sub>t(I)   
   
#### Example of running time of the algorithm   
// 알고리즘의 수행시간 예시   
   
```c
// A[0...n-1]
// n : Input Array and Number of Data
SumAverage(A[], n)
{
    sum = 0;    // 1 time
    i = 0;    // 1 time
    while(i < n) {    // n + 1 times
      sum = sum + A[i];   // n time
      i = i + 1;    // n time
    }
    average = sum / n;    // 1 time
    print sum, average;   // 1 time
}

// 알고리즘의 수행시간 T(n) = 3n + 5 → 점근성능 O(n)
// - Algorithm run time T(n) = 3n + 5 → Asymptotic analysis O(n)
```
   
<br />
### Asymptotic Analysis   
// 점근성능   
   
// 입력 크기 n이 무한히 커짐에 따라 결정되는 성능   
- Performance determined as input size n grows infinitely   
   
||expression 1|expression 2|
|:---|:---:|:---:|
||f<sub>1</sub>(n) = 10n + 9|f<sub>2</sub>(n) = <sup>n²</sup>/<sub>2</sub> + 3n|
|n=5|59|27.5|
|n=10|109|80|
|n=15|159|157.5|
|<b>n=16</b>|<b>169</b>|<b>176</b>|
|<b>n=20</b>|<b>209</b>|<b>260</b>|
|...|...|...|
   
||expression 1|
|:---|:---:|
||f<sub>3</sub>(n) = 2n² + 5n + 200|
|n=1|2 + 5 + 200 = <b>207</b>|
|n=5|50 + 25 + 200 = <b>275</b>|
|n=10|200 + 50 + 200 = <b>450</b>|
|n=20|800 + 100 + 200 = <b>1,100</b>|
|...|...|
|n=1000|2,000,000 + 5,000 + 200 = <b>2,005,200</b>|
   
#### How to determine asymptotic analysis   
// 점근성능의 결정 방법   
   
// 입력 크기가 충분히 커짐에 따라 함수값에 가장 큰 영향을 미치는 차수를 찾음   
// 수행시간의 다항식 함수에서 최고차항만을 계수 없이 취해서 표현   
// - 수행시간의 정확한 값이 아닌 어림값   
// -- 수행시간의 증가 추세를 파악하는 것이 쉬움   
// -- 알고리즘 간의 우열을 따질 때 유용   
- Finds the degree that has the greatest effect on the function value as the input size becomes large enough   
- Expression by taking the highest degree term without coefficient in the polynomial function of the running time   
  - An approximation that is not an exact value of the running time   
    - It's easy to understand the trend of increasing running time   
    - Useful in determining the superiority and inferiority between algorithms   
   
<br />
### Notation of asymptotic analysis   
// 점근성능의 표기법   
   
#### Definition of 'Big-oh' asymptotic upper limit   
// 'Big-oh' 점근적 상한에 대한 정의   
   
// 함수 f와 g를 각각 양의 정수를 갖는 함수라 하자   
// 어떤 양의 상수 c와 n<sub>0</sub>이 존재하여   
// 모든 n ≥ n<sub>0</sub> 에 대하여 f(n) ≤ c · g(n) 이면 f(n) = O(g(n)) 이다   
// f(n) = O(g(n)) : 최악의 수행시간   
- Let f and g be functions with positive integers, respectively   
- There are certain positive constants c and n<sub>0</sub>   
- For all n ≥ n<sub>0</sub>, if f(n) ≤ c · g(n), then f(n) = O(g(n))   
- f(n) = O(g(n)) : Worst running time   
   
#### Definition of 'Big-Omega' asymptotic lower bound   
// 'Big-omega' 점근적 하한에 대한 정의   
   
// 함수 f와 g를 각각 양의 정수를 갖는 함수라 하자   
// 어떤 양의 상수 c와 n<sub>0</sub>이 존재하여   
// 모든 n ≥ n<sub>0</sub> 에 대하여 f(n) ≥ c · g(n) 이면 f(n) = Ω(g(n)) 이다   
// f(n) = Ω(g(n)) : 최선의 수행시간   
- Let f and g be functions with positive integers, respectively   
- There are certain positive constants c and n<sub>0</sub>   
- For all n ≥ n<sub>0</sub>, if f(n) ≥ c · g(n), then f(n) = Ω(g(n))   
- f(n) = Ω(g(n)) : Best running time   
   
#### Definition of 'Big-theta' asymptotic upper and lower limits   
// 'Big-theta' 점근적 상하한에 대한 정의   
   
// 함수 f와 g를 각각 양의 정수를 갖는 함수라 하자   
// 어떤 양의 상수 c<sub>1</sub>, c<sub>2</sub>와 n<sub>0</sub>이 존재하여   
// 모든 n ≥ n<sub>0</sub> 에 대하여 c<sub>1</sub> · g(n) ≤ f(n) ≤ c<sub>2</sub> · g(n) 이면 f(n) = θ(g(n)) 이다   
// f(n) = θ(g(n)) : 최선과 최악 사이의 수행시간   
- Let f and g be functions with positive integers, respectively   
- There are certain positive constants c<sub>1</sub>, c<sub>2</sub>, and n<sub>0</sub>   
- For all n ≥ n<sub>0</sub>, if c<sub>1</sub> · g(n) ≤ f(n) ≤ c<sub>2</sub> · g(n), then f(n) = θ(g(n))   
- f(n) = θ(g(n)) : best-to-worst running time   
   
<br />
#### Example 1   
// 예시 1   
   
Function   
- f(n) = 3n + 3   
- g(n) = n   
   
// c = 5, n<sub>0</sub> = 2 이면   
// n ≥ 2 인 모든 n에 대하여   
// f(n) ≤ c · g(n) 이면, 즉 3n + 3 ≤ 5 · n 을 만족하면   
// f(n) = O(g(n)) = O(n)이다   
- if c = 5, n<sub>0</sub> = 2   
  - For all n with n ≥ 2   
  - If f(n) ≤ c · g(n), that is, if 3n + 3 ≤ 5 · n is satisfied   
  - f(n) = O(g(n)) = O(n)   
   
// c = 3, n<sub>0</sub> = 1 이면   
// n ≥ 1 에 대하여   
// f(n) ≥ c · g(n) 이면, 즉 3n + 3 ≥ 3 · n 을 만족하면   
// f(n) = Ω(g(n)) = Ω(n) 이다   
- if c = 3, n<sub>0</sub> = 1   
  - about n ≥ 1   
  - If f(n) ≥ c · g(n), that is, if 3n + 3 ≥ 3 · n is satisfied   
  - f(n) = Ω(g(n)) = Ω(n)   
   
// f(n) = O(n) 이면서 f(n) = Ω(n) 이면   
// f(n) = θ(n) 이다   
- If f(n) = O(n) and f(n) = Ω(n)   
  - f(n) = θ(n)   
   
// O(n), Ω(n), θ(n) 에서 n은 f(n)의 최고차항인 n임   
- In O(n), Ω(n), and θ(n), n is the highest degree term of f(n)   
   
<br />
#### Example   
// 예시 2   
   
Function   
- f(n) = 3n³ + 3n - 1   
- g(n) = n³   
   
// c = 7, n<sub>0</sub> = 1 이면   
// n ≥ 1 에 대해서   
// f(n) ≤ c · g(n) 이면, 즉 3n³ + 3n - 1 ≤ 5 · n³ 을 만족하면   
// f(n) = O(g(n)) = O(n³)이다   
- if c = 7, n<sub>0</sub> = 1   
  - about n ≥ 1   
  - If f(n) ≤ c · g(n), that is, if 3n³ + 3n - 1 ≤ 5 · n³ is satisfied   
  - f(n) = O(g(n)) = O(n³)   
   
// c = 2, n<sub>0</sub> = 2 이면   
// n ≥ 2 에 대하여   
// f(n) ≥ c · g(n) 이면, 즉 3n³ + 3n - 1 ≥ 2 · n³ 을 만족하면   
// f(n) = Ω(g(n)) = Ω(n³) 이다   
- if c = 2, n<sub>0</sub> = 2   
  - about n ≥ 2   
  - If f(n) ≥ c · g(n), that is, if 3n³ + 3n - 1 ≥ 2 · n³ is satisfied   
  - f(n) = Ω(g(n)) = Ω(n³)   
   
// f(n) = O(n³) 이면서 f(n) = Ω(n³) 이면   
// f(n) = θ(n³) 이다   
- If f(n) = O(n³) and f(n) = Ω(n³)   
  - f(n) = θ(n³)   
   
// O(n³), Ω(n³), θ(n³) 에서 n³은 f(n)의 최고차항인 n³임   
- In O(n³), Ω(n³), and θ(n³), n³ is the highest degree term of f(n)   
   
<br />
#### Size relationship of operation time between key O-notation   
// 주요 O-표기 간 연산 시간의 크기 관계   
   
||expression 1|expression 2|expression 3|
|:---:|:---:|:---:|:---:|
||f<sub>1</sub>(n) = 10n + 9|f<sub>2</sub>(n) = <sup>n²</sup>/<sub>2</sub> + 3n|f<sub>3</sub>(n) = 3n³ + 3n + 2|
|Asymptotic analysis|O(n)|O(n²)|O(n³)|
   
|O(1) < O(logn) < O(n) < O(nlogn) < O(n²) < O(n³) < O(2n)|
|:---:|
|// 상수 시간 < 로그 시간 < 선형 시간 < 로그 선형 시간 < 제곱 시간 < 세제곱 시간 < 지수 시간|
|Constant time < Logarithmic time < Linear time < Linearithmic time < Quadratic time < Cubic time < Exponential time|
|// ← 효율적 \| 비효율적 →<br />// ← 시간이 적게걸림 \| 시간이 오래걸림 →<br />// ← 가장 좋음 \| 가장 좋지 않음 →|
|← Efficient \| Inefficient →<br />← Less time \| Long time →<br />← Best \| Worst →|
   
<br />
### Increasing trend of operation time according to Big-O function   
// 빅오 함수에 따른 연산 시간의 증가 추세   
   
|O(logn)|O(n)|O(nlogn)|O(n²)|O(n³)|O(2n)|
|:---:|:---:|:---:|:---:|:---:|:---:|
|// 로그 시간|// 선형 시간|// 로그 선형 시간|// 제곱 시간|// 세제곱 시간|// 지수 시간|
|Logarithmic time|Linear time|Linearithmic time|Quadratic time|Cubic time|Exponential time|
|0|1|0|1|1|2|
|1|2|2|4|8|4|
|2|4|8|16|64|16|
|3|8|24|64|512|256|
|4|16|64|256|4,096|65,536|
|5|32|160|1,024|32,768|4,294,967,296|
   
<br />
### Finding the time complexity of an algorithm   
// 알고리즘의 시간 복잡도 구하기   
   
// 알고리즘의 시간 복잡도를 구하려면   
// - 기본 연산의 수행 횟수의 합 f(n)을 구한 후,   
// - f(n) = O(g(n)) 을 만족하는 최소 차수의 함수 g(n)을 찾음   
// -- 최소 차수의 함수 g(n) == f(n)의 최고 차수
- To find the time complexity of an algorithm   
  - After calculating the sum f(n) of the number of runnings of the basic operation,   
  - Find function g(n) of minimum degree that satisfies f(n) = O(g(n))   
    - Minimum degree of function g(n) == highest degree term of f(n)   
   
// 실용적인 접근 방법   
// - 알고리즘의 모든 문장이 아닌 루프의 반복 횟수만을 조사하여 최고 차수를 시간 복잡도로 취합   
// - → O(최고차수)   
- Practical approach methods  
  - By examining only the number of iterations of loops rather than all expressions in the algorithm, the highest degree term is taken as time complexity   
  - → O(highest degree term)   
   
```c
i = 1;    // 1 time
while(i <= n) {    // n + 1 times
    x = x + 1;    // 1 time
    i = i + 1;    // 1 time
}

// → f(n) = 3n + 2

// 반복문에서만 찾으면 n + 1번 수행하므로
// - If the number of times to running is found only in the iteration statement, n + 1 times
// → O(n)
```
   
```c
count = 0;    // 1 time
for(i = 0; i < n; i++)    // n + 1 times
    for(j = 0; j < n; j++)    // n + 1 times
        count ++;   // n² times
print count;    // 1 time

// → f(n) = n² + 2n + 4

// 반복문에서만 찾으면 n + 1번, n + 1번 수행 → n x n번 수행하므로
// - If the number of times to running is found only in the iteration statement, n + 1 times, n + 1 times → n x n times 
// → O(n²)
```
   
<br />
### Recursion Algorithm   
// 순환 알고리즘, 재귀 알고리즘   
   
// 알고리즘의 수행 과정에서 자기 자신의 알고리즘을 다시 수행하는 형태   
// 순환 알고리즘의 수행시간은 점화식 형태로 정의되며, 폐쇄형을 구해서 표현   
// 분할정복 방법이 적용된 알고리즘은 기본적으로 순환 알고리즘 형태를 가짐   
- the form of re-performing one's own algorithm in the course of performing an algorithm   
- The running time of the cyclic algorithm is defined in the recurrence relation, and the closed form is obtained and expressed   
- Algorithms to which the Divide-and-Conquer method is applied basically have a cyclic algorithm form   
   
```c
BinarySearch(A[], key, Left, Right) {
    if (Left > Right) return (-1);    // 1 time

    mid = ⌊(Left + Right)⌋ / 2;   // 1 time

    // Search Success
    if(A[Mid] == key) return (Mid);   // 1 time
    // Circular call when search fails - number of runnings unknown
    else if(key < A[Mid]) BinarySearch(A, key, Left, Mid - 1)
        else BinarySearch(A, key, Mid + 1, Right);
}
```
   
// 이진 탐색의 수행 시간 T(n) = T(<sup>n</sup>/<sub>2</sub>) + O(1), T(1) = c<sub>1</sub>   
// O(1) 은 상수 수행 시간   
// T(<sup>n</sup>/<sub>2</sub>) 은 if문 수행 시간 : else...if 와 else 중 하나만 수행하므로 n의 <sup>1</sup>/<sub>2</sub> 임   
- Time to running binary search T(n) = T(<sup>n</sup>/<sub>2</sub>) + O(1), T(1) = c<sub>1</sub>   
- O(1) is constant running time   
- T(<sup>n</sup>/<sub>2</sub>) is if statement running time : <sup>1</sup>/<sub>2</sub> of n since only one of else...if and else is performed   
   
<br />
#### Obtaining the closed type of recurrence relation   
// 점화식의 폐쇄형 구하기   
   
// Recurrence Relation   
T(n) = T(<sup>n</sup>/<sub>2</sub>) + c<sub>2</sub>   
T(1) = c<sub>1</sub>   
   
// The process of solving a problem   
T(n) = T(<sup>n</sup>/<sub>2</sub>) + c<sub>2</sub>   
= T(<sup>n</sup>/<sub>4</sub>) + c<sub>2</sub> + c<sub>2</sub> = T(<sup>n</sup>/<sub>2²</sub>) + 2c<sub>2</sub>  
= T(<sup>n</sup>/<sub>8</sub>) + c<sub>2</sub> + c<sub>2</sub> + c<sub>2</sub> = T(<sup>n</sup>/<sub>2³</sub>) + 3c<sub>2</sub>   
...   
= T(<sup>n</sup>/<sub>2<sup>k-1</sup></sub>) + (k - 1)c<sub>2</sub>   
= T(<sup>n</sup>/<sub>2<sup>k</sup></sub>) + kc<sub>2</sub>   
= T(1) + kc<sub>2</sub> (Defined only when n = 2<sup>k</sup>, k = log<sub>2</sub>n)   
= c<sub>1</sub> + c<sub>2</sub>log<sub>2</sub>n   
= θ(log<sub>2</sub>n)   
   
<br />
#### Basic recurrence relation and closed type   
// 기본 점화식과 폐쇄형   
   
1. Basic recurrence relation T(n) =    
  θ(1), n = 1   
  T(n - 1) + θ(1), n ≥ 2   
  → Closed type T(n) = θ(n)   
2. Basic recurrence relation T(n) =    
  θ(1), n = 1   
  T(n - 1) + θ(n), n ≥ 2   
  → Closed type <b>T(n) = θ(n²)</b> (※ Quick Sort - Worst Case)   
3. Basic recurrence relation T(n) =    
  θ(1), n = 1   
  T(<sup>n</sup>/<sub>2</sub>) + θ(1), n ≥ 2   
  → Closed type <b>T(n) = θ(logn)</b> (※ binary search)   
4. Basic recurrence relation T(n) =   
  θ(1), n = 1   
  T(<sup>n</sup>/<sub>2</sub>) + θ(n), n ≥ 2   
  → Closed type T(n) = θ(n)   
5. Basic recurrence relation T(n) =    
  θ(1), n = 1   
  2T(<sup>n</sup>/<sub>2</sub>) + θ(1), n ≥ 2   
  → Closed type T(n) = θ(n)   
6. Basic recurrence relation T(n) =   
  θ(1), n = 1   
  2T(<sup>n</sup>/<sub>2</sub>) + θ(n), n ≥ 2   
  → Closed type <b>T(n) = θ(nlogn)</b> (※ Merger sort. Quick sort - Best Case)   
   
<br />
#### Importance of Efficient Algorithm   
// 효율적인 알고리즘의 중요성   
   
// 입력 크기가 커질수록 수행시간의 차이가 확연   
// → 효율적인 알고리즘의 설계/선택이 중요   
- The larger the input size, the greater the difference in running time   
- → Design/selection of efficient algorithms is important   
   
// Time to running unit operation = 1ns   
// 1ns = 10<sup>-9</sup>seconds   
// 1㎲ = 10<sup>-6</sup>seconds   
// 1ms = 10<sup>-3</sup>seconds   
   
|n|f(n)=logn|f(n)=n|f(n)=nlogn|f(n)=n²|f(n)=n³|f(n)=2<sup>n</sup>|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|10|0.003 ㎲|0.01 ㎲|0.033 ㎲|0.10 ㎲|1.0 ㎲|1 ㎲|
|20|0.004 ㎲|0.02 ㎲|0.086 ㎲|0.40 ㎲|8.0 ㎲|1 ms|
|30|0.005 ㎲|0.03 ㎲|0.147 ㎲|0.90 ㎲|27.0 ㎲|1 s|
|40|0.005 ㎲|0.04 ㎲|0.213 ㎲|1.60 ㎲|64.0 ㎲|18.3 minutes|
|50|0.006 ㎲|0.05 ㎲|0.282 ㎲|2.50 ㎲|125.0 ㎲|13 days|
|10<sup>2</sup>|0.007 ㎲|0.10 ㎲|0.664 ㎲|10.00 ㎲|1.0 ms| 4 x 10<sup>13</sup>years|
|10<sup>3</sup>|0.010 ㎲|1.00 ㎲|9.966 ㎲|1.00 ms|1.0 s|Uncountable|
|10<sup>4</sup>|0.013 ㎲|10.00 ㎲|130.000 ㎲|100.00 ms|16.7 minutes|Uncountable|
|10<sup>5</sup>|0.017 ㎲|0.10 ms|1.670 ms|10.00 s|11.6 days|Uncountable|
|10<sup>6</sup>|0.020 ㎲|1.00 ms|19.930 ms|16.70 minutes|31.7 years|Uncountable|
|10<sup>7</sup>|0.023 ㎲|0.01 s|2.660 s|1.16 days|31,709 years|Uncountable|
|10<sup>8</sup>|0.027 ㎲|0.10 s|26.60 s|115.70 days|3.17 x 10<sup>7</sup> years|Uncountable|
|10<sup>9</sup>|0.030 ㎲|1.00 s|29.900 s|31.70 years|Uncountable|Uncountable|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
