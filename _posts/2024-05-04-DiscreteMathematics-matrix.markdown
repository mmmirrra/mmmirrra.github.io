---
layout: post
title:  "Discrete Mathematics: Matrix"
date:   2024-05-04 09:00:00 +0900
categories: [Discrete Mathematics]
---

### Basic Information   
// 기본사항   
   
#### Matrix   
// 행렬   
   
// 행과 열로 구성되는 사각형 형태로 수를 배열한 것   
- An array of numbers in rectangular form consisting of rows and columns   
   
```
( 1 2 3 4
  5 6 7 8
  9 0 2 5 )
```
   
// m, n이 양의 정수일 때, m개의 행과 n개의 열로 구성된 직사각형의 수 배열 A를 m x n 행렬이라 함   
// - 행렬 A에서 i번째 행의 j번째 열의 수를 행렬 A 의 (i, j) 원소라 하며 a<sub>ij</sub> 로 표시함   
// - 행렬 A를 간단히 A = (a<sub>ij</sub>) 로 표기하기도 함   
- If m and n are positive integers, the number array A of rectangles consisting of m rows and n columns is called the m x n matrix   
  - In matrix A, the number of j-th columns of the i-th row is called the (i, j) element of matrix A, and write a<sub>ij</sub>   
  - Matrix A can also be written simply as A = (a<sub>ij</sub>)   
   
// 행벡터 (row vector) : 1 x n 행렬   
// 열벡터 (column vector) : m x 1 행렬   
- Row vector : 1 x n matrix   
- Column vector : m x 1 matrix   
   
#### The application of the computer field   
// 컴퓨터 분야의 활용   
   
// 프로그래밍 언어   
// 패턴 인식   
// 자료구조   
// 로봇 동작   
// 컴퓨터 그래픽스   
// 인공지능   
- Programming language   
- Pattern recognition   
- Data structure   
- Robot motion   
- Computer graphics   
- Artificial intelligence   
   
#### Zero matrix   
// 영행렬   
   
// 모든 원소가 0인 행렬을 영행렬이라고 함   
- A matrix with all zero elements is called a zero matrix   
   
```
[ 0 ]

┌ 0 0 ┐
└ 0 0 ┘

┌ 0 0 0 ┐
└ 0 0 0 ┘

┌ 0 0 0 ┐
│ 0 0 0 │
└ 0 0 0 ┘

┌ 0 0 0 0 ┐
│ 0 0 0 0 │
└ 0 0 0 0 ┘
```
   
<br />
### The operation of a matrix   
// 행렬의 연산   
   
#### Basic operation   
// 기본연산   
   
#### Sum, Difference, Scalar Multiplication of the Matrix   
// 행렬의 합, 차 스칼라 곱   
   
// 크기가 같은 행렬 A, B가 있고 k를 실수라 할 때   
// - ① 행렬의 합 : A + B 는 같은 위치의 A와 B의 원소를 더해서 구해지는 행렬로서 (i, j) 원소의 값은 a<sub>ij</sub> + b<sub>ij</sub> 이다   
// - ② 행렬의 차 : A - B 는 같은 위치의 A의 원소로부터 B의 원소를 빼서 구해지는 행렬로서 (i, j) 원소의 값은 a<sub>ij</sub> - b<sub>ij</sub> 이다   
// - ③ 스칼라 곱 : kA는 A의 각 원소에 k를 곱해서 구해지는 행렬로서 (i, j) 원소의 값은 ka<sub>ij</sub> 이다   
- If there are matrices A and B of the same size and k is a real number   
  - ① Sum of Matrix : A + B is a matrix obtained by adding elements of A and B in the same position, and the value of the element (i, j) is a<sub>ij</sub> + b<sub>ij</sub>   
  - ② Difference of Matrix : A - B is a matrix obtained by subtracting the element of B from the element of A in the same position, and the value of the element (i, j) is a<sub>ij</sub> - b<sub>ij</sub>   
  - ③ Scalar Multiplication : kA is a matrix obtained by multiplying each element of A by k, and the value of the element (i, j) is ka<sub>ij</sub>   
   
// 예시   
// - 행렬 A와 B가 다음과 같을 때 질문에 답하시오   
- Example   
  - Answer the question when matrices A and B are as follows   
   
- Matrix A   
```
┌ 1 1 0 0 ┐
│ 0 1 1 0 │
└ 0 0 1 1 ┘
```
   
- Matrix B   
```
┌ 2 4 1 3 ┐
│ 1 4 2 3 │
└ 2 3 1 6 ┘
```
   
- B - A?   
```
┌ 1 3 1 3 ┐
│ 1 3 1 3 │
└ 2 3 0 5 ┘
```
   
- 3A?   
```
┌ 3 3 0 0 ┐
│ 0 3 3 0 │
└ 0 0 3 3 ┘
```
   
- 3A + (B - A)?   
```
┌ 4 6 1 3 ┐
│ 1 6 4 3 │
└ 2 3 3 8 ┘
```
   
#### The laws of operations of sum of matrix and scalar multiplication   
// 행렬의 합과 스칼라 곱의 연산법칙   
   
// 정리   
// - 행렬의 합과 스칼라 곱은 같은 크기의 행렬 A, B, C에 대해 다음과 같은 연산법칙들을 만족한다 (a, b는 실수이고 0은 모든 원소가 0인 영행렬을 의미한다)   
// -- ① 합의 교환법칙 : A + B = B + A   
// -- ② 합의 결합법칙 : A + (B + C) = (A + B) + C   
// -- ③ 합의 항등원 : A + O = A   
// -- ④ 합의 역원 : A + (-A) = O   
// -- ⑤ 스칼라 곱의 결합법칙 : (ab)A = a(bA)   
// -- ⑥ 스칼라 곱의 분배법칙 : (a + b)A = aA + bA   
// -- ⑦ 스칼라 곱의 분배법칙 : (a - b)A = aA - bA   
// -- ⑧ 스칼라 곱의 분배법칙 : a(A + B) = aA + aB   
// -- ⑨ 스칼라 곱의 분배법칙 : a(A - B) = aA - aB   
- Theorem   
  - The sum and scalar multiplication of the matrix satisfy the following operational laws for matrix A, B, and C of the same size (a and b are real numbers, and 0 means zero matrix with zero elements.)   
    - ① The law of commutative of sum : A + B = B + A   
    - ② The law of associative of sum : A + (B + C) = (A + B) + C   
    - ③ Identity element of sum : A + O = A   
    - ④ Inverse element of sum : A + (-A) = O   
    - ⑤ Law of associative of scalar multiplication : (ab)A = a(bA)   
    - ⑥ Law of distributive of scalar multiplication : (a + b)A = aA + bA   
    - ⑦ Law of distributive of scalar multiplication : (a - b)A = aA - bA   
    - ⑧ Law of distributive of scalar multiplication : a(A + B) = aA + aB   
    - ⑨ Law of distributive of scalar multiplication : a(A - B) = aA - aB   
   
