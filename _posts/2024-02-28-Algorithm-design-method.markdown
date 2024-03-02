---
layout: post
title:  "Algorithm: Design, Method"
date:   2024-02-28 09:00:00 +0900
categories: [Algorithm]
---

### Algorithm Design   
// 알고리즘 설계   
   
// 주어진 문제와 조건 등이 매우 다양함   
// 일반적/범용적인 설계 기법은 미존재   
- The problems and conditions given vary widely   
- No general/universal design techniques exist   
   
<br />
### Representative Algorithmic Design Techniques   
// 대표적인 알고리즘 설계 기법   
   
#### Greedy Method   
// 욕심쟁이 방법   
   
  // 탐욕적 방법, 탐욕 알고리즘   
  // 해를 구하는 일련의 선택 과정에서 전후 단계의 선택과는 상관없이 각 단계마다 가장 최선이라고 여겨지는 국부적인 최적해를 선택해 나가면 결과적으로 전체적인 최적해를 구할 수 있을 것이라는 희망적인 전략을 취하는 방법   
  // 각 단계마다 선택한 국부적인 최적해가 항상 전체적인 최적해를 구성하지 못하는 경우도 있음   
  // 간단하면서 효율적인 알고리즘을 만들 수 있는 강력한 기법   
  // 최소값/최대값을 구하는 최적화 문제에 주로 사용   
  - Greed Algorithm   
  - How to take a hopeful strategy that the selection of a local optimal solution, which is considered the best for each step, will result in the overall optimal solution, regardless of the selection of the solution in a series of choices   
  - The local optimal solution selected at each stage may not always make up the overall optimal solution   
  - Powerful techniques to create simple and efficient Algorithm   
  - Mainly used for optimization problems to obtain minimum/maximum values   
   
#### Divide-and-Conquer Method   
// 분할정복 방법   
   
  // 순환적으로 문제를 푸는 하향식 접근 방식   
  // 주어진 문제의 입력을 더 이상 나눌 수 없을 때까지 2개 이상의 작은 문제로 순환적으로 분할하고, 이렇게 분할된 작은 문제들을 각각 해결한 후 이들의 해를 결합하여 원래 문제의 해를 구하는 방법   
  // 분할된 문제는 입력 크기만 작아졌을 뿐 원래 문제와 동일   
  // 분할된 문제는 서로 독립적이므로 순환적인 분할 및 결과의 결합이 가능   
  - Top-down approach to solving problems cyclically   
  - How to cyclically divide the input of a given problem into two or more small problems until it is no longer possible to divide them, solve each of these divided small problems, and combine their solutions to find a solution to the original problem   
  - The segmented problem is the same as the original problem, with only a smaller input size   
  - The segmented problem is independent of each other, allowing for cyclical segmentation and combination of results   
   
  // 각 순환 호출마다 세 단계의 작업을 수행 : ‘분할’-‘정복’-‘결합’의 단계로 구성   
  - Perform three steps for each cyclic call : 'Segmentation'- 'Conquest'- 'Combine'   
   
    // - 분할 : 주어진 문제의 입력을 여러 개의 작은 문제로 분할   
    // - 정복 : 작은 문제들을 순환적으로 분할. 만약 작은 문제가 더이상 분할되지 않을 정도로 크기가 충분히 작으면 순환 호출 없이 작은 문제에 대한 해를 구함   
    // - 결합 : 작은 문제에 대해 정복된 해를 결합하여 원래 문제의 해를 구함   
    - Segmentation : Split the input of a given problem into several small problems   
    - Conquest : Circularly dividing small problems. If the small problem is small enough that it is no longer divided, find a solution to the small problem without a circular call   
    - Combine : Combine the conquered solutions to a small problem to find a solution to the original problem   
   
#### Dynamic Programming Method   
// 동적 프로그래밍 방법   
   
  // 주어진 문제의 입력의 크기가 가장 작은 부분 문제부터 해를 구하여 테이블에 저장해 놓고, 이를 이용하여 입력 크기가 보다 큰 문제의 해를 점진적으로 해결해 가는 상향식 접근 방법   
  // 분할된 문제는 입력 크기만 작아졌을 뿐 원래 문제와 동일   
  // 분할된 문제들은 서로 독립적일 필요는 없음   
  - Bottom-up approach to gradually solve a problem with a larger input size by finding a solution from the smallest part of the given problem and storing it in the table   
  - The segmented problem is the same as the original problem, with only a smaller input size   
  - Divided problems do not have to be independent of each other   
   
<br />
### Representative Application Problem of Greedy Method   
// 욕심쟁이 방법 대표적인 적용 문제   
   
