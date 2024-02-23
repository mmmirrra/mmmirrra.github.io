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
- Type of memory space to be allocated : 데이터 영역, 힙 영역, 스택 영역   
   
|Type|Description|
|:---:|:---|
|// 데이터 영역<br />|// 전역변수와 정적변수 static variable 가 저장되는 영역<br />// 프로그램이 시작함과 동시에 할당되고, 프로그램이 종료되면 소멸함<br />|
|// 힙 영역<br />|// 프로그래머의 필요에 의해 할당/소멸이 이루어지는 영역<br />// 실행이 되면서 그 크기가 늘어나고 줄어들어 자유 기억공간이라 불리며, 메모리 동적 할당에 사용되는 영역<br />|
|// 스택 영역<br />|// 지역변수와 매개변수가 저장되는 영역<br />// 함수 호출이 완료되면 사라짐<br />|


<br />
### 기억공간의 확보방법
// 메모리 정적 할당   
// 메모리 동적 할당
- Static Allocation   
- Dynamic Allocation   

<br />
### 메모리 정적 할당
// 설명 : 기억공간의 데이터 영역과 스택 영역 이용. 변수 선언이나 배열 선언과 같이 프로그램을 작성하는 단계에서 필요한 기억공간의 크기를 결정. 변수 선언과 같이 할당시켜줘야 할 기억공간의 한계 크기를 명확히 알고 있는 경우 사용. 프로그램이 시작될 때 미리 기억공간의 크기를 고정하여 할당함.    
// 장점 : 프로그램에서 사용하게 될 변수의 기억공간의 크기를 명확히 알고 있다면, 메모리 정적 할당은 쉽게 기억공간을 사용할 수 있고 에러의 발생 확률을 줄일 수 있음
// 단점 : 사용하게 될 기억공간의 크기를 정확히 알지 못하거나, 사용되는 자료의 크기가 각각 차이가 심하다면, 기억공간의 낭비를 가져오게 되는 문제가 있음
- 
- 
- 

<br />
### 메모리 동적 할당
// 설명 : 기억공간의 힙 영역 이용. 프로그램 실행 중에 입력되는 자료에 맞게 기억공간의 크기를 결정 
// 장점 : 많은 자료를 처리하는 배열의 크기를 실행 시간에 정의해야 하는 경우에 특히 유용함. 프로그램 실행 시 기억공간의 크기를 지정할 수 있고, 재조정이 가능
// 단점 : 시간이 지체되는 단점이 있음
- 
- 
-  

<br />
#### 메모리 동적 할당 순서
// 1. 기억공간을 동적으로 할당 받을 변수를 포인터를 이용하여 선언
// 2. malloc() 함수 등을 이용하여 기억공간을 동적으로 할당
// 3. 기억공간의 사용이 끝나면 free() 함수를 이용하여 기억공간을 해제
- 1. 
- 2. 
- 3. 
   
<br />
#### 메모리 동적 할당 함수의 종류
   
|Function|Type of use|Description|
|:---|:---|:---|
|`malloc()`|void * malloc(size_t number_of_bytes);<br />Example : `void * malloc(sizeof(int());`|// number_of_bytes에서 주어지는 크기만큼 기억공간을 동적으로 할당<br />// 인자로 할당받고자하는 기억공간의 크기를 byte 단위로 전달<br />// 힙 영역에 그 크기만큼 기억공간을 할당하고, 할당한 기억공간의 첫번째 주소를 반환<br />// void*로 명시하여 어떤 형으로든 형 변환이 가능<br />// 초기화 안됨. 기억공간의 초기화를 위해서는 malloc() 대신 memset() 사용해야 함<br />|
|`calloc()`|void * calloc(int n, int size);<br />Example : `void * calloc(n, sizeof(int));`|// 주어진 size의 크기를 가지는 기억공간 n개를 할당 받음<br />// 힙 영역에 기억공간을 할당<br />// malloc() 함수와는 사용하는 형태와 할당된 기억공간을 0으로 초기화 한다는 점이 다름<br /><br /><br />|
|`realloc()`|void * realloc(void *p, int size);<br />Example : `a = (int *)realloc(a, 10*sizeof(int));`|// 포인터 p가 가리키고 이ㅆ는 기억공간의 크기를 지정된 size의 크기로 변경<br />// 이미 할당받은 기억공간의 크기를 변경해야 할 필요가 있을 경우 사용|
|`free()`|void free(void *p);<br />Example : `free(pt);`|// 동적으로 할당된 기억공간을 해제할 때 사용<br />// 할당된 기억공간을 해제하지 않으면 기억공간의 부족현상이 발생함. 따라서 명시적인 반납이 필요<br /><br />|
  
<br />
#### 기억공간 관리 함수의 종류
// 기억공간 관리함수를 위한 헤더파일 인크루드 : #include <mem.h>

|Function|Type of use|Description|
|:---|:---|:---|
|`memcmp()`|int memcmp(void *s1, void *s2, size_t n);<br />Example : `stat = memcmp(s1, s2, 3);`|// s1과 s2가 가리키는 기억공간의 내용을 n byte만큼 비교<br />// 기억공간에 들어있는 자료를 주어지는 크기만큼 비교하여, 같은지 여부를 알 수 있게 해주는 함수<br /><br /><br />|
|`memcpy()`|void * memcpy(void *dest, const void *src, size_t n);<br />Example : `stat = (char *)memcpy(dest, str, strlen(src));`|// src에서 n byte만큼 dest에 복사<br />// 기억공간의 자료를 다른 기억공간 영역으로 복사하기 위한 함수<br /><br />|
|`memset()`|void * memset(void *s, int c, size_t n);<br />Example : `memset(s, '*', strlen(s));`|// 포인터 s가 가리키는 곳을 c값으로 n byte만큼 채움<br />// 기억공간의 자료를 지정한 문자로 채우는 함수<br />// 할당된 기억공간의 초기화나 내용 삭제를 위해 주로 사용<br /><br />|
