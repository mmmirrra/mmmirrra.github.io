---
layout: post
title:  "Introduction to Computer Science: Data structure"
date:   2024-05-04 09:00:00 +0900
categories: [Computer Science]
---

### Basic Concept   
// 기본 개념   
   
#### Concept of data structure   
// 자료구조의 개념   
   
// 자료 사이의 논리적 관계를 컴퓨터나 프로그램에 적용하기 위해서는 자료의 추상화가 필요함   
// - 자료구조 (data structure) : 추상화를 통해 자료의 논리적 관계를 구조화한 것   
// 자료가 복잡해지거나 소프트웨어가 복잡해질수록 자료구조의 중요성이 강조됨   
- Data abstraction is required to apply logical relationships between data to computers or programs   
  - Data structure : Structured the logical relationship of data through abstraction   
- The more complex the data or the more complex the software, the greater the importance of the data structure   
   
// 추상화 : 공통적인 개념을 이용하여 같은 종류의 다양한 객체를 정의하는 것   
// - 수식, 프로그램 언어 등   
- Abstraction : Defining various objects of the same kind using common concepts   
  - Mathematical expression, program languages, etc.   
   
// 자료 (데이터) 의 추상화 : 다양한 객체를 컴퓨터에서 표현하고 활용하기 위해 필요한 데이터의 구조에 대해서 공통의 특징만을 뽑아 정의한 것   
- Abstraction of data : The structure of data necessary to express and utilize various objects in a computer is defined by extracting only common features   
   
// 자료의 추상화가 구조화가 적절히 이루어지지 못하면 소프트웨어는 비효율적으로 개발되거나, 비효율적으로 수행되거나, 소프트웨어의 확장성에 문제가 생기거나, 소프트웨어의 유지보수에 문제가 생길 수 있음   
- If data abstraction is not properly structured, software can be developed inefficiently, performed inefficiently, software scalability problems, or software maintenance problems   
   
#### Types and Relationships of Data Structure   
// 자료구조의 종류와 관계   
   
|// 미리 정의된 자료구조<br />Predefined Data Structure||// 사용자 정의 자료구조<br />Custom Data Structure|
|:---|:---|:---|
|// 기본 자료구조<br />Basic Data Structure|// 파생된 자료구조<br />Derived Data Structure||
|// 정수<br />Integer<br />// 실수<br />Real Number<br />// 문자<br />Character|// 배열<br />Array<br />// 구조체<br />Structure<br />// 포인터<br />Pointer|// 리스트<br />List<br />// 스택<br />Stack<br />// 큐<br />Queue<br />// 트리<br />Tree<br />// 그래프<br />Graph|
   
// 미리 정의된 자료구조   
// - 프로그래밍 언어에서 제공함   
// - 프로그래밍 언어 설계나 컴파일러 구현 단계에서 정의되어 개발자에게 제공되는 자료구조   
- Predefined Data Structure   
  - Provided by programming languages   
  - Data structure defined during programming language design or compiler implementation and provided to developers   
   
// 사용자 정의 자료구조   
// - 개발자가 정의하여 사용함   
// - 소프트웨어 개발 중에 개발자에 의해 만들어지는 자료구조 (리스트, 스택, 큐, 트리, 그래프 등)   
- Custom Data Structure   
  - Defined and used by the developer   
  - Data structures created by developers during software development (list, stack, queue, tree, graph, etc.)   
   
<br />
### Array   
// 배열   
   
#### Concept of array   
// 배열의 개념   
   
// 배열 (array) : 동일한 자료형을 갖는 여러 개의 데이터를 동일한 변수 이름의 방에 일렬로 저장하는 자료 집합체 (원소 + 인덱스)   
// 원소 (요소) : 자료 집합체에서 각 원소의 항목값   
// - 데이터   
// 인덱스 (첨자) : 자료 집합체에서 각 원소가 저장된 방을 접근하기 위한 방 번호에 해당하는 것   
// - 번호   
- Array : A collection of data (element + index) that stores multiple data of the same type in a row in a room with the same variable name   
- Element : The value of each element's entry in the data set   
  - Data   
