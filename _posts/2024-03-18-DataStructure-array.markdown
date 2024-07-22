---
layout: post
title:  "Data Structure: Array"
date:   2024-03-18 09:00:00 +0900
categories: [Data Structure]
---

### Definition of Array   
// 배열의 정의   
   
// 일정의 차례나 간격에 따라 벌여 놓음 (사전적 정의)   
// '차례' (순서) 와 관련된 기본적인 자료구조   
- Set up according to the order or interval of a schedule (dictionary definition)   
- Basic data structure related to order   
   
// 원소의 메모리 공간 (메인 메모리, DDR) 의 물리적인 위치를 '순서'적으로 결정하는 특징   
// 배열의 순서는 메모리 공간에서 저장되는 '원소값의 물리적 순서'   
- Features that 'orderly' determine the physical location of an element's memory space (Main memory, DDR)   
- The order of the array is the 'physical order of element values' stored in memory space   
   
// 인덱스와 원소값 (`<index, value>`) 의 쌍으로 구성된 집합   
- A set of pairs of index and element values (`<index, value>`)   
   
#### Meaning of an array   
// 배열의 의미   
   
// '호수' (인덱스) 로 표현되는 순서를 갖는 '아파트'   
// - 호수 : 인덱스 / 거주민 : 원소값   
- 'Apartment' with an order expressed as 'Number' (index)   
  - Number : Index / Resident : Element value   
   
// 원소들이 모두 같은 자료형과 같은 크기의 기억 공간을 가짐   
// 배열의 인덱스값을 이용해서 원소값에 접근하기 때문에 직접 접근 (direct access) 이 가능함   
- All elements have the same data type and the same size of memory   
- Direct access is possible because the element values are accessed using the index values of the array   
   
// 배열의 인덱스값 : 추상화된 값 = 컴퓨터의 내부구조나 메모리 주소와 무관하게 개발자에게 개념적으로 정의됨   
// 메모리 주소값은 실제 메모리의 물리적인 위치값   
// 배열의 (추상화된) 인덱스값은 프로그래밍 언어와 컴파일 과정을 통해 메모리 주소값과 연결됨   
- Index value of array : Abstract value = conceptually defined by the developer regardless of the internal structure or memory address of the computer   
- The memory address value is the physical location value of the actual memory   
- Index values in an array (abstract) are associated with memory address values through programming languages and compilation processes   
   
// 인덱스와 주소값의 관계 (보통 배열의 인덱스는 0부터 시작)   
- The relationship between index and address value (usually the index in the array starts at 0)   
   
||Address value|Value|Index||
|:---:|:---:|:---:|:---:|:---:|
|Computer|00ffff00<br />00ffff04<br />00ffff08<br />00ffff0c<br />00ffff10|100<br />200<br />300<br />400<br />500|1<br />2<br />3<br />4<br />5|Developer|
   
<br />
### Abstract data type for array   
// 배열의 추상 자료형   
   
// 추상자료형   
// - 객체 및 관련된 연산의 정의로 구성됨   
// - 자료구조 구현전의 설계 단계   
- Abstract data type   
  - Consists of definitions of object and associated operations   
  - Design stage prior to data structure implementation   
   
// 자료형   
// - 메모리 저장 할당을 위한 변수 선언   
// - 자료구조의 구현 단계 (프로그래밍 언어를 이용한 선언)   
- Data type   
  - Declare Variables for Memory Storage Allocation   
  - Implementation phase of data structure (declaration using programming language)   
   
#### ADT Array object : `<i∈Index, e∈Element>` Set of Pairs   
// ADT Array 객체 : `<i∈Index, e∈Element>` 쌍들의 집합   
   
// Index : 순서를 나타내는 원소의 유한집합   
// Element : 자료형이 같은 원소의 집합   
- Index : a finite set of ordered elements   
- Element : a set of elements of the same data type   
   
#### Operation : The following operations are defined for all a, item, and n of `a∈Array; i∈Index; item∈Element; n∈Integer`   
// 연산 : `a∈Array; i∈Index; item∈Element; n∈Integer`인 모든 a, item, n에 대하여 다음과 같은 연산이 정의됨   
   
