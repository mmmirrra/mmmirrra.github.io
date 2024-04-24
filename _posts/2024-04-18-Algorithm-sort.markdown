---
layout: post
title:  "Algorithm: Sort"
date:   2024-04-18 09:00:00 +0900
categories: [Algorithm]
---

### The basic concept of Sort   
// 정렬의 기본 개념   
   
// 정렬 : 주어진 데이터를 값의 크기 순서에 따라 재배치하는 것   
// - 오름차순, 내림차순   
- Sort : Relocating given data in order of size of values   
  - Ascending order, Descending order   
   
// 정렬 구분 : 정렬 수행 시점에 데이터가 어디에 저장되어 있는가에 따라 구분   
// - 내부 정렬   
// -- 전체 데이터를 주기억장치에 저장한 후 정렬을 수행하는 방식   
// - 외부 정렬   
// -- 모든 데이터를 주기억장치에 저장할 수 없는 경우 모든 데이터를 보조기억장치에 저장해 두고 그 중 일부 데이터만을 반복적으로 주기억장치로 옮겨와서 정렬을 수행하는 방식   
- Sort by : Categorize by where the data is stored at the time of sorting   
  - Internal Sort   
    - To store the entire data in the main memory and then perform sorting   
  - External Sort   
    - If all data cannot be stored in the main memory, all data is stored in the secondary memory, and only some of the data is repeatedly moved to the main memory to perform sorting   
   
#### Internal sorting algorithm   
// 내부 정렬 알고리즘   
   
// 정렬 방식에 따른 구분   
// - 비교 기반 알고리즘   
// - 데이터 분포 기반 알고리즘   
- Classification by sorting method   
  - Comparison-based algorithm   
  - Data distribution-based algorithm   
   
// 비교 기반 알고리즘 : 키값의 비교 횟수로 알고리즘의 성능을 나타냄   
// - 성능이 O(n²) 인 정렬   
// -- 선택 정렬   
// -- 버블 정렬   
// -- 삽입 정렬   
// -- 셸 정렬   
// - 성능이 O(nlogn) 인 정렬   
// -- 퀵 정렬   
// -- 합병 정렬   
// -- 힙 정렬   
- Comparison-based algorithm : The number of comparisons of key values shows the performance of the algorithm   
  - Sort of O(n²) performance   
    - Selection Sort   
    - Bubble Sort   
    - Insertion Sort   
    - Shell Sort   
  - Sort of O(nlogn) performance   
    - Quick Sort   
    - Merge Sort   
    - Heap Sort   
   
// 데이터 분포 기반 알고리즘 : 데이터의 이동 횟수로 알고리즘의 성능을 나타냄   
// - 성능이 O(n) 인 정렬 : 정렬을 하기 전에 데이터가 어떻게 분포되어 있는지 제한된 조건에 맞는 정보를 활용하여 정렬하는 과정에 사용함   
// -- 계수 정렬   
// -- 기수 정렬   
// -- 버킷 정렬   
- Data distribution-based algorithm : The number of movements of data indicates the performance of the algorithm   
  - Sort of O(n) performance : Use to sort how data is distributed before sorting, using information that meets limited conditions   
    - Counting Sort   
    - Radix Sort   
    - Bucket Sort   
   
// 어떤 데이터를 정렬할 때 대부분의 경우 어떤 데이터가 분포되어 있는지 사전에 알기 어렵기 때문에 비교 기반 알고리즘을 일반적으로 사용함   
- When sorting which data, comparison-based algorithms are commonly used because in most cases it is difficult to know in advance what data is distributed   
   
#### Sort-Related Concepts   
// 정렬 관련 개념   
   
// 안정적 (Stable) 정렬 : 동일한 값을 갖는 데이터가 여러 개 있을 때 정렬 전의 상대적 위치가 정렬 후에도 그대로 유지되는 정렬   
// - 예시   
// -- 입력 데이터 : [50, 10, 20 (이름A), 30, 60, 20 (이름B), 40]   
// --- 정렬 데이터 1 : [10, 20 (이름A), 20 (이름B), 30, 40, 50, 60] → "안정적 (Stable) 정렬"   
// --- 정렬 데이터 2 : [10, 20 (이름B), 20 (이름A), 30, 40, 50, 60] → "불안정적 (Unstable) 정렬"   
- Stable Sort : Sort in which the relative position before sort remains the same after sort when there are multiple pieces of data with the same value   
  - Example   
    - Input data : [50, 10, 20 (name A), 30, 60, 20 (name B), 40]   
      - Sorting data 1 : [10, 20 (name A), 20 (name B), 30, 40, 50, 60] → "Stable Sort"   
      - Sorting data 2 : [10, 20 (name B), 20 (name A), 30, 40, 50, 60] → "Unstable Sort"   
   
// 제자리 (in-place) 정렬   
// - 입력 배열 외에도 별도로 필요한 저장 공간이 상수 개를 넘지 않는 정렬   
// -- 입력 크기 n이 증가함에도 불가하고 추가적인 저장 공간은 증가하지 않음   
- In-place Sort   
  - In addition to the input array, an sort that does not exceed a set number of storage requirements   
    - No additional storage despite increasing input size n   
   
#### Basic assumptions of sorting algorithm   
// 정렬 알고리즘의 기본 가정   
   
// A[] → [0, 1, ..., n - 1] : 총 n개 값을 가진 배열   
- A[] → [0, 1, ..., n - 1] : Array with a total of n values   
   
```c
A[i] ＞ 0, (0 ≤ i ≤ n - 1)
Sorting Result → if i ＜ j then A[i] ≤ A[j], (0 ≤ i, j ≤ n - 1)
```
   
// 입력 배열 : A[0 .. n - 1]   
// 입력 크기 : n   
// 입력 데이터 : 양의 정수   
// 정렬 방식 : 오름차순   
- Input Array : A[0 .. n - 1]   
- Input Size : n   
- Input Data : Positive integer   
- Sorting Method : Ascending order   
   
<br />
### Selection Sort   
// 선택 정렬   
   
// 입력 배열에서 가장 작은 값부터 순서대로 '선택'해서 나열하는 방식   
- To 'select' and list the smallest values in the input array in order   
   