- Index (subscript) : In a data set, each element corresponds to the room number for accessing the room where it is stored   
  - number   
   
#### One-dimensional array   
// 1차원 배열   
   
// 가장 간단한 형태의 배열임   
// 한 개의 인덱스 (첨자) 를 사용해서 원소에 직접 접근   
// 배열의 원소들은 컴퓨터 메모리의 연속적인 기억장소에 할당되어 순차적으로 저장됨   
// 배열 A의 크기를 k라고 가정하고 시작 주소를 a라고 가정하면, A[i]의 저장 주소는 a + i * k 가 됨   
- The simplest form of array   
- Accessing an element directly using one index (subscript)   
- Elements in an array are assigned to a continuous storage location in computer memory and stored sequentially   
- Assuming the size of array A is k and the starting address is a, the storage address of A[i] is a + i * k   
   
#### Multidimensional array   
// 다차원 배열   
   
// 두 개 이상의 첨자들을 가지는 배열을 총칭함   
- Collectively refer to an array with two or more subscripts   
   
// 2차원 배열   
// - A[i][j]   
// - 행 (row) : 첨자 i에 해당하는 것   
// - 열 (column) : 첨자 j에 해당하는 것   
- Two-dimensional array   
  - A[i][j]   
  - row : Corresponding to subscript i   
  - column : Corresponding to subscript j   
   
// 3차원 배열   
- Three-dimensional array   
  - A[m][n][j]   
   
#### Storage order of two-dimensional array   
// 2차원 배열 저장 순서   
   
// 열 우선 순서 저장   
// - 첫 열에 있는 각 행의 원소를 차례대로 컴퓨터 메모리에 저장하고, 다음 열로 이동하여 각 해에 있는 원소를 차례대로 컴퓨터 메모리에 저장하는 방법   
- Save column priority order   
  - Store the elements in each row in the first column in computer memory in turn, move to the next column, and store the elements in each row in computer memory in turn   
   
// 행 우선 순서 저장   
// - 첫 행에 있는 각 열의 원소를 차례대로 컴퓨터 메모리에 저장하고, 다음 행으로 이동하여 각 열에 있는 원소를 차례대로 컴퓨터 메모리에 저장하는 방법   
- Save row priority order   
  - Store the elements in each column in the first row in computer memory in turn, move to the next row, and store the elements in each column in computer memory in turn   
   
<br />
### Spare matrix   
// 희소 행렬   
   
// 원소 값이 0인 원소가 그렇지 않은 원소보다 상대적으로 많은 행렬   
// 0값을 저장하기 위해 컴퓨터 메모리의 낭비를 막고, 처리의 효율성을 높이기 위해 사용됨   
// 희소 행렬의 0인 원소는 저장하지 않고, 0이 아닌 값 만을 따로 모아서 저장하는 방법   
// 0이 아닌 각 원소를 (행 번호, 열 번호, 원소 값) 의 형태로 나타내면 2차원 배열로 표현 가능함   
- A sparse matrix is a matrix that has a relatively larger number of elements with an element value of zero than an element that does not   
- Used to prevent waste of computer memory to store zero values and to increase processing efficiency   
- Save only nonzero values separately without storing elements that are zero   
- If each nonzero element is represented in the form of (row number, column number, element value), it can be represented in a two-dimensional array   
   
// 희소행렬의 일반적 배열표현   
- General array representation of sparse matrices   
   
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
   
// 희소행렬의 효율적 배열 표현   
- Expression of an efficient array of sparse matrices   
   
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
### List   
// 리스트   
   
#### linear list   
// 선형 리스트   
   
// 순서 리스트 (ordered list) 라고도 함   
// 1개 이상의 원소들이 순서를 가지고 구성됨   
// A = (a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>i</sub>, ..., a<sub>n</sub>) 과 같이 표시함   
// - a<sub>i</sub>는 i번째 원소를 나타냄   
// - a<sub>n</sub>의 n은 리스트의 크기가 됨   
- Also called ordered list   
- One or more elements are organized in order   
- Displayed as A = (a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>i</sub>, ..., a<sub>n</sub>)   
  - a<sub>i</sub> denotes the i-th element   
  - n of a<sub>n</sub> becomes the size of the list   
   