#### Multiplication of matrices   
// 행렬의 곱   
   
// A가 m x n 행렬이고 B가 n x l 행렬일 때 행렬의 곱 AB 는 (i, j) 원소가 다음과 같이 정의되는 m x l 행렬이다   
// - A 의 열 개수 n과 B 의 행 개수 n 이 같아야 A x B 곱이 가능함   
// - AB<sub>ij</sub> = ∑<sup>n</sup><sub>k = 1</sub>a<sub>ik</sub>b<sub>kj</sub> = a<sub>i1</sub>b<sub>1j</sub> + a<sub>i2</sub>b<sub>2j</sub> + ... + a<sub>in</sub>b<sub>nj</sub>   
// -- A (= m x n 행렬) x B (= n x l 행렬) = C (= m x l 행렬)   
- When A is an m x n matrix and B is an n x l matrix, the multiplication AB of the matrix is an m x l matrix in which the elements (i, j) are defined as follows   
  - A x B multiplication is possible when the number of columns of A must be n and the number of rows of B must be n   
  - AB<sub>ij</sub> = ∑<sup>n</sup><sub>k = 1</sub>a<sub>ik</sub>b<sub>kj</sub> = a<sub>i1</sub>b<sub>1j</sub> + a<sub>i2</sub>b<sub>2j</sub> + ... + a<sub>in</sub>b<sub>nj</sub>   
    -  A (= m x n matrix) x B (= n x l matrix) = C (= m x l matrix)   
   
```
┌ ...     ...     ...    ...  ┐
│ a i1    a i2    ...    a in │
└ ...     ...     ...    ...  ┘
x
┌ ... b 1j ... ┐
│ ... b 2j ... │
│ ... ...  ... │
└ ... b nj ... ┘
=
┌ ... ...  ... ┐
│ ... c ij ... │
└ ... ...  ... ┘
```
   
∴ c<sub>ij</sub> = ∑<sup>n</sup><sub>k = 1</sub>a<sub>ik</sub>b<sub>kj</sub>   
   
#### The inner product of a vector   
// 벡터의 내적 (inner product)   
   
// A = (a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub>) 와 B = (b<sub>1</sub>, b<sub>2</sub>, ..., b<sub>n</sub>) 가 n차원 벡터라고 할 때 A와 B의 내적 A·B 는 다음과 같이 정의한다   
// - A·B = a<sub>1</sub>b<sub>1</sub> + a<sub>2</sub>b<sub>2</sub> + ... + a<sub>n</sub>b<sub>n</sub>   
// - 예시   
// -- A = (1, 2, 3), B = (-1, 0, 2) 이면   
// --- A·B = (1 x -1) + (2 x 0) + (3 x 2) = (-1) + 0 + 6 = 5   
- If A = (a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub>) and B = (b<sub>1</sub>, b<sub>2</sub>, ..., b<sub>n</sub>) is an n-dimensional vector, the inner product A and B of A and B are defined as follows   
  - A·B = a<sub>1</sub>b<sub>1</sub> + a<sub>2</sub>b<sub>2</sub> + ... + a<sub>n</sub>b<sub>n</sub>   
  - Example   
    - If A = (1, 2, 3), B = (-1, 0, 2)   
      - A·B = (1 x -1) + (2 x 0) + (3 x 2) = (-1) + 0 + 6 = 5   
   
#### Example of matrix multiplication   
// 행렬의 곱 예시   
   
// 행렬 A, B가 다음과 같을 때 AB를 계산하시오   
- Calculate AB when matrices A and B are as follows   
   
- Matrix A   
```
┌ 4 -1 ┐
│ 2  3 │
└ 1  5 ┘
```
   
- Matrix B   
```
┌ 7 -3 ┐
└ 9 -2 ┘
```
   
- AB?   
   
```
┌ (((4 x 7) + ((-1) x 9)) = (28 + (-9)) = 19)    (((4 x (-3)) + ((-1) x (-2))) = ((-12) + 2) = (-10)) ┐
│ (((2 x 7) + (3 x 9)) = (14 + 27) = 41)    (((2 x (-3)) + (3 x (-2))) = ((-6) + (-6)) = (-12)) │
└ (((1 x 7) + (5 x 9)) = (7 + 45) = 52)    (((1 x (-3)) + (5 x (-2))) = ((-3) + (-10)) = (-13)) ┘

┌ 19 -10 ┐
│ 41 -12 │
└ 52 -13 ┘
```
   
#### The operational law of matrix multiplication   
// 행렬 곱의 연산법칙   
   
// 정리   
// - 행렬 A, B, C가 각 연산에 적합한 크기의 행렬이라 할 때, 다음과 같은 연산법칙들을 만족한다   
// -- ① 곱의 결합법칙 : A(BC) = (AB)C   
// -- ② 곱의 분배법칙 : A(B + C) = AB + AC   
// -- ③ 곱의 분배법칙 : (A + B)C = AC + BC   
- Theorem   
  - If matrices A, B, and C are of the appropriate sizes for each operation, they satisfy the following operational laws   
    - ① Law of associative of multiplication : A(BC) = (AB)C   
    - ② Law of distributive of multiplication : A(B + C) = AB + AC   
    - ③ Law of distributive of multiplication : (A + B)C = AC + BC   
   