// - 예시   
// -- 입력 데이터 : [60, 20, 70, 10, 80, 30, 50, 40]   
// -- 정렬 결과 : [10, 20, 30, 40, 50, 60, 70, 80]   
  - Example   
    - Input Data : [60, 20, 70, 10, 80, 30, 50, 40]   
    - Sorting Result : [10, 20, 30, 40, 50, 60, 70, 80]   
   
#### Processing of Selection Sort   
// 선택 정렬의 처리 과정   
   
|A[0 .. n - 1], i = 0|
|:---:|
|↓|
|──── i = i + 1 ──→ ◇ i ＜ n - 1 ──→ No ────|
|│ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Yes ↓ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; │|
|① 미정렬 부분 A[i .. n - 1]에서 최소값 찾기<br />│ &nbsp; ① Find a minimum value in Unsorted part A[i .. n - 1] &nbsp; │|
|│ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ↓ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; │|
|② 최소값과 데이터 A[i]와 위치 교환<br />└─ ② Interchange the minimum value with the data A[i] │|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ┌──────────|
|↓|
|정렬 완료<br />Sorting is complete|
   
#### Selection Sort Algorithm   
// 선택 정렬 알고리즘   
   
```c
SelectionSort (A[], n)
{
    for (i = 0; i < n - 1; i++)    // Repeat (n - 1)
    { 
        // ① A[i .. n - 1] 에서 최소값 찾기 
        // ① Find a minimum value in A[i .. n - 1]
        min = i;
        for (j = i + 1; j < n; j++)
            if (A[min] > A[j])
                min = j;
        // ② 최소값과 A[i] 의 위치 교환
        // ② Interchange the minimum and A[i] positions
        // A[i] 와 A[min] 의 자리바꿈;
        Change of A[i] and A[min] places;
    }
    return (A);
}
```
   
#### Performance and Features   
// 성능과 특징   
   
// 성능   
// - `for (i = 0; i < n - 1; i++)` → 루프 i : [0, 1, 2, ..., n - 2]   
// - `for (j = i + 1; j < n; j++)` → 루프 j의 비교 횟수 : [n - 1, n - 2, n - 3, ..., 1]   
// -- → 총 비교 횟수 (n - 1) + (n - 2) + ... + 1 = <sup>n(n - 1)</sup> / <sub>2</sub>   
// -- → 최고차수는 n²   
// -- → ∴ O(n²)   
- Performance   
  - `for (i = 0; i < n - 1; i++)` → loop i : [0, 1, 2, ..., n - 2]   
  - `for (j = i + 1; j < n; j++)` → Number of comparisons of loop j : [n - 1, n - 2, n - 3, ..., 1]   
    - Total number of comparisons is (n - 1) + (n - 2) + ... + 1 = <sup>n(n - 1)</sup> / <sub>2</sub>   
    - The highest degree term is n²   
    - ∴ O(n²)   
   
// 특징   
// - 입력 데이터의 순서에 민감하지 않음   
// -- 최소값 찾기 : 미정렬 부분 A[i .. n - 1] 에서 항상 (n - 1) - i 번의 비교가 필요   
// --- 입력 데이터의 상태와 상관없이 항상 동일한 성능 O(n²) 을 가짐   
// - 제자리 정렬 알고리즘   
// -- 입력 배열 A[] 이외에 상수 개의 저장 공간 (예시 : i, j, min, tmp) 만 필요   
// -- 이 외 추가적인 메모리가 필요하지 않음   
// - 안정적이지 않은 정렬 알고리즘   
- Features   
  - Not sensitive to the order of input data   
    - Finding the minimum value : Unsorted part A[i .. n - 1] always requires (n - 1) - i comparisons   
      - Always have the same performance O(n²) regardless of the state of the input data   
  - In-place Sort algorithm   
    - Only a constant number of storage spaces (e.g., i, j, min, tmp) other than the input array A[]   
    - No additional memory required   
  - Unstable Sort algorithm   
   
<br />
### Bubble Sort   
// 버블 정렬   
   
// 모든 인접한 두 데이터를 차례대로 비교해서 왼쪽 데이터가 더 큰 경우에는 오른쪽 데이터와 자리를 바꾸는 과정을 반복해서 정렬을 수행하는 방식   
- Compare all two adjacent data in turn, and if the data on the left is larger, replace the data on the right with the data on the left. This process is repeatedly sorted   
   
// 비교를 진행하는 방향   
// - 왼쪽에서 오른쪽으로 진행 (→)   
// -- 가장 큰 값부터 찾아서 오른쪽 끝에서부터 위치시킴   
// - 오른쪽에서 왼쪽으로 진행 (←)   
// -- 가장 작은 값부터 찾아서 왼쪽 끝에서부터 위치시킴   
- Direction of comparison   
  - From left to right (→)   
    - Find the largest value first and position it from the right end   
  - From right to left (→)   
    - Find the smallest value first and position it from the left end   
   
#### Basic form of Bubble Sort algorithm   
// 기본 형태의 버블 정렬 알고리즘   
   
```c
BubbleSort (A[], n)
{
    for (i = 0; i < n - 1; i++)    // Step : Repeat (n - 1) times
        for (j = 0; j < n - 1; j++)    // From left to right
            if (A[j] > A[j + 1])    // If it is 'left data > right data'
                // A[j] 와 A[j + 1] 의 자리바꿈;
                Change of A[j] and A[j + 1] places;
    return (A);
}
```
   
#### Example 1 of Bubble Sort (left → right)   
// 버블 정렬의 예시 1 (왼쪽 → 오른쪽)   
   
|Step||||||||||||||||||||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>0</b>|30|↔|20||40|↔|35|↔|5|↔|10||45||50|↔|25|↔|15|
|<b>1</b>|20||30||35|↔|5|↔|10||40||45|↔|25|↔|15||<b>50</b>|
|<b>2</b>|20||30|↔|5|↔|10||35||40|↔|25|↔|15||<b>45</b>||<b>50</b>|
|<b>3</b>|20|↔|5|↔|10||30||35|↔|25|↔|15||<b>40</b>||<b>45</b>||<b>50</b>|
|<b>4</b>|5||10||20||30|↔|25|↔|15||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
|<b>5</b>|5||10||20||25|↔|15||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
|<b>6</b>|5||10||20|↔|15||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
|<b>7</b>|5||10||15||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
|<b>8</b>|5||10||<b>15</b>||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
|<b>Finish</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
   