// 예시   
// - 요일 리스트 : (월, 화, 수, 목, 금, 토, 일)   
// - 전쟁 리스트 : ((황산벌 전투, 660), (임진왜란, 1592), (세계 1차 대전, 1914), (세계 2차 대전, 1939))   
- Example   
  - List of days of the week : (Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday)   
  - War List : ((Battle of the Hwangsan Bees, 660), (Imjin War, 1592), (World War I, 1914), (World War II, 1939))   
   
#### Implementation of Linear Listing 1 - Implementation with Array   
// 선형 리스트의 구현 1 - 배열 (array) 을 통한 구현   
   
// 선형 리스트와 1차원 배열은 순차적인 구조를 가지고 있으므로 1차원 배열로 간단하게 표현할 수 있음   
- Linear lists and one-dimensional arrangements have sequential structures, so they can be simply expressed as one-dimensional arrangements   
   
// 원소 삭제의 경우에도 삭제할 원소를 찾아 삭제한 후, 그 뒤에 있는 모든 원소들을 한 칸 씩 앞으로 이동시켜야 함   
- Even in the case of element deletion, all the elements behind it must be moved forward one by one after finding and deleting the elements to be deleted   
   
#### Implementation of Linear Listing 1 - Implementation with linked list   
// 선형 리스트의 구현 2 - 연결 리스트 (linked list) 를 통한 구현   
   
// 노드 간의 포인터 연결을 통해서 구현됨   
// 각 노드는 적어도 두 종류의 필드, 원소 값을 저장하는 데이터 필드와 노드 연결을 위한 링크 필드를 가짐   
// 선형 리스트의 논리적 순서만을 지원함   
- Implemented through pointer connections between nodes   
- Each node has at least two types of fields, a data field for storing element values, and a link field for node connection   
- Supports only the logical order of linear lists   
   
<br />
### Type of linked list   
// 연결 리스트 종류   
   
#### Singly linked list   
// 단일 연결 리스트   
   
// 특정 노드의 링크 필드를 사용해서 후행 노드를 가리킴   
// 특정 노드의 후행 노드는 쉽게 접근할 수 있지만, 선행 노드에 대한 접근은 헤드 노드부터 새로 시작해야 함   
- Use the link field for a particular node to point to a trailing node   
- Although the trailing node of a particular node is easily accessible, access to the leading node must start anew with the head node   
   
#### Double linked list   
// 이중 연결 리스트   
   
// 특정 노드의 첫번째 링크는 후행 노드를 가리키고 두번째 링크는 선행 노드를 가리킴   
// 특정 노드에서 후행 노드 뿐만 아니라 선행 노드에 대한 접근을 쉽게 제공하기 위한 것   
- The first link on a particular node points to the trailing node and the second link points to the preceding node   
- To provide easy access to the preceding node as well as the trailing node from a particular node   
   
<br />
### Stack   
// 스택   
   
// 데이터의 삽입과 삭제가 한쪽 끝에서만 이루어지는 자료구조   
// 가장 먼저 입력된 데이터가 가장 나중에 제거되는 선입후출 (FILO, First-In-Last-Out) 특징을 가짐   
- Data structure where data is inserted and deleted at only one end   
- FILO (First-In-Last-Out) feature where the first data entered is the last to be removed   
   
#### Operation of the stack   
// 스택의 연산   
   
// 스택 오버플로 (overflow)   
// - 삽입 연산을 수행할 때 발생함   
// - 스택을 위해 할당된 저장 공간을 초과해서 더 이상 데이터를 삽입할 수 없는 현상   
- Stack overflow   
  - Occurs when performing the insert operation   
  - A phenomenon in which data can no longer be inserted beyond the storage space allocated for the stack   
   
// 스택 언더플로 (underflow)   
// - 삭제 연산을 수행할 때 발생함   
// - 스택에 데이터가 존재하지 않으면 삭제가 일어나지 않는 현상   
- Stack underflow   
  - Occurs when performing a delete operation   
  - Deletion does not occur if data does not exist in the stack   
   
#### Operation of the stack   
// 스택의 동작   
   