// 예시 1   
// - 행렬 A, B가 다음과 같을 때 AB 와 BA 를 계산하시오   
- Example 1   
  - Calculate AB and BA when matrices A and B are as follows   
   
- Matrix A   
```
[ -1 2 6 ]
```
   
- Matrix B   
```
┌ 1 ┐
│ 4 │
└ 2 ┘
```
   
- AB?   
```
[ 19 ]
```
   
- BA?   
```
┌ -1 2  6 ┐
│ -4 8 24 │
└ -2 4 12 ┘
```
   
// 행렬 곱 연산의 특이 성질 1   
- Unique properties of matrix multiplication operations 1   
  - AB ≠ BA   
   
// 예시 2   
// - 행렬 A가 다음과 같을 때 A<sup>2</sup>, A<sup>3</sup>, A<sup>4</sup>, A<sup>n</sup> 을 계산하시오   
- Example 2   
  - Calculate A<sup>2</sup>, A<sup>3</sup>, A<sup>4</sup>, and A<sup>n</sup> when matrix A is as follows   
   
- Matrix A   
```
┌ 2  0 ┐
└ 0 -1 ┘
```
   
- A<sup>2</sup>?   
```
┌ 2  0 ┐┌ 2  0 ┐
└ 0 -1 ┘└ 0 -1 ┘
=
┌ 4  0 ┐
└ 0  1 ┘
```
   
- A<sup>3</sup>?   
```
┌ 4  0 ┐┌ 2  0 ┐
└ 0  1 ┘└ 0 -1 ┘
=
┌ 8  0 ┐
└ 0 -1 ┘
```
   
- A<sup>4</sup>?   
```
┌ 8  0 ┐┌ 2  0 ┐
└ 0 -1 ┘└ 0 -1 ┘
=
┌ 16 0 ┐
└ 0  1 ┘
```
   
- A<sup>n</sup>?   
```
┌ 2ⁿ   0   ┐
└ 0  (-1)ⁿ ┘
```
   
// 행렬의 거듭제곱 (A가 정방행렬)   
- The power of a matrix (A is a square matrix)   
  - A<sup>r</sup>A<sup>s</sup> = A<sup>r + s</sup>   
   - (A<sup>r</sup>)<sup>s</sup> = A<sup>rs</sup>   
   
// 예시 3   
// - 행렬 A, B가 다음과 같을 때 AB 를 계산하시오   
- Example 3   
  - Calculate AB when matrices A and B are as follows   
   
- Matrix A   
```
┌ 0 1 ┐
└ 0 1 ┘
```
   
- Matrix B   
```
┌ 1 1 ┐
└ 0 0 ┘
```
   
- AB?   
```
┌ 0 0 ┐
└ 0 0 ┘
```
   
// 행렬 곱 연산의 특이 성질 2   
- Unique properties of matrix multiplication operations 2   
  - ∃A ≠ O, ∃B ≠ O ⇒ AB = O   
   
#### Gaussian elimination method   
// 가우스 소거법   
   
```
 x + 2y -  z = 2
2x + 5y +  z = 3
3x + 4y - 4z = 13

   ┌ 1 2 -1 ┐┌ x ┐    ┌ 2  ┐
⇒ │ 2 5  1 ││ y │  = │ 3  │
   └ 3 4 -4 ┘└ z ┘    └ 13 ┘
       A       X        B
// ⇒ 행렬방정식 AX = B
// A : 계수행렬
// X : 미지수행렬
// B : 상수행렬
// (A\|B) : 확대행렬
⇒ Matrix Equation AX = B
A : Counting matrix
X : Unknowns matrix
B : Constant matrix
(A\|B) : Augmented coefficient matrix
```
   
// 만일 A의 역행렬 A<sup>-1</sup> 가 존재한다면 AX = B 의 양 변에 A<sup>-1</sup> 를 곱하면 A<sup>-1</sup>AX = IX = X = A<sup>-1</sup>B 와 같이 방정식의 해를 구할 수 있음   
// - A<sup>-1</sup>A ⇒ 단위행렬 I = 곱셈에 대한 항등원   
- If the inverse matrix A<sup>-1</sup> of A exists, multiplying both sides of AX = B by A<sup>-1</sup> yields a solution to the equation as A<sup>-1</sup>AX = IX = X = A<sup>-1</sup>B   
  - A<sup>-1</sup>A ⇒ Unit matrix I = Identity for multiplication   
   
#### Gaussian elimination method - Elementary row operation   
// 가우스 소거법 - 기본행연산   
   
// 행 교환 (row interchange) 연산 (R<sub>i, j</sub>)   
// - 두 행의 위치를 서로 바꾸는 연산   
// 행 스케일링 (row scaling) 연산 (R<sub>i</sub>(c))   
// - 하나의 행에 0이 아닌 스칼라를 곱하는 연산   
// 행 대체 (row replacement) 연산 (R<sub>i, j</sub>(c))   
// - 하나의 행에 스칼라 곱을 해서 다른 행에 더하는 연산   
- Row interchange operation (R<sub>i, j</sub>)   
  - An operation in which the positions of two rows are interchanged   
- Row scaling operation (R<sub>i</sub>(c))   
  - An operation in which a row is multiplied by a nonzero scalar   
- Row replacement operation (R<sub>i, j</sub>(c))   
  - An operation in which one row is multiplied by a scalar and added to another row   
   
#### The relationship between system of linear equations and matrices   
// 일차연립방정식과 행렬의 관계   
   