#### Example 2 of Bubble Sort (right → left)   
// 버블 정렬의 예시 2 (오른쪽 → 왼쪽)   
   
|Step||||||||||||||||||||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>0</b>|30|↔|20|↔|40|↔|35|↔|5||10||45|↔|50|↔|25|↔|15|
|<b>1</b>|<b>5</b>|↔|30|↔|20|↔|40|↔|35|↔|10||15||45|↔|50|↔|25|
|<b>2</b>|<b>5</b>||<b>10</b>||30|↔|20|↔|40|↔|35|↔|15||25||45||50|
|<b>3</b>|<b>5</b>||<b>10</b>||<b>15</b>||30|↔|20||40|↔|35|↔|25||45||50|
|<b>4</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||30|↔|25||40|↔|35||45||50|
|<b>5</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||<b>25</b>||30||35||40||45||50|
|<b>6</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||<b>25</b>||<b>30</b>||35||40||45||50|
|<b>7</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||40||45||50|
|<b>8</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||45||50|
|<b>Finish</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
   
#### Performance and Features   
// 성능과 특징   
   
// 성능   
// - `for (i = 0; i < n - 1; i++)` → 루프 i의 비교 횟수 : [0, 1, 2, ..., n - 2] → (n - 1) 회   
// - `for (j = 0; j < n - 1; j++)` → 루프 j의 비교 횟수 : [0, 1, 2, ..., n - 2] → (n - 1) 회   
// -- → 총 비교 횟수 ∴ O(n²)   
- Performance   
  - `for (i = 0; i < n - 1; i++)` → Number of comparisons of loop i : [0, 1, 2, ..., n - 2] → (n - 1)   
  - `for (j = 0; j < n - 1; j++)` → Number of comparisons of loop j : [0, 1, 2, ..., n - 2] → (n - 1)   
    -  → Total number of comparisons is ∴ O(n²)   
   
// 특징   
// - 안정적인 정렬 알고리즘   
// -- 인접한 두 데이터가 동일한 경우 → 위치 교환이 미발생   
// - 제자리 정렬 알고리즘   
// -- 입력 배열 A[] 이외에 상수 개의 저장 공간 (예시 : i, j, tmp) 만 필요   
// - 선택 정렬에 비해 데이터 교환이 많이 발생   
// -- 선택 정렬과 성능은 O(n²) 으로 동일하지만, 선택 정렬보다 비효율적   
- Features   
  - Stable Sort algorithm   
    - If two adjacent data are the same → No location exchange has occurred   
  - In-place Sort algorithm   
    - Only a constant number of storage spaces (e.g., i, j, tmp) other than the input array A[]   
  - More data exchange than Selection Sort   
    - The performance of Bubble Sort and Selection Sort is the same as O(n²), but less inefficient than Selection Sort   
   
#### Improved Bubble Sort algorithm   
// 개선된 버블 정렬 알고리즘   
   
// 각 루프의 반복 횟수를 줄여서 개선 가능   
// - 처리 단계의 수   
// -- 자리바꿈이 발생하지 않으면 이미 정렬된 상태이므로 이후의 처리 단계를 수행하지 않고 종료   
// - 인접한 두 데이터의 비교 횟수   
// -- 각 단계에서 무조건 오른쪽/왼쪽 끝까지 이동하면서 인접한 두 데이터의 비교가 불필요   
// --- 이미 제자리를 잡은 데이터에 대해서는 비교를 수행하지 않도록 함   
- Improvements can be made by reducing the number of iterations of each loop   
  - Number of processing steps   
    - If no place change occurs, it is already sorted, so exit without performing any further processing steps   
  - Number of comparisons between two adjacent data   
    - Unconditionally moving to the right/left end at each stage, requiring no comparison of two adjacent data   
      - Avoid making comparisons for data that are already in place   
   
```c
Advanced_BubbleSort (A[], n)
{
    for (i = 0; i < n - 1; i++)    // Step : 0, 1, ..., (n - 2)
        Sorted = TRUE;    // TRUE means that sort is finished
        for (j = 0; j < (n - 1) - i; j++)    // From left to right
            if (A[j] > A[j + 1])    // If it's 'left Data > right data'
            {
                // A[j] 와 A[j + 1] 의 자리바꿈;
                Change of A[j] and A[j + 1] places;
                Sorted = FALSE;    // Place change occurred → Unsorted status (FALSE means that sort is not finished)
            }
            if (Sorted == TRUE) break;    // Break because it is already sorted
    return (A);
}
```
   
#### Performance and Features of Improved Algorithms   
// 개선된 알고리즘의 성능과 특징   
   
// 성능   
// - 시간 복잡도 ∴ O(n²)   
// -- → 총 비교 횟수 (n - 1) + (n - 2) + ... + 1 = <sup>n(n - 1)</sup> / <sub>2</sub>   
- Performance   
  - Time complexity ∴ O(n²)   
    - Total number of comparisons is (n - 1) + (n - 2) + ... + 1 = <sup>n(n - 1)</sup> / <sub>2</sub>   
   
// 특징   
// - 입력 데이터의 상태에 따라 성능이 달라짐   
// -- 역순으로 정렬된 경우   
// --- 비교 횟수 (n - 1) + (n - 2) + ... + 2 + 1   
// --- 최악의 경우 O(n²)   
// -- 원하는 순서로 이미 정렬된 경우   
// --- 비교 횟수 n - 1   
// --- 최선의 경우 O(n)   
- Features   
  - Performance varies depending on the state of the input data   
    - If sorted in reverse order   
      - Number of comparisons is (n - 1) + (n - 2) + ... + 2 + 1   
      - Worst case O(n²)   
    - If it's already sorted in the desired order   
      - Number of comparisons is n - 1   
      - Best case O(n)   
   
<br />
### Insertion Sort   
// 삽입 정렬   
   