```c
push (S, 'A')
push (S, 'B')
if not empty(S) then pop(S)
push (S, 'C')
push (S, 'D')
```
   
<br />
### Queue   
// 큐   
   
// 선형 리스트의 한쪽 끝에서는 데이터의 삭제만 이루어지고, 다른 한쪽 끝에서는 데이터의 삽입만 이루어지는 자료구조   
// 가장 먼저 입력된 데이터가 가장 먼저 제거되는 선입선출 (FIFO, First-In-First-Out) 특징을 가짐   
- A data structure in which only data is deleted at one end of the linear list and only data is inserted at the other end   
- FIFO (First-in-first-out) feature in which the first data entered is removed first   
   
#### Operation of the queue   
// 큐의 연산   
   
// 큐 오버플로 (overflow)   
// - 삽입 연산을 수행할 때 발생함   
// - 큐를 위해 할당된 저장 공간을 초과해서 더 이상 데이터를 삽입할 수 없는 현상   
- Queue overflow   
  - Occurs when performing the insert operation   
  - A phenomenon in which data can no longer be inserted beyond the storage space allocated for the queue   
   
// 큐 언더플로 (underflow)   
// - 삭제 연산을 수행할 때 발생함   
// - 큐에 데이터가 존재하지 않으면 삭제가 일어나지 않는 현상   
- Queue underflow   
  - Occurs when performing a delete operation   
  - Deletion does not occur if data does not exist in the queue   
   
#### Operation of the queue   
// 큐의 동작   
   
```c
engueue (Q, 'A')
engueue (Q, 'B')
engueue (Q, 'C')
if not empty(Q) then dequeue(Q)
engueue (Q, 'D')
if not empty(Q) then dequeue(Q)
```
   
#### The state of the queue after the operation (full state)   
// 연산 후의 큐의 상태 (만원 상태)   
   
// 데이터가 큐에 삽입됨에 따라 rear 변수 값이 증가하다가 n-1이 되면 더이상 데이터가 삽입될 수 없는 상태가 됨   
// 하지만, 이 경우가 반드시 큐에 n개의 항목이 가득 차 있다는 것을 의미하는 것은 아님   
// 큐가 가득 채워진 상태를 결정하기 위한 다른 방법이 필요함   
- The value of the near variable increases as the data is inserted into the queue, and when it reaches n-1, the data can no longer be inserted   
- However, this does not necessarily mean that the queue is full of n entries   
- Another method is needed to determine the state of the queue being full   
   
<br />
### Tree Terminology Definition   
// 트리 용어 정의   
   
// 데이터 간의 관계를 나타내는 비선형 자료구조   
// 노드 (node) 라고 불리는 부분과 노드를 연결하는 가지 (branch, edge) 로 구분됨   
// 노드 사이에는 계층적인 관계성을 갖음   
- Non-linear data structure that represents the relationship between data   
- It is separated by a part called a node and a branch (edge) that connects the node   
- Hierarchical relationships between nodes   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataStructureTree.png)
   
// 노드 (node)   
// - 정보 항목을 의미함   
// 루트 (root)   
// - 빈 트리가 아닌 경우에 맨 꼭대기에 있는 하나의 노드   
// 차수 (degree)   
// - 각 노드에 있는 가지의 수   
// 잎 노드 (leaf node)   
// - 단말 노드 (terminal node)   
// - 노드의 차수가 0인 노드   
// 내부 노드 (internal node)   
// - 비단말 노드 (non-terminal node)   
// - 루트 노드와 단말 노드를 제외한 나머지 노드   
// 조상 (선조) 노드   
// - 루트 노드로부터 어떤 노드 X까지의 경로 (가지들의 모듬) 상에 존재하는 모든 노드를 X의 조상 노드라고 함   
// 자손 (후손) 노드   
// - 어떤 노드 X에서 단말 노드까지의 경로 상에 존재하는 모든 노드를 자손 노드라고 함   
// 레벨 (level)   
// - 루트 노드로부터의 거리 (가지의 수)를 의미함   
// 트리의 깊이 (depth) / 높이 (height)   
// - 루트 노드로부터 가장 긴 경로에 있는 단말 노드의 레벨에 1의 값을 더한 것 (예시 : 깊이 : 4)   
// 서브 트리 (subtree)   
// - 특정 노드를 루트 노드로 하고, 그 아래에 잇는 연결된 구조의 트리   
// 숲 (forest)   
// - n개의 서브 트리를 가진 트리에서 루트 노드를 제거해서 얻을 수 있는 분리된 서브 트리의 집합   
- node   
  - Meaning information items   