// 정리   
// - L<sub>1</sub>, L<sub>2</sub> : 일차연립방정식   
// - A : L<sub>1</sub>의 확대행렬   
// - B : L<sub>2</sub>의 확대행렬   
// - A ~ B ⇒ L<sub>1</sub> ~ L<sub>2</sub> ( = A → B ⇒ L<sub>1</sub> → L<sub>2</sub>)   
// -- A ~ B : A에 유한번의 기본행연산을 적용하여 B를 얻을 수 있음   
// -- L<sub>1</sub> ~ L<sub>2</sub> : L<sub>1</sub> 과 L<sub>2</sub> 의 해집합이 동일함   
- Theorem   
  -  L<sub>1</sub>, L<sub>2</sub> : System of linear equations   
  - A : Augmented coefficient matrix for L<sub>1</sub>   
  - B : Augmented coefficient matrix for L<sub>2</sub>   
  - A ~ B ⇒ L<sub>1</sub> ~ L<sub>2</sub> ( = A → B ⇒ L<sub>1</sub> → L<sub>2</sub>)   
    - A ~ B : B can be obtained by applying a finite number of elementary row operation to A   
    - L<sub>1</sub> ~ L<sub>2</sub> : L<sub>1</sub> and L<sub>2</sub> have the same solution set   
   
#### Gaussian Elimination method   
// 가우스 소거법   
   
```
일차연립방정식            확대행렬
      L            →        A
                            ↓
                      행제형 행렬
                            A'
```
   
```
System of linear equations         Augmented coefficient matrix
            L                 →                 A
                                                ↓
                                        Row echelon matrix
                                                A'
```
   
#### Gauss-Jordan Elimination method   
// 가우스 조르단 소거법   
   
```
일차연립방정식            확대행렬
      L            →        A
                            ↓
소거 행제형 행렬       행제형 행렬
      A''          ←        A'
```
   
```
system of linear equations           Augmented coefficient matrix
            L                  →                  A
                                                  ↓
Reduced row-echelon matrix                Row echelon matrix
            A''                ←                  A'
```
   
#### Row echelon matrix   
// 행제형 행렬   
   
// 다음 세 가지 조건을 만족하는 행렬을 행사다리꼴 (행제형) 이라고 한다   
// - 영행이 아닌 행은 영행의 위에 있다   
// - 영행이 아닌 행의 첫번째 0이 아닌 원소를 그 행의 선도원소라 하는데, 모든 선도원소는 1이다   
// - 주어진 행의 선도원소는 그 아래 행의 선도원소보다 왼쪽에 있다   
- A matrix that satisfies the following three conditions is called a row trapezoid (Row echelon matrix)   
  - A non-zero row is above the zero row   
  - The first non-zero element in a row is called the leading element of the row, and all leading elements are 1   
  - The leading element of a given row is to the left of the leading element of the row below it   
   
#### Reduced row-echelon matrix   
// 소거 행제형 행렬   
   
// 다음 조건을 만족하는 행제형 행렬을 소거 행제형 행렬이라고 한다   
// - 행제형 행렬 세 가지 조건을 모두 만족한다   
// - 선도원소가 포함된 열에서 선도원소를 제외한 모든 원소는 0이다   
- A row echelon matrix that satisfies the following conditions is called an reduced row-echelon matrix   
  - All three conditions of a row echelon matrix are satisfied   
  - In a column containing leading elements, all elements except leading elements are zero   
   
// 예시 1   
// - 다음 행렬을 보고 행제형 행렬인지 여부를 판단하시오   
- Example 1   
  - Look at the following matrix to determine whether it is a row echelon matrix   
   
(1)   
```
┌ 1 0 0 ┐
│ 0 0 0 │
└ 0 1 2 ┘
```
// ∴ 행제형 행렬 아님   
// ⇒ 행제형 행렬로 만들려면 R<sub>2, 3</sub> ⇒   
∴ Not a row echelon matrix   
⇒ To make a row echelon matrix, R<sub>2, 3</sub> ⇒   
```
┌ 1 0 0 ┐
│ 0 1 2 │
└ 0 0 0 ┘
```
   
(2)   
```
┌ 1 0 0 0 ┐
│ 0 1 3 3 │
└ 0 0 0 2 ┘
```
// ∴ 행제형 행렬 아님   
// ⇒ 행제형 행렬로 만들려면 R<sub>3</sub>(<sup>1</sup> / <sub>2</sub>) ⇒   
∴ Not a row echelon matrix   
⇒ To make a row echelon matrix, R<sub>3</sub>(<sup>1</sup> / <sub>2</sub>) ⇒   
```
┌ 1 0 0 0 ┐
│ 0 1 3 3 │
└ 0 0 0 0 ┘
```
   
(3)   
```
┌ 1 0 4 6 ┐
│ 0 0 1 5 │
└ 0 1 0 0 ┘
```
// ∴ 행제형 행렬 아님   
// ⇒ 행제형 행렬로 만들려면 R<sub>2, 3</sub> ⇒   
∴ Not a row echelon matrix   
⇒ To make a row echelon matrix, R<sub>2, 3</sub> ⇒   
```
┌ 1 0 4 6 ┐
│ 0 1 0 0 │
└ 0 0 1 5 ┘
```
   
(4)   
```
┌ 1 2 3 ┐
│ 0 0 1 │
└ 0 0 0 ┘
```
// ∴ 행제형 행렬임   
∴ Row echelon matrix   
   
// 예시 2   
// - 다음 행렬을 보고 소거 행제형 행렬인지 여부를 판단하시오   
- Example 2   
  - Look at the following matrix to determine whether it is an Reduced row-echelon matrix   
   
(1)   
```
┌ 1 0 0 ┐
│ 0 0 0 │
└ 0 1 2 ┘
```
// ∴ 소거 행제형 행렬 아님   
// ⇒ 소거 행제형 행렬로 만들려면 R<sub>2, 3</sub> ⇒   
∴ Not a reduced row-echelon matrix   
⇒ To make a reduced row-echelon matrix, R<sub>2, 3</sub> ⇒   
```
┌ 1 0 0 ┐
│ 0 1 2 │
└ 0 0 0 ┘
```
   
(2)   
```
┌ 1 0 0 0 ┐
│ 0 1 3 3 │
└ 0 0 0 1 ┘
```
// ∴ 소거 행제형 행렬 아님   
// ⇒ 소거 행제형 행렬로 만들려면 R<sub>3, 2</sub>(-3) ⇒   
∴ Not an reduced row-echelon matrix   
⇒ To make a reduced row-echelon matrix, R<sub>3, 2</sub>(-3) ⇒   
```
┌ 1 0 0 0 ┐
│ 0 1 3 0 │
└ 0 0 0 1 ┘
```
   
