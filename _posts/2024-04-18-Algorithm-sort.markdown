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
    - If all data cannot be stored in the main memory, all data is stored in the auxiliary memory, and only some of the data is repeatedly moved to the main memory to perform sorting   
   
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
SelectionSort (A[], n) {
    for (i = 0; i < n - 1; i++) {   // Repeat (n - 1)
        // - ① A[i .. n - 1] 에서 최소값 찾기 
        // ① Find a minimum value in A[i .. n - 1]
        min = i;
        for (j = i + 1; j < n; j++)
            if (A[min] > A[j])
                min = j;
        // - ② 최소값과 A[i] 의 위치 교환
        // - A[i] 와 A[min] 의 자리바꿈;
        // ② Interchange the minimum and A[i] positions
        // Replacement of A[i] and A[min];
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
    - → Total number of comparisons is (n - 1) + (n - 2) + ... + 1 = <sup>n(n - 1)</sup> / <sub>2</sub>   
    - → The highest degree term is n²   
    - → ∴ O(n²)   
   
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
  - From right to left (←)   
    - Find the smallest value first and position it from the left end   
   
#### Basic form of Bubble Sort algorithm   
// 기본 형태의 버블 정렬 알고리즘   
   
```c
BubbleSort (A[], n) {
    for (i = 0; i < n - 1; i++)    // Step : Repeat (n - 1) times
        for (j = 0; j < n - 1; j++)    // From left to right
            if (A[j] > A[j + 1])    // If it is 'left data > right data'
                // - A[j] 와 A[j + 1] 의 자리바꿈;
                // Replacement of A[j] and A[j + 1];
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
Advanced_BubbleSort (A[], n) {
    for (i = 0; i < n - 1; i++)    // Step : 0, 1, ..., (n - 2)
        Sorted = TRUE;    // TRUE means that sort is finished
        for (j = 0; j < (n - 1) - i; j++)    // From left to right
            if (A[j] > A[j + 1]) {    // If it's 'left Data > right data'
                // - A[j] 와 A[j + 1] 의 자리바꿈;
                // Replacement of A[j] and A[j + 1];
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
    - → Total number of comparisons is (n - 1) + (n - 2) + ... + 1 = <sup>n(n - 1)</sup> / <sub>2</sub>   
   
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
  - Processing input array into Sorted part A[0 .. K - 1] and Unsorted part A [k .. n - 1]   
    - Start by treating A[0] as an Sorted part and A[1 .. n - 1] as an Unsorted part   
    - k = Repeat until 1, ..., n - 1   
      - Pull out the first data A[k] of the Unsorted part A[k .. n - 1],   
      - Finding a right place in the Sorted part A[0..k-1] and insert A[k] to ensure that A[0..k] remains sorted   
      - Locate the correct place in the Sorted part A[0..k-1] and insert A[k] to ensure that A[0..k] remains sorted   
   
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
InsertionSort (A[], n) {
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
InsertionSort (A[], n) {
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
    - → Total number of comparisons is ∴ O(n²)   
   
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
    - Repeat the process of performing Insertion Sort by dividing the input array into partial array while changing the size and number of partial array   
   
#### To determine the number of partial array   
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
    - The first step : Processed by dividing the entire array into h<sub>k</sub> partial array (perform Insertion Sort)   
    - The second step : Process the entire partially sorted array divided into h<sub>k - 1</sub> partial array   
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
  - Divide the entire array into h<sub>k</sub> partial array and apply Insertion Sort for each partial array   
- Distance between neighboring data within each partial array   
  - The data that make up the i-th partial array   
    - Data with the remainder i - 1 when the array index is divided by h<sub>k</sub>   
  - Each partial array consists of data h<sub>k</sub> away from the entire array   
   
#### Shell Sort algorithm   
// 셸 정렬 알고리즘   
   
```c
ShellSort (A[], n) {
    for (D = ⌊ n / 2 ⌋; D >= 1; D = ⌊ D / 2 ⌋) {    // D : Number of Partial Array & Size of Spacing
        // D개의 부분 배열에 대한 삽입 정렬 과정. D = 1인 경우 삽입 정렬과 똑같은 알고리즘이 됨
        // Insertion Sort process for D partial array. If D = 1, it will be the same algorithm as Insertion Sort
        for (i = D; i < n; i++) {
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
- Do not physically divide an input array into multiple partial array   
- Alternate each part array, pick the first data in the Unsorted part, and then locate and insert the correct place in the Sorted part separated by D   
   
#### Example 1 of Shell Sort   
// 셸 정렬의 예시 1   
   
// Step 1 : 부분 배열로 분리   
- Step 1 : Separation into a partial array   
   
```c
D = ⌊ n / 2 ⌋ = ⌊ 16 / 2 ⌋ = 8    
// 8은 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 8 is the number of partial array, and also shows the distance between neighboring data within each partial array
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
D = ⌊ n / 2 ⌋ = ⌊ 8 / 2 ⌋ = 4
// 4는 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 4 is the number of partial array, and also shows the distance between neighboring data within each partial array
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
D = ⌊ n / 2 ⌋ = ⌊ 4 / 2 ⌋ = 2
// 2는 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 2 is the number of partial array, and also shows the distance between neighboring data within each partial array
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
D = ⌊ n / 2 ⌋ = ⌊ 2 / 2 ⌋ = 1
// 1은 부분 배열의 개수이면서, 각 부분 배열 내에서 이웃한 데이터간의 떨어진 거리도 나타냄
// 1 is the number of partial array, and also shows the distance between neighboring data within each partial array
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
// -- D = ⌊ n / 2<sup>i</sup> ⌋ (n : 데이터 개수, i = 1, 2, 3, ...)   
// -- 가장 좋은 간격을 찾는 것은 아직 미해결 과제   
// --- 1, 4, 13, 40, 121, 364, 1093, ... (h<sub>i + 1</sub> = 3h<sub>i</sub> + 1, h<sub>1</sub> = 1)   
// --- 1, 3, 7, 15, 31, 63, ... (2<sup>i</sup> - 1)   
// --- 1, 3, 7, 21, 48, 112, 336, 861, 1968, 4592, ...   
// --- 1, 4, 10, 23, 57, 132, 391, 701   
// -- 순열값의 역순으로 차례대로 적용 : h<sub>k</sub> → h<sub>k - 1</sub> → ... → h<sub>1</sub>   
// -- 최선 O(nlogn) ~ 최악 O(n<sup>2</sup>)   
- Performance   
  - Performance varies depending on the permutation used   
    - D = ⌊ n / 2<sup>i</sup> ⌋ (n : Number of data, i = 1, 2, 3, ...)   
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
### Quick Sort   
// 퀵 정렬   
   
// 특정 데이터를 기준으로 주어진 배열을 2개의 부분 배열로 분할하고, 각 부분 배열에 대해서 퀵 정렬을 순환적으로 적용하는 방식   
- A method of dividing a given array into two partial arrays based on specific data and applying quick sorting to each partial array in a circular manner   
   
// 피벗 (pivot, 분할 원소)   
// - 주어진 배열을 두 부분 배열로 분할하는 기준이 되는 특정 데이터   
// -- 보통 주어진 배열의 첫 번째 데이터로 지정   
- pivot (split elements)   
  - Specific data that serves as a basis for dividing a given array into two partial arrays   
    - Typically, specify as the first data in a given array   
   
#### Principles of Quick Sort   
// 퀵 정렬의 원리   
   
// 피벗이 제자리를 잡도록 하여 정렬하는 방식   
// - 입력 배열 : [30 (pivot), 45, 20, 15, 40, 25, 35, 10]   
// - 분할 후 상태 : [25, 10, 20, 15, 30 (pivot), 40, 35, 45]   
// -- [25, 10, 20, 15] 은 피벗의 왼쪽 부분 배열, [40, 35, 45] 은 피벗의 오른쪽 부분 배열   
// - 왼쪽 부분 배열의 모든 데이터 ＜ 오른쪽 부분 배열에서 가장 작은 데이터   
// - 왼쪽 부분 배열에서 가장 큰 데이터 ＜ 오른쪽 부분 배열의 모든 데이터   
// ∴ 왼쪽 부분 배열의 모든 값 ＜ 피벗 ＜ 오른쪽 부분 배열의 모든 값   
- This is how the pivot is aligned so that it is in place   
  - Input Array : [30 (pivot), 45, 20, 15, 40, 25, 35, 10]   
  - Post-Split Status : [25, 10, 20, 15, 30 (pivot), 40, 35, 45]   
    - [25, 10, 20, 15] is the arrangement of the left part of the pivot, [40, 35, 45] is the arrangement of the right part of the pivot   
  - All data in left part array ＜ smallest data in right part array   
  - Largest data in left partial array ＜ All data in right partial array   
  ∴ All Values in Left Part Array ＜ Pivot ＜ All Values in Right Part Array   
   
#### Processing of Quick Sort   
// 퀵 정렬의 처리 과정   
   
// Step 1   
// - 입력 배열 : [30 (pivot), 45, 20, 15, 40, 25, 35, 10]   
// - 피벗을 30으로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [25, 10, 20, 15, 30 (pivot), 40, 35, 45]   
// Step 2   
// - 입력 배열 : [25, 10, 20, 15, <s>30</s>, 40, 35, 45]   
// - 왼쪽 부분 배열 [25, 10, 20, 15] 의 피벗을 25로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [15, 10, 20, 25 (pivot), <s>30</s>, 40, 35, 45]   
// Step 3   
// - 입력 배열 : [15, 10, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
// - 왼쪽 부분 배열 [15, 10, 20] 의 피벗을 15로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [10, 15 (pivot), 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
// Step 4   
// - 입력 배열 : [10, <s>15</s>, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
// - 왼쪽 부분 배열 [10] 의 피벗을 10로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [10 (pivot), <s>15</s>, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
// Step 5   
// - 입력 배열 : [<s>10</s>, <s>15</s>, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
// - 왼쪽 부분 배열의 마지막 남은 오른쪽 부분 배열 [20] 의 피벗을 20로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [<s>10</s>, <s>15</s>, 20 (pivot), <s>25</s>, <s>30</s>, 40, 35, 45]   
// Step 6   
// - 입력 배열 : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, 40, 35, 45]   
// - 오른쪽 부분 배열의 [40, 35, 45] 의 피벗을 40으로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [<s>10</s>, <s>15</s>, 20 <s>20</s>, <s>25</s>, <s>30</s>, 35, 40 (pivot), 45]   
// Step 7   
// - 입력 배열 : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, 35, <s>40</s>, 45]   
// - 오른쪽 부분 배열의 왼쪽 부분 배열 [35] 의 피벗을 35으로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, 35 (pivot), <s>40</s>, 45]   
// Step 8   
// - 입력 배열 : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, <s>35</s>, <s>40</s>, 45]   
// - 오른쪽 부분 배열의 마지막 남은 오른쪽 부분 배열 [45] 의 피벗을 45으로 정하고 피벗이 제자리를 잡도록하여 분할   
// - 분할 후 상태 : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, <s>35</s>, <s>40</s>, 45 (pivot)]   
// ∴ 최종 정렬 상태 : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, <s>35</s>, <s>40</s>, <s>45</s>]   
- Step 1   
  - Input Array : [30 (pivot), 45, 20, 15, 40, 25, 35, 10]   
  - Set the pivot to 30 and split it into place   
  - Post-Split Status : [25, 10, 20, 15, 30 (pivot), 40, 35, 45]   
- Step 2   
  - Input Array : [25, 10, 20, 15, <s>30</s>, 40, 35, 45]   
  - Set the pivot of the left partial array [25, 10, 20, 15] to 25 and divide it by allowing the pivot to be in place   
  - Post-Split Status : [15, 10, 20, 25 (pivot), <s>30</s>, 40, 35, 45]   
- Step 3   
  - Input Array : [15, 10, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
  - Set the pivot of the left partial array [15, 10, 20] to 15 and divide it by allowing the pivot to be in place   
  - Post-Split Status : [10, 15 (pivot), 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
- Step 4   
  - Input Array : [10, <s>15</s>, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
  - Set the pivot of the left partial array [10] to 10 and divide it by allowing the pivot to be in place   
  - Post-Split Status : [10 (pivot), <s>15</s>, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
- Step 5   
  - Input Array : [<s>10</s>, <s>15</s>, 20, <s>25</s>, <s>30</s>, 40, 35, 45]   
  - Set the pivot of the last remaining right part of the left part array [20] to 20 and divide it by allowing the pivot to be in place   
  - Post-Split Status : [<s>10</s>, <s>15</s>, 20 (pivot), <s>25</s>, <s>30</s>, 40, 35, 45]   
- Step 6   
  - Input Array : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, 40, 35, 45]   
  - Set the pivot of [40, 35, 45] in the right partial array to 40 and divide it by allowing the pivot to be in place   
  - Post-Split Status : [<s>10</s>, <s>15</s>, 20 <s>20</s>, <s>25</s>, <s>30</s>, 35, 40 (pivot), 45]   
- Step 7   
  - Input Array : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, 35, <s>40</s>, 45]   
  - Set the pivot of the left part array [35] of the right part array to 35 and divide it by allowing the pivot to be in place   
  - Post-Split Status : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, 35 (pivot), <s>40</s>, 45]   
- Step 8   
  - Input Array : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, <s>35</s>, <s>40</s>, 45]   
  - Set the pivot of the last remaining right part array [45] of the right part array to 45 and divide it by allowing the pivot to be in place   
  - Post-Split Status : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, <s>35</s>, <s>40</s>, 45 (pivot)]   
∴ Final Alignment Status : [<s>10</s>, <s>15</s>, <s>20</s>, <s>25</s>, <s>30</s>, <s>35</s>, <s>40</s>, <s>45</s>]   
   
#### Quick Sort Algorithm   
// 퀵 정렬 알고리즘   
   
// 퀵 정렬 (A[], n) 실행   
// - A[8] = [30, 40, 20, 15, 40, 25, 35, 10]   
// -- 피벗은 30   
// -- 피벗위치 j = 분할함수 (A[0..n - 1], n)   
// - A[8] = [25, 10, 25, 15, 30, 40, 35, 45]   
// -- 피벗위치 j 는 30의 인덱스인 4   
// -- 왼쪽 부분 배열은 [25, 10, 25, 15]   
// -- 오른쪽 부분 배열은 [40, 35, 45]   
// - 퀵 정렬 (왼쪽 부분 배열 A[0..j - 1], j) 실행   
// - 퀵 정렬 (오른쪽 부분 배열 A[j + 1..n - 1], n - (j - 1))   
- Run Quick Alignment (A[], n)   
  - A[8] = [30, 40, 20, 15, 40, 25, 35, 10]   
    - The pivot is 30   
    - Pivot position j = split function (A[0..n - 1], n)   
  - A[8] = [25, 10, 25, 15, 30, 40, 35, 45]   
    - The pivot position j is 4 which is the index of 30   
    - The left partial arrangement is [25, 10, 25, 15]   
    - The right partial arrangement is [40, 35, 45]   
  - Quick Alignment (Left Part Array A[0..j - 1], j) Run   
  - Quick Alignment (Right Part Array A[j + 1..n - 1], n - (j - 1)) Run   
   
```c
QuickSort (A[], n) {
    if (n > 1) {
        // - ① 피벗을 기준으로 두 부분배열을 분할
        // - pivot은 제자리를 잡은 피벗의 위치 (인덱스) 를 표시
        // - Partition 은 분할 함수임
        // ① Split the two partial arrangements based on the pivot
        // Indicate the position (index) of the pivot in place
        // Partition is a function of division
        pivot = Partition (A[0..n - 1], n);

        // - ② 왼쪽 부분 배열에 대한 퀵 정렬의 순환 호출
        // ② Recurring call of quick sort to left partial array
        QuickSort (A[0..pivot - 1], pivot);

        // - ③ 오른쪽 부분 배열에 대한 퀵 정렬의 순환 호출
        // ③ Recurring call of quick sort to right partial array
        QuickSort (A[pivot + 1..n - 1], n - pivot - 1);
    }
}
```
   
#### Example of a Quick Sort segmentation process   
// 퀵 정렬 분할 과정 예시   
   
- Step 1   
   
||피벗보다 큰 (같은) 값을 찾기<br />(Left 찾기)<br />- Find a (same) value greater than the pivot<br />- (Find Left)<br />------->||||||피벗보다 작은 값을 찾기<br />(Right 찾기)<br />- Find a value less than the pivot<br />- (Find Right)<br /><-------|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|pivot =<br />A<br />[0]|Left =<br />A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|Right =<br />A<br />[7]|
|30|<b>45</b>|20|15|40|25|35|<b>10</b>|
   
- Left ＜ Right   
// - 가장 큰 값과 가장 작은 값을 교환   
  - Exchange the largest and smallest values   
   
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|<b>10</b>|20|15|40|25|35|<b>45</b>|
   
- Step 2   
   
||피벗보다 큰 (같은) 값을 찾기<br />(Left 찾기)<br />- Find a (same) value greater than the pivot<br />- (Find Left)<br />------->||||||피벗보다 작은 값을 찾기<br />(Right 찾기)<br />- Find a value less than the pivot<br />- (Find Right)<br /><-------|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|Left =<br />A<br />[4]|Right =<br />A<br />[5]|A<br />[6]|A<br />[7]|
|30|<i>10</i>|20|15|<b>40</b>|<b>25</b>|35|<i>45</i>|
   
- Left ＜ Right   
// - 가장 큰 값과 가장 작은 값을 교환   
  - Exchange the largest and smallest values   
   
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|<i>10</i>|20|15|<b>25</b>|<b>40</b>|35|<i>45</i>|
   
- Step 3   
   
|||피벗보다 큰 (같은) 값을 찾기<br />(Left 찾기)<br />- Find a (same) value greater than the pivot<br />- (Find Left)<br />------->||||피벗보다 작은 값을 찾기<br />(Right 찾기)<br />- Find a value less than the pivot<br />- (Find Right)<br /><-------||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|Right =<br />A<br />[4]|Left =<br />A<br />[5]|A<br />[6]|A<br />[7]|
|30|<i>10</i>|20|15|<b><i>25</i></b>|<b><i>40</i></b>|35|<i>45</i>|
   
- Left ＞ Right   
// - 피벗과 Right 값을 교환하고 끝남   
  - Finished after exchanging pivot and right values   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|pivot =<br />A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b><i>25</i></b>|<i>10</i>|20|15|<b><i>30</i></b>|<i>40</i>|35|<i>45</i>|
   
// ∴ 피벗을 중심으로 왼쪽에는 피벗보다 적은 수만, 오른쪽에는 피버보다 큰 수만 정렬됨   
// - 왼쪽 부분 배열 : [25, 10, 20, 15]   
// - 오른쪽 부분 배열 : [40, 35, 45]   
∴ Only fewer than the pivot are aligned to the left around the pivot, and only more than the pivot is aligned to the right   
  - Left Part Array : [25, 10, 20, 15]   
  - Right Part Array : [40, 35, 45]   
   
#### Quick sort partition function Partition()   
// 퀵 정렬 분할 함수 Partition()   
   
```c
int Partition (A[], n) {
    Left = 1;
    Right = n - 1;
    while (Left < Right) {
        // 오른쪽으로 진행하면서 피벗 A[0] 보다 큰 값의 위치를 찾기
        // Proceeding to the right to find a position with a value greater than Pivot A[0]
        while (Left < n && A[Left] < A[0])
            Left++;
        // 왼쪽으로 진행하면서 피벗 A[0] 보다 작은 값의 위치를 찾기
        // Proceeding to the left to find the position of the value less than the pivot A[0]
        while (Right > 0 && A[Right] >= A[0])
            Right--;
        if (Left < Right)
            // A[Left] 와 A[Right] 의 위치 교환
            Exchange the positions of A[Left] and A[Right]
        else
            // 피벗과의 위치 교환 후 첫 번째 while 문 종료
            // Terminate the first while statement after exchanging the position with the pivot
            // 피벗 A[0] 와 A[Right] 의 위치 교환
            Exchange the positions of pivot A[0] and A[Right]
    }
    return (Right);
}
```
   
#### Example of Quick Sort   
// 퀵 정렬의 예시   
   
// 피벗보다 큰 (같은) 값을 찾기 = Left 찾기   
// 피벗보다 작은 값을 찾기 = Right 찾기   
- Find a (same) value greater than the pivot = Find Left   
- Find a value less than the pivot = Find Right   
   
- Step 1   
   
||Left 찾기<br />- Find Left<br />------->|||||||||||Right 찾기<br />- Find Right<br /><-------|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|pivot =<br />A<br />[0]|Left =<br />A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|A<br />[10]|Right =<br />A<br />[11]|A<br />[12]|
|30|<b>50</b>|17|40|88|15|44|55|22|11|66|<b>13</b>|85|
   
- Left ＜ Right   
// - 가장 큰 값과 가장 작은 값을 교환   
  - Exchange the largest and smallest values   
   
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|<b>13</b>|17|40|88|15|44|55|22|11|66|<b>50</b>|85|
   
- Step 2   
   
||Left 찾기<br />- Find Left<br />------->|||||||||||Right 찾기<br />- Find Right<br /><-------|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|Left =<br />A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|Right =<br />A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|30|<i>13</i>|17|<b>40</b>|88|15|44|55|22|<b>11</b>|66|<i>50</i>|85|
   
- Left ＜ Right   
// - 가장 큰 값과 가장 작은 값을 교환   
  - Exchange the largest and smallest values   
   
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|<i>13</i>|17|<b>11</b>|88|15|44|55|22|<b>40</b>|66|<i>50</i>|85|
   
- Step 3   
   
|||Left 찾기<br />- Find Left<br />------->|||||||||Right 찾기<br />- Find Right<br /><-------||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|Left =<br />A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|Right =<br />A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|30|<i>13</i>|17|<i>11</i>|<b>88</b>|15|44|55|<b>22</b>|<i>40</i>|66|<i>50</i>|85|
   
- Left ＜ Right   
// - 가장 큰 값과 가장 작은 값을 교환   
  - Exchange the largest and smallest values   
   
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|<i>13</i>|17|<i>11</i>|<b>22</b>|15|44|55|<b>88</b>|<i>40</i>|66|<i>50</i>|85|
   
- Step 4   
   
|||Left 찾기<br />- Find Left<br />------->|||||||||Right 찾기<br />- Find Right<br /><-------||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|pivot =<br />A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|Right =<br />A<br />[5]|Left =<br />A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|30|<i>13</i>|17|<i>11</i>|<i>22</i>|<b>15</b>|<b>44</b>|55|<i>88</i>|<i>40</i>|66|<i>50</i>|85|
   
- Left ＞ Right   
// - 피벗과 Right 값을 교환하고 끝남   
  - Finished after exchanging pivot and right values   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|pivot =<br />A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<b>15</b>|<i>13</i>|17|<i>11</i>|<i>22</i>|<b>30</b>|44|55|<i>88</i>|<i>40</i>|66|<i>50</i>|85|
   
// ∴ 피벗을 중심으로 왼쪽에는 피벗보다 적은 수만, 오른쪽에는 피버보다 큰 수만 정렬됨   
// - 왼쪽 부분 배열 : [15, 13, 17, 11, 22]   
// - 오른쪽 부분 배열 : [44, 55, 88, 40, 66, 50, 85]   
∴ Only fewer than the pivot are aligned to the left around the pivot, and only more than the pivot is aligned to the right   
  - Left Part Array : [15, 13, 17, 11, 22]   
  - Right Part Array : [44, 55, 88, 40, 66, 50, 85]   
   
- Step 5 ~ 9   
// 왼쪽 부분 배열에 대해 퀵 정렬 수행   
- Perform Quick Sort for left partial array   
   
- Step 10 ~ 11   
// 오른쪽 부분 배열에 대해 퀵 정렬 수행   
- Perform Quick Sort for right partial array   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|pivot =<br />A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|88|55|66|50|85|
   
- Step 12   
// 피벗보다 큰 수가 없으므로 오른쪽 끝에 무한대가 있다고 가정하고 수행   
- No number greater than the pivot, so do it assuming there is infinity on the right end   
   
||||||||||Left 찾기<br />- Find Left<br />------->|||Right 찾기<br />- Find Right<br /><-------||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|pivot =<br />A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|Right =<br />A<br />[12]|Left =<br />A<br />[∞]|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|88|55|66|50|<b>85</b>|∞|
   
- Left ＞ Right   
// - 피벗과 Right 값을 교환하고 끝남   
  - Finished after exchanging pivot and right values   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|pivot =<br />A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<b>85</b>|55|66|50|<b>88</b>|
   
- Step 13   
// 피벗보다 큰 수가 없으므로 오른쪽 끝에 무한대가 있다고 가정하고 수행   
- No number greater than the pivot, so do it assuming there is infinity on the right end   
   
||||||||||Left 찾기<br />- Find Left<br />------->||Right 찾기<br />- Find Right<br /><-------|||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|pivot =<br />A<br />[8]|A<br />[9]|A<br />[10]|Right =<br />A<br />[11]|Left =<br />A<br />[∞]|A<br />[12]|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|85|55|66|<b>50</b>|∞|<i>88</i>|
   
- Left ＞ Right   
// - 피벗과 Right 값을 교환하고 끝남   
  - Finished after exchanging pivot and right values   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|pivot =<br />A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<b>50</b>|55|66|<b>85</b>|<i>88</i>|
   
- Step 14   
// 피벗보다 큰 수가 없으므로 오른쪽 끝에 무한대가 있다고 가정하고 수행   
- No number greater than the pivot, so do it assuming there is infinity on the right end   
   
||||||||||Left 찾기<br />- Find Left<br />------->|Right 찾기<br />- Find Right<br /><-------||||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|pivot =<br />Right =<br />A<br />[8]|A<br />[9]|A<br />[10]|Left =<br />A<br />[∞]|A<br />[11]|A<br />[12]|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<b>50</b>|55|66|∞|<i>85</i>|<i>88</i>|
   
- Left ＞ Right   
// - 피벗과 Right 값을 교환하고 끝남   
  - Finished after exchanging pivot and right values   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|pivot =<br />A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<b>50</b>|55|66|<i>85</i>|<i>88</i>|
   
- Step 15   
// 피벗보다 큰 수가 없으므로 오른쪽 끝에 무한대가 있다고 가정하고 수행   
- No number greater than the pivot, so do it assuming there is infinity on the right end   
   
||||||||||Left 찾기<br />- Find Left<br />------->|Right 찾기<br />- Find Right<br /><-------||||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|pivot =<br />Right =<br />A<br />[9]|A<br />[10]|Left =<br />A<br />[∞]|A<br />[11]|A<br />[12]|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<i>50</i>|<b>55</b>|66|∞|<i>85</i>|<i>88</i>|
   
- Left ＞ Right   
// - 피벗과 Right 값을 교환하고 끝남   
  - Finished after exchanging pivot and right values   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|pivot =<br />A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<i>50</i>|<b>55</b>|66|<i>85</i>|<i>88</i>|
   
- Step 16   
// 피벗보다 큰 수가 없으므로 오른쪽 끝에 무한대가 있다고 가정하고 수행   
- No number greater than the pivot, so do it assuming there is infinity on the right end   
   
|||||||||||Left 찾기<br />- Find Left<br />-------><br />Right 찾기<br />- Find Right<br /><-------||||
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|pivot =<br />Right =<br />A<br />[10]|Left =<br />A<br />[∞]|A<br />[11]|A<br />[12]|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<i>50</i>|<i>55</i>|<b>66</b>|∞|<i>85</i>|<i>88</i>|
   
- Left ＞ Right   
// - 피벗과 Right 값을 교환하고 끝남   
  - Finished after exchanging pivot and right values   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|pivot =<br />A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<i>50</i>|<i>55</i>|<b>66</b>|<i>85</i>|<i>88</i>|
   
// ∴ 전체 배열에 대한 퀵 정렬이 끝남   
∴ Quick sort for the entire array ended   
   
|A<br />[0]|A<br />[1]|A<br />[2]|A<br />[3]|A<br />[4]|A<br />[5]|A<br />[6]|A<br />[7]|A<br />[8]|A<br />[9]|A<br />[10]|A<br />[11]|A<br />[12]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|<i>11</i>|<i>13</i>|<i>15</i>|<i>17</i>|<i>22</i>|<i>30</i>|<i>40</i>|<i>44</i>|<i>50</i>|<i>55</i>|<i>66</i>|<i>85</i>|<i>88</i>|
   
#### Performance and Features   
// 성능과 특징   
   
// 분할 함수 Partition() 의 성능   
// - 피벗과의 비교 횟수는?   
// -- 각 데이터는 피벗과 1회 또는 많아야 2회씩 비교   
// --- Θ(n)   
- Performance of Split Function Partition()   
  - What is the number of comparisons with the pivot?   
    - Each data is compared once or twice at most with the pivot   
      - Θ(n)   
   
// 퀵 정렬 QuickSort() 의 수행시간은 분할되는 두 부분 배열의 크기에 따라 달라짐   
- The running time of QuickSort() depends on the size of the two partial arrays being split   
   
```c
QuickSort (A[], n) {
    if (n > 1) {
        pivot = Partition (A[0..n - 1], n);
        QuickSort (A[0..pivot - 1], pivot);
        QuickSort (A[pivot + 1..n - 1], n - pivot - 1);
    }
}
```
   
// T(n) : 데이터 n개를 퀵 정렬 하는데 걸리는 시간   
// - 분할 : 피벗이 제자리를 잡고 왼쪽과 오른쪽으로 나뉘어 지는 것   
// -- 분할하는데 걸린 시간 : Θ(n)   
// -- `pivot = Partition (A[0..n - 1], n);` → Θ(n)   
// T(n<sub>L</sub>) : 왼쪽 부분 배열에 대해서 퀵 정렬하는데 걸리는 시간   
// - `QuickSort (A[0..pivot - 1], pivot);` → T(n<sub>L</sub>)   
// T(n<sub>R</sub>) : 오른쪽 부분 배열에 대해서 퀵 정렬하는데 걸리는 시간   
// - `QuickSort (A[pivot + 1..n - 1], n - pivot - 1);` → T(n<sub>R</sub>)   
// T(n<sub>L</sub>) + T(n<sub>R</sub>) = n - 1   
// ∴ T(n) = T(n<sub>L</sub>) + T(n<sub>R</sub>) + Θ(n) (조건 : n > 1)   
// ∴ T(1) = Θ(1) (조건 : n = 1)   
- T(n) : Time taken to sort n pieces of data quickly   
  - Split : Pivot in place and split left and right   
    - The time it took to split : Θ(n)   
    - `pivot = Partition (A[0..n - 1], n);` → Θ(n)   
- T(n<sub>L</sub>) : How long does it take to Quick Sort for the left part array   
  - `QuickSort (A[0..pivot - 1], pivot);` → T(n<sub>L</sub>)   
- T(n<sub>R</sub>) : How long does it take to Quick Sort for the right part array   
  - `QuickSort (A[pivot + 1..n - 1], n - pivot - 1);` → T(n<sub>R</sub>)   
- T(n<sub>L</sub>) + T(n<sub>R</sub>) = n - 1   
∴ T(n) = T(n<sub>L</sub>) + T(n<sub>R</sub>) + Θ(n) (Condition : n > 1)   
∴ T(1) = Θ(1) (Condition : n = 1)   
   
// 분할된 두 부분 배열의 크기 (n<sub>L</sub>, n<sub>R</sub>) 는 총 n가지가 만들어짐   
- The size (n<sub>L</sub>, n<sub>R</sub>) of the two fractional arrays is n in total   
   
```
0 : n - 1 → Worst performance
1 : n - 2
2 : n - 3
...
n / 2 : n / 2 → Best performance
...
n - 1 : 0 → Worst performance
```
   
// 배열이 항상 0 : n - 1 또는 n - 1 : 0 으로 분할되는 경우   
// - 극심한 불균형적 분할 → 최악의 경우    
// - 0 : n - 1 또는 n - 1 : 0 → 피벗만 제자리를 잡고 나머지 모든 원소가 하나의 부분 배열이 되는 경우   
// - 피벗이 항상 부분 배열의 최소값 또는 최대값이 되는 경우   
// - 입력 데이터가 정렬된 경우 AND 피벗을 배열의 첫 번째 원소로 정한 경우   
// - T(n) = T(n - 1) + T(0) + Θ(n) (조건 : (n > 1), T(1) = 1)   
// -- → T(n) = T(n - 1) + Θ(n)   
// -- → T(n) = O(n²)   
// -- 예시   
// --- 배열이 항상 0 : n - 1 으로 분할되는 경우 예시   
// ---- [10, 20, 30, 40, 50]   
// --- 배열이 항상 n - 1 : 0 으로 분할되는 경우 예시   
// ---- [50, 40, 30, 20, 10]   
- If the array is always split 0 : n - 1 or n - 1: 0   
  - Extremely disproportionate segmentation → Worst case   
  - 0 : n - 1 or n - 1: 0 → a case in which only the pivot is in place and all other elements are in one partial array   
  - The case where the pivot is always the minimum or maximum value of the partial array   
  - The case where the input data is aligned, and the case where the pivot is the first element in the array   
  - T(n) = T(n - 1) + T(0) + Θ(n) (Condition : (n > 1), T(1) = 1)   
    - → T(n) = T(n - 1) + Θ(n)   
    - → T(n) = O(n²)   
    - Example   
      - Example of a case in which the array is always divided by 0 : n - 1   
        - [10, 20, 30, 40, 50]   
      - Example of a case in which the array is always divided by n - 1 : 0   
        - [50, 40, 30, 20, 10]   
   
// 배열이 항상 <sup>n</sup> / <sub>2</sub> : <sup>n</sup> / <sub>2</sub> 으로 분할되는 경우   
// 가장 균형적인 분할 → 최선의 경우   
// - 피벗을 중심으로 항상 동일한 크기의 두 부분배열로 분할되는 경우   
// - 피벗이 항상 배열의 중간값이 되는 경우   
// - T(n) = T(⌊ n / 2 ⌋) + T(⌊ n / 2 ⌋) + Θ(n) (조건 : (n > 1), T(1) = 1)   
// -- → T(n) = 2T(<sup>n</sup> / <sub>2</sub>) + Θ(n)   
// -- → T(n) = O(nlogn)   
// -- 예시   
// --- [25, 40, 10, 35, 15, 30, 20]   
- The case where the array is always split into <sup>n</sup> / <sub>2</sub> : <sup>n</sup> / <sub>2</sub>   
- Most balanced split → Best case   
  - A case that is always divided into two partial arrays of the same size, around the pivot   
  - The case where the pivot is always the middle of the array   
  - T(n) = T(⌊ n / 2 ⌋) + T(⌊ n / 2 ⌋) + Θ(n) (Condition : (n > 1), T(1) = 1)   
    - → T(n) = 2T(<sup>n</sup> / <sub>2</sub>) + Θ(n)   
    - → T(n) = O(nlogn)   
    - Example   
      - [25, 40, 10, 35, 15, 30, 20]   
   
// 퀵 정렬의 평균 수행시간   
// - 부분 배열의 모든 분할 비율에 따른 수행시간의 평균   
// -- 피벗은 동일한 확률을 가지고 분할 후 배열의 어느 곳에나 위치 가능   
// -- 0 : n - 1, 1 : n - 2, 2 : n - 3, ..., n - 2 : 1, n - 1 : 0   
// --- T(1) = T(0) = 0   
// --- T(n) = <sup>1</sup> / <sub>n</sub>∑<sup>n</sup><sub>i = 1</sub> (T(i - 1) + T(n - i)) + Θ(n), n ≥ 2   
// --- → ∴ T(n) = O(nlogn)   
- Average run time of Quick Sort   
  - Average of running times according to all split ratios in a partial array   
    - Pivot can be placed anywhere in the array after splitting with the same probability   
    - 0 : n - 1, 1 : n - 2, 2 : n - 3, ..., n - 2 : 1, n - 1 : 0   
      - T(1) = T(0) = 0   
      - T(n) = <sup>1</sup> / <sub>n</sub>∑<sup>n</sup><sub>i = 1</sub> (T(i - 1) + T(n - i)) + Θ(n), n ≥ 2   
      - → ∴ T(n) = O(nlogn)   
   
// 특징   
// - 피벗 선택의 임의성만 보장되면 평균 수행시간 O(nlogn) 을 보장   
// -- 최선 / 평균 수행시간 → O(nlogn)   
// -- 최악의 수행시간 → O(n²)   
// --- 피벗을 배열의 첫 번째 원소로 지정하는 경우 AND 배열이 정렬된 경우   
// ---- → 배열에서 임의의 값을 선택한 후, 배열의 첫 번째 원소와 서로 교환한 후 정렬 수행   
// - 제자리 정렬 알고리즘   
// -- 입력 배열 A[] 이외에 상수 개의 저장 공간 (예시 : Left, Right, tmp, n, pivot) 만 필요   
// -- 이 외 추가적인 메모리가 필요하지 않음   
// - 안정적이지 않은 정렬 알고리즘   
// - 분할정복 방법이 적용된 알고리즘   
// -- 순환 알고리즘임. 순환알고리즘의 성능은 점화식으로 표현됨   
// -- 퀵 정렬에서의 분할 단계   
// --- 피벗을 기준으로 주어진 배열을 두 부분 배열로 분할 → 두 부분 배열의 크기는 일정하지 않음   
// -- 퀵 정렬에서의 정복 단계   
// --- 두 부분 배열에 대해서 퀵 정렬을 순환적으로 적용하여 각 부분 배열을 정렬함   
// -- 퀵 정렬에서의 결합 단계   
// --- 필요 없음   
- Features   
  - Ensure average run time O(nlogn) as long as the arbitrariness of pivot selection is guaranteed   
    - Best / Average running time → O(nlogn)   
    - Worst running time → O(n²)   
      - Specify the pivot as the first element in the array, and the case where the array is aligned   
        - Select any value in the array, exchange it with the first element in the array, and perform alignment   
  - In-place Sort algorithm   
    - Only a constant number of storage spaces (e.g., Left, Right, tmp, n, pivot) other than the input array A[]   
    - No additional memory required   
  - Unstable Sort algorithm   
  - Algorithms with Split Conquest Method   
    - Cyclic algorithm. The performance of the cyclic algorithm is represented by recurrence relation   
    - Split Step in Quick Sort   
      - Split a given array into two partial arrays based on the pivot → two partial arrays are not constant in size   
    - Conquering Steps in Quick Sort   
      - Apply quick sort cyclically for both part arrays to align each part array   
    - Combination Steps in Quick Sort   
      - No need   
   
<br />
### Merge Sort   
// 합병 정렬   
   
// ① 주어진 배열을 동일한 크기의 두 부분 배열로 분할하고   
// ② 각 부분 배열에 순환적으로 합병 정렬을 적용하여 정렬 시킨 후   
// ③ 정렬된 두 부분 배열을 합병하여 하나의 정렬된 배열을 만듦   
- ① Divide a given array into two partial arrays of the same size   
- ② After sorting by applying merge sort to each partial array   
- ③ Merge two aligned partial arrays to create one aligned array   
   
// 예시   
// - [60, 20, 70, 10, 80, 30, 50, 40]   
// - → ① 동일한 크기의 두 부분 배열로 분할   
// - [60, 20, 70, 10], [80, 30, 50, 40]   
// - → ② 합병 정렬의 순환 적용 (①, ②, ③)*   
// - [10, 20, 60, 70], [30, 40, 50, 80]   
// - → ③ 정렬된 두 부분 배열의 합병   
// - [10, 20, 30, 40, 50, 60, 70, 80]   
- Example   
  - [60, 20, 70, 10, 80, 30, 50, 40]   
  - → ① Split into two partial arrays of equal size   
  - [60, 20, 70, 10], [80, 30, 50, 40]   
  - → ② Circular application of Merge Sort (①, ②, ③)*   
  - [10, 20, 60, 70], [30, 40, 50, 80]   
  - → ③ Merger of two aligned partial arrays   
  - [10, 20, 30, 40, 50, 60, 70, 80]   
   
#### Merge Sort Algorithm   
// 합병 정렬 알고리즘   
   
```c
MergeSort (A[], n) {
    if (n > 1) {
        Mid = ⌊ n / 2 ⌋;
        // 왼쪽 부분 배열의 순환 호출 → 크기 n / 2 인 정렬된 배열 반환
        // Circular call of left partial array  → Return ordered array of size n / 2
        B[0..Mid - 1] = MergeSort(A[0..Mid - 1], Mid);
        // 오른쪽 부분 배열의 순환 호출 → 크기 n / 2 인 정렬된 배열 반환
        // Circular call of right partial array  → Return ordered array of size n / 2
        C[0..n - Mid - 1] = MergeSort(A[Mid..n - 1], n - Mid);
        // 정렬된 두 부분 배열 B[] 와 C[] 의 합병 : A[] = B[] + C[]
        // The merger of two aligned partial arrays B[] and C[] : A[] = B[] + C[]
        A[0..n - 1] = Merge(B[0..Mid - 1], C[0..n - Mid - 1], Mid, n - Mid);
    }
    return (A);
}
```
   
#### Example of the overall execution of Merge Sort   
// 합병 정렬의 전체적인 수행 과정 예시   
   
- [60, 20, 70, 10, 80, 30, 50, 40]   
  - → [60, 20, 70, 10], [80, 30, 50, 40]   
  - → [60, 20], [70, 10], [80, 30, 50, 40]   
  - → [60], [20], [70], [10], [80, 30, 50, 40]   
  - → [20, 60], [10, 70], [80, 30, 50, 40]   
  - → [10, 20, 60, 70], [80, 30, 50, 40]   
  - → [10, 20, 60, 70], [80, 30], [50, 40]   
  - → [10, 20, 60, 70], [80], [30], [50], [40]   
  - → [10, 20, 60, 70], [30, 80], [40, 50]   
  - → [10, 20, 60, 70], [30, 40, 50, 80]   
  - → [10, 20, 30, 40, 50, 60, 70, 80]   
   
#### Merger function Merge()   
// 합병 함수 Merge()   
   
```c
Merge(B[], C[], n, m) {
    i = j = k = 0;
    // 정렬된 부분 배열 B[i] 와 C[j]를 비교해서 작은 데이터를 A[k]에 복사
    // Copy small data to A[k] by comparing aligned partial arrays B[i] and C[j]
    while (i < n && j < m)
        if (B[i] <= C[j])
            A[k++] = B[i++];
        else A[k++] = C[j++];

    // 정렬된 부분 배열 B[] 또는 C[]에 남아 있는 모든 데이터를 A[]로 복사
    // Copy all data remaining in the aligned partial array B[] or C[] to A[]
    for (; i < n; i++)
        A[k++] = B[i];
    for (; j < m; j++)
        A[k++] = C[j];

    return (A[0..n + m - 1]);
}
```
   
#### Behavior of Merge() function   
// 합병 함수 Merge() 의 동작   
   
- B[10, 20, 60, 70]   
- C[30, 40, 50, 80]   
   
- Step 1   
  - B[n / 2] : [<b>10</b>, 20, 60, 70]   
  - C[n / 2] : [<b>30</b>, 40, 50, 80]   
  - → A[n] : [10]   
   
- Step 2   
  - B[n / 2] : [<b>20</b>, 60, 70]   
  - C[n / 2] : [<b>30</b>, 40, 50, 80]   
  - → A[n] : [10, 20]   
   
- Step 3   
  - B[n / 2] : [<b>60</b>, 70]   
  - C[n / 2] : [<b>30</b>, 40, 50, 80]   
  - → A[n] : [10, 20, 30]   
   
- Step 4   
  - B[n / 2] : [<b>60</b>, 70]   
  - C[n / 2] : [<b>40</b>, 50, 80]   
  - → A[n] : [10, 20, 30, 40]   
   
- Step 5   
  - B[n / 2] : [<b>60</b>, 70]   
  - C[n / 2] : [<b>50</b>, 80]   
  - → A[n] : [10, 20, 30, 40, 50]   
   
- Step 6   
  - B[n / 2] : [<b>60</b>, 70]   
  - C[n / 2] : [<b>80</b>]   
  - → A[n] : [10, 20, 30, 40, 50, 60]   
   
- Step 7   
  - B[n / 2] : [<b>70</b>]   
  - C[n / 2] : [<b>80</b>]   
  - → A[n] : [10, 20, 30, 40, 50, 60, 70]   
   
- Step 8   
  - B[n / 2] : []   
  - C[n / 2] : [<b>80</b>]   
  - → A[n] : [10, 20, 30, 40, 50, 60, 70, 80]   
   
- ∴ Final   
  - B[n / 2] : []   
  - C[n / 2] : []   
  - → A[n] : [10, 20, 30, 40, 50, 60, 70, 80]   
   
#### Performance and Features   
// 성능과 특징   
   
// 합병함수 Merge() 의 수행시간   
// - B[n / 2] + C[n / 2] = A[n]   
// - 두 부분 배열 B[] 와 C[] 간의 비교 횟수   
// - → <sup>n</sup> / <sub>2</sub> ~ (<sup>n</sup> / <sub>2</sub> + <sup>n</sup> / <sub>2</sub> - 1 = n - 1)   
// - → ∴ Θ(n)   
// -- 퀵 정렬의 분할함수와 동일한 수행시간   
- Running time of Merge Function Merge()   
  - B[n / 2] + C[n / 2] = A[n]   
  - Number of comparisons between two partial arrays B[] and C[]   
  - → <sup>n</sup> / <sub>2</sub> ~ (<sup>n</sup> / <sub>2</sub> + <sup>n</sup> / <sub>2</sub> - 1 = n - 1)   
  - → ∴ Θ(n)   
    - Time of run equal to the split function of Quick Sort   
   
// 합병 정렬 MergeSort()의 수행시간   
- Running time of Merge Sort MergeSort()   
   
```c
MergeSort (A[], n) {    // → T(n)
    if (n > 1) {
        Mid = ⌊ n / 2 ⌋;
        B[0..Mid - 1] = MergeSort(A[0..Mid - 1], Mid);    // → T(⌊ n / 2 ⌋)
        C[0..n - Mid - 1] = MergeSort(A[Mid..n - 1], n - Mid);    // → T(⌈ n / 2 ⌉)
        A[0..n - 1] = Merge(B[0..Mid - 1], C[0..n - Mid - 1], Mid, n - Mid);    // → Θ(n)
    }
    return (A);
}
```
   
// T(n) : 데이터 n개를 합병 정렬 하는데 걸리는 시간   
// T(⌊ n / 2 ⌋) : 왼쪽 절반 n / 2 개를 합병 정렬하는데 걸리는 시간   
// `B[0..Mid - 1] = MergeSort(A[0..Mid - 1], Mid);` → T(⌊ n / 2 ⌋)   
// T(⌈ n / 2 ⌉) : 오른쪽 절반 n / 2 개를 합병 정렬하는데 걸리는 시간   
// `C[0..n - Mid - 1] = MergeSort(A[Mid..n - 1], n - Mid);` → T(⌈ n / 2 ⌉)   
// 합병하는데 걸린 시간 : Θ(n)   
// `A[0..n - 1] = Merge(B[0..Mid - 1], C[0..n - Mid - 1], Mid, n - Mid);` → Θ(n)   
// ∴ T(n) = T(⌊ n / 2 ⌋) + T(⌈ n / 2 ⌉) + Θ(n) (조건 : n > 1, T(1) = 0)   
// ∴ T(n) = 2T(n / 2) + Θ(n)   
// ∴ T(n) = O(nlogn) (최선, 최악, 평균)   
- T(n) : Time taken to Merge Sort n pieces of data   
- T(⌊ n / 2 ⌋) : The time it takes to Merge Sort the left half n/2   
- `B[0..Mid - 1] = MergeSort(A[0..Mid - 1], Mid);` → T(⌊ n / 2 ⌋)   
-  T(⌈ n / 2 ⌉) : The time it takes to Merge Sort the right half n/2   
- `C[0..n - Mid - 1] = MergeSort(A[Mid..n - 1], n - Mid);` → T(⌈ n / 2 ⌉)   
- The time it took to merge : Θ(n)   
- `A[0..n - 1] = Merge(B[0..Mid - 1], C[0..n - Mid - 1], Mid, n - Mid);` → Θ(n)   
∴ T(n) = T(⌊ n / 2 ⌋) + T(⌈ n / 2 ⌉) + Θ(n) (Condition : n > 1, T(1) = 0)   
∴ T(n) = 2T(n / 2) + Θ(n)   
∴ T(n) = O(nlogn) (best, worst, average)   
   
// 특징   
// - 안정적인 정렬 알고리즘   
// -- 합병 과정에서 동일한 두 데이터에 대해서 항상 왼쪽 데이터를 먼저 선택함   
// - 제자리 정렬 알고리즘이 아님   
// -- A[n] = B[n / 2] + C[n / 2] → 입력 크기 n만큼의 추가적인 공간을 요구   
// - 전형적인 분할정복 방법이 적용된 알고리즘
// -- 순환 알고리즘임. 순환알고리즘의 성능은 점화식으로 표현됨   
// -- 합병 정렬에서의 분할 단계   
// --- 주어진 배열을 동일한 크기의 2개의 부분 배열로 분할   
// -- 합병 정렬에서의 정복 단계   
// --- 각 부분 배열에 대해서 합병 정렬을 순환적으로 적용하여 정렬함   
// -- 합병 정렬에서의 결합 단계   
// --- 정렬된 두 부분 배열을 합병하여 하나의 정렬된 배열을 만듦   
// - 비순환적 방식 (반복분 사용) 으로도 합병 정렬 알고리즘을 표현할 수 있음   
// -- 예시   
// --- [60], [20], [70], [10], [80], [30], [50], [40]   
// --- → [20, 60], [10, 70], [30, 80], [40, 50]   
// --- → [10, 20, 60, 70], [30, 40, 50, 80]   
// --- → [10, 20, 30, 40, 50, 60, 70, 80]   
- Features   
  - Stable Sort algorithm   
    - Always select the data on the left first for the same two data in the merger process   
  - Not In-place Sort algorithm   
    - A[n] = B[n / 2] + C[n / 2] → Requires additional space equal to input size n   
  -  Algorithms with a typical split-conquer method   
    - Cyclic algorithm. The performance of the cyclic algorithm is represented by recurrence relation   
    - Split steps in Merge Sort   
      - Split a given array into two subarrays of the same size   
    - Conquest Steps in Merge Sort   
      - Arrange by applying merge sort cyclically for each partial array   
    - Combination steps in Merge Sort   
      - Merge two aligned partial arrays to create one aligned array   
  - Can also express merge sort algorithms in an acyclic manner (using iterations)   
    - Example   
      - [60], [20], [70], [10], [80], [30], [50], [40]   
      - → [20, 60], [10, 70], [30, 80], [40, 50]   
      - → [10, 20, 60, 70], [30, 40, 50, 80]   
      - → [10, 20, 30, 40, 50, 60, 70, 80]   
   
<br />
### Heap Sort   
// 힙 정렬   
   
#### Heap's Data Structure   
// 힙의 자료구조   
   
// 힙 정렬 → '힙' 자료구조의 장점을 활용한 정렬   
// - 임의의 값 삽입과 최대값 삭제가 쉬움   
- Heap sort → sort that takes advantage of 'Heap' data structure   
  - Easy to insert any values and delete maximum values   
   
// (최대) 힙 (heap)   
// - 완전 이진 트리 (complete binary tree)   
// - 각 노드의 값은 자신의 자식 노드의 값보다 크거나 같아야 함   
// - 오름차순   
- (Maximum) Heap   
  - Complete binary tree   
  - Each node must have a value greater than or equal to that of its own child node   
  - Ascending order   
   
// (최소) 힙 (heap)   
// - 완전 이진 트리 (complete binary tree)   
// - 각 노드의 값은 자신의 자식 노드의 값보다 작거나 같아야 함   
// - 내림차순   
- (Minimum) Heap   
  - Complete binary tree   
  - Each node must have a value less than or equal to that of its own child node   
  - Descending order   
   
#### Realization of Heap   
// 힙의 구현   
   
// 완전 이진 트리를 일차원 배열로 구현함   
- Implementation of a fully binary tree in a one-dimensional array   
   
- Example   
   
|[0]|[1]|[2]|[3]|[4]|[5]|[6]|[7]|[8]|[9]|[10]|[11]|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|30|15|20|10|9|20|18|30|7|8|5|10|
   
// 부모노드에서 자식노드를 찾을 수 있음   
// - 인덱스 [4]의 왼쪽 자식노드는 [2 * 4 + 1], 오른쪽 자식노드는 [2 * 4 + 2]   
// -- 인덱스 [i]의 왼쪽 자식노드는 [2i + 1], 오른쪽 자식노드는 [2i + 2]   
// 자식노드에서 부모노드를 찾을 수 있음   
// - 인덱스 [9]의 부모노드는 [⌈ <sup>9</sup> / <sub>2</sub> ⌉ - 1] 또는 [⌊ <sup>9 - 1</sup> / <sub>2</sub> ⌋]   
// -- 인덱스 [j]의 부모노드는 [⌈ <sup>j</sup> / <sub>2</sub> ⌉ - 1] 또는 [⌊ <sup>j - 1</sup> / <sub>2</sub> ⌋]   
- Child nodes can be found on parent nodes   
  - The left child node of index [4] is [2 * 4 + 1] and the right child node is [2 * 4 + 2]   
    - The left child node of index [i] is [2i + 1] and the right child node is [2i + 2]   
- Parent node can be found on child node   
  - The parent node of index [9] is [⌈ <sup>9</sup> / <sub>2</sub> ⌉ - 1] or [⌊ <sup>9 - 1</sup> / <sub>2</sub> ⌋]   
    - The parent node of index [j] is [⌈ <sup>j</sup> / <sub>2</sub> ⌉ - 1] or [⌊ <sup>j - 1</sup> / <sub>2</sub> ⌋]   
   
#### Strengths of heap   
// 힙의 장점   
   
// 임의의 값의 삽입   
- Insert any value   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/algorithmHeapInsert1.png)
   
// 최대값 삭제   
// - 최대값은 항상 루트 노드에 존재함   
- Delete the maximum value   
  - The maximum value is always present on the root node   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/algorithmHeapInsert2.png)
   
#### Heap Sort   
// 힙 정렬   
   
// 힙 구조의 장점을 활용한 정렬 방식   
- Sort method utilizing the advantages of heap structure   
   
// 힙 정렬의 처리 과정   
// 단계 1 : 1차원 배열을 힙으로 변환   
// 단계 2 : 배열의 개수만큼 '힙의 최대값을 삭제 → 힙의 재구성' 반복   
- Processing of heap sort   
  - Step 1 : Converting a one-dimensional array to a heap   
  - Step 2 : Repeat 'Delete maximum heap → Reconfigure heap' as many as array   
   
#### Heap Sort Algorithm   
// 힙 정렬 알고리즘   
   
```c
HeapSort (A[], n) {
    // --- 단계 1 (새 노드의 삽입) ---
    // --- Step 1 (insert a new node) ---
    for (i = 0; i < n; i++) {
        par = ⌈ i / 2 ⌉ - 1;
        while (par >= 0 && A[par] < A[i]) {
            // A[par] 과 A[i] 의 교환;
            The exchange of A[par] and A[i];
            i = par;
            par = ⌊ (i - 1) / 2 ⌋;
        }
    }

    // --- 단계 2 ---
    // --- Step 2 ---
    for (i = n - 1; i > 0; i--) {
        // --- 최대값 삭제 ---
        // --- Delete the maximum value ---
        // 최대값 A[0] 와 마지막 노드 A[i] 의 교환;
        Exchange the maximum value A[0] with the last node A[i];

        cur = 0;
        lch = 1;
        rch = 2;

        // --- 힙의 재구성 ---
        // --- Reconfiguration of Heap ---
        do {
            if (rch < i && A[lch] < A[rch]) lch = rch;
            if (A[lch] > A[cur]) {
                // A[cur] 과 A[lch] 의 교환;
                Exchange of A[cur] and A[lch];;
                cur = lch;
                lch = cur * 2 + 1;
                rch = cur * 2 + 2;
            } else {
                lch = i;
            }
        } while (lch < i)
    }

    return (A);
}
```
   
#### Processing of Heap Sort   
// 힙 정렬의 처리 과정   
   
// 입력 배열 : [40, 60, 10, 30, 50, 20]   
// → 1단계 : 1차원 배열을 힙으로 변환   
// - → [60, 50, 20, 30, 40, 10]   
// → 2단계   
// - 최대값과 마지막 노드의 교환 후 최대값을 삭제하고 힙으로 재구성하는 과정을 데이터 개수만큼 반복   
// -- 최대값과 마지막 노드의 교환   
// --- → [10, 50, 20, 30, 40, 60]   
// -- 최대값 삭제   
// --- → [10, 50, 20, 30, 40, <s>60</s>]   
// -- 힙으로 재구성   
// --- → [50, 10, 20, 30, 40, <s>60</s>]   
// --- → [50, 40, 20, 30, 10, <s>60</s>]   
// → 2단계 반복   
// -- 최대값과 마지막 노드의 교환   
// --- → [10, 40, 20, 30, 50, <s>60</s>]   
// -- 최대값 삭제   
// --- → [10, 40, 20, 30, <s>50</s>, <s>60</s>]   
// -- 힙으로 재구성   
// --- → [40, 10, 20, 30, <s>50</s>, <s>60</s>]   
// --- → [40, 30, 20, 10, <s>50</s>, <s>60</s>]   
// → 2단계 반복   
// -- 최대값과 마지막 노드의 교환   
// --- → [10, 30, 20, 40, <s>50</s>, <s>60</s>]   
// -- 최대값 삭제   
// --- → [10, 30, 20, <s>40</s>, <s>50</s>, <s>60</s>]   
// -- 힙으로 재구성   
// --- → [30, 10, 20, <s>40</s>, <s>50</s>, <s>60</s>]   
// → 2단계 반복   
// -- 최대값과 마지막 노드의 교환   
// --- → [20, 10, 30, <s>40</s>, <s>50</s>, <s>60</s>]   
// -- 최대값 삭제   
// --- → [20, 10, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// -- 힙으로 재구성   
// --- → [20, 10, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// → 2단계 반복   
// -- 최대값과 마지막 노드의 교환   
// --- → [10, 20, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// -- 최대값 삭제   
// --- → [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// -- 힙으로 재구성   
// --- → [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// → 2단계 반복   
// -- 최대값과 마지막 노드의 교환   
// --- → [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// -- 최대값 삭제   
// --- → [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// -- 힙으로 재구성   
// --- → [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
// ∴ 정렬 결과   
// → [10, 20, 30, 40, 50, 60]   
- Input Array : [40, 60, 10, 30, 50, 20]   
- → Step 1 : onverting a one-dimensional array to a heap   
  - → [60, 50, 20, 30, 40, 10]   
- → Step 2   
  - Repeat the process of deleting the maximum value and reconfiguring it into a heap after exchanging the maximum value and the last node as many times as the number of data   
    - Exchange the last node with the maximum value   
      - → [10, 50, 20, 30, 40, 60]   
    - Delete the maximum value   
      - → [10, 50, 20, 30, 40, <s>60</s>]   
    - Reconfiguration with heap   
      - → [50, 10, 20, 30, 40, <s>60</s>]   
      - → [50, 40, 20, 30, 10, <s>60</s>]   
- → Repeat Step 2   
    - Exchange the last node with the maximum value   
      - → [10, 40, 20, 30, 50, <s>60</s>]   
    - Delete the maximum value   
      - → [10, 40, 20, 30, <s>50</s>, <s>60</s>]   
    - Reconfiguration with heap   
      - → [40, 10, 20, 30, <s>50</s>, <s>60</s>]   
      - → [40, 30, 20, 10, <s>50</s>, <s>60</s>]   
- → Repeat Step 2   
    - Exchange the last node with the maximum value   
      - → [10, 30, 20, 40, <s>50</s>, <s>60</s>]   
    - Delete the maximum value   
      - → [10, 30, 20, <s>40</s>, <s>50</s>, <s>60</s>]   
    - Reconfiguration with heap   
      - → [30, 10, 20, <s>40</s>, <s>50</s>, <s>60</s>]   
- → Repeat Step 2   
    - Exchange the last node with the maximum value   
      - → [20, 10, 30, <s>40</s>, <s>50</s>, <s>60</s>]   
    - Delete the maximum value   
      - → [20, 10, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
    - Reconfiguration with heap   
      - → [20, 10, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
- → Repeat Step 2   
    - Exchange the last node with the maximum value   
      - → [10, 20, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
    - Delete the maximum value   
      - → [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
    - Reconfiguration with heap   
      - → [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
- → Repeat Step 2   
    - Exchange the last node with the maximum value   
      - → [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
    - Delete the maximum value   
      - → [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
    - Reconfiguration with heap   
      - → [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>]   
∴ Sort Results   
- → [10, 20, 30, 40, 50, 60]   
   
#### Initial Heap Construction   
// 초기 힙 구축   
   
// 1차원 입력 배열을 힙으로 변환하는 것   
// 두 가지 접근 방법   
// - 방법 1 : 주어진 입력 배열의 각 원소를 힙에 삽입하는 과정을 반복   
// - 방법 2 : 주어진 입력 배열을 우선 완전 이진 트리로 만든 후, 각 노드에 대해 아래에서 위로 그리고 오른쪽에서 왼쪽으로 진행하면서 해당 노드의 아랫부분이 힙의 조건을 만족할 수 있도록 트리를 따라 내려가면서 자신의 자손 노드들과의 위치 교환을 계속해 나가는 방법   
// -- 비교 / 위치 교환은 힙의 조건이 만족될 때까지 트리를 따라 내려가면서 계속 진행   
- Converting a one-dimensional input array into a heap   
- Two approaches   
  - Method 1 : Repeat the process of inserting each element of the given input array into the heap   
  - Method 2 : First, make the given input array a complete binary tree, then proceed from bottom to top and from right to left for each node and continue to exchange locations with their descendant nodes while going down the tree so that the lower part of the node can satisfy the heap condition   
    - Comparison/position exchange continues down the tree until heap conditions are met   
   
#### Initial Heap Construction Method 1   
// 초기 힙 구축 방법 1   
   
// 입력 배열 : [60, 20, 70, 10, 80, 30, 50, 40]   
- Input Array : [60, 20, 70, 10, 80, 30, 50, 40]   
   
// 힙에 노드 삽입 순서   
// - [60] 삽입 : Level 0 : (60)   
// - [20, 70] 삽입 : Level 1 : (20) (70) → (70) 과 부모노드 (60) 의 자리 교환 → Level 0 : (70) / Level 1 : (20) (60)   
// - [10, 80] 삽입 : Level 2 : (10) (80) → (80) 과 부모노드 (20) 의 자리 교환 → Level 1 : (80) (60) / Level 2 : (10) (20) → (80) 과 부모노드 (70) 의 자리 교환 → Level 0 : (80) / Level 1 : (70) (60) / Level 2 : (10) (20)   
// - [30, 50] 삽입 : Level 2 : (10) (20) (30) (50)   
// - [40] 삽입 : Level 3 : (40) → (40) 과 부모노드 (10) 의 자리 교환 → Level 2 : (40) (20) (30) (50) / Level 3 : (10)   
// ∴ 힙으로 변환된 최종 상태   
// - [80, 70, 60, 40, 20, 30, 50, 10]   
// -- Level 0 : (80)   
// -- Level 1 : (70) (60)   
// -- Level 2 : (40) (20) (30) (50)   
// -- Level 3 : (10)   
- Order of node insertion in heap   
  - Insert [60] : Level 0 : (60)   
  - Insert [20, 70] : Level 1 : (20) (70) → Place exchange between (70) and parent node (60) → Level 0 : (70) / Level 1 : (20) (60)   
  - Insert [10, 80] : Level 2 : (10) (80) → Place exchange between (80) and parent node (20) → Level 1 : (80) (60) / Level 2 : (10) (20) → Place exchange between (80) and parent node (70) → Level 0 : (80) / Level 1 : (70) (60) / Level 2 : (10) (20)   
  - Insert [30, 50] : Level 2 : (10) (20) (30) (50)   
  - Insert [40] : Level 3 : (40) → Place exchange between (40) and parent node (10) → Level 2 : (40) (20) (30) (50) / Level 3 : (10)   
∴ Final status converted to heap   
  - [80, 70, 60, 40, 20, 30, 50, 10]   
    - Level 0 : (80)   
    - Level 1 : (70) (60)   
    - Level 2 : (40) (20) (30) (50)   
    - Level 3 : (10)   
   
#### Initial Heap Construction Method 2   
// 초기 힙 구축 방법 2   
   
// 입력 배열 : [60, 20, 70, 10, 80, 30, 50, 40]   
- Input Array : [60, 20, 70, 10, 80, 30, 50, 40]   
   
// 완전 이진트리로 만듦   
// - Level 0 : (60)   
// - Level 1 : (20) (70)   
// - Level 2 : (10) (80) (30) (50)   
// - Level 3 : (40)   
// 각 노드에 대해 아래에서 위로 그리고 오른쪽에서 왼쪽으로 진행하면서 해당 노드의 아랫부분이 힙의 조건을 만족할 수 있도록 트리를 따라 내려가면서 자신의 자손 노드들과의 위치 교환을 계속함   
// - (40) (50) (30) (80) 은 자식노드가 없으므로 처리할 노드가 없으므로 넘어감   
// - (10) 은 자식노드보다 작으므로 자식노드 (40) 과 자리 교환 → Level 2 : (40) (80) (30) (50) / Level 3 : (10)   
// - (20) 은 자식노드보다 작으므로 자식노드 (80) 과 자리 교환 → Level 1 : (80) (70) / Level 2 : (40) (20) (30) (50)   
// - (60) 은 자식노드보다 작으므로 자식노드 (80) 과 자리 교환 → Level 0 : (80) / Level 1 : (60) (70)   
// ∴ 힙으로 변환된 최종 상태   
// - [80, 60, 70, 40, 20, 30, 50, 10]   
// -- Level 0 : (80)   
// -- Level 1 : (60) (70)   
// -- Level 2 : (40) (20) (30) (50)   
// -- Level 3 : (10)   
- Make a completely binary tree   
  - Level 0 : (60)   
  - Level 1 : (20) (70)   
  - Level 2 : (10) (80) (30) (50)   
  - Level 3 : (40)   
- For each node, as it progresses from bottom to top and from right to left, it continues to exchange positions with its descendant nodes as it descends down the tree to ensure that the lower part of the node meets the heap's condition   
  - (40) (50) (30) (80) has no child nodes, so it has no nodes to process, so it is skipped   
  - (10) is smaller than the child node, so exchange seats with the child node (40) → Level 2 : (40) (80) (30) (50) / Level 3 : (10)   
  - (20) is smaller than the child node, so exchange seats with the child node (80) → Level 1 : (80) (70) / Level 2 : (40) (20) (30) (50)   
  - (60) is smaller than the child node, so exchange seats with the child node (80) → Level 0 : (80) / Level 1 : (60) (70)   
∴ Final status converted to heap   
  - [80, 60, 70, 40, 20, 30, 50, 10]   
    - Level 0 : (80)   
    - Level 1 : (60) (70)   
    - Level 2 : (40) (20) (30) (50)   
    - Level 3 : (10)   
   
#### Heap Sort Step 2   
// 힙 정렬 단계 2   
   
// 입력 배열 : A[] = [60, 20, 70, 10, 80, 30, 50, 40]   
// 초기 힙 : [80, 60, 70, 40, 20, 30, 50, 10]   
// 단계 2 실행 1   
// - 최대값과 마지막 노드 교환 : [10, 60, 70, 40, 20, 30, 50, 80]   
// - 최대값 삭제 : [10, 60, 70, 40, 20, 30, 50, <s>80</s>]   
// - 힙으로 재구성 : [70, 60, 10, 40, 20, 30, 50, <s>80</s>]   
// - 힙으로 재구성 : [70, 60, 50, 40, 20, 30, 10, <s>80</s>]   
// 단계 2 실행 2   
// - 최대값과 마지막 노드 교환 : [10, 60, 50, 40, 20, 30, 70, <s>80</s>]   
// - 최대값 삭제 : [10, 60, 50, 40, 20, 30, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [60, 10, 50, 40, 20, 30, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [60, 40, 50, 10, 20, 30, <s>70</s>, <s>80</s>]   
// 단계 2 실행 3   
// - 최대값과 마지막 노드 교환 : [30, 40, 50, 10, 20, 60, <s>70</s>, <s>80</s>]   
// - 최대값 삭제 : [30, 40, 50, 10, 20, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [50, 40, 30, 10, 20, <s>60</s>, <s>70</s>, <s>80</s>]   
// 단계 2 실행 4   
// - 최대값과 마지막 노드 교환 : [20, 40, 30, 10, 50, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 최대값 삭제 : [20, 40, 30, 10, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [40, 20, 30, 10, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// 단계 2 실행 5   
// - 최대값과 마지막 노드 교환 : [10, 20, 30, 40, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 최대값 삭제 : [10, 20, 30, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [30, 20, 10, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// 단계 2 실행 6   
// - 최대값과 마지막 노드 교환 : [10, 20, 30, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 최대값 삭제 : [10, 20, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [20, 10, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// 단계 2 실행 7   
// - 최대값과 마지막 노드 교환 : [10, 20, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 최대값 삭제 : [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// 단계 2 실행 8   
// - 최대값과 마지막 노드 교환 : [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 최대값 삭제 : [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// - 힙으로 재구성 : [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
// ∴ 힙 정렬 완료된 최종 상태   
// - [10, 20, 30, 40, 50, 60, 70, 80]   
- Input Array : A[] = [60, 20, 70, 10, 80, 30, 50, 40]   
- Initial Heap : [80, 60, 70, 40, 20, 30, 50, 10]   
- Step 2 Run 1   
  - Exchange the Maximum and Last Node : [10, 60, 70, 40, 20, 30, 50, 80]   
  - Delete the maximum value : [10, 60, 70, 40, 20, 30, 50, <s>80</s>]   
  - Reconfiguration to Heap : [70, 60, 10, 40, 20, 30, 50, <s>80</s>]   
  - Reconfiguration to Heap : [70, 60, 50, 40, 20, 30, 10, <s>80</s>]   
- Step 2 Run 2   
  - Exchange the Maximum and Last Node : [10, 60, 50, 40, 20, 30, 70, <s>80</s>]   
  - Delete the maximum value : [10, 60, 50, 40, 20, 30, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [60, 10, 50, 40, 20, 30, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [60, 40, 50, 10, 20, 30, <s>70</s>, <s>80</s>]   
- Step 2 Run 3   
  - Exchange the Maximum and Last Node : [30, 40, 50, 10, 20, 60, <s>70</s>, <s>80</s>]   
  - Delete the maximum value : [30, 40, 50, 10, 20, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [50, 40, 30, 10, 20, <s>60</s>, <s>70</s>, <s>80</s>]   
- Step 2 Run 4   
  - Exchange the Maximum and Last Node : [20, 40, 30, 10, 50, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Delete the maximum value : [20, 40, 30, 10, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [40, 20, 30, 10, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
- Step 2 Run 5   
  - Exchange the Maximum and Last Node : [10, 20, 30, 40, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Delete the maximum value : [10, 20, 30, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [30, 20, 10, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
- Step 2 Run 6   
  - Exchange the Maximum and Last Node : [10, 20, 30, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Delete the maximum value : [10, 20, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [20, 10, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
- Step 2 Run 7   
  - Exchange the Maximum and Last Node : [10, 20, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Delete the maximum value : [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
- Step 2 Run 8   
  - Exchange the Maximum and Last Node : [10, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Delete the maximum value : [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
  - Reconfiguration to Heap : [<s>10</s>, <s>20</s>, <s>30</s>, <s>40</s>, <s>50</s>, <s>60</s>, <s>70</s>, <s>80</s>]   
∴ Final status of Heap Sort completed   
  - [10, 20, 30, 40, 50, 60, 70, 80]   
   
#### Performance and Features   
// 성능과 특징   
   
// 성능   
// - 최선, 최악, 평균 수행시간 → ∴ O(nlogn)   
// -- 초기 힙 생성, 최대값 삭제 및 힙 재구성   
// --- 바깥 루프 → 입력 크기 n에 비례   
// --- 안쪽 루프 → 완전 이진 트리의 높이 logn에 비례   
- Performance   
  - Best, Worst, Average Time to Run → ∴ O(nlogn)   
    - Create an initial heap, delete a maximum value, and reconfigure the heap   
      - Outer loop → Proportional to input size n   
      -  Inner loop → Proportional to the height logn of the full binary tree   
   
// 특징   
// - 안정적이지 않은 정렬 알고리즘   
// - 제자리 정렬 알고리즘   
// -- 입력 배열 A[] 이외에 상수 개의 저장 공간 (예시 : i, par, cur, lch, rch, tmp) 만 필요   
// -- 이 외 추가적인 메모리가 필요하지 않음   
- Features   
  - Unstable Sort algorithm   
  - In-place Sort algorithm   
    - Only a constant number of storage spaces (e.g., i, par, cur, lch, rch, tmp) other than the input array A[]   
    - No additional memory required   
   
<br />
### Counting Sort   
// 계수 정렬   
   
// 주어진 데이터 중에서 자신보다 작거나 같은 값을 갖는 데이터의 개수를 계산하여 정렬할 위치를 찾아 정렬하는 방식   
// - 입력값이 어떤 작은 정수 범위 내에 있다는 것을 알고 있는 경우에 적용 가능   
// - k보다 작거나 같은 값을 갖는 데이터의 개수   
// -- 정렬 순서상 k의 마지막 위치   
// - 자신보다 작거나 같은 값을 갖는 데이터의 개수의 효율적인 계산 방법   
// -- 입력값의 범위 a ~ b에 해당하는 크기의 배열 COUNT[a..b]를 할당하고, 주어진 값들을 한 번 쭉 훑으면 각 입력값의 출현횟수의 누적값 계산이 가능   
- A method of finding and sorting a position to be aligned by calculating the number of data that have a value less than or equal to itself among the given data   
  - Applicable when you know that the input is within some small integer range   
  - Number of data with a value less than or equal to k   
    - Last position of k in sort order   
  - An efficient method of calculating the number of pieces of data that are less than or equal to one's own   
    - By allocating an array COUNT[a..b] of the size corresponding to the range a ~ b of the input value, and scanning the given values once, the cumulative value of the number of appearances of each input value can be calculated   
   
#### Counting Sort Algorithm   
// 계수 정렬 알고리즘   
   
```c
CountingSort (A[i..n], n) {
    MIN = MAX = A[1];
    // 입력값의 범위 MIN ~ MAX 계산
    // Calculate the range of inputs MIN to MAX
    for (i = 2; i <= n; i++) {
        if (A[i] < MIN) MIN = A[i];
        if (A[i] > MAX) MAX = A[i];
    }
    for (j = MIN; j <= MAX; j++)
        COUNT[j] = 0;
    // 각 입력값의 출현횟수 계산
    // Calculate the number of appearances of each input
    for (i = 1; i <= n; i++)
        COUNT[ A[i] ]++;
    // 각 입력값의 출현횟수의 누적값 계산
    // Calculate the cumulative value of the number of appearances of each input
    for (j = MIN + 1; j <= MAX; j++)
        COUNT[j] = COUNT[j] + COUNT[j - 1];
    // 입력 배열 A[] → 정렬 배열 B[]
    // Input Array A[] → Sort Array B[]
    // Input Array A[] ....
    for (i = n; i > 0; i--) {
        B[ COUNT[ A[i] ] ] = A[i];
        COUNT[ A[i] ]--;
    }
    return (B);
}
```
   
#### Example of Counting Sort   
// 계수 정렬의 예시   
   
// 입력 배열 A[] : [7, 5, 9, 8, 4, 5, 7, 5]   
// 입력값의 범위 : 4 ~ 9   
- Input Array A[] : [7, 5, 9, 8, 4, 5, 7, 5]   
- Range of Inputs : 4 ~ 9   
   
// COUNT[] : [4] = 0, [5] = 0, [6] = 0, [7] = 0, [8] = 0, [9] = 0   
// 각 입력값의 출현 횟수 계산 : COUNT[ A[i] ]++   
// - [<b>7</b>, 5, 9, 8, 4, 5, 7, 5] → 7에 카운트 1 추가 → COUNT[] : [4] = 0, [5] = 0, [6] = 0, [7] = 1, [8] = 0, [9] = 0   
// - [<i>7</i>, <b>5</b>, 9, 8, 4, 5, 7, 5] → 5에 카운트 1 추가 → COUNT[] : [4] = 0, [5] = 1, [6] = 0, [7] = 1, [8] = 0, [9] = 0   
// - [<i>7</i>, <i>5</i>, <b>9</b>, 8, 4, 5, 7, 5] → 9에 카운트 1 추가 → COUNT[] : [4] = 0, [5] = 1, [6] = 0, [7] = 1, [8] = 0, [9] = 1   
// - [<i>7</i>, <i>5</i>, <i>9</i>, <b>8</b>, 4, 5, 7, 5] → 8에 카운트 1 추가 → COUNT[] : [4] = 0, [5] = 1, [6] = 0, [7] = 1, [8] = 1, [9] = 1   
// - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <b>4</b>, 5, 7, 5] → 4에 카운트 1 추가 → COUNT[] : [4] = 1, [5] = 1, [6] = 0, [7] = 1, [8] = 1, [9] = 1   
// - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <i>4</i>, <b>5</b>, 7, 5] → 5에 카운트 1 추가 → COUNT[] : [4] = 1, [5] = 2, [6] = 0, [7] = 1, [8] = 1, [9] = 1   
// - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <i>4</i>, <i>5</i>, <b>7</b>, 5] → 7에 카운트 1 추가 → COUNT[] : [4] = 1, [5] = 2, [6] = 0, [7] = 2, [8] = 1, [9] = 1   
// - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <i>4</i>, <i>5</i>, <i>7</i>, <b>5</b>] → 5에 카운트 1 추가 → COUNT[] : [4] = 1, [5] = 3, [6] = 0, [7] = 2, [8] = 1, [9] = 1   
// 각 입력값의 출현 횟수의 누적값 계산   
// - COUNT[i] = COUNT[i] + COUNT[i - 1]   
// - COUNT[i] : [4] = 1, [5] = 4, [6] = 4, [7] = 6, [8] = 7, [9] = 8   
// -- 각 값이 나타날 마지막 위치를 나타냄   
// 예상되는 정렬 결과   
// - B[] : [4, 5 or 6, 5 or 6, 5 or 6, 7, 7, 8, 9]   
- COUNT[] : [4] = 0, [5] = 0, [6] = 0, [7] = 0, [8] = 0, [9] = 0   
- Calculate the number of appearances of each input : COUNT[ A[i] ]++   
  - [<b>7</b>, 5, 9, 8, 4, 5, 7, 5] → Add 1 count to 7 → COUNT[] : [4] = 0, [5] = 0, [6] = 0, [7] = 1, [8] = 0, [9] = 0   
  - [<i>7</i>, <b>5</b>, 9, 8, 4, 5, 7, 5] → Add 1 count to 5 → COUNT[] : [4] = 0, [5] = 1, [6] = 0, [7] = 1, [8] = 0, [9] = 0   
  - [<i>7</i>, <i>5</i>, <b>9</b>, 8, 4, 5, 7, 5] → Add 1 count to 9 → COUNT[] : [4] = 0, [5] = 1, [6] = 0, [7] = 1, [8] = 0, [9] = 1   
  - [<i>7</i>, <i>5</i>, <i>9</i>, <b>8</b>, 4, 5, 7, 5] → Add 1 count to 8 → COUNT[] : [4] = 0, [5] = 1, [6] = 0, [7] = 1, [8] = 1, [9] = 1   
  - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <b>4</b>, 5, 7, 5] → Add 1 count to 4 → COUNT[] : [4] = 1, [5] = 1, [6] = 0, [7] = 1, [8] = 1, [9] = 1   
  - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <i>4</i>, <b>5</b>, 7, 5] → Add 1 count to 5 → COUNT[] : [4] = 1, [5] = 2, [6] = 0, [7] = 1, [8] = 1, [9] = 1   
  - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <i>4</i>, <i>5</i>, <b>7</b>, 5] → Add 1 count to 7 → COUNT[] : [4] = 1, [5] = 2, [6] = 0, [7] = 2, [8] = 1, [9] = 1   
  - [<i>7</i>, <i>5</i>, <i>9</i>, <i>8</i>, <i>4</i>, <i>5</i>, <i>7</i>, <b>5</b>] → Add 1 count to 5 → COUNT[] : [4] = 1, [5] = 3, [6] = 0, [7] = 2, [8] = 1, [9] = 1   
- Calculate the cumulative value of the number of appearances of each input   
  - COUNT[i] = COUNT[i] + COUNT[i - 1]   
  - COUNT[i] : [4] = 1, [5] = 4, [6] = 4, [7] = 6, [8] = 7, [9] = 8   
    - Indicates the last location where each value will appear   
- Expected sorting results   
  - B[] : [4, 5 or 6, 5 or 6, 5 or 6, 7, 7, 8, 9]   
   
// 입력값의 정렬 : B[ COUNT[ A[i] ] ] = A[i], COUNT[ A[i] ]--   
- Sort of Input Values : B[ COUNT[ A[i] ] ] = A[i], COUNT[ A[i] ]--   
   
|A[] : [7, 5, 9, 8, 4, 5, 7, 5]|COUNT[] : <br />[4] = 1, [5] = 4, [6] = 4, [7] = 6, [8] = 7, [9] = 8|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[8] ] ] = A[8]<br />B[ COUNT[ 5 ] ] = 5<br />B[ 4 ] = 5|COUNT[ A[i] ]--<br />COUNT[ A[8] ]--<br />COUNT[ 5 ]--|
|B[] : [?, ?, ?, 5, ?, ?, ?, ?]|[4] = 1, [5] = 3, [6] = 4, [7] = 6, [8] = 7, [9] = 8|
   
|A[] : [7, 5, 9, 8, 4, 5, 7, <s>5</s>]|COUNT[] : <br />[4] = 1, [5] = 3, [6] = 4, [7] = 6, [8] = 7, [9] = 8|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[7] ] ] = A[7]<br />B[ COUNT[ 7 ] ] = 7<br />B[ 6 ] = 7|COUNT[ A[i] ]--<br />COUNT[ A[7] ]--<br />COUNT[ 7 ]--|
|B[] : [?, ?, ?, 5, ?, 7, ?, ?]|[4] = 1, [5] = 3, [6] = 4, [7] = 5, [8] = 7, [9] = 8|
   
|A[] : [7, 5, 9, 8, 4, 5, <s>7</s>, <s>5</s>]|COUNT[] : <br />[4] = 1, [5] = 3, [6] = 4, [7] = 5, [8] = 7, [9] = 8|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[6] ] ] = A[6]<br />B[ COUNT[ 5 ] ] = 5<br />B[ 3 ] = 5|COUNT[ A[i] ]--<br />COUNT[ A[6] ]--<br />COUNT[ 5 ]--|
|B[] : [?, ?, 5, 5, ?, 7, ?, ?]|[4] = 1, [5] = 2, [6] = 4, [7] = 5, [8] = 7, [9] = 8|
   
|A[] : [7, 5, 9, 8, 4, <s>5</s>, <s>7</s>, <s>5</s>]|COUNT[] : <br />[4] = 1, [5] = 2, [6] = 4, [7] = 5, [8] = 7, [9] = 8|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[5] ] ] = A[5]<br />B[ COUNT[ 4 ] ] = 4<br />B[ 1 ] = 4|COUNT[ A[i] ]--<br />COUNT[ A[5] ]--<br />COUNT[ 4 ]--|
|B[] : [4, ?, 5, 5, ?, 7, ?, ?]|[4] = 0, [5] = 2, [6] = 4, [7] = 5, [8] = 7, [9] = 8|
   
|A[] : [7, 5, 9, 8, <s>4</s>, <s>5</s>, <s>7</s>, <s>5</s>]|COUNT[] : <br />[4] = 0, [5] = 2, [6] = 4, [7] = 5, [8] = 7, [9] = 8|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[4] ] ] = A[4]<br />B[ COUNT[ 8 ] ] = 8<br />B[ 7 ] = 8|COUNT[ A[i] ]--<br />COUNT[ A[4] ]--<br />COUNT[ 8 ]--|
|B[] : [4, ?, 5, 5, ?, 7, 8, ?]|[4] = 0, [5] = 2, [6] = 4, [7] = 5, [8] = 6, [9] = 8|
   
|A[] : [7, 5, 9, <s>8</s>, <s>4</s>, <s>5</s>, <s>7</s>, <s>5</s>]|COUNT[] : <br />[4] = 0, [5] = 2, [6] = 4, [7] = 5, [8] = 6, [9] = 8|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[3] ] ] = A[3]<br />B[ COUNT[ 9 ] ] = 9<br />B[ 8 ] = 9|COUNT[ A[i] ]--<br />COUNT[ A[3] ]--<br />COUNT[ 9 ]--|
|B[] : [4, ?, 5, 5, ?, 7, 8, 9]|[4] = 0, [5] = 2, [6] = 4, [7] = 5, [8] = 6, [9] = 7|
   
|A[] : [7, 5, <s>9</s>, <s>8</s>, <s>4</s>, <s>5</s>, <s>7</s>, <s>5</s>]|COUNT[] : <br />[4] = 0, [5] = 2, [6] = 4, [7] = 5, [8] = 6, [9] = 7|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[2] ] ] = A[2]<br />B[ COUNT[ 5 ] ] = 5<br />B[ 2 ] = 5|COUNT[ A[i] ]--<br />COUNT[ A[2] ]--<br />COUNT[ 5 ]--|
|B[] : [4, 5, 5, 5, ?, 7, 8, 9]|[4] = 0, [5] = 1, [6] = 4, [7] = 5, [8] = 6, [9] = 7|
   
|A[] : [7, <s>5</s>, <s>9</s>, <s>8</s>, <s>4</s>, <s>5</s>, <s>7</s>, <s>5</s>]|COUNT[] : <br />[4] = 0, [5] = 1, [6] = 4, [7] = 5, [8] = 6, [9] = 7|
|:---|:---|
|B[ COUNT[ A[i] ] ] = A[i]<br />B[ COUNT[ A[1] ] ] = A[1]<br />B[ COUNT[ 7 ] ] = 7<br />B[ 5 ] = 7|COUNT[ A[i] ]--<br />COUNT[ A[1] ]--<br />COUNT[ 7 ]--|
|B[] : [4, 5, 5, 5, 7, 7, 8, 9]|[4] = 0, [5] = 1, [6] = 4, [7] = 4, [8] = 6, [9] = 7|
   
#### Performance and Features   
// 성능과 특징   
   
```c
CountingSort (A[i..n], n) {
    MIN = MAX = A[1];
    for (i = 2; i <= n; i++) {    // → O(n)
        if (A[i] < MIN) MIN = A[i];
        if (A[i] > MAX) MAX = A[i];
    }
    for (j = MIN; j <= MAX; j++)    // → O(k)
        COUNT[j] = 0;
    for (i = 1; i <= n; i++)    // → O(n)
        COUNT[ A[i] ]++;
    for (j = MIN + 1; j <= MAX; j++)    // → O(k)
        COUNT[j] = COUNT[j] + COUNT[j - 1];
    for (i = n; i > 0; i--) {    // → O(n)
        B[ COUNT[ A[i] ] ] = A[i];
        COUNT[ A[i] ]--;
    }
    return (B);
}
```
   
// 성능   
// - `for (i = 2; i <= n; i++)` → 루프 i : O(n)   
// - `for (j = MIN; j <= MAX; j++)` → 루프 j : O(k) (k는 범위 : MAX - MIN + 1)   
// - O(n) + O(k) = O(n + k)   
// - → k = O(n) (조건 : 입력값의 범위는 데이터에 비례해야 함)   
// - → ∴ O(n)   
- Performance   
  - `for (i = 2; i <= n; i++)` → Loop i : O(n)   
  - `for (j = MIN; j <= MAX; j++)` → Loop j : O(k) (K is the range : MAX - MIN + 1)   
  - O(n) + O(k) = O(n + k)   
  - → k = O(n) (Condition : The range of input must be proportional to the data)   
  - → ∴ O(n)   
   
// 특징   
// - 입력값의 범위가 데이터의 개수보다 작거나 비례할 때 유용함   
// -- 이런 조건이 만족될 때만 선형 시간의 성능 O(n) 이 보장됨   
// --- 입력값의 범위를 k 라고 할 때 O(n + k) 시간   
// --- → k = O(n) 이 되어야 선형 시간 O(n) 에 동작   
// - 안정적인 정렬 알고리즘   
// -- 입력 배열 A[] 의 오른쪽의 것부터 뽑아서 결과 배열 B[] 의 오른쪽에서부터 저장   
// - 제자리 정렬 알고리즘이 아님   
// -- 입력 배열 A[1..n] + ( COUNT[a..b], B[1..n])   
// - 보편적이지 못한 정렬 알고리즘   
// -- 입력값의 범위를 미리 알아야 함 + 추가적인 배열이 필요   
- Features   
  - Useful when the range of inputs is less than or proportional to the number of data   
    - Performance O(n) of linear time is guaranteed only when these conditions are met   
      - O(n + k) time when the input is in the range of k   
      - → It must be k = O(n) to operate at linear time O(n)   
  - Stable Sort algorithm   
    - Pull from the right side of the input array A[] and save from the right side of the result array B[]   
  - Not In-place Sort algorithm   
    - Input Array A[1..n] + ( COUNT[a..b], B[1..n])   
  - A non-universal sort algorithm   
    - Need to know the range of inputs in advance + Need additional array   
   
<br />
### Radix Sort   
// 기수 정렬   
   
// 입력값을 자릿수별로 구분해서 부분적으로 비교하여 정렬하는 방식   
// - 주어진 데이터의 값을 자릿수별로 나누고, 각 자릿수에 대해 계수 정렬과 같은 안정적인 정렬 알고리즘을 적용하여 정렬   
// -- LSD (Least Significant Digit) 기수 정렬   
// --- 낮은 자리부터 높은 자리로 진행   
// --- Right-to-Left   
// -- MSD (Most Significant Digit) 기수 정렬   
// --- 높은 자리부터 낮은 자리로 진행   
// --- Left-to-Right   
- A method of sorting inputs by separating them by digits and partially comparing them   
  - Divide the values of the given data by digits and align them by applying a stable sort algorithm, such as counting sort, for each digit   
    - LSD (Least Significant Digit) Radix Sort   
      - From low digit to high digit   
      - Right-to-Left   
    - MSD (Most Significant Digit) Radix Sort   
      - From high digit to low digit   
      - Left-to-Right   
   
#### Radix Sort Algorithm   
// 기수 정렬 알고리즘   
   
```c
RadixSort (A[], n) {
    // d 자릿수, LSD 기수 정렬
    // d-digit, LSD radix sort
    for (i = 1; i <= d; i++) {
        // 각 데이터의 i자리의 값에 대해서 안정적인 정렬 알고리즘 적용;
        Apply a stable sort algorithm to the i-digit value of each data;
    }
    return (A);
}
```
   
#### Example of Radix Sort - LSD Radix Sort   
// 기수 정렬의 예시 - LSD 기수 정렬   
   
// 입력 데이터 : [2 8 8], [2 6 5], [4 8 2], [0 9 5], [3 6 1], [0 6 8], [1 8 5], [1 0 0]   
// - 3자리 10진수   
- Input data : [2 8 8], [2 6 5], [4 8 2], [0 9 5], [3 6 1], [0 6 8], [1 8 5], [1 0 0]   
  - A three-digit decimal number   
   
// → 1의 자리수로 정렬 : [1 0 <b>0</b>], [3 6 <b>1</b>], [4 8 <b>2</b>], [2 6 <b>5</b>], [0 9 <b>5</b>], [1 8 <b>5</b>], [2 8 <b>8</b>], [0 6 <b>8</b>]   
// - 안정적인 정렬 알고리즘이기 때문에 1의 자리수가 동일한 경우 입력 데이터의 순서가 유지됨   
// → 10의 자리수로 정렬 : [1 <b>0</b> 0], [3 <b>6</b> 1], [2 <b>6</b> 5], [0 <b>6</b> 8], [4 <b>8</b> 2], [1 <b>8</b> 5], [2 <b>8</b> 8], [0 <b>9</b> 5]   
// - 안정적인 정렬 알고리즘이기 때문에 10의 자리수가 동일한 경우 입력 데이터의 순서가 유지됨   
// → 100의 자리수로 정렬 : [<b>0</b> 6 8], [<b>0</b> 9 5], [<b>1 </b>0 0], [<b>1</b> 8 5], [<b>2</b> 6 5], [<b>2</b> 8 8], [<b>3</b> 6 1], [<b>4</b> 8 2]   
// - 안정적인 정렬 알고리즘이기 때문에 100의 자리수가 동일한 경우 입력 데이터의 순서가 유지됨   
- → Sort by 1 digit : [1 0 <b>0</b>], [3 6 <b>1</b>], [4 8 <b>2</b>], [2 6 <b>5</b>], [0 9 <b>5</b>], [1 8 <b>5</b>], [2 8 <b>8</b>], [0 6 <b>8</b>]   
  - Because it is a stable sort algorithm, the order of the input data is maintained if 1 digit is the same   
- → Sort by 10 digit : [1 <b>0</b> 0], [3 <b>6</b> 1], [2 <b>6</b> 5], [0 <b>6</b> 8], [4 <b>8</b> 2], [1 <b>8</b> 5], [2 <b>8</b> 8], [0 <b>9</b> 5]   
  - Because it is a stable sort algorithm, the order of the input data is maintained if 10 digit is the same   
- → Sort by 100 digit : [<b>0</b> 6 8], [<b>0</b> 9 5], [<b>1 </b>0 0], [<b>1</b> 8 5], [<b>2</b> 6 5], [<b>2</b> 8 8], [<b>3</b> 6 1], [<b>4</b> 8 2]   
  - Because it is a stable sort algorithm, the order of the input data is maintained if 100 digit is the same   
   
#### Example of Radix Sort - LSD Radix Sort   
// 기수 정렬의 예시 - LSD 기수 정렬   
   
// 입력 데이터 : [2 8 8], [2 6 5], [4 8 2], [0 9 5], [3 6 1], [0 6 8], [1 8 5], [1 0 0]   
// - 3자리 10진수   
- Input data : [2 8 8], [2 6 5], [4 8 2], [0 9 5], [3 6 1], [0 6 8], [1 8 5], [1 0 0]   
  - A three-digit decimal number   
   
// → 100의 자리수로 정렬 : [[<b>0</b> 9 5], [<b>0</b> 6 8]], [[<b>1</b> 8 5], [<b>1 </b>0 0]], [[<b>2</b> 8 8], [<b>2</b> 6 5]], [[<b>3</b> 6 1], [<b>4</b> 8 2]]   
// - 안정적인 정렬 알고리즘이기 때문에 100의 자리수가 동일한 경우 입력 데이터의 순서가 유지됨   
// → 10의 자리수로 정렬 : [[0 <b>6</b> 8], [0 <b>9</b> 5]], [[1 <b>0</b> 0], [1 <b>8</b> 5]], [[2 <b>6</b> 5], [2 <b>8</b> 8]], [[3 <b>6</b> 1], [4 <b>8</b> 2]]   
// - 안정적인 정렬 알고리즘이기 때문에 10의 자리수가 동일한 경우 입력 데이터의 순서가 유지됨   
// → 1의 자리수로 정렬 : [[0 6 <b>8</b>], [0 9 <b>5</b>]], [[1 0 <b>0</b>], [1 8 <b>5</b>]], [[2 6 <b>5</b>], [2 8 <b>8</b>]], [[3 6 <b>1</b>], [4 8 <b>2</b>]]   
// - 안정적인 정렬 알고리즘이기 때문에 1의 자리수가 동일한 경우 입력 데이터의 순서가 유지됨   
- Sort by 100 digit : [[<b>0</b> 9 5], [<b>0</b> 6 8]], [[<b>1</b> 8 5], [<b>1 </b>0 0]], [[<b>2</b> 8 8], [<b>2</b> 6 5]], [[<b>3</b> 6 1], [<b>4</b> 8 2]]   
  - Because it is a stable sort algorithm, the order of the input data is maintained if 100 digit is the same   
- Sort by 10 digit : [[0 <b>6</b> 8], [0 <b>9</b> 5]], [[1 <b>0</b> 0], [1 <b>8</b> 5]], [[2 <b>6</b> 5], [2 <b>8</b> 8]], [[3 <b>6</b> 1], [4 <b>8</b> 2]]   
  - Because it is a stable sort algorithm, the order of the input data is maintained if 10 digit is the same   
- Sort by 1 digit : [[0 6 <b>8</b>], [0 9 <b>5</b>]], [[1 0 <b>0</b>], [1 8 <b>5</b>]], [[2 6 <b>5</b>], [2 8 <b>8</b>]], [[3 6 <b>1</b>], [4 8 <b>2</b>]]   
  - Because it is a stable sort algorithm, the order of the input data is maintained if 1 digit is the same   
   
#### Performance and Features   
// 성능과 특징   
   
```c
RadixSort (A[], n) {
    for (i = 1; i <= d; i++) {
        // 각 데이터의 i자리의 값에 대해서 안정적인 정렬 알고리즘 적용;    // 계수 정렬 사용 → O(n)
        Apply a stable sort algorithm to the i-digit value of each data;    // Use counting sort → O(n)
    }
    return (A);
}
```
   
// 성능   
// - `각 데이터의 i자리의 값에 대해서 안정적인 정렬 알고리즘 적용;` → O(n)   
// - → 자릿수 d만큼 반복 → O(dn)   
// - → 자릿수 d를 상수로 취급 → O(n)   
// - ∴ 선형 시간의 성능 = O(n)   
- Performance   
  - `Apply a stable sort algorithm to the i-digit value of each data;` → O(n)   
  - → Repeat by the number of digits d → O(dn)   
  - → Treat the digit d as a constant → O(n)   
  - ∴ Performance of linear time = O(n)   
   
// 특징   
// - 입력 데이터의 자릿수가 상수일 때 유용   
// -- d 자릿수 n개의 숫자들에 대해 계수 정렬을 적용하면 O(dn)   
// --- 여기서 d를 입력 크기 n과 무관한 상수로 간주하면 O(n)   
// - 안정적인 정렬 알고리즘   
// -- 각 자릿수별로 안정적인 정렬 알고리즘을 적용하므로 기수 정렬도 안정적임   
// - 제자리 정렬 알고리즘이 아님   
// -- 계수 정렬 적용 : 전체 데이터 개수와 진법 크기만큼의 추가 공간이 필요   
- Features   
  - Useful when the digits in the input data are constant   
    - Applying counting sort to d-digit n numbers results in O(dn)   
      - Here, if d is considered a constant independent of the input size n, it becomes O(n)   
  - Stable Sort algorithm   
    - The radix sort is also stable as a stable sort algorithm is applied for each digit   
  - Not In-place Sort algorithm   
    - Apply counting sort : Requires additional space equal to the total number of data and base (radix) size   
   
<br />
### Bucket Sort   
// 버킷 정렬   
   
// ① 주어진 데이터들의 값의 범위를 균등하게 나누어 여러 개의 버킷을 만든 뒤   
// ② 각 데이터를 해당하는 버킷에 넣고   
// ③ 각 버킷을 삽입 정렬과 같은 안정적인 정렬을 수행한 후   
// ④ 버킷 순서대로 각 데이터를 나열하는 정렬 방식   
- ① Make several buckets by dividing the range of values of the given data equally   
- ② Put each data into the corresponding bucket   
- ③ After performing a stable sort of each bucket, such as insertion sort   
- ④ Sort method that lists each data in bucket order   
   
// 입력값의 범위 내에서 값이 확률적으로 균등하게 분포될 때 선형 시간에 동작   
- Operates in linear time when values are distributed probabilistically evenly within a range of inputs   
   
#### Bucket Sort Algorithm   
// 버킷 정렬 알고리즘   
   
```c
BuckerSort (A[], n) {
    MIN = MAX = A[0];
    // 입력값의 범위 MIN ~ MAX 계산
    // Calculate the range of inputs MIN to MAX
    for (i = 1; i < n; i++) {
        if (A[i] < MIN)
            MIN = A[i];
        if (A[i] > MAX)
            MAX = A[i];
    }
    // 버킷 구간의 크기 계산
    // Calculate the size of the bucket section
    INTERVAL = ⌊ (MAX - MIN + 1) / n ⌋;
    // 각 데이터를 해당 버킷에 넣기
    // Put each data into the corresponding bucket
    for (i = 0; i < n; i++)
        // A[i]를 BUCKET[ ⌊ (A[i] - MIN) / INTERVAL ⌋ ] 에 삽입;
        Insert A[i] into the BUCKET[ ⌊ (A[i] - MIN) / INTERVAL ⌋ ];
    // 버킷별로 정렬
    // Sort by bucket
    for (i = 0; i < n; i++)
        // 삽입 정렬에 의해 BUCKET[i]를 정렬;
        Align BUCKET[i] by insertion sort;
    // BUCKET[0], BUCKET[1], ... 의 순서대로 데이터를 배열 B[] 에 삽입;
    Insert data into array B[] in the order of  BUCKET[0], BUCKET[1], ...;
    return (B);
}
```
   
#### Example of Bucket Sort   
// 버킷 정렬의 예시   
   
// 입력 배열 A[] : [85, 68, 65, 100, 88, 61, 82, 95]   
// 입력값의 범위 : 61 ~ 100   
// 구간의 크기 5 (= ⌊ (MAX - MIN + 1) / n ⌋ = ⌊ (100 - 61 + 1) / 8 ⌋)   
- Input Array A[] : [85, 68, 65, 100, 88, 61, 82, 95]   
- Range of Inputs : 61 ~ 100   
- Size of the section 5 (= ⌊ (MAX - MIN + 1) / n ⌋ = ⌊ (100 - 61 + 1) / 8 ⌋)   
   
// ① 여러 개의 버킷 만들기   
// - 연결리스트 BUCKET[]   
- ① Creating Multiple Buckets   
  - Connection list BUCKET[]   
   
|61 ~ 65|66 ~ 70|71 ~ 75|76 ~ 80|81 ~ 85|86 ~ 90|91 ~ 95|96 ~ 100|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|[0]|[1]|[2]|[3]|[4]|[5]|[6]|[7]|
   
// ② 각 데이터를 해당 버킷에 넣기   
- ② Put each data into the corresponding bucket   
   
|61 ~ 65|66 ~ 70|71 ~ 75|76 ~ 80|81 ~ 85|86 ~ 90|91 ~ 95|96 ~ 100|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|[0]|[1]|[2]|[3]|[4]|[5]|[6]|[7]|
|65 → 61|68|||85 → 82|88|95|100|
   
// ③ 각 버킷을 삽입 정렬 수행하기   
- ③ Perform insertion sort of each bucket   
   
|61 ~ 65|66 ~ 70|71 ~ 75|76 ~ 80|81 ~ 85|86 ~ 90|91 ~ 95|96 ~ 100|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|[0]|[1]|[2]|[3]|[4]|[5]|[6]|[7]|
|61 → 65|68|||82 → 85|88|95|100|
   
// ④ 버킷 순서대로 각 데이터를 나열하기   
// - ∴ 정렬 결과 B[] = [61, 65, 68, 82, 85, 88, 95, 100]   
- ④ List each data in bucket order   
  - ∴ Sort Results B[] = [61, 65, 68, 82, 85, 88, 95, 100]   
   
#### Performance and Features   
// 성능과 특징   
   
```c
BuckerSort (A[], n) {
    MIN = MAX = A[0];
    for (i = 1; i < n; i++) {    // O(n)
        if (A[i] < MIN)
            MIN = A[i];
        if (A[i] > MAX)
            MAX = A[i];
    }
    INTERVAL = ⌊ (MAX - MIN + 1) / n ⌋;
    for (i = 0; i < n; i++)    // O(n)
        // A[i]를 BUCKET[ ⌊ (A[i] - MIN) / INTERVAL ⌋ ] 에 삽입;
        Insert A[i] into the BUCKET[ ⌊ (A[i] - MIN) / INTERVAL ⌋ ];
    for (i = 0; i < n; i++)    // O(n)
        // 삽입 정렬에 의해 BUCKET[i]를 정렬;
        Align BUCKET[i] by insertion sort;
    // BUCKET[0], BUCKET[1], ... 의 순서대로 데이터를 배열 B[] 에 삽입;    // O(n)
    Insert data into array B[] in the order of BUCKET[0], BUCKET[1], ...;    // O(n)
    return (B);
}
```
   
// 성능   
// - ∴ O(n)   
- Performance     
  - ∴ O(n)   
   
// 특징   
// - 입력 데이터의 값이 확률적으로 균등하게 분포할 때 유용함   
// -- 버킷별 정렬 : 데이터들이 각 버킷에 균등하게 들어갈 때 효율적인 정렬이 가능   
// - 버킷의 개수가 입력 데이터의 개수에 비례해야 유용함   
// -- 버킷의 개수를 ⌊ n / k ⌋ 개로 정하면 각 버킷에는 상수(k) 개의 데이터가 존재   
// --- → 각 버킷을 상수 시간에 정렬 가능   
// --- → 선형 시간의 동작이 가능   
// - 안정적인 정렬 알고리즘   
// -- 데이터를 버킷에 넣을 때 그리고 각 버킷의 정렬 과정에서 상대적인 순서를 유지   
// - 제자리 정렬 알고리즘이 아님   
// -- 추가적인 저장 공간 (BUCKET[] 과 크기 n 의 배열 B[]) 이 필요   
- Features   
  - Useful when values in the input data are distributed probabilistically evenly   
    - Sort by bucket: When data is evenly distributed in each bucket, efficient sorting is possible   
  - Useful when the number of buckets is proportional to the number of input data   
    - If the number of buckets is set to ⌊ n / k ⌋, each bucket has a constant (k) of data   
      - → Each bucket can be sorted in constant time   
      - → Allows linear time to operate   
  - Stable Sort algorithm   
    - When data is placed in the bucket and the sort process of each bucket is carried out, the relative order is maintained   
  - Not In-place Sort algorithm   
    - Additional storage space (BUCKET[] and array B[] of size n) are required   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