- root   
  - One node at the top if it is not an empty tree   
- degree   
  - Number of branches on each node   
- leaf node   
  - terminal node   
  - Node with degree 0 of the node   
- internal node   
  - non-terminal node   
  - Except root node and terminal node, remaining nodes   
- ancestral (Parent) Node   
  - Any node that exists on the path from the root node to any node X (a set of branches) is called the ancestor node of X   
- offspring (child) node   
  - Any node that exists on the path from any node X to a terminal node is called a offspring node   
- level   
  - Indicates the distance (number of branches) from the root node   
- depth / height of the tree   
  - The level of the terminal node on the longest path from the root node plus 1 (e.g., depth : 4)   
- subtree   
  - A tree of connected structures with a specific node as the root node and below it   
- forest   
  - A set of separate subtrees that can be obtained by removing root nodes from a tree with n subtrees   
   
<br />
### Binary Tree   
// 이진 트리   
   
// 트리 중에서 차수가 2인 트리   
// 모든 노드의 차수는 최대 2를 넘지 않음   
// 모든 노드는 최대 2개의 서브 트리를 가짐   
- A tree with degree 2 among the trees   
- All nodes have degree not greater than 2 max   
- All nodes have up to two subtrees   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataStructureBinaryTree.png)
   
// 각 서브 트리는 왼쪽 서브 트리와 오른쪽 서브 트리로 구분됨   
// 왼쪽 노드와 오른쪽 노드에 '순서'의 의미를 부여함   
// 이진 트리의 각 서브 트리는 다시 이진 트리가 됨   
- Each subtree is divided into a left subtree and a right subtree   
- Giving the meaning of 'order' to the left and right nodes   
- Each subtree in a binary tree becomes a binary tree again   
   
#### Height of the binary tree   
// 이진 트리의 높이   
   
// N개의 노드를 가진 이진 트리의 높이를 계산으로 구할 수 있음   
// 최대 높이 : N으로 노드의 개수와 같음   
// 최소 높이 : 최대 2개의 자식 노드를 갖는 경우로서 [log<sub>2</sub> N] + 1 이 높이가 됨   
- The height of a binary tree with N nodes can be calculated   
- Maximum height : Equal to the number of nodes in N   
- Minimum height : Has up to two offspring nodes. [log<sub>2</sub> N] + 1 is the height   
   
#### Binary tree round operation   
// 이진 트리 순회 연산   
   
// 일정한 순서에 따라 트리에 있는 각 노드를 한 번씩 방문하는 것   
- Visiting each node in the tree once in a certain order   
   
// 전위 순회 (DLR : preorder)   
// - 루트 노드 방문 → 왼쪽 서브 트리 방문 → 오른쪽 서브 트리 방문   
// 중위 순회 (LDR : inorder)   
// - 왼쪽 서브 트리 방문 → 루트 노드 방문 → 오른쪽 서브 트리 방문   
// 후위 순회 (LRD : postorder)   
// - 왼쪽 서브 트리 방문 → 오른쪽 서브 트리 방문 → 루트 노드 방문   
- DLR : preorder   
  - Visit the root node → Visit the left subtree → Visit the right subtree   
- LDR : inorder   
  - Visit the left subtree → Visit the root node → Visit the right subtree   
- LRD : postorder   
  - Visit the left subtree → Visit the right subtree → Visit the root node   
   
<br />
### Full Binary Tree   
// 포화 이진 트리   
   