// a : 0개 이상의 원소를 갖는 배열   
// item : 배열에 저장되는 원소   
// n : 배열의 최대 크기를 정의하는 정수값   
- a : an array of 0 or more elements   
- item : Elements stored in an array   
- n : An integer value that defines the maximum size of an array   
   
```c
// 1. Array create(n) ::= 배열의 크기가 n인 빈 배열을 생성하고 배열을 반환한다;
// 2. Element retrieve(a, i) ::= if (i∈Index)
//    then { 배열의 i번째에 해당하는 원소값 'e'를 반환한다; }
//    else { 에러 메시지를 반환한다; }
// 3. Array store(a, i, e) ::= if (i∈Index)
//    then { 배열 a의 i번째 위치에 원소값 'e'를 저장하고 배열 a를 반환한다; }
//    else { 인덱스 i가 배열 a의 크기를 벗어나면 에러 메시지를 반환한다; }
1. 
    Array create(n) ::= Create an empty array with n array size and return the array;
2. 
    Element retrieve(a, i) ::= if (i∈Index)
    then { Returns the element value 'e' corresponding to the i-th of the array; }
    else { Returns an error message; }
3. 
    Array store(a, i, e) ::= if (i∈Index)
    then { Store the element value 'e' in the i-th position of array a and return the array a; }
    else { Returns an error message if index i is outside the size of array a; }
```
   
<br />
### Implementation of Array Operations   
// 배열연산의 구현   
   
#### Create Array (create operation)   
// 배열의 생성 (create 연산)   
   
// n개의 원소들을 저장할 수 있는 공백 배열 (empty array) 을 생성   
// 배열을 생성할 때 n개의 원소들을 저장할 수 있는 공간은 만들어지지만 그 안에 채워진 원소값들이 아직은 없다는 것을 의미함   
- Create an empty array that can store n elements   
- When creating an array, a space is created to store n elements, but there are not yet filled element values in it   
   
```c
void create(int n) {    // n = 5
    int a[n];
    Int i;
    for (i = 0; i < n, i++) {
        a[i] = 0;
    }
}
```
   
#### Search for array values (retrieve operation)   
// 배열값의 검색 (retrieve 연산)   
   
// 배열 a와 인덱스 i를 매개 변수로 전달받아 인덱스 i 위치에 대응되는 원소값 e가 있다면 원소값 e를 반환하고 그렇지 않은 경우 에러 메시지를 반환   
- Returns the element value e if it receives array a and index i as parameters and has an element value e corresponding to the index i location, otherwise returns an error message   
   
```c
#define array_size 5

int retrieve(int *a, int i) {   // i = 2
    if (i >= 0 && i < array_size)
        return a[i];
    else {
        printf("Error\n");
        return (-1);
    }
}
```
   
// 배열의 검색 결과   
// 다음과 같은 원소값이 저장되어 있다고 가정하면, a[2]인 '30'이 출력됨   
- Search Results for Array   
- Assuming that the following element values are stored, output value of '30' for a[2]   
   
||a[0]|a[1]|a[2]|a[3]|a[4]|
|:---:|:---:|:---:|:---:|:---:|:---:|
|a|10|20|30|40|50|
   
#### Store array values (store operation)   
// 배열값의 저장 (store 연산)   
   
// 배열 a와 인덱스 i, 원소값 e를 매개 변수로 전달받아 Index를 검사하여 i값이 유효할 경우 쌍이 되게 원소값을 i번째 인덱스에 저장하고 배열 a를 반환   
- An array a, an index i, and an element value e are transferred as parameters to inspect the index, and if the i value is valid, the element value is stored in the i-th index to pair, and return array a   
   
```c
#define array_size 5

void store(int *a, int i, int e) {    // i = 3, e = 35
    if (i >= 0 && i < array_size)
        a[i] = e;
    else printf("Error\n");
}
```
   
// a[3]의 값이 35로 변경되어 저장된 모습   
- The value of a[3] changed to 35 and saved   
   