// 주어진 데이터를 하나씩 뽑은 후 이미 나열된 데이터가 항상 정렬된 상태를 유지하도록 뽑은 데이터를 바른 위치에 삽입해서 나열하는 방식   
// - 입력 배열을 정렬 부분 A[0 .. K - 1] 과 미정렬 부분 A [k .. n - 1] 으로 구분해서 처리   
// -- A[0] 를 정렬 부분, A[1 .. n - 1] 은 미정렬 부분으로 취급하여 시작   
// -- k = 1, ..., n - 1 까지 반복   
// --- 미정렬 부분 A[k .. n - 1] 의 첫 번째 데이터 A[k] 를 뽑고,   
// --- 정렬 부분 A[0 .. k - 1] 에서 제자리를 찾아 A[k] 를 삽입해서 A[0 .. k] 가 정렬 상태를 유지하도록 만듦   
- To insert and list the selected data in the correct place, while the data already listed remains sorted, after extracting the given data one by one   
  - Processing input arrays into Sorted part A[0 .. K - 1] and Unsorted part A [k .. n - 1]   
    - Start by treating A[0] as an Sorted part and A[1 .. n - 1] as an Unsorted part   
    - k = Repeat until 1, ..., n - 1   
      - Pull out the first data A[k] of the Unsorted part A[k .. n - 1],   
      - Finding a right place in the Sorted part A[0...k-1] and insert A[k] to ensure that A[0...k] remains sorted   
      - Locate the correct place in the Sorted part A[0...k-1] and insert A[k] to ensure that A[0...k] remains sorted   
   
#### The process of finding the correct place in the Sorted part   
// 정렬 부분에서 제자리를 찾는 과정   
   
// Step 1 ~ 2 는 설명 생략   
// Step 3   
// - 정렬 부분 A[0 .. 2] : [10, 30, 40]   
// - 미정렬 부분 A[3 .. 6] : [20, 70, 50, 60]   
// - 20을 뽑아서 정렬 부분에 삽입 : 맨 뒤에서부터 값을 비교하여 들어갈 수 있는지 확인   
// -- 20과 40을 비교 : [10, 30, (40 ? 20)] [비었음, 70, 50, 60] → 40이 큼 → [10, 30, 비었음] [40, 70, 50, 60]   
// -- 20과 30을 비교 : [10, (30 ? 20), 비었음] [40, 70, 50, 60] → 30이 큼 → [10, 비었음, 30] [40, 70, 50, 60]   
// -- 20과 10을 비교 : [(10 ? 20), 비었음, 30] [40, 70, 50, 60] → 10이 작음 → [10, 20, 30] [40, 70, 50, 60]   
// ∴ 20이 자리를 찾았으므로 정렬 부분, 미정렬 부분이 달라짐   
// - 정렬 부분 A[0 .. 3] : [10, 20, 30, 40]   
// - 미정렬 부분 A[4 .. 6] : [70, 50, 60]   
// Step 4   
// - 70을 뽑아서 정렬 부분에 삽입 : 맨 뒤에서부터 값을 비교하여 들어갈 수 있는지 확인   
// -- 70과 40을 비교 : [10, 20, 30, (40 ? 70)] [비었음, 50, 60] → 40이 작음 → [10, 20, 30, 40] [70, 50, 60]   
// ∴ 70이 자리를 찾았으므로 정렬 부분, 미정렬 부분이 달라짐   
// - 정렬 부분 A[0 .. 4] : [10, 20, 30, 40, 70]   
// - 미정렬 부분 A[5 .. 6] : [50, 60]   
// Step 5   
// - 50을 뽑아서 정렬 부분에 삽입 : 맨 뒤에서부터 값을 비교하여 들어갈 수 있는지 확인   
// -- 50과 70을 비교 : [10, 20, 30, 40, (70 ? 50)] [비었음, 60] → 70이 큼 → [10, 20, 30, 40, 비었음] [70, 60]   
// -- 50과 40을 비교 : [10, 20, 30, (40 ? 50), 비었음] [70, 60] → 40이 작음 → [10, 20, 30, 40, 50] [70, 60]   
// ∴ 50이 자리를 찾았으므로 정렬 부분, 미정렬 부분이 달라짐   
// - 정렬 부분 A[0 .. 5] : [10, 20, 30, 40, 50, 70]   
// - 미정렬 부분 A[6 .. 6] : [60]   
// Step 6   
// - 60을 뽑아서 정렬 부분에 삽입 : 맨 뒤에서부터 값을 비교하여 들어갈 수 있는지 확인   
// -- 60과 70을 비교 : [10, 20, 30, 40, 50, (70 ? 60)] [비었음] → 70이 큼 → [10, 20, 30, 40, 50, 비었음] [70]   
// -- 60과 50을 비교 : [10, 20, 30, 40, (50 ? 60), 비었음] [70] → 50이 작음 → [10, 20, 30, 40, 50, 60] [70]   
// ∴ 60이 자리를 찾았으므로 정렬 부분, 미정렬 부분이 달라짐   
// - 정렬 부분 A[0 .. 6] : [10, 20, 30, 40, 50, 60, 70]   
// - 미정렬 부분 없음   
- Steps 1 to 2 omit explanation   
- Step 3   
  - Sorted part A[0 .. 2] : [10, 30, 40]   
  - Unsorted part A[3 .. 6] : [20, 70, 50, 60]   
  - Pull 20 and insert it into the Sorted part : Check if it can be inserted by comparing values from the back   
    - Compare 20 and 40 : [10, 30, (40 ? 20)] [Empty, 70, 50, 60] → 40 is big → [10, 30, Empty] [40, 70, 50, 60]   
    - Compare 20 and 30 : [10, (30 ? 20), Empty] [40, 70, 50, 60] → 30 is big → [10, Empty, 30] [40, 70, 50, 60]   
    - Compare 20 and 10 : [(10 ? 20), Empty, 30] [40, 70, 50, 60] → 10 is small → [10, 20, 30] [40, 70, 50, 60]   
- ∴ 20 has found a place, so the Sorted part and Unsorted part are different   
  - Sorted part A[0 .. 3] : [10, 20, 30, 40]   
  - Unsorted part A[4 .. 6] : [70, 50, 60]   
- Step 4   
  - Pull 70 and insert it into the Sorted part : Check if it can be inserted by comparing values from the back   
    - Compare 70 and 40 : [10, 20, 30, (40 ? 70)] [Empty, 50, 60] → 40 is small → [10, 20, 30, 40] [70, 50, 60]   