// 깊이가 k인 이진 트리 중에서 노드의 개수가 2<sup>k</sup> - 1 개인 이진 트리   
// 깊이가 k인 이진 트리가 가질 수 있는 노드의 최대 개수는 2<sup>k</sup> - 1 개   
// 단말 노드의 개수가 2<sup>k</sup> - 1 개   
// 각 레벨에서 빈자리가 없이 노드를 모두 가지고 있음   
// 모든 내부 노드들은 2개의 자식 노드를 가짐   
- Binary trees with 2<sup>k</sup> - 1 nodes among binary trees with depth k   
- The maximum number of nodes that a binary tree with depth k can have is 2<sup>k</sup> - 1   
- 2<sup>k</sup> - 1 terminal nodes   
- Have all nodes, no vacancies at each level   
- All internal nodes have two offspring nodes   
   
<br />
### Complete Binary Tree   
// 완전 이진 트리   
   
// 트리의 최대 레벨이 k일 때 레벨 k - 1 까지는 포화 이진 트리를 형성하고, 레벨 k에서는 왼쪽부터 오른쪽으로 채워진 트리임   
// 총 노드의 개수가 2<sup>k + 1</sup> - 1 을 초과하지 않으면서 포화 이진 트리의 노드 번호에 해당하는 연속적인 번호를 갖는 트리임   
- When the maximum level of the tree is k, a saturated binary tree is formed up to level k-1, and at level k, a tree filled from left to right   
- A tree with consecutive numbers corresponding to the node number of a saturated binary tree without the total number of nodes exceeding 2<sup>k + 1</sup> - 1   
   
<br />
### Skewed Binary Tree   
// 경사 이진 트리   
   
// 한 쪽 방향으로만 가지가 뻗어 나간 이진 트리   
// 왼쪽 방향으로만 가지가 뻗어 나간 경사 이진 트리   
// 오른쪽 방향으로만 가지가 뻗어 나간 경사 이진 트리   
- A binary tree with branches extending only in one direction   
- A skewed binary tree with branches extending only to the left   
- A skewed binary tree with branches extending only to the right   
   
<br />
### Graph   
// 그래프   
   
#### Concepts and Terms of Graphs   
// 그래프의 개념과 용어   
   
// 그래프 G   
// - 정점 (vertex) 들의 유한 집합 V와 두 개의 정점을 연결하는 간선 (edge) 들의 유한 집합 E로 정의   
- Graph G   
  - Defined by the finite set V of vertices and the finite set E of edges connecting two vertices   
  - G = (V, E)   
   
// 무방향 그래프 (undirected graph)   
// - 간선이 방향성이 없는 간선으로 연결된 그래프   
- Undirected graph   
  - Graphs with edges connected by non-directional edges   
   
// 방향 그래프 (directed graph, digraph)   
// - 두 정점을 연결하는 간선이 방향성을 가지는 간선으로 연결된 그래프   
- Directed graph (digraph)   
  - Graph of an edge connecting two vertices by a directional edge   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataStructureGraph.png)
   
```c
V(G1) = {1, 2, 3, 4}
E(G1) = {(1, 2), (1, 3), (1, 4), (2, 1), (2, 3), (2, 4), (3, 1), (3, 2), (3, 4), (4, 1), (4, 2), (4, 3)}

V(G2) = {1, 2, 3, 4}
E(G2) = {<1, 2>, <1, 3>, <3, 2>, <3, 4>, <4, 1>, <4, 2>}
```
   