||a[0]|a[1]|a[2]|a[3]|a[4]|
|:---:|:---:|:---:|:---:|:---:|:---:|
|a|10|20|30|40|50|
|||||↓||
|a|10|20|30|35|50|
   
<br />
### One-dimensional array   
// 1차원 배열   
   
#### Definition of a one-dimensional array   
// 1차원 배열의 정의   
   
// 한 줄짜리 배열을 의미하며, 하나의 인덱스로 구분됨   
// 한 줄짜리 배열은 메모리 영역도 한줄로 할당 받음   
- It means a single-line array, separated by one index   
- A single-line array also has a single-line memory footprint   
   
|A[0]|A[1]|A[2]|A[3]|A[4]|
|:---:|:---:|:---:|:---:|:---:|
|A(L)|A(L + 1)|A(L + 2)|A(L + 3)|A(U)|
   
// A[i]는 배열의 첫 번째 원소 A[0]이 저장된 메모리 주소인 a로부터 시작하여, A[0]부터 A[i - 1]개까지 i개의 배열 A[]를 지나서 저장됨   
// 따라서, A[]의 메모리 시작주소를 a라고 가정하면, A[i]의 메모리 저장 주소는 [a + i * k]가 됨   
- A[i] is stored through i array A[] from A[0] to A[i-1] starting with the memory address where the first element A[0] of an array is stored   
- Thus, assuming that the memory start address of A[] is a, the memory storage address of A[i] is [a + i * k]   
   
|A[0]|A[1]|A[2]|A[3]|A[4]|
|:---:|:---:|:---:|:---:|:---:|
|A(L)|A(L + 1)|A(L + 2)|A(L + 3)|A(U)|
|k|k|k|k|k|
   
#### Address calculation in a one-dimensional array   
// 1차원 배열에서의 주소 계산   
   
// A[0]의 시작주소를 a라고 가정하면 A[3] 저장 주소는?   
- Assuming that the starting address of A[0] is a, what is the storage address of A[3]?   
   
|A[0] <sup>← α</sup>|A[0] <sup>← α</sup>|
|:---|:---|
|A[1] <sup>← α + k</sup>|A[1] <sup>← α + 8</sup>|
|...|A[2] <sup>← α + 2 * k</sup>|
|A[i] <sup>← α + i * k</sup>|A[3] <sup>← α + 3 * k</sup>|
|...|A[4] <sup>← α + 4 * k</sup>|
|A[u] <sup>← α + u * k</sup>|A[5] <sup>← α + 5 * k</sup>|
   
<br />
### Expansion of the array   
// 배열의 확장   
   
#### Array representation of matrices   
// 행렬의 배열 표현   
   
// 행렬을 컴퓨터에서 표현하기에는 2차원 배열이 적합함   
- Two-dimensional array are suitable for representing matrices on computers   
   
```
5   2   6   2
7   2   0   0
0   1   1   9
```
   
#### Representation of a two-dimensional array of matrices   
// 행렬의 2차원 배열 표현   
   
||Column<br />↓|||||
|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>Row</b> →|A[0][0]|A[0][1]|A[0][2]|...|A[0][m-1]|
||A[1][0]|...|...|...|...|
||A[2][0]|...|...|...|...|
||...|...|...|...|...|
||A[n - 1][0]|...|...|...|A[n -1][m - 1]|
   
#### Row priority array   
// 행 우선 배열   
   
// 1차원 배열을 여러 개 쌓아 놓은 것이 2차원 배열   
- A two-dimensional array of stacked one-dimensional array   
   
// 행 우선 할당   
// - 가로의 1차원 배열 단위로 메모리 영역을 우선 할당함   
// - 하나의 행을 연속적으로 메모리에 할당하고, 그 다음 행을 메모리 영역에 할당하는 방법   
- Row priority allocation   
  - Priority allocation of memory area in one-dimensional units of horizontal array   
  - It is a method of assigning one row to memory successively and the next row to memory area   
   
A[2, 3]
   
