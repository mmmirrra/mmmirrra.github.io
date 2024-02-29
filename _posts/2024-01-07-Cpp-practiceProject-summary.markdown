---
layout: post
title:  "C++: practice project summary"
date:   2024-01-07 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - .cpp   
#### main() sourceFile   
`FirstStep.cpp` : C++ practice project main function   
   
#### etc sourceFile   
// 스택 공간 확인 예제   
`CharStack.cpp` : Example of verifying stack space   
// 복소수 계산 예제 - 정수   
`Complex1.cpp` : Example of calculating complex number - Integer   
// 복소수 계산 예제 - 실수   
`Complex2.cpp` : Example of calculating complex number - Real Number   
// 헤더파일 외부에 정의하는 함수 예제   
`Counter.cpp` : Example of a function defined outside of a header file   
// 사용자 정의 객체 오류 처리 예제   
`IntArray1.cpp` : Example of error handling of a custom object   
// 생성자, 소멸자 동작 예제   
`NamedObj.cpp` : Example of how Constructor and Destructor work   
// ++ 연산자 전위 표기, 후위 표기 예제   
`Pencils.cpp` : Example of prefix and postfix for ++ operator   
// 메모리 동적 할당 예제   
`Person.cpp` : Example of dynamically allocating memory   
   
<br />
   