- ∴ 70 has found a place, so the Sorted part and Unsorted part are different   
  - Sorted part A[0 .. 4] : [10, 20, 30, 40, 70]   
  - Unsorted part A[5 .. 6] : [50, 60]   
- Step 5   
  - Pull 50 and insert it into the Sorted part : Check if it can be inserted by comparing values from the back   
    - Compare 50 and 70 : [10, 20, 30, 40, (70 ? 50)] [Empty, 60] → 70 is big → [10, 20, 30, 40, Empty] [70, 60]   
    -  Compare 50 and 40 : [10, 20, 30, (40 ? 50), Empty] [70, 60] → 40 is small → [10, 20, 30, 40, 50] [70, 60]   
- ∴ 50 has found a place, so the Sorted part and Unsorted part are different   
  - Sorted part A[0 .. 5] : [10, 20, 30, 40, 50, 70]   
  - Unsorted part A[6 .. 6] : [60]   
- Step 6   
  - Pull 60 and insert it into the Sorted part : Check if it can be inserted by comparing values from the back   
    - Compare 60 and 70 : [10, 20, 30, 40, 50, (70 ? 60)] [Empty] → 70 is big → [10, 20, 30, 40, 50, Empty] [70]   
    - Compare 60 and 50 : [10, 20, 30, 40, (50 ? 60), Empty] [70] → 50 is small → [10, 20, 30, 40, 50, 60] [70]   
- ∴ 60 has found a place, so the Sorted part and Unsorted part are different   
  - Sorted part A[0 .. 6] : [10, 20, 30, 40, 50, 60, 70]   
  - No Unsorted part   
   
#### Insertion Sort algorithm   
// 삽입 정렬 알고리즘   
   
// 오름차순 정렬   
- Sort in ascending order   
   
```c
InsertionSort (A[], n)
{
    for (i = 1; i < n; i++) {    // Sorted part A[0] : Repeat (n - 1) times until 1, ..., (n - 1)
        val = A[i];    // Select the first data of the unsorted part A[i .. n - 1]
        for (j = 1; j > 0 && A[j - 1] > val; j--)    // Find a place to insert
            A[j] = A[j - 1];    // Move back when A[j - 1] in Sorted part is large
        A[j] = val;    // Insert selected data in the found place
    }
    return (A);
}
```
   
// 내림차순으로 정렬할 경우 부등호 하나만 바꾸면 됨   
- Change only one inequality when sorted in descending order   
- `for (j = 1; j > 0 && A[j - 1] > val; j--)` → `for (j = 1; j > 0 && A[j - 1] < val; j--)`   
   
```c
InsertionSort (A[], n)
{
    for (i = 1; i < n; i++) {    // Sorted part A[0] : Repeat (n - 1) times until 1, ..., (n - 1)
        val = A[i];    // Select the first data of the unsorted part A[i .. n - 1]
        for (j = 1; j > 0 && A[j - 1] < val; j--)    // Find a place to insert
            A[j] = A[j - 1];    // Move back when A[j - 1] in Sorted part is small
        A[j] = val;    // Insert selected data in the found place
    }
    return (A);
}
```
   
#### Example of Insertion Sort   
// 삽입 정렬의 예시   
   
|Step||||||||||||||||||||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>1</b>|<b>30</b>|?|20||40||35||5||10||45||50||25||15|
|<b>2</b>|<b>20</b>||<b>30</b>|?|40||35||5||10||45||50||25||15|
|<b>3</b>|<b>20</b>||<b>30</b>||<b>40</b>|?|35||5||10||45||50||25||15|
|<b>4</b>|<b>20</b>||<b>30</b>||<b>35</b>||<b>40</b>|?|5||10||45||50||25||15|
|<b>5</b>|<b>5</b>||<b>20</b>||<b>30</b>||<b>35</b>||<b>40</b>|?|10||45||50||25||15|
|<b>6</b>|<b>5</b>||<b>10</b>||<b>20</b>||<b>30</b>||<b>35</b>||<b>40</b>|?|45||50||25||15|
|<b>7</b>|<b>5</b>||<b>10</b>||<b>20</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>|?|50||25||15|
|<b>8</b>|<b>5</b>||<b>10</b>||<b>20</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|?|25||15|
|<b>9</b>|<b>5</b>||<b>10</b>||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|?|15|
|<b>Finish</b>|<b>5</b>||<b>10</b>||<b>15</b>||<b>20</b>||<b>25</b>||<b>30</b>||<b>35</b>||<b>40</b>||<b>45</b>||<b>50</b>|
   
#### Performance and Features   
// 성능과 특징   
   
// 성능   
// - `for (i = 1; i < n; i++)` → 바깥 루프 i : [1, 2, ..., n - 1]   
// - `for (j = 1; j > 0 && A[j - 1] > val; j--)` → 루프 j의 비교 횟수 : [1, 2, ..., n - 1] → 1 + 2 + ... + (n - 2) + (n - 1) = <sup>n(n - 1)</sup> / <sub>2</sub>   
// -- → 총 비교 횟수 ∴ O(n²)   
- Performance   
  - `for (i = 1; i < n; i++)` → Outer loop i : [1, 2, ..., n - 1]   
  - `for (j = 1; j > 0 && A[j - 1] > val; j--)` → Number of comparisons of loop j : [1, 2, ..., n - 1] → 1 + 2 + ... + (n - 2) + (n - 1) = <sup>n(n - 1)</sup> / <sub>2</sub>   
    - Total number of comparisons is ∴ O(n²)   
   
// 특징   
// - 안정적인 정렬 알고리즘   
// -- 인접한 두 데이터가 정렬되지 않은 경우에만 위치 교환 발생   
// - 제자리 정렬 알고리즘   
// -- 입력 배열 A[] 이외에 상수 개의 저장 공간 (예시 : i, j, val) 만 필요   
// - 입력 데이터의 원래 순서에 민감   
// -- 원하는 정렬 순서의 역순으로 주어지는 경우   
// --- 최악의 경우 O(n²)   
// -- 원하는 순서의 정렬된 상태로 주어지는 경우   
// --- 최선의 경우 O(n)   
- Features   
  - Stable Sort algorithm   
    - Place change only occurs when two adjacent data are not sorted   
  - In-place Sort algorithm   
    - Only a constant number of storage spaces (e.g., i, j, val) other than the input array A[]   
  - Sensitive to the original order of input data   
    - If given in reverse order of the desired sort order   
      - Worst case O(n²)   
    - If given in an sorted state of the desired order   
      - Best case O(n)   
   