(3)   
```
┌ 1 1 2 6 ┐
│ 0 0 1 2 │
└ 0 0 0 0 ┘
```
// ∴ 소거 행제형 행렬 아님   
// ⇒ 소거 행제형 행렬로 만들려면 R<sub>2, 1</sub>(-2) ⇒   
∴ Not an reduced row-echelon matrix   
⇒ To make a reduced row-echelon matrix, R<sub>2, 1</sub>(-2) ⇒   
```
┌ 1 1 0 2 ┐
│ 0 0 1 2 │
└ 0 0 0 0 ┘
```
   
(4)   
```
┌ 1 2 0 ┐
│ 0 0 1 │
└ 0 0 0 ┘
```
// ∴ 소거 행제형 행렬임   
∴ Reduced row-echelon matrix   
   
#### Example of Gaussian elimination method   
// 가우스 소거법 예시   
   
// 다음 일차연립방정식의 해를 구하시오   
- Find the solution of the following system of linear equations   
   
```
       x₂ + 5x₃ = 2
 x₁       - 3x₃ = -2
2x₁ + 2x₂ + 9x₃ = 1
```
   
// 확대행렬   
- Augmented coefficient matrix   
   
```
┌ 0   1   5   2 ┐
│ 1   0  -3  -2 │
└ 2   2   9   1 ┘
```
   
// 기본행연산으로 소거 행제형으로 바꿈   
- Change to reduced row-echelon matrix by elementary row operation   
   
⇒ R<sub>1, 2</sub>   
```
┌ 0   1   5   2 ┐   ┌ 1   0  -3  -2 ┐
│ 1   0  -3  -2 │ ~ │ 0   1   5   2 │
└ 2   2   9   1 ┘   └ 2   2   9   1 ┘
```
   
⇒ R<sub>1, 3</sub>(-2)   
```
┌ 1   0  -3  -2 ┐   ┌ 1   0  -3  -2 ┐
│ 0   1   5   2 │ ~ │ 0   1   5   2 │
└ 2   2   9   1 ┘   └ 0   2  15   5 ┘
```
   
⇒ R<sub>2, 3</sub>(-2)   
```
┌ 1   0  -3  -2 ┐   ┌ 1   0  -3  -2 ┐
│ 0   1   5   2 │ ~ │ 0   1   5   2 │
└ 0   2  15   5 ┘   └ 0   0   5   1 ┘
```
   
⇒ R<sub>3</sub>(<sup>1</sup> / <sub>5</sub>)   
```
┌ 1   0  -3  -2 ┐   ┌ 1   0  -3  -2  ┐
│ 0   1   5   2 │ ~ │ 0   1   5   2  │
└ 0   0   5   1 ┘   └ 0   0   1  0.2 ┘
```
   
⇒ R<sub>3, 2</sub>(-5)   
```
┌ 1   0  -3  -2  ┐   ┌ 1   0  -3  -2  ┐
│ 0   1   5   2  │ ~ │ 0   1   0   1  │
└ 0   0   1  0.2 ┘   └ 0   0   1  0.2 ┘
```
   
⇒ R<sub>3, 1</sub>(3)   
```
┌ 1   0  -3  -2  ┐   ┌ 1   0   0 -1.4 ┐
│ 0   1   0   1  │ ~ │ 0   1   0   1  │
└ 0   0   1  0.2 ┘   └ 0   0   1  0.2 ┘
```
⇒ 소거 행제형 행렬임   
⇒ Reduced row-echelon matrix   
   
```
┌ 1   0   0 -1.4 ┐
│ 0   1   0   1  │
└ 0   0   1  0.2 ┘
     (A    | B)
```
   
```
┌ 1   0   0 ┐ // ⇒ 3차 단위행렬 I₃ : A
│ 0   1   0 │ ⇒ A third-order unit matrix I₃ : A
└ 0   0   1 ┘

┌ -1.4 ┐         ┌ x₁ ┐
│   1  │ ⇒ B ⇒ │ x₂ │
└  0.2 ┘         └ x₃ ┘
```
   
```
x₁         = -1.4
    x₂     = 1
        x₃ = 0.2
```
   
∴ x₁ = -1.4, x₂ = 1, x₃ = 0.2   
   
<br />
### Type of matrix   
// 행렬의 종류   
   
// 정방행렬   
// 대각행렬   
// 단위행렬   
// 대칭행렬   
// 역대칭행렬   
// 삼각행렬   
// 전치행렬   
// 역행렬   
- Square matrix   
- Diagonal matrix   
- Unit matrix   
- Symmetric matrix   
- Skew symmetric matrix   
- Triangular matrix   
- Transpose matrix   
- Inverse matrix   
   
#### Square matrix   
// 정방행렬   
   
// n x n 행렬을 n차 정방행렬이라고 함   
// n을 정방행렬의 차수라고 함   
- An n x n matrix is called an nth-order square matrix   
- N is called the degree of the square matrix   
   
// n차 정방행렬은 다음과 같은 형태를 가진다   
- The nth-order square matrix has the following form   
   
```
┌ a ₁₁   a ₁₂   ...   a ₁n ┐
│ a ₂₁   a ₂₂   ...   a ₂n │
│  ...    ...   ...    ... │
└ a n₁   a n₂   ...   a nn ┘
```
   
// 정방행렬의 a₁₁, a₂₂, ..., a<sub>nn</sub> 원소를 대각원소라고 함   
// 대각원소를 포함하는 대각선을 주대각선이라고 함   
- The a₁₁, a₂₂, ..., a<sub>nn</sub> element in a square matrix is called a diagonal element   
- Diagonals containing diagonal elements are called main diagonal lines   
   
#### Diagonal matrix   
// 대각행렬   
   
// n차 정방행렬에서 대각원소 이외의 모든 원소가 0인 행렬을 대각행렬이라 함   
// 즉, i ≠ j 이면 a<sub>ij</sub> = 0 이다   
- In the nth-order square matrix, a matrix in which all elements other than diagonal elements are zero is called a diagonal matrix   
- That is, if i ≠ j then a<sub>ij</sub> = 0   
   
