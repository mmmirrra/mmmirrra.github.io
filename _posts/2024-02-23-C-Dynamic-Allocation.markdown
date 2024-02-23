---
layout: post
title:  "C: Dynamic Allocation"
date:   2024-02-23 09:00:00 +0900
categories: [C]
---

### Memory space   
// 프로그램 실행을 위해 기억공간 필요   
// 기억공간은 운영체제에서 할당   
// 할당되는 기억공간 영역의 종류 : 데이터 영역, 힙 영역, 스택 영역   
- Memory space required for program execution   
- Memory is assigned by the operating system   
- Type of memory space to be allocated : Data, Heap, Stack   
   
|Type|Description|
|:---:|:---|
|// 데이터 영역<br />Data|// 메모리 정적 할당으로 확보<br />// 전역변수와 정적변수가 저장되는 영역<br />// 프로그램이 시작함과 동시에 할당되고, 프로그램이 종료되면 소멸함<br />- Use as a Static Allocation of memory<br />- The area where the global and static variable are stored<br />- It is assigned as soon as the program starts, and disappears when the program ends|
|// 힙 영역<br />Heap|// 메모리 동적 할당으로 확보<br />// 프로그래머의 필요에 의해 할당/소멸이 이루어지는 영역<br />// 실행이 되면서 그 크기가 늘어나고 줄어들어 자유 기억공간이라 불리며, 메모리 동적 할당에 사용되는 영역<br />- Use as a Dynamic Allocation of memory<br />- Areas where allocation/extinction is made by programmer's needs<br />- An area called free memory space because it increases and decreases in size as it is executed, and is used for Dynamic Memory Allocation|
|// 스택 영역<br />Stack|// 메모리 정적 할당으로 확보<br />// 지역변수와 매개변수가 저장되는 영역<br />// 함수가 호출되면 할당되고, 함수의 호출이 완료되면 사라짐<br />- Use as a Static Allocation of memory<br />- The area where the local variable and parameter are stored<br />- When a function is called, it is assigned, and disappears when the function is complete|
   
<br />
### How to secure storage space   
// 기억공간의 확보방법 : 메모리 정적 할당, 메모리 동적 할당   
- Static Allocation   
- Dynamic Allocation   
   
<br />
### Static Allocation   
// 설명 : 기억공간의 데이터 영역과 스택 영역 이용. 변수 선언이나 배열 선언과 같이 프로그램을 작성하는 단계에서 필요한 기억공간의 크기를 결정. 변수 선언과 같이 할당시켜줘야 할 기억공간의 한계 크기를 명확히 알고 있는 경우 사용. 프로그램이 시작될 때 미리 기억공간의 크기를 고정하여 할당함    
// 장점 : 프로그램에서 사용하게 될 변수의 기억공간의 크기를 명확히 알고 있다면, 메모리 정적 할당은 쉽게 기억공간을 사용할 수 있고 에러의 발생 확률을 줄일 수 있음   
// 단점 : 사용하게 될 기억공간의 크기를 정확히 알지 못하거나, 사용되는 자료의 크기가 각각 차이가 심하다면, 기억공간의 낭비를 가져오게 되는 문제가 있음   
- Description : Using the data and stack of the memory space. Determines the size of memory space required in the step of writing a program, such as a variable or an array declaration. Use when you clearly know the limit size of the memory space to be allocated, such as a variable declaration. When the program starts, the memory space is fixed and assigned in advance   
- Strengths : If you clearly know the size of the memory space of the variable that will be used by the program, Static Allocation of memory can easily use memory space and reduce the probability of error   
- Weaknesses : If you don't know exactly the size of the memory space to be used, or if the size of the data used varies greatly, there is a problem that leads to waste of memory space   
   
<br />
### Dynamic Allocation   
// 설명 : 기억공간의 힙 영역 이용. 프로그램 실행 중에 입력되는 자료에 맞게 기억공간의 크기를 결정   
// 장점 : 많은 자료를 처리하는 배열의 크기를 실행 시간에 정의해야 하는 경우에 특히 유용함. 프로그램 실행 시 기억공간의 크기를 지정할 수 있고, 재조정이 가능   
// 단점 : 시간이 지체되는 단점이 있음   
- Description : Using the heap of memory space. Determine the size of the storage space to match the data input during program execution   
- Strengths : Especially useful when you need to define the size of an array that processes a lot of data at run time. You can specify the size of the memory space when the program runs, and it can be readjusted   
- Weaknesses : There is a disadvantage of time delay   
   
<br />
#### Order of Dynamic Allocation of memory   
// 메모리 동적 할당 순서   
// 1. 기억공간을 동적으로 할당 받을 변수를 포인터를 이용하여 선언   
// 2. malloc() 함수 등을 이용하여 기억공간을 동적으로 할당   
// 3. 기억공간의 사용이 끝나면 free() 함수를 이용하여 기억공간을 해제   
-  1. Declare variables that will dynamically allocate storage space using pointers   
-  2. Dynamic Allocation of memory space using malloc() function, etc   
-  3. When the memory space is used, release the memory space using the free() function   
   
<br />
#### Types of Memory Dynamic Allocation function   
// 메모리 동적 할당 함수의 종류   
   