<br />
### Shell Sort   
// 셸 정렬   
   
// 도날드 셸 (Donald L. Shell) 이라는 사람이 정의   
- Defined by Donald L. Shell   
   
// 삽입 정렬의 단점 보완   
// - 현재 삽입하고자 하는 데이터가 삽입될 제 위치에서 많이 벗어나 있어도 한 번에 한 자리씩만 이동해서 찾아가야 함   
- Complement the shortcomings of Insertion Sort   
  - The data currently intended to be inserted should be moved one digit at a time to find its place, even if it is far from where it is to be inserted   
   
// 기본 아이디어   
// - 멀리 떨어진 데이터와의 비교·교환으로 한 번에 이동할 수 있는 거리를 늘려서 처리 속도 향상   
// -- 처음에는 멀리 떨어진 두 데이터를 비교해서 필요시 위치를 교환하고, 점차 가까운 위치의 데이터를 비교·교환한 뒤, 맨 마지막에는 인접한 데이터를 비교·교환하는 방식   
// -- 입력 배열을 부분 배열로 나누어 삽입 정렬을 수행하는 과정을 부분 배열의 크기와 개수를 변화시켜 가면서 반복   
- Basic Idea   
  - Increase processing speed by increasing the distance traveled at once by comparing and exchanging far-flung data   
    - First, compare two far-flung data, exchange places if necessary, then gradually compare and exchange data at a nearby place, and finally compare and exchange adjacent data   
    - Repeat the process of performing Insertion Sort by dividing the input array into partial arrays while changing the size and number of partial arrays   
   
#### To determine the number of partial arrays   
// 부분 배열의 개수를 정하는 방법   
   
// 양수로 이루어진 임의의 순열 h<sub>1</sub>, ..., h<sub>k-1</sub>, h<sub>k</sub> 을 사용   
// - 1 ＜ i ＜ k 인 i에 대하여 h<sub>i - 1</sub> ＜ h<sub>i</sub> ＜ h<sub>i + 1</sub> 를 항상 만족   
// - 임의의 i, j에 대하여 i ＜ j 이면 h<sub>j</sub> 는 h<sub>i</sub> 의 배수가 되지 않음   
// - 항상 h<sub>1</sub> == 1 이 되어야 함   
- Use any permutation h<sub>1</sub>, ..., h<sub>k-1</sub>, h<sub>k</sub> consisting of positive numbers   
  - For i with 1 ＜ i ＜ k, h<sub>i - 1</sub> ＜ h<sub>i</sub> ＜ h<sub>i + 1</sub> is always satisfied   
  - If i < j for any i, j, h<sub>j</sub> is not a multiple of h<sub>i</sub>   
  - Always h<sub>1</sub> == 1   
   
// 순열의 역순으로 적용   
// - h<sub>k</sub> → h<sub>k - 1</sub> → ... → h<sub>1</sub> (h<sub>1</sub> == 1)   
// - h<sub>k</sub> ＞ h<sub>k - 1</sub> ＞ ... ＞ h<sub>1</sub>   
// -- 첫 번째 단계 : 전체 배열을 h<sub>k</sub> 개의 부분 배열로 나누어 처리 (삽입 정렬 수행)   
// -- 두 번째 단계 : 부분 정렬된 전체 배열을 h<sub>k - 1</sub> 개의 부분 배열로 나누어 처리   
// -- ... 단계   
// -- 마지막 단계 : 부분 정렬된 전체 배열을 h<sub>1</sub> == 1 개의 부분 배열, 즉 전체에 대해서 처리   
- Apply in reverse order of permutation   
  - h<sub>k</sub> → h<sub>k - 1</sub> → ... → h<sub>1</sub> (h<sub>1</sub> == 1)   
  - h<sub>k</sub> ＞ h<sub>k - 1</sub> ＞ ... ＞ h<sub>1</sub>   
    - The first step : Processed by dividing the entire array into h<sub>k</sub> partial arrays (perform Insertion Sort)   
    - The second step : Process the entire partially sorted array divided into h<sub>k - 1</sub> partial arrays   
    - ... step   
    - The last step : Process the entire partially sorted array for h<sub>1</sub> == 1 partial array (i.e., process the entire array)   
   
#### Meaning of permutation value h<sub>k</sub>   
// 순열값 h<sub>k</sub> 의 의미   
   
// 부분 배열의 개수   
// - 전체 배열을 h<sub>k</sub> 개의 부분 배열로 나누어 각 부분 배열에 대해서 삽입 정렬을 적용   
// 각 부분 배열 내에서 이웃한 데이터 간의 거리   
// - i번째 부분 배열을 구성하는 데이터   
// -- 배열 인덱스를 h<sub>k</sub> 로 나누었을 때 나머지가 i - 1 인 데이터   
// - 각 부분 배열은 전체 배열에서 h<sub>k</sub> 씩 떨어진 데이터로 구성   
- Number of Partial Arrangements   
  - Divide the entire array into h<sub>k</sub> partial arrays and apply Insertion Sort for each partial array   
- Distance between neighboring data within each partial array   
  - The data that make up the i-th partial array   
    - Data with the remainder i - 1 when the array index is divided by h<sub>k</sub>   
  - Each partial array consists of data h<sub>k</sub> away from the entire array   
   
#### Shell Sort algorithm   
// 셸 정렬 알고리즘   
   
```c
ShellSort (A[], n)
{
    for (D = ⌊ n/2 ⌋; D >= 1; D = ⌊ D/2 ⌋)    // D : Number of Partial Arrays & Size of Spacing
    {
        // D개의 부분 배열에 대한 삽입 정렬 과정. D = 1인 경우 삽입 정렬과 똑같은 알고리즘이 됨
        // Insertion Sort process for D partial arrays. If D = 1, it will be the same algorithm as Insertion Sort
        for (i = D; i < n; i++)
        {
            val = A[i];
            for (j = i; j >= D && A[j - D] > val; j = j - D)
                A[j] = A[j - D];
            A[j] = val;
        }
    }
    return (A);
}
```
   
