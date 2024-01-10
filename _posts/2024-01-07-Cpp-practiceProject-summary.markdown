---
layout: post
title:  "C++: practice project summary"
date:   2024-01-07 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - .cpp   
main() sourceFile   
`FirstStep.cpp` : C++ practice project main function   
   
etc sourceFile   
`CharStack.cpp` : example of verifying stack space // 스택 공간 확인 예제   
`Complex1.cpp` : example of calculating complex number - integer // 복소수 계산 예제 - 정수   
`Complex2.cpp` : example of calculating complex number - real numbers // 복소수 계산 예제 - 실수   
`Counter.cpp` : example of a function defined outside of a header file // 헤더파일 외부에 정의하는 함수 예제   
`IntArray1.cpp` : example of error handling of a custom object // 사용자 정의 객체 오류 처리 예제   
`NamedObj.cpp` : example of how constructor and destructor work // 생성자, 소멸자 동작 예제   
`Pencils.cpp` : example of prefix and postfix for ++ operator // ++ 연산자 전위 표기, 후위 표기 예제   
`Person.cpp` : example of dynamically allocating memory // 메모리 동적 할당 예제   
   
<br />
   
### headerFile list - .h   
`AClass.h` : abstract class - unable to create object // 추상 클래스 - 객체를 만들 수 없음   
`BaseC.h` : example of a member's scope of use by permission // 권한에 따른 멤버 사용 범위 예제   
`BaseClass.h` : example of creating a virtual function of a destructor in a base class // 기초 클래스의 소멸자를 가상함수로 만드는 예제   
`Buffer.h` : example of receiving data types and integer as parameters when creating a template // 템플릿 생성 시 매개변수로 자료형과 정수를 받는 예제   
`CClass.h` : detail class - able to create object // 상세 클래스 - 객체를 만들 수 있음   
`CharStack.h` : example of verifying stack space // 스택 공간 확인 예제   
`Circle.h` : detail class - example of a circle class drawing a circle // 상세 클래스 - 원을 그리는 원 클래스 예제   
`Complex1.h` : example of calculating complex number - integer // 복소수 계산 예제 - 정수   
`Complex2.h` : example of calculating complex number - real numbers // 복소수 계산 예제 - 실수   
`Counter.h` : example of a function defined outside of a header file - a numeric accumulator that increases the number when clicked // 헤더파일 외부에 정의하는 함수 예제 - 클릭 시 숫자가 올라가는 숫자 누적 계산기   
`CounterM.h` : a numeric accumulator that resets to zero when the counter reaches its maximum value // 카운터가 최대값에 도달했을 때 0으로 리셋되는 숫자 누적 계산기   
`DrvClass.h` : example of a detail class that inherits a base class with an destructor defined as a virtual function // 가상함수로 정의된 소멸자를 가진 기초 클래스를 상속받는 상세 클래스 예제   
`Drvd1.h` : example of determining the range of availability based on permission settings during class inheritance - public inheritance // 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - public 상속   
`Drvd2.h` : example of determining the range of availability based on permission settings during class inheritance - protected inheritance // 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - protected 상속   
`Drvd3.h` : example of determining the range of availability based on permission settings during class inheritance - private inheritance // 클래스 상속 시 권한 설정에 따른 사용가능범위 확인하는 예제 - private 상속   
`Figure.h` : abstract class - abstract class for class that can draw shapes // 추상 클래스 - 도형을 그릴 수 있는 클래스에 대한 추상 클래스   
`GrAttrib.h` : abstract class - abstract class for class that specify graphic properties of a shapes // 추상 클래스 - 도형의 그래픽 속성을 지정할 수 있는 클래스에 대한 추상 클래스   
`Greater.h` : class with function objects - object that can be used as function // 함수객체를 포함한 클래스 - 함수처럼 사용될 수 있는 객체   
`IntArray1.h` : example of error handling of a custom object - returns a subscript with an error // 사용자 정의 객체 오류 처리 예제 - 오류가 발생한 첨자 리턴   
`IntArray2.h` : example of error handling of a custom object - use exception() // 사용자 정의 객체 오류 처리 예제 - exception() 사용   
`IntClass1.h` : prefix ++ operator multiple definitions // 전위 표기 ++ 연산자 다중정의   
`IntClass2.h` : postfix ++ operator multiple definitions // 후위 표기 ++ 연산자 다중정의   
`Less.h` : template class that compares two values and returns true if the first value is less than the second value - available when implementing an ascending sort function // 두 값을 비교하여 첫번째 값이 두번째 값보다 작은 경우 true를 리턴하는 템플릿 클래스 - 오름차순 정렬 함수 구현 시 사용 가능   
`MIEmployee.h` : class for Multiple Inheritance // 클래스 다중상속을 위한 클래스   
`MIParttime.h` : class that receive multiple inheritances - multiple inheritance of class in the MIEployee.h and MISstudent.h files // 클래스를 다중상속 받는 클래스 - MIEmployee.h 와 MIStudent.h 파일의 클래스를 다중상속   
`MIStudent.h` : class for Multiple Inheritance // 클래스 다중상속을 위한 클래스   
`MyString.h` : example of multiple definitions of an operator so that a string can be computed like an integer // 문자열을 정수처럼 계산할 수 있도록 연산자를 다중정의하는 예제   
`NamedObj.h` : example of how constructor and destructor work // 생성자, 소멸자 동작 예제   
`noExceptT.h` : example of a noexcept declaration - a declaration not to cause exceptions // noexcept 선언 예제 - 예외를 일으키지 않는다는 선언   
`Pencils.h` : example of prefix and postfix for ++ operator - calculate the number of pencil bundles and individuals // ++연산자 전위 표기, 후위 표기 예제 - 연필 묶음과 낱개의 개수 계산   
`Person.h` : example of dynamically allocating memory - dynamic assignment of memory to the constructors of objects with names and addresses // 메모리 동적 할당 예제 - 이름과 주소를 가진 객체 생성자에 동적 할당 적용   
`Person1.h` : examples of base class and derived class - base class - without virtual function // 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person2.h` : examples of base class and derived class - base class - without virtual function // 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 미포함   
`Person3.h` : examples of base class and derived class - base class - include virtual function // 기초 클래스와 파생 클래스 예제 - 기초 클래스 - 가상함수 포함   
`SafeIntArray.h` : example of verifying that subscripts are accessible by data storage space // 데이터 저장공간에 따른 첨자 접근 가능여부를 확인하는 예제   
`softFT.h` : bubble sort algorithm function template // 버블 정렬 알고리즘 bubble sort algorithm 함수 템플릿   
`StackT.h` : example of a class template - definition of functions that can manipulate stack data type // 클래스 템플릿 예제 - 스택이라는 자료형을 조작할 수 있는 함수 정의   
`Student1.h` : examples of base class and derived class - derived class - without virtual function // 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함   
`Student2.h` : examples of base class and derived class - derived class - without virtual function - initialize data members through the constructor of Person2 // 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 미포함 - Person2 생성자를 통해 데이터멤버 초기화   
`Student3.h` : examples of base class and derived class - derived class - include virtual function // 기초 클래스와 파생 클래스 예제 - 파생 클래스 - 가상함수 포함   
`SwapFunc.h` : example of a function template - a function that exchanges values // 함수 템플릿 예제 - 값을 서로 교환하는 함수   
`Triangle.h` : detail class - example of a triangle class drawing a triangle // 상세 클래스 - 삼각형을 그리는 삼각형 클래스 예제   
`VBEmployee.h` : Employee2 class inherits Person5 class as a virtual base class // Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Employee2   
`VBParttime.h` : class that inherit Student5 class and Employee2 class - Parttime2 class // Student5와 Employee2를 상속받는 클래스 - Parttime2 클래스   
`VBPerson.h` : virtual base class - Person5 class // 가상 기초 클래스 - Person5 클래스   
`VBStudent.h` : Student5 class inherits Person5 class as a virtual base class // Person5 클래스를 가상 기초 클래스로 상속받는 클래스 Student5   
`VecF.h` : example for conceptual understanding of multiple definitions // 다중정의에 대한 개념 이해를 위한 예제   
   