|Function<br /><br />Type of use|Example|Description|
|:---|:---|:---|
|`malloc()`<br /><br />void * malloc(size_t number_of_bytes);|`a = (int*)malloc( sizeof(int() );`|// number_of_bytes에서 주어지는 크기만큼 기억공간을 동적으로 할당<br />// 인자로 할당받고자하는 기억공간의 크기를 byte 단위로 전달<br />// 힙 영역에 그 크기만큼 기억공간을 할당하고, 할당한 기억공간의 첫번째 주소를 반환<br />// void*로 명시하여 어떤 형으로든 형 변환이 가능<br />// 초기화 안됨. 기억공간의 초기화를 위해서는 memset() 함수를 사용해야 함<br />- Dynamic Allocation of storage space by size given by number_of_bytes<br />- Deliver the size of the memory space you want to be allocated in bytes<br />- Assign storage space to the Heap area by its size and return the first address of the allocated storage space<br />- Can be converted to any type by specifying it as void*<br />- Not initialized. The memset() function must be used for the initialization of the memory space|
|`calloc()`<br /><br />void * calloc(int n, int size);|`a = (int*)calloc(n, sizeof(int));`|// 주어진 size의 크기를 가지는 기억공간 n개를 할당 받음<br />// 힙 영역에 기억공간을 할당<br />// 할당된 기억공간을 0으로 초기화함<br />// malloc() 함수와는 사용하는 형태와 할당된 기억공간을 0으로 초기화 한다는 점이 다름<br />- Allocated n storage spaces with a given size of 'size'<br />- Assign storage space to the heap area<br />- Initialize allocated memory space to zero<br />- Calloc() and malloc() have different forms of use, and it is different to initialize the allocated memory space to zero|
|`realloc()`<br /><br />void * realloc(void *p, int size);|`a = (int*)realloc(a, 10*sizeof(int));`|// 포인터 p가 가리키고 있는 기억공간의 크기를 지정된 size의 크기로 변경<br />// 이미 할당받은 기억공간의 크기를 변경해야 할 필요가 있을 경우 사용<br />- Change the size of the memory space that Pointer p points to to the size of the specified size<br />- Use if you need to change the size of your already allocated storage space|
|`free()`<br /><br />void free(void *p);|`free(pt);`|// 동적으로 할당된 기억공간을 해제할 때 사용<br />// 힙 영역에 할당된 공간은 free() 함수로 해제하지 않으면 프로그램이 종료될 때까지 유지됨<br />// 할당된 기억공간을 해제하지 않으면 기억공간의 부족현상이 발생함. 따라서 명시적인 반납이 필요<br />- Used to unlock dynamically allocated memory space<br />- If the space assigned to the heap area is not released by the free() function, it will remain until the program ends<br />- If the allocated memory space is not released, a lack of memory space will occur. Therefore, explicit return is required|
   
<br />
### Types of storage management function   
// 기억공간 관리 함수의 종류   
// 기억공간 관리함수를 위한 헤더파일 인크루드 : '#include <mem.h>'   
Include header files for memory space management function : `#include <mem.h>`   
   
|Function<br /><br />Type of use|Example|Description|
|:---|:---|:---|
|`memcmp()`<br /><br />int memcmp(void *s1, void *s2, size_t n);|`stat = memcmp(s1, s2, 3);`<br /><br />// s1과 s2의 내용을 3byte만큼 비교하여 s1>s2이면 양수, s1<s2이면 음수, s1=s2이면 0을 반환<br />Compare the contents of s1 and s2 by 3 bytes and return positive if s1>s2, negative if s1<s2, and 0 if s1=s2|// s1과 s2가 가리키는 기억공간의 내용을 n byte만큼 비교<br />// 기억공간에 들어있는 자료를 주어지는 크기만큼 비교하여, 같은지 여부를 알 수 있게 해주는 함수<br />- Compare the contents of the memory space indicated by s1 and s2 by n bytes<br />- A function that compares the data in a memory space by a given size and tells if it is the same|
|`memcpy()`<br /><br />void * memcpy(void *dest, const void *src, size_t n);|`stat = (char*)memcpy(dest, str, strlen(src));`<br /><br />// src의 첫 부분에서부터 문자열의 길이(strlen())만큼의 자료를 dest에 복사(덮어쓰기)<br />Copy (overwrite) data from the first part of src to dest as long as string (stren())|// src에서 n byte만큼 dest에 복사<br />// 기억공간의 자료를 다른 기억공간 영역으로 복사하기 위한 함수<br />- Copy to dest by n bytes from src<br />- A function for copying data from a memory space to another memory area|
|`memset()`<br /><br />void * memset(void *s, int c, size_t n);|`memset(s, '*', strlen(s));`<br /><br />// 배열 s의 데이터를 '*'로 문자열의 길이만큼 (strlen()) 채움<br />Fill data in array 's' with '*' as long as string|// 포인터 s가 가리키는 곳을 c값으로 n byte만큼 채움<br />// 기억공간의 자료를 지정한 문자로 채우는 함수<br />// 할당된 기억공간의 초기화나 내용 삭제를 위해 주로 사용<br />- Fill in the point where pointer s points by n bytes with the value c<br />- Functions that populate the data in the storage space with the specified characters<br />- Mainly used for initialization or content deletion of allocated memory space|