#### Coin Change Problem   
// 거스름돈 문제   
   
  // 동전 문제, 동전 거스름돈 문제   
  // 가게에게 고객에게 돌려줄 거스름돈이 T만큼 있을 때 고객이 받을 동전의 개수를 최소로 하면서 거스름돈을 돌려주는 방법을 찾는 문제   
  // 기본 해결 방법 : 거스름돈의 액수를 초과하지 않으면서 동전의 액면가가 단순히 큰 것부터 욕심을 부려서 최대한 뽑아서 거스름돈을 만듦   
  - Coin problem   
  - The problem of finding a way to return the change while minimizing the number of coins the customer will receive when the store has as much change as T to return to the customer   
  - Basic Solution : Making change by drawing as much as possible by simply being greedy with the large amount of coins without exceeding the amount of change   
   
  // 동전의 액면가가 일반적인 경우에는 욕심쟁이 방법 적용 불가   
  - If the amount of coins is general, the greedy method cannot be applied   
   
    // - 예시 : 120원이라는 동전이 존재한다고 가정하고, 거스름돈이 650원 이라면 500원 동전 1개, 120원 동전 1개, 10원 동전 3개 -> 총 5개의 동전 필요   
    // - 예시 : 120원이라는 동전이 존재하지 않으면, 거스름돈이 650원 이라면 500원 동전 1개, 100원 동전 1개, 50원 동전 1개 -> 총 3개의 동전 필요   
    - Example : Assuming that there are W120 coins, if the change is W650, one W500 coin, one W120 coin, and three W10 coins -> 5 coins in total are required   
    - Example : Assuming that there is no W120 coin, if the change is W650, one W500 coin, one W100 coin, and one W50 coin -> 3 coins in total are required   
   
#### Knapsack Problem   
// 배낭 문제   
   
  // 최대 용량 M인 하나의 배낭, n개의 물체가 있다고 가정하고, 각 물체 i에는 물체의 무게 Wi와 해당 물체를 배낭에 넣었을 때 얻을 수 있는 이익 Pi가 부여됨   
  // 배낭의 용량을 초과하지 않는 범위에서 배낭에 들어있는 물체들의 이익의 합이 최대가 되도록 배낭에 물체를 넣는 방법(또는 최대 이익)을 찾아내는 문제   
  - Assuming that there are 1 backpack (the maximum capacity of the backpack is M) and n items, each item (i) is given the weight of the item (Wi) and the profit (Pi) of putting that item in the backpack   
  - The problem of finding a way (or maximum profit) to put things in a backpack so that the sum of the profit of the items in the backpack is maximum within the backpack's capacity range   
   
  // 기본 해결 방법 : 물체의 무게는 적으면서도 이익이 가장 큰 물체부터 골라서 욕심을 내어 최대한 넣는 과정을 반복. 단위 무게당 이익이 가장 큰 물체부터 최대한 넣는 과정을 반복   
  - Basic Solution : Pick the item with the greatest profit while the weight of the item is small, and repeat the process of greedily putting it in as much as possible. Repeat the process of putting the item with the greatest profit per unit weight as possible   
   
    // - 배낭에 넣는 물체를 쪼개서 넣을 수 있는 경우 배낭의 남은 용량에 맞게 물체를 쪼개서 넣음   
    // - 배낭에 넣는 물체를 쪼개서 넣을 수 없는 0/1 배낭 문제 : 이 경우에는 욕심쟁이 방법으로 해결할 수 없는 NP-완전문제가 됨   
    - If an item splits, it splits the item according to the remaining capacity of the backpack   
    - 0/1 backpack problem that can't split items in a backpack : This is an NP-complete problem that cannot be solved by the greedy method   
   
```c
Expressing the problem

The maximum capacity of the backpack is M = 10
Number of items is N = 4
profit (p1, p2, p3, p4) = (15, 20, 9, 14)
Weight (w1, w2, w3, w4) = (3, 5, 3, 4)

profit per unit weight
(p1, p2, p3, p4) = (5, 4, 3, 3.5)

If an item splits
/* (p1, p2, p3, p4) = (1개 무게 3 이익 15, 1개 무게 5 이익 20, 0개, 1개를 쪼개어 무게 2만큼만 담음 이익 14/2 = 7) */
(p1, p2, p3, p4) = (One weighs 3 and the profit is 15, One weighs 5 and the profit is 20, Zero, The weight of one split item is 2 and the profit is only 14/2 = 7)
/* Maximum profit is 42 */

0/1 backpack problem that can't split items in a backpack
/* (p1, p2, p3, p4) = (1개 무게 3 이익 15, 1개 무게 5 이익 20, 0개, 0개) */
(p1, p2, p3, p4) = (One weighs 3 and the profit is 15, One weighs 5 and the profit is 20, Zero, Zero)
/* Maximum profit is 35 */

/* (p1, p2, p3, p4) = (1개 무게 3 이익 15, 0개, 1개 무게 3 이익 9, 1개 무게 4 이익 14) */
(p1, p2, p3, p4) = (One weighs 3 and the profit is 15, Zero, One weighs 3 and the profit is 9, One weighs 4 and the profit is 14)
/* Maximum profit is 38 */

--> This is an NP-complete problem that cannot be solved by the greedy method
```   
   
