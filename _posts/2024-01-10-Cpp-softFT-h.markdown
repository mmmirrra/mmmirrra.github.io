---
layout: post
title:  "C++: softFT.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - softFT.h   
`softFT.h` : bubble sort algorithm function template // 버블 정렬 알고리즘 bubble sort algorithm 함수 템플릿   
   
```cpp
#pragma once
#include "SwapFunc.h"

template <typename T> void sortFT(T arr[], int size) {		// 버블 정렬 알고리즘 bubble sort algorithm 함수 템플릿 - T라는 매개변수로 전달되는 자료형에 대한 데이터 저장 배열을 받음. 받은 데이터 저장 배열의 자료형은 T임. 
	bool doAgain = true;		// for 최초 실행을 위해 초기값을 true로 지정
	for (int i = 1; doAgain; i++) {		// doAgain 이 true 이면 반복 실행
		doAgain = false;		// doAgain값을 false로 변경하고 시작 - 두번째 for에서 true로 변경되지 않으면 첫번째 for 종료됨
		for (int j = 0; j < size - i; j++)		// size 만큼 반복 실행 - 반복 시마다 제일 마지막 값이 되는 값을 제외시킬 수 있도록 size - i 지정
			if (arr[j] > arr[j + 1])		// 두 값을 비교하여 앞의 값이 크면 swapFT 함수로 순서 변경 - 오름차순 정렬 - sortFT 함수를 사용하려는 클래스에서는 대소 비교를 할 수 있는 관계 연산자의 다중정의가 정의되어 있어야 함
				swapFT(arr[j], arr[j + 1]), doAgain = true;		// 변경된 값이 있으면 doAgain 을 true로 변경하여 첫번째 for 반복 실행되도록 함
	}
};
```