// 하나의 입력 배열을 물리적으로 여러 개의 부분 배열로 분할하지 않음   
// 각 부분 배열을 번갈아 가면서 미정렬 부분의 첫 번째 데이터를 뽑은 후 D만큼씩 떨어진 정렬 부분에서 제자리를 찾아서 삽입하는 방식   
- Do not physically divide an input array into multiple partial arrays   
- Alternate each part array, pick the first data in the Unsorted part, and then locate and insert the correct place in the Sorted part separated by D   
   
#### Example 1 of Shell Sort   
// 셸 정렬의 예시 1   
   
// Step 1 : 부분 배열로 분리   
- Step 1 : Separation into a partial array   
   
```c
D = ⌊ n/2 ⌋ = ⌊ 16/2 ⌋ = 8    
// 8은 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 8 is the number of partial arrays, and also shows the distance between neighboring data within each partial array
```
   
|30|50|10|40|75|20|45|55|25|35|65|80|15|60|5|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30||||||||25||||||||
||50||||||||35|||||||
|||10||||||||65||||||
||||40||||||||80|||||
|||||75||||||||15||||
||||||20||||||||60|||
|||||||45||||||||5||
||||||||55||||||||70|
   
// Step 2 : 삽입 정렬 수행   
- Step 2 : Perform Insertion Sort   
   
|30|50|10|40|75|20|45|55|25|35|65|80|15|60|5|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>25</b>||||||||<b>30</b>||||||||
||<b>35</b>||||||||<b>50</b>|||||||
|||10||||||||65||||||
||||40||||||||80|||||
|||||<b>15</b>||||||||<b>75</b>||||
||||||20||||||||60|||
|||||||<b>5</b>||||||||45||
||||||||55||||||||70|
|<b>25</b>|<b>35</b>|<b>10</b>|<b>40</b>|<b>15</b>|<b>20</b>|<b>5</b>|<b>55</b>|<b>30</b>|<b>50</b>|<b>65</b>|<b>80</b>|<b>75</b>|<b>60</b>|<b>45</b>|<b>70</b>|
   
// Step 3 : 부분 배열로 분리   
- Step 3 : Separation into a partial array   
   
```c
D = ⌊ n/2 ⌋ = ⌊ 8/2 ⌋ = 4
// 4는 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 4 is the number of partial arrays, and also shows the distance between neighboring data within each partial array
```
   
|25|35|10|40|15|20|5|55|30|50|65|80|75|60|45|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|25||||15||||30||||75||||
||35||||20||||50||||60|||
|||10||||5||||65||||45||
||||40||||55||||80||||70|
   
// Step 4 : 삽입 정렬 수행   
- Step 4 : Perform Insertion Sort   
   
|25|35|10|40|15|20|5|55|30|50|65|80|75|60|45|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>15</b>||||<b>25</b>||||30||||75||||
||<b>20</b>||||<b>35</b>||||50||||60|||
|||<b>5</b>||||<b>10</b>||||<b>45</b>||||<b>65</b>||
||||40||||55||||<b>70</b>||||<b>80</b>|
|<b>15</b>|<b>20</b>|<b>5</b>|<b>40</b>|<b>25</b>|<b>35</b>|<b>10</b>|<b>55</b>|<b>30</b>|<b>50</b>|<b>45</b>|<b>70</b>|<b>75</b>|<b>60</b>|<b>65</b>|<b>80</b>|
   
// Step 5 : 부분 배열로 분리   
- Step 5 : Separation into a partial array   
   
```c
D = ⌊ n/2 ⌋ = ⌊ 4/2 ⌋ = 2
// 2는 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 2 is the number of partial arrays, and also shows the distance between neighboring data within each partial array
```
   
|15|20|5|40|25|35|10|55|30|50|45|70|75|60|65|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|15||5||25||10||30||45||75||65||
||20||40||35||55||50||70||60||80|
   
// Step 6 : 삽입 정렬 수행   
- Step 6 : Perform Insertion Sort   
   
|15|20|5|40|25|35|10|55|30|50|45|70|75|60|65|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>5</b>||<b>10</b>||<b>15</b>||<b>25</b>||30||45||<b>65</b>||<b>75</b>||
||20||<b>35</b>||<b>40</b>||<b>50</b>||<b>55</b>||<b>60</b>||<b>70</b>||80|
|<b>5</b>|<b>20</b>|<b>10</b>|<b>35</b>|<b>15</b>|<b>40</b>|<b>25</b>|<b>50</b>|<b>30</b>|<b>55</b>|<b>45</b>|<b>60</b>|<b>65</b>|<b>70</b>|<b>75</b>|<b>80</b>|
   
// Step 7 : 부분 배열로 분리   
- Step 7 : Separation into a partial array   
   
```c
D = ⌊ n/2 ⌋ = ⌊ 2/2 ⌋ = 1
// 1은 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 1 is the number of partial arrays, and also shows the distance between neighboring data within each partial array
```
   
|5|20|10|35|15|40|25|50|30|55|45|60|65|70|75|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|5|20|10|35|15|40|25|50|30|55|45|60|65|70|75|80|
   
// Step 8 : 삽입 정렬 수행   
- Step 8 : Perform Insertion Sort   
   
|5|20|10|35|15|40|25|50|30|55|45|60|65|70|75|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|5|<b>10</b>|<b>15</b>|<b>20</b>|<b>25</b>|<b>30</b>|<b>35</b>|<b>40</b>|<b>45</b>|<b>50</b>|<b>55</b>|60|65|70|75|80|
   
// 최종 정렬 결과   
- Final Sorting Result   
   
|5|10|15|20|25|30|35|40|45|50|55|60|65|70|75|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|||||||||||||||||
   
#### Example 2 of Shell Sort   
// 셸 정렬의 예시 2   
   