```
┌ 1 0 0 0 ┐
│ 0 1 0 0 │
│ 0 0 1 0 │
└ 0 0 0 1 ┘
```
   
```
┌ 0  0  0  0 ┐
│ 0  6  0  0 │
│ 0  0  1  0 │
└ 0  0  0 -2 ┘
```
   
```
┌ 0 0 0 0 ┐
│ 0 0 0 0 │
│ 0 0 0 0 │
└ 0 0 0 0 ┘
```
   
// 스칼라 행렬   
// - 대각행렬이면서 a<sub>ii</sub> = k 인 행렬   
- Scalar matrix   
  - Diagonal matrix with a<sub>ii</sub> = k   
   
```
┌ k 0 0 0 ┐
│ 0 k 0 0 │
│ 0 0 k 0 │
└ 0 0 0 k ┘
```
   
#### Unit matrix   
// 단위행렬   
   
// 스칼라 행렬 중 k 가 1인 행렬   
// 곱셈에 관한 항등원임   
// - AA<sup>-1</sup>X = IX = X ⇒ I 는 단위행렬 = 곱셈에 관한 항등원   
- In a scalar matrix, a matrix with k equal to 1   
- It's an identity about multiplication   
  - AA<sup>-1</sup>X = IX = X ⇒ I is a unit matrix = The identity of multiplication   
   
// n차 정방행렬에서 대각원소가 모두 1이고 나머지 원소는 모두 0인 행렬을 단위행렬이라 함 (I<sub>n</sub>으로 표기)   
// 즉, i = j 이면 a<sub>ij</sub> = 1 이고, i ≠ j 이면 a<sub>ij</sub> = 0 이다   
- In the nth-order square matrix, a matrix with diagonal elements all 1 and all other elements all 0 is called a unit matrix (Write as I<sub>n</sub>)   
- That is, if i = j, a<sub>ij</sub> = 1, and if i ≠ j, a<sub>ij</sub> = 0   
   
- I<sub>2</sub>   
```
┌ 1 0 ┐
└ 0 1 ┘
```
   
- I<sub>3</sub>   
```
┌ 1 0 0 ┐
│ 0 1 0 │
└ 0 0 1 ┘
```
   
- I<sub>n</sub>   
```
┌  1     0    ...    0  ┐
│  0     1    ...    0  │
│ ...   ...   ...   ... │
└  0     0    ...    1  ┘
```
   
#### Symmetric matrix   
// 대칭행렬   
   
// n차 정방행렬에서 a<sub>ij</sub> = a<sub>ji</sub> 인 행렬을 대칭행렬이라 함   
- In the nth-order square matrix, a matrix with a<sub>ij</sub> = a<sub>ji</sub> is called a symmetric matrix   
   
```
┌ a ₁₁   a ₁₂   ...   a ₁n ┐
│ a ₁₂   a ₂₂   ...   a ₂n │
│  ...    ...   ...    ... │
└ a ₁n   a ₂n   ...   a nn ┘
```
   
// 예시   
// - 다음 행렬들에 대해서 각각 정방행렬, 단위행렬, 대각행렬, 대칭행렬의 여부를 판단하시오   
- Example   
  - Determine whether each of the following matrices has a square, unit, diagonal, or symmetric matrix   
   
(1)   
```
┌ 1 1 0 0 ┐
│ 0 1 1 0 │
└ 0 0 0 1 ┘
```
// ∴ 3 x 4. 정방행렬 아님. 단위행렬 아님. 대각행렬 아님. 대칭행렬 아님   
∴ 3 x 4. It's not a square matrix. It's not a unit matrix. It's not a diagonal matrix. It's not a symmetric matrix   
   
(2)   
```
┌ 1 1 0 ┐
│ 1 1 0 │
└ 0 0 0 ┘
```
// ∴ 3 x 3. 정방행렬임. 단위행렬 아님. 대각행렬 아님. 주대각선을 기준으로 대칭이므로 대칭행렬임   
∴ 3 x 3. It's a square matrix. It's not a unit matrix. It's not a diagonal matrix. It's symmetric because it's symmetric about the main diagonal   
   
(3)   
```
┌ 1 0 0 ┐
│ 0 1 0 │
└ 0 0 3 ┘
```
// ∴ 3 x 3. 정방행렬임. 단위행렬 아님. 주대각선을 제외한 나머지가 모두 0이므로 대각행렬임. 주대각선을 기준으로 대칭이므로 대칭행렬임   
∴ 3 x 3. It's a square matrix. It's not a unit matrix. It's a diagonal matrix because everything except the main diagonal is zero. It's symmetric because it's symmetric about the main diagonal   
   
(4)   
```
┌ 1 0 0 0 ┐
│ 0 1 0 0 │
│ 0 0 1 0 │
└ 0 0 0 1 ┘
```
// ∴ 4 x 4. 정방행렬임. 주대각선이 모두 1이고 주대각선을 제외한 나머지가 모두 0이므로 단위행렬임. 주대각선을 제외한 나머지가 모두 0이므로 대각행렬임. 스칼라행렬임. 주대각선을 기준으로 대칭이므로 대칭행렬임   
∴ 4 x 4. It's a square matrix. It's a unit matrix because the main diagonal lines are all 1, and the rest are all 0. It's a diagonal matrix because all but the main diagonal lines are 0. It's a scalar matrix. It's symmetric because it's symmetric about the main diagonal line   
   
#### Skew symmetric matrix   
// 역대칭행렬   
   
// n차 정방행렬에서 a<sub>ij</sub> = -a<sub>ji</sub> 이고 대각원소가 모두 0인 행렬을 역대칭행렬 [교대행렬] 이라 함   
// 즉, i = j 이면 a<sub>ij</sub> = 0 이고, i ≠ j 이면 a<sub>ij</sub> = -a<sub>ji</sub> 이다   
- In the nth-order square matrix, a matrix with a<sub>ij</sub> = -a<sub>ji</sub> and all diagonal elements 0 is called an skew symmetric matrix [alternating matrix]   
- That is, if i = j, a<sub>ij</sub> = 0, and if i ≠ j, a<sub>ij</sub> = -a<sub>ji</sub>   
   