||0|1|2|
|:---:|:---:|:---:|:---:|
|0|[0, 0]|[0, 1]|[0, 2]|
|1|[1, 0]|[1, 1]|[1, 2]|
   
// 행 우선 컴퓨터 메모리 할당   
- Row-first computer memory allocation   
   
|Memory||
|:---:|:---:|
|[0, 0]|0 Row|
|[0, 1]|0 Row|
|[0, 2]|0 Row|
|[1, 0]|1 Row|
|[1, 1]|1 Row|
|[1, 2]|1 Row|
   
#### Column priority array   
// 열 우선 배열   
   
// 1차원 배열을 여러 개 세워 놓은 것이 2차원 배열   
- Two-dimensional array with multiple verticals of one-dimensional array   
   
// 열 우선 할당   
// - 세로의 1차원 배열 단위로 메모리 영역을 우선 할당함   
// - 하나의 열을 연속적으로 메모리에 할당하고, 그 다음 열을 메모리 영역에 할당하는 방법   
- Column priority allocation   
  - Priority allocation of memory area in vertical one-dimensional array units   
  - It is a method of assigning one column to memory successively, and then a column to memory area   
   
A[2, 3]
   
||0|1|2|
|:---:|:---:|:---:|:---:|
|0|[0, 0]|[0, 1]|[0, 2]|
|1|[1, 0]|[1, 1]|[1, 2]|
   
// 열 우선 컴퓨터 메모리 할당   
- Column-first allocation of computer memory   
   
|Memory||
|:---:|:---:|
|[0, 0]|0 Column|
|[1, 0]|0 Column|
|[0, 1]|1 Column|
|[1, 1]|1 Column|
|[0, 2]|2 Column|
|[1, 2]|2 Column|
   
#### Two-dimensional array in C language (storing row priority order)   
// C언어에서의 2차원 배열 (행 우선 순서 저장)   
   
// C언어에서 A[3][5]을 선언하면 다음과 같은 배열이 생성됨   
- Declaring A[3][5] in C language produces the following array   
   
||Column|||||
|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>Row</b>|0, 0|0, 1|0, 2|0, 3|0, 4|
||1, 0|1, 1|1, 2|1, 3|1, 4|
||2, 0|2, 1|2, 2|2, 3|2, 4|
   
<br />
### Expression of a sparse matrix   
// 희소행렬의 표현   
   
// 희소행렬   
// - 원소값이 0인 원소가 그렇지 않은 원소보다 상대적으로 많은 행렬   
- Sparse matrix   
  - A sparse matrix is a matrix that has a relatively larger number of elements with an element value of zero than an element that does not   
   
#### General array representation of sparse matrices   
// 희소행렬의 일반적 배열표현   
   
||[0]|[1]|[2]|[3]|[4]|[5]|[6]|[7]|[8]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|[0]|0|20|0|0|9|0|0|11|0|
|[1]|0|0|0|0|0|0|0|0|0|
|[2]|78|0|0|0|0|0|0|0|0|
|[3]|0|0|0|0|67|0|0|0|0|
|[4]|0|31|0|0|0|0|0|0|0|
|[5]|0|0|0|91|0|0|44|0|0|
|[6]|0|0|0|0|0|0|0|0|0|
|[7]|0|0|0|0|19|0|0|27|0|
   
#### Expression of an efficient array of sparse matrices   
// 희소행렬의 효율적 배열 표현   
   
// 0인 원소는 저장하지 않고 0이 아닌 값만을 따로 모아서 저장   
// 메모리 낭비를 막고 효율성 향상   
- Save only nonzero values separately without storing elements that are zero   
- Reduce memory waste and improve efficiency   
   
||Row|Column|Value|
|:---:|:---:|:---:|:---:|
|<b>0</b>|<b>8</b>|<b>9</b>|<b>10</b>|
|1|0|1|20|
|2|0|4|9|
|3|0|7|11|
|4|2|0|78|
|5|3|4|67|
|6|4|1|31|
|7|5|3|91|
|8|5|6|44|
|9|7|4|19|
|10|7|7|27|
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