// h<sub>i + 1</sub> = 3h<sub>i</sub> + 1, h<sub>1</sub> = 1 → 순열 h<sub>i</sub> = 1, 4, 13, 40, 121, 364, ...   
- h<sub>i + 1</sub> = 3h<sub>i</sub> + 1, h<sub>1</sub> = 1 → Permutation h<sub>i</sub> = 1, 4, 13, 40, 121, 364, ...   
   
// 데이터 개수가 16개인 경우 순열 중 16보다 작으면서 가장 큰 수부터 작은 수의 순으로 D로 사용   
- If the number of data is 16, use D in order of the largest to the smallest number, while being less than 16 in the permutation   
   
// Step 1 : 부분 배열로 분리   
// - D = (h<sub>3</sub> = 13) 의 경우   
- Step 1 : Separation into a partial array   
  - For D = (h<sub>3</sub> = 13)   
   
|30|50|10|40|75|20|45|55|25|35|65|80|15|60|5|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|||||||||||||60|||
||50|||||||||||||5||
|||10|||||||||||||70|
||||40|||||||||||||
|||||75||||||||||||
||||||20|||||||||||
|||||||45||||||||||
||||||||55|||||||||
|||||||||25||||||||
||||||||||35|||||||
|||||||||||65||||||
||||||||||||80|||||
|||||||||||||15||||
   
// Step 2 : 삽입 정렬 수행   
- Step 2 : Perform Insertion Sort   
   
|30|50|10|40|75|20|45|55|25|35|65|80|15|60|5|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|||||||||||||60|||
||<b>5</b>|||||||||||||<b>50</b>||
|||10|||||||||||||70|
||||40|||||||||||||
|||||75||||||||||||
||||||20|||||||||||
|||||||45||||||||||
||||||||55|||||||||
|||||||||25||||||||
||||||||||35|||||||
|||||||||||65||||||
||||||||||||80|||||
|||||||||||||15||||
|30|<b>5</b>|10|40|75|20|45|55|25|35|65|80|15|60|<b>50</b>|70|
   
// Step 3 : 부분 배열로 분리   
// - D = (h<sub>2</sub> = 4) 의 경우   
- Step 3 : Separation into a partial array   
  - For D = (h<sub>2</sub> = 4)   
   
|30|5|10|40|75|20|45|55|25|35|65|80|15|60|50|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30||||75||||25||||15||||
||5||||20||||35||||60|||
|||10||||45||||65||||50||
||||40||||55||||80||||70|
   
// Step 4 : 삽입 정렬 수행   
- Step 4 : Perform Insertion Sort   
   
|30|5|10|40|75|20|45|55|25|35|65|80|15|60|50|70|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>15</b>||||<b>25</b>||||<b>30</b>||||<b>75</b>||||
||5||||20||||35||||60|||
|||10||||45||||<b>50</b>||||<b>65</b>||
||||40||||55||||<b>70</b>||||<b>80</b>|
|<b>15</b>|5|10|40|<b>25</b>|20|45|55|<b>30</b>|35|<b>50</b>|<b>70</b>|<b>75</b>|60|<b>65</b>|<b>80</b>|
   
// Step 5 : 부분 배열로 분리   
// - D = (h<sub>1</sub> = 1) 의 경우   
- Step 5 : Separation into a partial array   
  - For D = (h<sub>1</sub> = 1)   
   
|15|5|10|40|25|20|45|55|30|35|50|70|75|60|65|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|15|5|10|40|25|20|45|55|30|35|50|70|75|60|65|80|
   
// Step 6 : 삽입 정렬 수행   
- Step 6 : Perform Insertion Sort   
   
|15|5|10|40|25|20|45|55|30|35|50|70|75|60|65|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>5|<b>10|<b>15|<b>20|25|<b>30|<b>35|<b>40|<b>45|<b>50|<b>55|<b>60|<b>65|<b>70|<b>75|80|
   
// 최종 정렬 결과   
- Final Sorting Result   
   
|5|10|15|20|25|30|35|40|45|50|55|60|65|70|75|80|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|||||||||||||||||
   
#### Performance and Features   
// 성능과 특징   
   
// 성능   
// - 사용하는 순열에 따라 성능이 달라짐   
// -- D = ⌊ n/2<sup>i</sup> ⌋ (n : 데이터 개수, i = 1, 2, 3, ...)   
// -- 가장 좋은 간격을 찾는 것은 아직 미해결 과제   
// --- 1, 4, 13, 40, 121, 364, 1093, ... (h<sub>i + 1</sub> = 3h<sub>i</sub> + 1, h<sub>1</sub> = 1)   
// --- 1, 3, 7, 15, 31, 63, ... (2<sup>i</sup> - 1)   
// --- 1, 3, 7, 21, 48, 112, 336, 861, 1968, 4592, ...   
// --- 1, 4, 10, 23, 57, 132, 391, 701   
// -- 순열값의 역순으로 차례대로 적용 : h<sub>k</sub> → h<sub>k - 1</sub> → ... → h<sub>1</sub>   
// -- 최선 O(nlogn) ~ 최악 O(n<sup>2</sup>)   
- Performance   
  - Performance varies depending on the permutation used   
    - D = ⌊ n/2<sup>i</sup> ⌋ (n : Number of data, i = 1, 2, 3, ...)   
    - Finding the best interval is still an open question   
      - 1, 4, 13, 40, 121, 364, 1093, ... (h<sub>i + 1</sub> = 3h<sub>i</sub> + 1, h<sub>1</sub> = 1)   
      - 1, 3, 7, 15, 31, 63, ... (2<sup>i</sup> - 1)   
      - 1, 3, 7, 21, 48, 112, 336, 861, 1968, 4592, ...   
      - 1, 4, 10, 23, 57, 132, 391, 701   
    - Apply permutation values in reverse order : h<sub>k</sub> → h<sub>k - 1</sub> → ... → h<sub>1</sub>   
    - Best O(nlogn) ~ Worst O(n<sup>2</sup>)   
   
// 특징   
// - 제자리 정렬 알고리즘   
// -- 입력 배열 A[] 이외에 상수 개의 저장 공간 (예시 : D, i, j, val) 만 필요   
// - 안정적이지 않은 정렬 알고리즘   
- Features   
  - In-place Sort algorithm   
    - Only a constant number of storage spaces (e.g., D, i, j, val) other than the input array A[]   
  - Unstable Sort algorithm   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