```
┌   0      a ₁₂   ...   a ₁n ┐
│ -a ₁₂     0     ...   a ₂n │
│  ...     ...    ...    ... │
└ -a ₁n   -a ₂n   ...     0  ┘
```
   
// 예시   
// - 3차 정방행렬에서 a<sub>12</sub> = 3, a<sub>13</sub> = 2, a<sub>23</sub> = -1 의 원소를 가지는 역대칭행렬이 존재할 때 행렬의 나머지 원소를 구하시오   
- Example   
  - If there is an skew symmetric matrix with elements a<sub>12</sub> = 3, a<sub>13</sub> = 2, a<sub>23</sub> = -1 in third-order square matrix, find the remaining elements of the matrix   
   
```
┌  0  3  2 ┐
│ -3  0 -1 │
└ -2  1  0 ┘
```
   
#### Triangular matrix   
// 삼각행렬   
   
// n차 정방행렬에서   
- in the nth-order square matrix   
   
// ① 상삼각행렬 : 주대각선 아래에 있는 모든 원소들이 0일 경우 (i ＞ j 일 때, a<sub>ij</sub> = 0)   
① Upper triangular matrix : A case where all the elements below the main diagonal are zero (When i ＞ j, a<sub>ij</sub> = 0)   
   
```
┌ a ₁₁   a ₁₂   ...   a ₁n ┐
│  0     a ₂₂   ...   a ₂n │
│ ...    ...    ...   ...  │
└  0      0     ...   a nn ┘
```
   
// ② 하삼각행렬 : 주대각선 위에 있는 모든 원소들이 0일 경우 (i ＜ j 일 때, a<sub>ij</sub> = 0)   
② Lower triangular matrix : A case where all the elements above the main diagonal are zero (When i ＜ j, a<sub>ij</sub> = 0)   
   
```
┌ a ₁₁    0     ...    0   ┐
│ a ₂₁   a ₂₂   ...    0   │
│ ...    ...    ...   ...  │
└ a n₁   a n₂   ...   a nn ┘
```
   
// ③ 삼각행렬 : 상삼각행렬 또는 하삼각행렬   
③ Triangular matrix : Upper or Lower triangular matrix   
   
// 예시   
// - 다음 행렬들 중에서 삼각행렬이 아닌 것을 고르시오   
- Example   
  - Choose one of the following matrices that is not a triangular matrix   
   
(1)   
```
┌ 1 0 0 0 ┐
│ 0 1 0 0 │
│ 0 0 1 0 │
└ 0 0 0 1 ┘
```
// ∴ 상삼각행렬임. 하삼각행렬임. 삼각행렬임. 단위행렬임   
∴ It's an upper triangular matrix. It's a lower triangular matrix. It's a triangular matrix. It's a unit matrix   
   
(2)   
```
┌  1  0  0  0 ┐
│  0  1  0  0 │
│  0  0  0  0 │
└ -1  0  0  1 ┘
```
// ∴ 상삼각행렬 아님. 하삼각행렬임. 삼각행렬임   
∴ It's not an upper triangular matrix. It's a lower triangular matrix. It's a triangular matrix   
   
(3)   
```
┌ 0 0 0 3 ┐
│ 0 0 3 0 │
│ 0 2 1 0 │
└ 3 1 0 1 ┘
```
// ∴ 상삼각행렬 아님. 하삼각행렬 아님. 삼각행렬 아님   
∴ It's not an upper triangular matrix. It's not a lower triangular matrix. It's not a triangular matrix   
   
(4)   
```
┌ 0 0 0 0 ┐
│ 0 0 0 0 │
│ 0 0 0 0 │
└ 0 0 0 0 ┘
```
// ∴ 상삼각행렬임. 하삼각행렬임. 삼각행렬임. 스칼라행렬임   
∴ It's an upper triangular matrix. It's a lower triangular matrix. It's a triangular matrix. It's a scalar matrix   
   
#### Transpose matrix   
// 전치행렬   
   
// m x n 행렬 A가 주어졌을 때 A의 행과 열을 서로 교환한 행렬을 A의 전치행렬이라고 함 (A<sup>T</sup>로 표기)   
// A<sup>T</sup>의 크기는 n x m 임   
- Given an m x n matrix A, the matrix that exchanged rows and columns of A is called the transpose of A (Write as A<sup>T</sup>)   
- A<sup>T</sup> has a size of n x m   
   
- Matrix A   
```
┌ a ₁₁   a ₁₂   a ₁₃   ...   a ₁n ┐
│ a ₂₁   a ₂₂   a ₂₃   ...   a ₂n │
│ ...    ...    ...    ...   ...  │
└ a m₁   a m₂   a m₃   ...   a mn ┘
```
   
- Matrix A<sup>T</sup>   
```
┌ a ₁₁   a ₂₁   ...   a m₁ ┐
│ a ₁₂   a ₂₂   ...   a m₂ │
│ a ₁₃   a ₂₃   ...   a m₃ │
│ ...    ...    ...   ...  │
└ a ₁n   a ₂n   ...   a mn ┘
```
   
// 예시   
// - 다음 행렬들의 전치행렬을 구하시오   
- Example   
  - Find the transpose matrix of the following matrices   
   
- Matrix A   
```
┌ 1 0 0 0 ┐
│ 3 1 0 0 │
│ 0 0 1 0 │
└ 1 0 0 1 ┘
```
   
- Matrix A<sup>T</sup>   
```
┌ 1 3 0 1 ┐
│ 0 1 0 0 │
│ 0 0 1 0 │
└ 0 0 0 1 ┘
```
   
- Matrix B   
```
┌ 1 0 0 0 3 ┐
└ 0 0 1 0 0 ┘
```
   
- Matrix B<sup>T</sup>   
```
┌ 1 0 ┐
│ 0 0 │
│ 0 1 │
│ 0 0 │
└ 3 0 ┘
```
   
#### Inverse matrix   
// 역행렬   
   