// 두 정점이 간선으로 직접 연결되어 있으면 두 정점은 인접 (adjacent) 해 있다고 하며, 해당 간선은 두 정점에 부수 (incident) 되었다고 함   
// '인접한다'   
// - 정점 간의 관계   
// '부수되었다'   
// - 정점과 간선 간의 관계   
// 경로 (path)   
// - 간선으로 연결된 정점들의 순차적 나열을 의미함   
// 경로의 길이   
// - 경로에 포함된 간선의 개수   
// 단순 경로 (simple path)   
// - 경로 상에 존재하는 정점들이 모두 다른 경로   
// 사이클 (cycle)   
// - 세 개 이상의 정점을 가진 경로 중에서 시작 정점과 끝 정점이 같은 경로   
// 단순 사이클 (simple cycle)   
// - 시작 정점과 끝 정점을 제외하고 모든 정점이 다른 사이클   
// '두 정점은 서로 연결되었다'   
// - 두 정점 사이에 경로가 존재함   
// '그래프가 서로 연결되었다'   
// - 무방향 그래프에서 서로 다른 모든 정점들 사이에 경로가 존재함   
// 무방향 그래프에서 한 정점의 차수 (degree)   
// - 정점에 부수된 간선의 개수   
// 방향 그래프 정점의 차수는 진입 차수와 진출 차수로 나뉨   
// - 진입 차수 (indegree)   
// -- 다른 정점에서 해당 정점을 향하는 간선의 개수   
// - 진출 차수 (outdegree)   
// -- 해당 정점으로부터 다른 정점으로 향하는 간선의 개수   
// 트리는 그래프의 특수한 형태로 봄   
// 무방향 그래프에서 모든 정점이 서로 연결되어 있으면서 사이클이 존재하지 않는 그래프를 트리라고 함   
- If two vertices are directly connected by an edge, two vertices are said to be adjacent, and the edge is incidental to the two vertices   
- Adjacent   
  - Relationship between vertices   
- Incidental   
  - The relationship between a vertex and an edge   
- path   
  - Indicates a sequential list of vertices connected by an edge   
- the length of the path   
  - Number of edges included in the path   
- simple path   
  - Paths where all the vertices on the path are different   
- cycle   
  - Paths with the same starting and ending vertices among paths with three or more vertices   
- simple cycle   
  - Cycle where all vertices are different except for the starting and ending vertices   
- 'The two vertices were connected to each other'   
  - Path exists between two vertices   
- 'The graphs were interconnected'   
  - Path exists between all different vertices in a directionless graph   
- degree (Degree of a vertex in a undirected graph)   
  - Number of edges incidental to the vertex   
- The order of the directional graph vertices is divided into indegree and outdegree   
  - indegree   
    - Number of edges from another vertex to that vertex   
  - outdegree   
    - Number of edges from that vertex to another vertex   
- A tree is a special form of a graph   
- In an undirected graph, a graph in which all vertices are interconnected and no cycles exist is called a tree   
   
<br />
### Expression of Graph   
// 그래프의 표현   
   
// 그래프를 컴퓨터 프로그래밍 언어로 구현하기 위해서는 인접 행렬 (adjacency matrix) 이나 인접 리스트 (adjacency list) 를 이용하여 표현   
// 인접 행렬을 이용하여 n개의 정점을 가진 그래프를 표현하기 위해서는 n x n 크기의 2차원 배열을 이용함   
- To implement a graph in a computer programming language, use an adjacency matrix or adjacency list to express it   
- To represent a graph with n vertices using an adjacency matrix, a two-dimensional array of n x n size is used   
   
// 인접행렬 A[i][j]에 값이 존재하면 그래프의 정점 V<sub>i</sub>에서 정점 V<sub>j</sub> 사이에 간선이 존재함을 의미하고, A[i][j]의 값은 1로 정함   
- The presence of a value in the adjacent matrix A[i][j] implies that there is an edge between vertices V<sub>i</sub> and V<sub>j</sub> in the graph, with the value of A[i][j] set to 1   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/dataStructureGraphExpression.png)
   
<br />
### Navigating Graphs   
// 그래프의 탐색   
   
// 그래프의 모든 정점을 체계적으로 방문하는 것   
// 깊이 우선 탐색 (depth first search) 과 너비 우선 탐색 (breadth first search) 이 있음   
- To systematically visit all the vertices of a graph   
- There is depth first search and breadth first search   
   
#### Depth First Search   
// 깊이 우선 탐색   
   
// 최근의 방문하지 않은 인접한 하나의 정점을 우선적으로 방문함   
// 최종 방문 순서는 구현 방법에 따라 달라질 수 있음   
- Preferred visit to one adjacent vertex that was not recently visited   
- Final visit order may vary depending on how you implement it   
   
#### Breadth First Search   
// 너비 우선 탐색   
   
// 최근의 방문하지 않은 인접한 모든 정점을 모두 방문함   
// 최종 방문 순서는 구현 방법에 따라 달라질 수 있음   
- Visits all adjacent vertices that have not been visited recently   
- Final visit order may vary depending on how you implement it   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