#### Minimum Spanning Tree (Kruskal's Algorithm, Prim's Algorithm)   
// 최소 신장 트리 문제 (크루스칼 알고리즘, 프림 알고리즘)   
   
#### Single starting point shortest path problem (Dijkstra's Algorithm)   
// 단일 출발점 최단 경로 문제 (데이크스트라 알고리즘)   
   
<br />
### Representative Application Problem of Divide-and-Conquer Method   
// 분할정복 방법 대표적인 적용 문제   
    
#### Binary Search   
// 이진 탐색   
   
// 이진 탐색 알고리즘과 분할정복 방법의 관계   
Relationship between Binary Search Algorithm and Divide-and-Conquer Method   
   
// - 분할 : 배열의 가운데 원소를 기준으로 왼쪽과 오른쪽 부분배열로 절반씩 분할. 탐색 키와 가운데 원소가 같으면 해당 원소의 배열 인덱스를 반환/종료   
// - 정복 : 탐색 키가 가운데 원소보다 작으면 왼쪽 부분배열을 대상으로 이진 탐색을 순환 호출, 크면 오른쪽 부분배열을 대상으로 이진 탐색을 순환 호출   
// - 결합 : 부분배열에 대한 탐색 결과가 직접 반환되므로 결합이 불필요   
   
- Split : Split into left and right subarrays based on the middle element of the array. Returns/terminates the array index of that element if the search key and the middle element are the same   
- Conquest : If the search key is smaller than the middle element, circular calls binary search for the left subarray; if it is larger, circular calls for binary search for the right subarray   
- Combination : no combination is required as search results for partial arrangement are returned directly   
   
#### Quick sort   
// 퀵 정렬   
   
#### Merge Sort   
// 합병 정렬   
   
<br />
### Representative Application Problem of Dynamic Programming Method   
// 동적 프로그래밍 방법 대표적인 적용 문제   
   
// 모든 쌍 간의 최단 경로 문제 (플로이드 알고리즘)   
// 연쇄적 행렬 곱셈 문제   
// 최장 공통 부분 수열 문제   
- Shortest Path Problem Between All Pairs (Floyd's Algorithm)   
- Sequential matrix multiplication problem   
- Longest Common Partial Sequence Problem   
   
<br />
### Algorithm Example - Find the Minimum   
// 알고리즘 예시 - 최소값 찾기   
   
Array of Input Values : 80, 70, 40, 20, 30, 10, 60, 50   
   
// - 일상 언어로 표현/기술하는 경우   
- Expressions/descriptions with Everyday Language   
   
// 1. 첫번째 데이터를 최소값 [0]로 저장한다.   
// 2. 다음 숫자 [1]을 읽고, 이것과 저장된 최소값과 비교한다.   
// 3. 비교 후 더 작은 숫자를 최소값으로 다시 저장한다.   
// 4. 다음에 처리할 데이터가 남아 있으면 [2]로 간다.   
// 5. 저장된 최소값을 결과로 출력한다.   
1. Save the first data as the minimum [0].   
2. Read the following number [1] and compare it with the stored minimum.   
3. After comparison, save the smaller numbers back to the minimum.   
4. If there is any data left to process next, go to [2].   
5. The stored minimum value is output as a result.   
   
// - 의사코드로 표현/기술하는 경우   
- Expressions/descriptions with Pseudo Code   
   
```c
i = 1;
min = A[0];          // Data A[0..n-1]
while(i < n) {
  // A[i]가 min보다 작으면 min = A[i];
  if A[i] is less than min = A[i];
  i++;
}
// 최소값 min 출력;
Minimum min output;
```
   
<br />
### Algorithm Example - Koenigsberg Bridge Problem - Euler Path   
// 알고리즘 예시 - 퀘니히스베르크(퀘닉스버그) 다리 문제 - 오일러 경로   
   
// - 그래프의 모든 간선을 오직 한번씩만 지나가는 경로 찾기   
- Find the path that passes through every edge of the graph only once   
   
// 1. 각 정점의 차수가 홀수인 정점이 0개 혹은 2개이어야 한다.   
// 2. 홀수점이 2개일 경우에는 홀수점에서 시작해야 한다.   
1. Each vertex must have 0 or 2 vertices of which the order is odd.   
2. If there are two odd points, it should start at the odd point.   
   
// - 퀘니히스베르크(퀘닉스버그) 다리는 정점 4개, 간선 7개, 차수가 홀수인 정점이 4개이므로 오일러 경로가 존재하지 않음   
  - No Euler path exists for the Quenichberg (Quenichberg) bridge because it has four vertices, seven edges, and four vertices with odd orders   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