// n차 정방행렬 A, B가 주어졌을 때 AB = BA = I<sub>n</sub> 인 행렬 B가 존재하는 경우 행렬 A를 역가능 (invertible. 역연산이 가능한) 하다고 함 (I<sub>n</sub> 은 단위행렬임)   
// 이때 행렬 B를 행렬 A의 역행렬이라고 하고 A<sup>-1</sup>로 표기함   
- Given nth-order square matrices A and B, matrix A is called invertible (reverse-calculated) if there exists matrix B with AB = BA = I<sub>n</sub> (I<sub>n</sub> is a unit matrix)   
- In this case, matrix B is called the inverse matrix of matrix A and is written as A<sup>-1</sup>   
   
<br />
### Boolean matrix   
// 부울행렬   
   
// 행렬의 모든 원소가 부울값 (0 or 1) 으로만 구성된 행렬을 부울행렬이라 한다   
- A matrix in which all elements of a matrix consist only of Boolean values (0 or 1) is called a Boolean matrix   
   
// 예시   
// - 다음 중 부울행렬은?   
- Example   
  - Which of the following Boolean matrices?   
   
- Matrix A   
```
┌ 0 0 ┐
└ 0 0 ┘
```
// ∴ 부울행렬임   
∴ It's boolean matrix   
   
- Matrix B   
```
┌  1  2  3 ┐
└ -1 -2 -3 ┘
```
// ∴ 부울행렬 아님   
∴ It's not boolean matrix   
   
- Matrix C   
```
┌ 1 0 ┐
└ 0 1 ┘
```
// ∴ 부울행렬임   
∴ It's boolean matrix   
   
- Matrix D   
```
┌ 0 1 ┐
└ 1 1 ┘
```
// ∴ 부울행렬임   
∴ It's boolean matrix   
   
#### Join of Boolean matrix, Meet of Boolean matrix   
// 부울행렬의 합 (join), 교차 (meet)   
   
// 크기가 m x n인 두 행렬 A = [a<sub>ij</sub>] 와 B = [b<sub>ij</sub>] 가 부울행렬일 때   
- If A = [a<sub>ij</sub>] and B = [b<sub>ij</sub>] are boolean matrices with m x n size   
   
// ① A 와 B 의 합 (join) : (i, j) 원소가 a<sub>ij</sub> ∨ b<sub>ij</sub> 이고 크기가 m x n 인 부울행렬 C 이며, C = A ∨ B 로 나타낸다   
① Sum of A and B (join) : (i, j) element is a<sub>ij</sub> ∨ b<sub>ij</sub>, Boolean matrix C with size m x n, expressed as C = A ∨ B   
   
```
┌ 1 0 ┐ ∨ ┌ 1 0 ┐  = ┌ 1 0 ┐
└ 1 1 ┘    └ 0 0 ┘    └ 1 1 ┘
```
   
// ② A와 B의 교차 (meet) : (i, j) 원소가 a<sub>ij</sub> ∧ b<sub>ij</sub> 이고 크기가 m x n 인 부울행렬 C 이며, C = A ∧ B 로 나타낸다   
② Meet of A and B (meet) : (i, j) element is a<sub>ij</sub> ∧ b<sub>ij</sub>, Boolean matrix C with size m x n, expressed as C = A ∧ B   
   
```
┌ 1 0 ┐ ∧ ┌ 1 0 ┐  = ┌ 1 0 ┐
└ 1 1 ┘    └ 0 0 ┘    └ 0 0 ┘
```
   
#### Boolean product of a Boolean matrix   
// 부울행렬의 부울곱 (boolean product)   
   
// m x n 행렬 A = [a<sub>ij</sub>] 와 n x l 행렬 B = [b<sub>ij</sub>] 가 부울행렬일 때   
// - A와 B의 부울곱 (boolean product) 은 (i, j) 원소가 다음과 같이 정의되는 m x l 크기의 부울행렬 C 이며, C = A ⊙ B 로 나타낸다   
// -- c<sub>ij</sub> = (a<sub>i1</sub> ∧ b<sub>1j</sub>) ∨ (a<sub>i2</sub> ∧ b<sub>2j</sub>) ∨ ... ∨ (a<sub>in</sub> ∧ b<sub>nj</sub>)   
// --- ∨<sup>n</sup><sub>k = 1</sub>(a<sub>ik</sub> ∧ b<sub>kj</sub>)   
- If m x n matrix A = [a<sub>ij</sub>] and n x l matrix B = [b<sub>ij</sub>] are Boolean matrices   
  - The Boolean product of A and B is an m x l Boolean matrix C in which the (i, j) element is defined as follows, and is written with C = A ⊙ B   
    - c<sub>ij</sub> = (a<sub>i1</sub> ∧ b<sub>1j</sub>) ∨ (a<sub>i2</sub> ∧ b<sub>2j</sub>) ∨ ... ∨ (a<sub>in</sub> ∧ b<sub>nj</sub>)   
      - ∨<sup>n</sup><sub>k = 1</sub>(a<sub>ik</sub> ∧ b<sub>kj</sub>)   
   
// 예시   
// - 다음 연산을 수행하고 그 결과를 구하시오   
- Example   
  - Perform the following operations and obtain the results   
   
```
┌ 0 0 0 ┐    ┌ 1 0 0 ┐  = ┌ 1 0 0 ┐
│ 0 0 0 │ ∨ │ 1 1 0 │    │ 1 1 0 │
└ 1 1 1 ┘    └ 1 0 0 ┘    └ 1 1 1 ┘
```
   
```
┌ 0 0 0 ┐    ┌ 1 0 0 ┐  = ┌ 0 0 0 ┐
│ 0 0 0 │ ∧ │ 1 1 0 │    │ 0 0 0 │
└ 1 1 1 ┘    └ 1 0 0 ┘    └ 1 0 0 ┘
```
   
```
┌ 0 0 0 ┐    ┌ 1 0 0 ┐  = ┌ 0 0 0 ┐
│ 0 0 0 │ ⊙ │ 1 1 0 │    │ 0 0 0 │
└ 1 1 1 ┘    └ 1 0 0 ┘    └ 1 1 0 ┘
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
