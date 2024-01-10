---
layout: post
title:  "C++: practice project summary"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - .cpp   
main() sourceFile   
`FirstStep.cpp` : C++ practice project main function   
   
etc sourceFile   
`CharStack.cpp` : // 스택 공간 확인 예제   
`Complex1.cpp` : // 복소수 정수 계산 예제   
`Complex2.cpp` : // 복소수 실수 계산 예제   
`Counter.cpp` : // 헤더파일 외부에 정의하는 함수 예제   
`IntArray1.cpp` : // 사용자 정의 객체 오류 처리 예제   
`NamedObj.cpp` : // 생성자, 소멸자 동작 예제   
`Pencils.cpp` : // ++ 연산자 전위 표기, 후위 표기 예제   
`Person.cpp` : // 메모리 동적 할당 예제   
   
<br />
   
### headerFile list - .h   
`AClass.h` : // 추상 클래스 - 객체를 만들 수 없음   
`BaseC.h` : // 권한에 따른 멤버 사용 범위 예제   
`BaseClass.h` : // 기초클래스의 소멸자를 가상함수로 만드는 예제   
`Buffer.h` : // 템플릿 생성 시 매개변수로 자료형과 정수를 받는 예제   
`CClass.h` : // 상세 클래스 - 객체를 만들 수 있음   
`CharStack.h` : // 스택 공간 확인 예제   
`Circle.h` : // 상세 클래스 - 원을 그리는 원 클래스 예제   
`Complex1.h` : // 복소수 정수 계산 예제   
`Complex2.h` : // 복소수 실수 계산 예제   
`Counter.h` : // 헤더파일 외부에 정의하는 함수 예제 - 클릭 시 숫자가 올라가는 숫자 누적 계산기   
`CounterM.h` : // 카운터가 최대값에 도달했을 때 0으로 리셋되는 숫자 누적 계산기   
`DrvClass.h` : // 가상함수로 정의된 소멸가를 가진 기초클래스를 상속받는 상세 클래스 예제   
`Drvd1.h` : // 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - public 상속   
`Drvd2.h` : // 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - protected 상속   
`Drvd3.h` : // 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - private 상속   
`Figure.h` : // 추상 클래스 - 도형을 그릴 수 있는 클래스에 대한 추상 클래스   
`GrAttrib.h` : // 추상 클래스 - 도형의 그래픽 속성을 지정할 수 있는 클래스에 대한 추상 클래스   
`Greater.h` : // 함수객체를 포함한 클래스 - 함수처럼 사용될 수 있는 객체   
`IntArray1.h` : // 사용자 정의 객체 오류 처리 예제 - 오류가 발생한 첨자 리턴   
`IntArray2.h` : // 사용자 정의 객체 오류 처리 예제 - exception() 사용   
`IntClass1.h` : // 전위 표기 ++ 연산자 다중정의   
`IntClass2.h` : // 후위 표기 ++ 연산자 다중정의   
`Less.h` : // 두 값을 비교하여 첫번째 값이 두번째 값보다 작은 경우 true를 리턴하는 템플릿 클래스 - 오름차순 정렬 함수 구현 시 사용 가능   
`MIEmployee.h` : // 클래스 다중상속을 위한 클래스   
`MIParttime.h` : // 클래스를 다중상속 받는 클래스 - MIEmployee.h 와 MIStudent.h 파일의 클래스를 다상속   
`MIStudent.h` : // 클래스 다중상속을 위한 클래스   
`MyString.h` : // 문자열을 정수처럼 계산할 수 있도록 연산자를 다중정의하는 예제   
`NamedObj.h` : // 생성자, 소멸자 동작 예제   
`noExceptT.h` : // noexcept 선언 예제 - 예외를 일으키지 않는다는 선언   
`Pencils.h` : // ++연산자 전위 표기, 후위 표기 예제 - 연필 묶음과 낱개의 개수 계산   
`Person.h` : // 메모리 동적 할당 예제 - 이름과 주소를 가진 객체 생성자에 동적 할당 적용   
`Person1.h` : // 기초클래스와 파생클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person2.h` : // 기초클래스와 파생클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person3.h` : // 기초클래스와 파생클래스 예제 - 기초 클래스 - 가상함수 포함   
`SafeIntArray.h` : // 데이터 저장공간에 따른 첨자 접근 가능여부를 확인하는 예제   
`softFT.h` : // 버블 정렬 알고리즘 bubble sort algorithm 함수 템플릿   
`StackT.h` : // 클래스 템플릿 예제 - 스택이라는 자료형을 조작할 수 있는 함수 정의   
`Student1.h` : // 기초클래스와 파생클래스 예제 - 파생 클래스 - 가상함수 미포함   
`Student2.h` : // 기초클래스와 파생클래스 예제 - 파생 클래스 - 가상함수 미포함 - Person2 생성자를 통해 데이터멤버 초기화   
`Student3.h` : // 기초클래스와 파생클래스 예제 - 파생 클래스 - 가상함수 포함   
`SwapFunc.h` : // 함수 템플릿 에제 - 값을 서로 교환하는 함수   
`Triangle.h` : // 상세 클래스 - 삼각형을 그리는 삼각형 클래스 예제   
`VBEmployee.h` : // Person5를 가상 기초 클래스로 상속받는 클래스 Employee2   
`VBParttime.h` : // Student5와 Employee2를 상속받는 클래스 Parttime2   
`VBPerson.h` : // 가상 기초 클래스 Person5  
`VBStudent.h` : // Person5을 가상 기초 클래스로 상속받는 클래스 Student5   
`VecF.h` : // 다중정의에 대한 개념 이해를 위한 예제   
   