### headerFile list - .h   
// 추상 클래스 - 객체를 만들 수 없음   
`AClass.h` : Abstract Class - Unable to create object   
// 권한에 따른 멤버 사용 범위 예제   
`BaseC.h` : Example of a Member's scope of use by permission   
// 기초 클래스의 소멸자를 가상함수로 만드는 예제   
`BaseClass.h` : Example of creating a Virtual Function of a Destructor in a Base Class   
// 템플릿 생성 시 매개변수로 자료형과 정수를 받는 예제   
`Buffer.h` : Example of receiving data types and integer as parameters when creating a template   
// 상세 클래스 - 객체를 만들 수 있음   
`CClass.h` : Detail Class - Able to create object   
// 스택 공간 확인 예제   
`CharStack.h` : Example of verifying stack space   
// 상세 클래스 - 원을 그리는 원 클래스 예제   
`Circle.h` : Detail Class - Example of a Circle Class drawing a Circle   
// 복소수 계산 예제 - 정수   
`Complex1.h` : Example of calculating complex number - Integer   
// 복소수 계산 예제 - 실수   
`Complex2.h` : Example of calculating complex number - Real Number   
// 헤더파일 외부에 정의하는 함수 예제 - 클릭 시 숫자가 올라가는 숫자 누적 계산기   
`Counter.h` : Example of a function defined outside of a header file - a numeric accumulator that increases the number when clicked   
// 카운터가 최대값에 도달했을 때 0으로 리셋되는 숫자 누적 계산기   
`CounterM.h` : a numeric accumulator that resets to zero when the counter reaches its maximum value   
// 가상함수로 정의된 소멸자를 가진 기초 클래스를 상속받는 상세 클래스 예제   
`DrvClass.h` : Example of a detail Class that inherits a Base Class with an Destructor defined as a Virtual Function   
// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - public 상속   
`Drvd1.h` : Example of determining the range of availability based on permission settings during Class inheritance - public inheritance   
// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - protected 상속   
`Drvd2.h` : Example of determining the range of availability based on permission settings during Class inheritance - protected inheritance   
// 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - private 상속   
`Drvd3.h` : Example of determining the range of availability based on permission settings during Class inheritance - private inheritance   
// 추상 클래스 - 도형을 그릴 수 있는 클래스에 대한 추상 클래스   
`Figure.h` : Abstract Class - Abstract Class for Class that can draw shapes   
// 추상 클래스 - 도형의 그래픽 속성을 지정할 수 있는 클래스에 대한 추상 클래스   
`GrAttrib.h` : Abstract Class - Abstract Class for Class that specify graphic properties of a shapes   
// 함수객체를 포함한 클래스 - 함수처럼 사용될 수 있는 객체   
`Greater.h` : Class with function objects - Object that can be used as function   
// 사용자 정의 객체 오류 처리 예제 - 오류가 발생한 첨자 리턴   
`IntArray1.h` : Example of error handling of a custom object - Returns a subscript with an error   
// 사용자 정의 객체 오류 처리 예제 - exception() 사용   
`IntArray2.h` : Example of error handling of a custom object - Use exception()   
// 전위 표기 ++ 연산자 다중정의   
`IntClass1.h` : Prefix ++ operator multiple definitions   
// 후위 표기 ++ 연산자 다중정의   
`IntClass2.h` : Postfix ++ operator multiple definitions   
// 두 값을 비교하여 첫번째 값이 두번째 값보다 작은 경우 true를 리턴하는 템플릿 클래스 - 오름차순 정렬 함수 구현 시 사용 가능   
`Less.h` : Template Class that compares two values and returns true if the first value is less than the second value - Available when implementing an ascending sort function   
// 클래스 다중상속을 위한 클래스   
`MIEmployee.h` : Class for Multiple Inheritance   
// 클래스를 다중상속 받는 클래스 - MIEmployee.h 와 MIStudent.h 파일의 클래스를 다중상속   
`MIParttime.h` : Class that receive multiple inheritances - Multiple inheritance of Class in the MIEployee.h and MISstudent.h files   
// 클래스 다중상속을 위한 클래스   
`MIStudent.h` : Class for Multiple Inheritance   
// 문자열을 정수처럼 계산할 수 있도록 연산자를 다중정의하는 예제   
`MyString.h` : Example of multiple definitions of an operator so that a string can be computed like an integer   
// 생성자, 소멸자 동작 예제   
`NamedObj.h` : Example of how Constructor and Destructor work   
// noexcept 선언 예제 - 예외를 일으키지 않는다는 선언   
`noExceptT.h` : Example of a noexcept declaration - a declaration not to cause exceptions   
// ++연산자 전위 표기, 후위 표기 예제 - 연필 묶음과 낱개의 개수 계산   
`Pencils.h` : Example of prefix and postfix for ++ operator - Calculate the number of pencil bundles and individuals   
// 메모리 동적 할당 예제 - 이름과 주소를 가진 객체 생성자에 동적 할당 적용   
`Person.h` : Example of dynamically allocating memory - Dynamic assignment of memory to the Constructors of objects with names and addresses   
// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person1.h` : Examples of Base Class and Derived Class - Base Class - Without Virtual Function   
// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person2.h` : Examples of Base Class and Derived Class - Base Class - Without Virtual Function   
// 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 포함   
`Person3.h` : Examples of Base Class and Derived Class - Base Class - Include Virtual Function   
// 데이터 저장공간에 따른 첨자 접근 가능여부를 확인하는 예제   
`SafeIntArray.h` : Example of verifying that subscripts are accessible by data storage space   
// 버블 정렬 알고리즘 함수 템플릿   
`softFT.h` : Bubble Sort Algorithm Function Template   
// 클래스 템플릿 예제 - 스택이라는 자료형을 조작할 수 있는 함수 정의   
`StackT.h` : Example of a Class template - Definition of functions that can manipulate stack data type   
// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함   
`Student1.h` : Examples of Base Class and Derived Class - Derived Class - Without Virtual Function   
// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함 - Person2 생성자를 통해 데이터멤버 초기화   
`Student2.h` : Examples of Base Class and Derived Class - Derived Class - Without Virtual Function - Initialize data Members through the Constructor of Person2   
// 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 포함   
`Student3.h` : Examples of Base Class and Derived Class - Derived Class - Include Virtual Function   
// 함수 템플릿 예제 - 값을 서로 교환하는 함수   
`SwapFunc.h` : Example of a Function Template - a function that exchanges values   
// 상세 클래스 - 삼각형을 그리는 삼각형 클래스 예제   
`Triangle.h` : Detail Class - Example of a Triangle Class drawing a Triangle   
// Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Employee2   
`VBEmployee.h` : Employee2 Class inherits Person5 Class as a Virtual Base Class   
// Student5와 Employee2를 상속받는 클래스 - Parttime2 클래스   
`VBParttime.h` : Class that inherit Student5 Class and Employee2 Class - Parttime2 Class   
// 가상 기초 클래스 - Person5 클래스   
`VBPerson.h` : Virtual Base Class - Person5 Class   
// Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Student5   
`VBStudent.h` : Student5 Class inherits Person5 Class as a Virtual Base Class   
// 다중정의에 대한 개념 이해를 위한 예제   
`VecF.h` : Example for conceptual understanding of multiple definitions   
   
<br />
<cite>출처: 한국방송통신대학교 컴퓨터과학과</cite>
