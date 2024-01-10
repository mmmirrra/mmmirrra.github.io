---
layout: post
title:  "C++: FirstStep.cpp : main() sourceFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### sourceFile list - .cpp   
main() sourceFile   
`FirstStep.cpp` : C++ practice project main function   
   
{% highlight cpp %}
#include <iostream>
#include <climits>
#include "Counter.h"
#include "Person.h"
#include "CounterM.h"
#include "VecF.h"
#include "NamedObj.h"
#include "CharStack.h"
#include "Complex1.h"
#include "IntClass1.h"
#include "IntClass2.h"
#include "Pencils.h"
#include "Complex2.h"
#include "SafeIntArray.h"
#include "MyString.h"
#include <string>
#include "Person1.h"
#include "Student1.h"
#include "Student2.h"
#include "Drvd1.h"
#include "Drvd2.h"
#include "Drvd3.h"
#include "Person3.h"
#include "Student3.h"
#include "BaseClass.h"
#include "DrvClass.h"
#include "GrAttrib.h"
#include "Figure.h"
#include "Circle.h"
#include "Triangle.h"
#include "MIParttime.h"
#include "VBParttime.h"
#include "StackT.h"
#include "Buffer.h"
#include "SwapFunc.h"
#include "sortFT.h"
#include <vector>
#include <cstdlib>
#include <ctime>
#include <algorithm>
#include "Greater.h"
#include <map>
#include "Less.h"
#include <memory>
#include "IntArray1.h"

using namespace std;

// 배열에서 가장 큰 값을 구하는 함수
double maximum(double arr[], int n) {
	double max = arr[0];
	for (int i = 1; i < n; i++)
		if (max < arr[i]) max = arr[i];
	return max;
}

// 함수의 원형을 main 함수보다 위에 먼저 써줌. 실제 함수는 main 함수 다음에 있음
float FahrToC(float fahr);				// 인수이름인 fahr은 생략 가능함

void SwapValues(int& x, int& y);

int factorial(int n) {
	if (n <= 1)
		return 1;
	else
		return n * factorial(n - 1);
}

struct SalesRec {
	char pID[10];
	int dYear, dMonth, dDate;
	char deliverAddr[40];
};

void PrSalesRec(const SalesRec& srec);

// 함수의 원형에 디폴트 값 설정
double Round(double x, int d = 0);

struct TimeRec {
	int hours;
	int minutes;
};

void AddTime(TimeRec& t1, const TimeRec& t2);
void AddTime(TimeRec& t, int minutes);

void fff() {
	NamedObj x("Third");
	x.display();
}

// Person 객체 또는 Student 객체에 대한 포인트가 들어있는 배열을 매개변수로 받아 그 안에 들어있는 객체들에 대해 출력하는 함수 - 정적연결 함수 실행
void PrintPerson(const Person3* const p[], int n) {
	for (int i = 0; i < n; i++) {
		p[i]->print();									// 포인트가 가르키는 객체의 멤버에 액세스 함. (*p[i]).print(); 형태로 작성해야 하지만 번거롭기 때문에 p[i]->print(); 형태로 작성할 수도 있음
		cout << endl;
	}
}

// 동적연결 함수 실행
void PrintPersonVirtual(const Person3* const p[], int n) {
	for (int i = 0; i < n; i++) {
		p[i]->printVirtual();
		cout << endl;
	}
}

// 현재의 그래픽 속성 - 전역변수 - 모든 클래스에서 사용 가능
GrAttrib curAttrib("Black", "White");

// 도형을 그리는 함수
void drawFigs(const Figure* const figs[], int n) {		// 도형 Figure 기초 클래스의 포인트 배열을 매개변수로 받음. n은 배열의 크기임
	for (int i = 0; i < n; i++) {
		figs[i]->draw();								// (*figs[i]).draw(); 와 동일함
		cout << endl;
	}
}

// 조화평균 - 오류가 발생할 수 있는 코드
double hmean1(double a, double b) {
	return 2.0 * a * b / (a + b);						// a == -b 인 경우 (a + b) 는 0이 되어 오류가 발생하고 실행 중 프로그램 비정상 종료됨
}

// 조화평균 - 오류가 발생하지 않도록 방지한 코드
double hmean2(double a, double b) {
	if (a == -b) {
		cout << "Unable to divide." << endl;
		exit(EXIT_FAILURE);								// a == -b 인 경우 이를 알리고, 프로그램 강제 종료 - 오류값인 EXIT_FAILURE를 함수를 호출한 곳으로 리턴함
	}
	return 2.0 * a * b / (a + b);
}

// 조화평균 - throw로 리턴 처리
double hmean3(double a, double b) {
	if (a == -b)										// a == -b 인 경우 예외 검출
		throw "Harmonic mean cannot be calculated!";	// throw를 호출한 곳으로 리턴함
	return 2.0 * a * b / (a + b);
}

void fointTest() {
	int* p = new(nothrow) int[1000000000];				// nothrow는 자원 할당에 실패하면 nullptr을 반환함
	if (!p) {											// p가 nullptr 인지 확인 - nullptr 이면 if 내부 실행 
		cerr << "Memory allocation error" << endl;
		exit(EXIT_FAILURE);
	}
}

int main() {
	cout << "My First c++ program" << endl;
	cout << std::numeric_limits<int>::min() << endl;
	cout << 'A : ' << '\101' << '\x41' << endl;
	int korScore, mathScore;
	cout << "Please enter the integer number twice" << endl;
	cin >> korScore >> mathScore;
	std::cout << "sss" << std::endl;
	std::cout << korScore << std::endl;
	std::cout << 'bbb' << std::endl;
	cout << "Please enter an integer" << endl;
	cin >> mathScore;
	std::cout << "bbb" + mathScore << std::endl;
	float avrScore = (korScore + mathScore) / 2.0f;
	std::cout << "avrScore : " << avrScore << std::endl;
	auto iii{ 0 };
	std::cout << "iii : " << iii << std::endl;

	extern float avrScore;
	std::cout << "avrScore : " << std::endl;
	std::cout << avrScore << std::endl;

	int i1 = static_cast<int>(avrScore);
	std::cout << "i1 : " << std::endl;
	std::cout << i1 << std::endl;

	if (i1 > 0)
		std::cout << "greater than 0" << i1 << std::endl;
	else
		std::cout << "less than 0" << std::endl;
	cout << "namespace test" << endl;

	switch (19 - 1) {
	case 18:
		cout << "18" << endl;
		break;
	default:
		cout << "00000" << endl;
	}

	int total{ 0 };
	for (int a{ total }; a < 10; a++) {
		cout << "a " << a << endl;
		total += a;
		cout << "total " << total << endl;
	}

	int arr[5] = { 1,2,3,4,5 };
	int sum{ 0 };
	for (int a : arr) {
		sum += a;
		cout << "sum " << sum << endl;
	}

	int aa{ 100 };
	{
		while (aa < 110) {
			total += aa;
			aa++;
			cout << "total " << total << endl;
		}
	}

	{
		do {
			cout << "do while test " << aa << endl;
			aa++;
		} while (aa < 114);
	}

	struct StructName {
		short item1;
		int item2;
		long item3;
		long long item4;
		double item5, item6;
		float item7;
	};

	StructName bbb;
	bbb.item6 = 11;
	cout << "bbb.item6 " << bbb.item6 << endl;

	struct CircleType {
		StructName center;
		double radius;
	};

	CircleType ccc;
	ccc.center = { 222, 333, 444 };
	cout << "ccc.center.item3 " << ccc.center.item3 << endl;

	static double PI = 3.14;

	class CircleClass {
		StructName center;
		double radius;
	public:
		void init(double cx, double cy, double r) {
			center.item5 = cx;
			center.item6 = cy;
			radius = r;
			cout << "radius " << radius << endl;
		}
		double area() const {
			return radius * radius * PI;
		}
		bool chkOverlap(const CircleClass& c) const {
			double dx = center.item5 - c.center.item6;
			double dy = center.item6 - c.center.item6;
			double dCntr = sqrt(dx * dx + dy * dy);
			cout << "dCntr " << dCntr << endl;
			cout << "radius " << radius << endl;
			cout << "c.radius " << c.radius << endl;
			return dCntr < radius + c.radius;
		}
		void display() const {
			cout << "radius " << radius << endl;
		}
	};

	CircleClass c1, c2;
	c1.init(0, 0, 10);
	c2.init(30, 10, 5);
	cout << "circle 1 " << endl;
	c1.display();
	cout << "Area of ​​circle 1 : " << c1.area() << endl;
	cout << "circle 2 " << endl;
	c2.display();
	cout << "Area of ​​circle 2 : " << c2.area() << endl;
	cout << "c1.chkOverlap(c1) " << c1.chkOverlap(c1) << endl;
	cout << "c2.chkOverlap(c2) " << c2.chkOverlap(c2) << endl;

	float fArray[4];
	int j = 0;
	fArray[j] = 10.3f;
	cout << "fArray[0] " << fArray[0] << endl;
	cout << "Please enter the number with decimal point 3 times" << endl;
	cin >> fArray[1] >> fArray[2] >> fArray[3];
	cout << "fArray[1] * fArray[2] " << fArray[1] * fArray[2] << endl;

	int aaaa[4];
	cout << "no initial value for aaaa, and the address of aaaa is output. // No initial value of aaa, the address of aaaa is output " << aaaa << endl;

	int max;
	int dataArray[6] = { 1, 2, 3, 4, 5, 6 };

	max = dataArray[0];
	cout << "data : " << dataArray[0] << endl;

	for (int i = 1; i < 10; i++) {
		cout << "dataArray[" << i << "] : " << dataArray[i] << endl;
		if (max < dataArray[i]) max = dataArray[i];
	};
	cout << "max : " << max << endl;

	int* iPtr;
	cout << "Failure to assign a valid variable to the iptr results in an error : " << endl;		// iPtr에 유효한 변수를 할당하지 않으면 오류 발생
	iPtr = &max;
	cout << "Assignment of valid variables in iPtr will be normal : iPtr : " << iPtr << endl;		// iPtr에 유효한 변수를 할당하면 정상 처리
	*iPtr = 0;
	*iPtr = { 1 };
	cout << "*iPtr value == max value : " << *iPtr << endl;
	cout << "max : " << max << endl;

	int* intPtr;
	intPtr = new int;
	cout << "Allocating new data space to intPtr will work fine : intPtr : " << intPtr << endl;		// intPtr에 새로운 데이터 공간 할당하면 정상 처리
	*intPtr = 10;
	cout << "*intPtr value : " << *intPtr << endl;
	delete intPtr;
	cout << "*intPtr value after delete : " << *intPtr << endl;
	intPtr = nullptr;
	if (!intPtr) {
		cout << "intPtr memory allocation deleted " << endl;										// intPtr 메모리 할당이 삭제됨
	}
	if (intPtr == nullptr) {
		cout << "intPtr memory allocation deleted " << endl;
	}

	int* intPtr4;
	intPtr4 = new int[4];
	*intPtr4 = 10;
	*(intPtr4 + 1) = 20;
	*(intPtr4 + 2) = 30;
	cout << "*(intPtr4+2) : " << *(intPtr4 + 2) << endl;
	intPtr4[3] = 40;
	cout << "intPtr4[3] : " << intPtr4[3] << endl;
	delete[] intPtr4;
	cout << "*intPtr4 value after delete : " << *intPtr4 << endl;
	intPtr4 = nullptr;

	int& refMax = max;
	cout << "refMax : " << refMax << endl;
	refMax += 100;
	cout << "refMax : " << refMax << endl;
	cout << "max : " << max << endl;

	double a[50], b[100];
	for (int i = 0; i < 50;) {
		a[i] = i;
		b[i] = ++i;
	}
	cout << "maximum(a, 50) : " << maximum(a, 50) << endl;
	cout << "maximum(b, 100) : " << maximum(b, 100) << endl;

	float fTemp, cTemp;
	cout << "Fahrenheit temperature : ";
	cout << "Enter a decimal number" << endl;
	cin >> fTemp;												// 화씨온도 입력 받음
	cTemp = FahrToC(fTemp);
	cout << "---> Celsius temperature : " << cTemp << endl;		// 섭씨온도 출력됨

	int s, t;
	cout << "Enter two numbers : ";
	cout << "Enter an integer number twice" << endl;
	cin >> s >> t;
	if (s < t) SwapValues(s, t);											// 순서를 바꿔서 s에 큰 값을 넣음
	cout << "large number = " << s << " small number = " << t << endl;

	cout << "factorial : " << factorial(3) << endl;

	SalesRec sss{
		"pID12345", 2023, 11, 14, "서울시 용산구"
	};

	PrSalesRec(sss);

	istream& getline(char* str, int count, char delimiter = '\n');
	char str1[10], str2[10];
	cout << "Enter values to enter str1, str2 : " << endl;
	cout << "Type a word with 10 characters and type ',' at the end. " << endl;
	cin.getline(str1, 10, ',');
	cout << "str1 : " << str1 << endl;
	cout << "Enter a word with 10 characters." << endl;
	cin.getline(str2, 10);
	cout << "str2 : " << str2 << endl;

	double dd;
	cout << "double value to round up = ";
	cout << "Enter a decimal number" << endl;
	cin >> dd;
	cout << "round off 0 --> " << Round(dd) << endl;
	cout << "round off 1 --> " << Round(dd, 1) << endl;
	cout << "round off 2 --> " << Round(dd, 2) << endl;
	cout << "round off 3 --> " << Round(dd, 3) << endl;

	TimeRec tRec1 = { 2, 30 };
	TimeRec tRec2 = { 1, 45 };

	cout << tRec1.hours << "hours " << tRec1.minutes << "minutes + ";
	cout << tRec2.hours << "hours " << tRec2.minutes << "minutes = ";
	AddTime(tRec1, tRec2);
	cout << tRec1.hours << "hours " << tRec1.minutes << "minutes" << endl;

	cout << tRec1.hours << "hours " << tRec1.minutes << "minutes + ";
	cout << "135 minutes = ";
	AddTime(tRec1, 135);
	cout << tRec1.hours << "hours " << tRec1.minutes << "minutes" << endl;

	Counter cnt1, cnt2;
	//	cnt1.reset(); // Counter 함수에 생성자 Counter가 있으므로 여기에서 초기화할 필요 없음
	cout << "Current value of counter = Initial value : " << cnt1.getValue() << endl;
	cnt1.count();
	cnt1.count();
	cnt1.count();
	cnt1.count();
	cout << "Current value of counter --> count(); 함수를 " << cnt1.getValue() << "번 함" << endl;
	cnt1.f();

	Person* p1 = new Person("Lee", "서울시 종로구");
	Person* p2 = new Person("Park", "강원도 동해시");
	p1->print();
	(*p2).print();								// 괄호 ()와 화살표 -> 는 같은 기능임
	cout << endl << "Change address : ";
	p2->chAddr("대전시 서구");
	p2->print();
	delete p1;									// Person 객체가 소멸하기 때문에 ~Person 함수가 실행됨
	delete p2;

	Person p3("Mr.nobody", "노숙자");

	CounterM cnt3(999);
	CounterM cntMArr[3] = { CounterM(9), CounterM(99), CounterM(999) };
	CounterM cnt4(cnt3);
	CounterM cnt5 = cnt4;						// 묵시적 복사 생성자로 초기화됨

	Counter cntArr[4];							// Counter 객체를 4개 만듬. 배열임
	Counter* pt = new Counter[10];				// Counter 객체를 10개 만든. 배열임

	float af[3] = { 1, 2, 3 };
	VecF v1(3, af);
	VecF v2(v1);
	cout << " v1 ";
	v1.print();
	cout << endl;
	cout << " v2 ";
	v2.print();
	cout << endl;
	VecF v3(v1.add(v2));			// 명시적 이동 생성자가 실행됨
	cout << " v3 ";
	v3.print();
	cout << endl;
	VecF&& vRRef1 = v1.add(v2);
	cout << " vRRef1 ";
	vRRef1.print();
	cout << endl;
	VecF v4(3);
	v4 = v1;						// 대입 연산자
	cout << " v4 ";
	v4.print();
	cout << endl;
	v4 = v1.add(v2);				// 이동 대입 연산자
	cout << " v1 ";
	v1.print();
	cout << " + ";
	cout << " v2 ";
	v2.print();
	cout << " = ";
	cout << " v4 ";
	v4.print();
	cout << endl;
	float af1[3] = { 1, 2, 3 };
	float af2[3] = { 2, 4, 6 };
	VecF vec1(3, af1), vec2(3, af2);
	swapVecF1(vec1, vec2);
	cout << " Placement by copy constructor ";
	cout << endl;
	cout << " vec1 ";
	vec1.print();
	cout << " vec2 ";
	vec2.print();
	cout << endl;
	swapVecF2(vec1, vec2);
	cout << " Placement by move constructor ";
	cout << endl;
	cout << " vec1 ";
	vec1.print();
	cout << " vec2 ";
	vec2.print();
	cout << endl;

	cout << "Number of objects in the NamedObj class : " << NamedObj::nObj() << endl;
	NamedObj namedA("First");
	NamedObj namedB("Second");
	fff();
	NamedObj namedC("Fourth");
	namedC.display();
	cout << "Number of objects in the NamedObj class : " << NamedObj::nObj() << endl;

	CharStack chStack;													// 20개의 문자를 저장할 수 있는 스택
	char str[20];

	cout << "Enter English words : " << endl;
	cout << "Enter a word that is less than 20 characters long : " << endl;
	cin >> str;

	char* spt = str;													// 포인터로 문자열 시작 위치를 가리킴
	while (*spt)														// 문자열의 끝이 아니면 반복
		chStack.push(*(spt++));											// 스택에 문자를 넣음

	cout << "Output words in reverse order : ";
	while (!chStack.chkEmpty())															// 스택이 비어 있지 않으면 반복
		cout << "Outputs characters extracted from the stac : " << chStack.pop();		// 스택에서 인출한 문자를 출력
	cout << endl;

	Complex1 cc1(1, 2);				// 복소수 - 정수
	Complex1 cc2(2, 3);
	Complex1 cc3 = cc1.add(cc2);

	cc1.display();
	cout << " + ";
	cc2.display();
	cout << " = ";
	cc3.display();
	cout << endl;

	cc3 = cc1.mul(10.0);
	cc1.display();
	cout << " * 10 = ";
	cc3.display();
	cout << endl;

	IntClass1 ii;
	cout << (++ii).getValue() << endl;
	cout << (++ii).getValue() << endl;

	IntClass2 jj;
	cout << (jj++).getValue() << endl;
	cout << (jj++).getValue() << endl;
	
	Pencils pp1(5, 7);
	Pencils pp2(23);

	pp1.display();
	(++pp1).display();
	pp1.display();
	cout << endl;
	pp2.display();
	pp1 = pp2++;
	pp1.display();
	pp2.display();

	Complex2 aa1(1.5, 2);		// 복소수 - 실수
	Complex2 bb1(5, -3.9);
	cout << aa1 << " + " << bb1 << " = " << aa1 + bb1 << endl;

	SafeIntArray sa(10);													// 10개의 원소를 갖는 객체 생성

	for (int i = 0; i < 10; i++)
		sa[i] = i;
	cout << "Access the correct range of elements : " << sa[5] << endl;		// 올바른 범위의 원소 액세스
	//cout << sa[12] << endl;												// 범위를 벗어난 액세스

	size_t strlen(const char* str);											// 문자열의 길이 구하기
	cout << "The length of the str character strlen is " << strlen(str) << "개" << endl;
	int strn = strlen("abcde");
	cout << "The length of the abcde character strn is " << strn << "개" << endl;

	char* strcpy(char* strDestination, const char* strSource);				// 문자열 복사하기
	char str10[10] = "KNOU";
	strcpy(str10, "CS");
	cout << "The character of str10 is " << str10 << endl;					// CS가 출력됨

	char* strcat(char* strDestination, const char* strSource);				// 문자열 연결하기
	char str20[10] = "KNOU";
	strcat(str20, "CS");
	cout << "The character of str20 is " << str20 << endl;					// KNOUCS 가 출력됨

	char cstr1[10] = "C string";
	char cstr2[10];
	char* cstr3;
	MyString mstr1("MyString Object");
	MyString mstr2;
	// cstr2 = cstr1;												// 에러
	cstr3 = cstr1;													// 포인터 복사 - 문자열을 복사한 것이 아니고 포인트를 복사한 것임
	cout << "cstr3 output " << cstr3 << endl;
	mstr2 = mstr1;													// deep copy
	cout << "mstr2 output " << mstr2 << endl;

	MyString sstr1("MyString class");
	MyString sstr2("Object Oriented ");
	MyString sstr3;													// 빈 문자열

	cout << "sstr1 is " << sstr1 << endl;							// 문자열 출력
	sstr3 = "Programming";											// C스타일의 문자열을 대입하는 함수는 만들지 않았지만, C스타일의 문자열을 받는 생성자가 있으면 묵시적 형 변환이 일어나 rvalue 형태의 생성자 MyString(const char* str) 가 만들어져서 이동 연산자로 대입됨
	cout << "The string length of sstr3 is " << sstr3 << ".";
	cout << sstr3.length() << endl;									// 문자열 길이를 구하는 메소드
	sstr1 = sstr2;													// 대입 연산자 다중정의로 문자열 복사
	cout << "sstr1 with sstr2 as a substitute is " << sstr1 << endl;
	sstr1 = sstr2 + sstr3;											// 문자열 연결 연산자 다중정의에 의해 rvalue 가 만들어지고, 그 rvalue를 이동 대입 연산자 다중정의에 의해 이동해 넣음
	cout << "sstr1 = sstr2 + sstr3 -----> " << sstr1 << endl;

	Person1 dudley1;												// 기초 클래스의 객체 선언
	dudley1.setName("Dudley1");										// 기초 클래스의 함수 호출
	Student1 harry1;												// 파생 클래스의 객체 선언
	harry1.setName("Harry1");										// 기초 클래스의 함수 호출
	harry1.setSchool("Hogwarts1");									// 파생 클래스의 함수 호출
	cout << "Run dudley1.print(); ";
	dudley1.print();												// 기초 클래스의 함수 호출
	cout << endl;
	cout << "Run harry1.print(); ";
	harry1.print();													// 파생 클래스의 함수 호출
	cout << endl;
	cout << "Run harry1.Person1::print(); ";
	harry1.Person1::print();										// 기초 클래스의 함수 호출
	cout << endl;

	Student2 harry2("Harry2", "Hogwarts2");
	cout << harry2.getName() << " goes to "
		<< harry2.getSchool() << endl;

	Drvd1 d1;
	// d1.a = 1;									// 에러 (private 멤버)
	// d1.b = 2;									// 에러 (protected 멤버)
	d1.c = 3;										// ok (public 멤버)
	cout << "d1.c : " << d1.c << endl;

	Drvd2 d2;
	// d2.a = 1;									// 에러 (private 멤버)
	// d2.b = 2;									// 에러 (protected 멤버)
	// d2.c = 3;									// 에러 (protected 멤버로 권한 제한)
	// cout << "d2.c 는 " << d2.c << endl;			// 에러

	Drvd2 d3;
	// d3.a = 1;									// 에러 (private 멤버)
	// d3.b = 2;									// 에러 (private 멤버로 권한 제한)
	// d3.c = 3;									// 에러 (private 멤버로 권한 제한)
	// cout << "d3.c 는 " << d3.c << endl;			// 에러

	Person3 dudley3("Dudley3");
	Student3 harry3("Harry3", "Hogwarts3");
	Student3 ron3("Ron3", "Hogwarts3");
	cout << "Run dudley3.print(); ";
	dudley3.print();
	cout << endl;
	cout << "Run harry3.print(); ";
	harry3.print();
	cout << endl;
	Person3* pPerson3[3];
	pPerson3[0] = &dudley3;
	pPerson3[1] = &harry3;
	pPerson3[2] = &ron3;
	cout << "Run PrintPerson(pPerson3, 3); " << endl;
	PrintPerson(pPerson3, 3);								// 정적연결임

	cout << "Run dudley3.printVirtual(); ";
	dudley3.printVirtual();
	cout << endl;
	cout << "Run harry3.printVirtual(); ";
	harry3.printVirtual();
	cout << endl;
	cout << "Run PrintPersonVirtual(pPerson3, 3); " << endl;
	PrintPersonVirtual(pPerson3, 3);						// 동적연결임

	Person3* ppp1 = new Person3("Dudley4");
	cout << "Run ppp1->print(); ";
	ppp1->print();											// Person3::print() 호출
	cout << endl;
	Person3* ppp2 = new Student3("Harry", "Hogwarts");
	cout << "Run ppp2->print(); ";
	ppp2->print();											// Person3::print() 호출
	cout << endl;
	cout << "Run ((Student3*)ppp2)->print(); ";
	((Student3*)ppp2)->print();								// Person3 포인트를 Student3 의 포인트로 강제 형변환 후 Student3::print() 호출하는 정적연결임. ppp2가 Student 객체를 가리키고 있으리라는 보장이 없으므로 위험함
	cout << endl;

	BaseClass* pB1 = new BaseClass(5);
	BaseClass* pB2 = new DrvClass(10, 15);
	delete pB1;
	delete pB2;												// 소멸자를 가상함수로 만들었으므로 기초 클래스, 파생 클래스 모두 소멸자가 실행됨

	Figure* figs[2];
	figs[0] = new Circle(0, 20, 10);
	double vv[3][2] = { {0, 0}, {20, 0}, {10, 15} };
	curAttrib.setLineColor("Red");
	curAttrib.setFillColor("Yellow");
	figs[1] = new Triangle(vv);
	cout << "Draw all shapes" << endl;
	drawFigs(figs, 2);										// 모든 도형 그리기 방법 출력

	figs[0]->scale(2);										// 원의 크기 조정
	figs[1]->move(5, 10);									// 삼각형의 이동
	cout << "Redraw all shapes after modifying them" << endl;
	drawFigs(figs, 2);										// 모든 도형 그리기 방법 출력

	Parttime1 chulsoo1("ABC1 Univ.", "DEF1 Co. ");
	chulsoo1.printSchool();									// Student4의 멤버함수 호출
	chulsoo1.printCompany();								// Employee1의 멤버함수 호출
	chulsoo1.Student4::print();								// 동일한 이름의 함수인 경우 소속을 명확히 표기해야 함
	chulsoo1.Employee1::print();

	Parttime2 chulsoo2("Chulcoo2", "ABC2 Univ.", "EDF2 Co.");
	chulsoo2.print();

	Stack<char> sc(100);				// 문자를 100개까지 저장할 수 있는 char 스택 선언
	sc.push('a');						// char 스택 사용
	sc.push('b');
	cout << "Use a class template called Stack to save characters and output the saved characters - CHAR STACK : ";
	while (!sc.empty())					// Stack이라는 클래스 템플릿을 이용해서 문자를 저장하고 저장된 문자를 출력
		cout << sc.pop() << " ";
	cout << endl;

	Stack<int> si(50);					// 정수를 50개까지 저장할 수 있는 int 스택 선언
	si.push(5);							// int 스택 사용
	si.push(10);
	cout << "INT STACK : ";
	while (!si.empty())
		cout << si.pop() << " ";
	cout << endl;

	Stack<MyString> msStack(10);		// MyString 스택 선언
	// 사용자 정의 클래스 객체를 저장하기 위해 컨테이너 클래스 템플릿을 사용하는 경우 - 클래스 템플릿에서 필요로 하는 멤버함수가 대상 클래스에 포함되어 있어야 함 - Stack 클래스 템플릿은 사용자 정의 클래스 객체에 디폴트 생성자(매개변수가 없는 디폴트 생성자 - Stack 클래스 템플릿은 생성자 실행 시 포인트 메모리 동적 할당이 일어나므로 디폴트 생성자 필요함), 대입 연산자, 이동 대입 연산자 등이 필요함
	MyString s1("KNOU");
	MyString s2("Dep.");
	MyString s3("CS");
	msStack.push(s1);					// MyString 스택 사용
	msStack.push(s2 + s3);
	cout << "MuString STACK : ";
	while (!msStack.empty())
		cout << msStack.pop() << " ";
	cout << endl;

	Buffer<char, 128> buf1;				// 크기가 128개인 char형 버퍼 선언
	Buffer<Complex1, 20> buf2;			// 크기가 20개인 Complex1 버퍼 선언
	// int bn = 10;
	// Buffer<char, bn> buf3;			// 에러 - bn 자리에 int형 값을 직접 넣지 않았음. bn 자리에는 컴파일 시 알 수 있는 값을 넣어야 함. 컨테이너 클래스 템플릿을 컴파일시가 아닌 실행시 값이 결정되도록 작성하면 에러가 발생함. 실행시에는 값을 못찾음

	int sx1 = 10, sy1 = 20;
	cout << "before exchanging int values --> ";
	cout << "sx1 = " << sx1 << ", sy1 = " << sy1 << endl;
	swapFT(sx1, sy1);													// 함수 템플릿 실행
	cout << "after exchanging int values --> ";
	cout << "sx1 = " << sx1 << ", sy1 = " << sy1 << endl;

	MyString sx2 = "KNOU", sy2 = "CS";
	cout << "before exchanging MyString values --> ";
	cout << "sx2 = " << sx2 << ", sy2 = " << sy2 << endl;
	swapFT(sx2, sy2);													// 함수 템플릿 실행
	cout << "after exchanging MyString values --> ";
	cout << "sx2 = " << sx2 << ", sy2 = " << sy2 << endl;

	int sortx[10] = {6, 0, 3, 1, 2, 9, 4, 5, 7, 8};
	cout << "before sorting using sortFT function -->" << endl;
	for (auto i : sortx)
		cout << i << " ";
	cout << endl;
	sortFT(sortx, 10);
	cout << "after sorting using sortFT function -->" << endl;
	for (auto i : sortx)
		cout << i << " ";
	cout << endl;

	vector<float> fVector(10);											// 10개의 float 값을 저장하는 vector 객체 선언
	fVector[2] = 10.0f;													// 객체의 첨자에 직접 접근
	// fVector[12] = 10.0f;												// 범위를 벗어난 첨자이므로 실행 중 에러 발생함 - 예외처리 못함
	cout << "direct access to subscripts of objects using STL sequential container vectors : " << fVector[2] << endl;		// STL 순차 컨테이너 vector를 이용한 객체의 첨자 직접 접근

	vector<int> iVector = { 1, 2, 3, 4 };
	iVector.at(2) = 10;													// vecotr의 멤버함수 at()은 첨자에 직접접근 할 수 있는 []와 같은 결과를 가져올 수 있지만 첨자의 범위를 벗어난 경우 [] 와는 다르게 예외처리를 할 수 있음
	cout << "iVector.at(2) : "  << iVector.at(2) << endl;
	// cout << "iVector.at(4) 는 예외발생 " << iVector.at(4) << endl;	// 예외처리 구현 필요

	cout << "The size, which is the logical size of the stored value of the fVector, is " << fVector.size() << endl;		// fVector의 저장된 값의 논리적 크기인 size
	cout << "The physical size of the fVector's allocated memory, capacity, is " << fVector.capacity() << endl;				// fVector의 할당된 메모리 물리적 크기인 capacity

	cout << "The size, which is the logical size of the stored value of the iVector, is " << iVector.size() << endl;		// iVector의 저장된 값의 논리적 크기인 size
	cout << "The physical size of the iVector's allocated memory, capacity, is " << iVector.capacity() << endl;				// iVector의 할당된 메모리 물리적 크기인 capacity

	vector<int> intVec(5);
	for (int i = 0; i < intVec.size(); i++)
		intVec[i] = i + 1;
	cout << "logical Size of vector : " << intVec.size() << endl;		// 벡터의 논리적 크기
	cout << "physical Size of vector : " << intVec.capacity() << endl;	// 벡터의 물리적 크기
	cout << "stored data : ";
	for (int i = 0; i < intVec.size(); i++)								// 저장된 데이터
		cout << intVec[i] << " ";
	cout << endl;

	intVec.push_back(11);												// 제일 마지막에 push로 값 1개 추가
	cout << "The logical size of the vector is 6 : " << intVec.size() << endl;
	cout << "The physical size of the vector will be greater than 6 : " << intVec.capacity() << endl;
	cout << "Stored data is 1, 2, 3, 4, 5, 11 : ";
	for (int i = 0; i < intVec.size(); i++)
		cout << intVec[i] << " ";
	cout << endl;

	for (int i = 1; i <= 5; i++)
	intVec.push_back(i + 11);											// 제일 마지막에 push로 값 5개 추가
	cout << "The logical size of the vector is 11 : " << intVec.size() << endl;
	cout << "The physical size of the vector will be greater than 11 : " << intVec.capacity() << endl;
	cout << "Stored data is 1, 2, 3, 4, 5, 11, 12, 13, 14, 15, 16 : ";
	for (int i = 0; i < intVec.size(); i++)
		cout << intVec[i] << " ";
	cout << endl;

	for (int i = 0; i <3; i++)
		intVec.pop_back();												// 제일 마지막에 있는 값을 pop으로 3개 추출
	cout << "The logical size of the vector is 8 : " << intVec.size() << endl;
	cout << "The physical size of the vector retains its previous value : " << intVec.capacity() << endl;
	cout << "Stored data is 1, 2, 3, 4, 5, 11, 12, 13 : ";
	for (int i = 0; i < intVec.size(); i++)
		cout << intVec[i] << " ";
	cout << endl;

	// vector<int>::iterator it = intVec.begin();						// 반복자 선언 - begin() 은 처음 위치임 - 반복자는 컨테이너 내의 객체를 가리키는 포인터의 개념에 해당됨
	auto it = intVec.begin();											// 자료형 추론을 이용한 반복자 선언 - 윗 줄의 반복자 선언 vector<int>::iterator it = intVec.begin(); 과 동일한 기능 - intVec.begin();의 값에 의해 자료형이 추론됨
	cout << "iterator - Data stored from the beginning : ";
	for (; it < intVec.end(); it++)										// 반복자를 사용 - end() 는 끝 위치임
		cout << *it << " ";												// it라는 반복자를 사용. 포인트가 아니지만 *를 사용
	cout << endl;

	it = intVec.begin();
	cout << "Third data of intVec object : " << *(it + 2) << endl;
	
	srand((unsigned)time(NULL));										// 난수 발생기 srand 함수 초기화 - time은 현재시간 리턴. time으로 srand의 sead값 전달
	vector<int> iv1(5);
	cout << "vector 1: ";
	for (auto& i : iv1) {												// iv1에 대한 범위 기반 for 루프. 범위 기반 for 루프는 begin()과 end()라는 멤버함수를 이용해서 처음과 끝의 위치를 알아낼 수 있는 자료형에 사용 가능함. auto& i는 정수형 참조임
		i = rand() % 100;												// 0~99의 난수 발생
		cout << i << " ";
	}
	cout << endl;
	sort(iv1.begin(), iv1.end());										// 정렬 알고리즘 - iv1의 전체 범위를 정렬하도록 함
	cout << "sorted vector 1 : ";
	for (auto i : iv1)													// auto i는 정수 int형
		cout << i << " ";
	cout << endl;

	vector<int> iv2(5);
	cout << "vector 2: ";
	for (auto& i : iv2) {												// iv2에 대한 범위 기반 for 루프
		i = rand() % 100;												// 0~99의 난수 발생
		cout << i << " ";
	}
	cout << endl;
	sort(iv2.begin(), iv2.end());										// 정렬 알고리즘 - iv2의 전체 범위를 정렬하도록 함
	cout << "sorted vector 2 : ";
	for (auto i : iv2)													// auto i는 정수 int형
		cout << i << " ";
	cout << endl;

	vector<int> iv3(iv1.size() + iv2.size());							// 합병 결과를 저장할 벡터 - iv1의 사이즈와 iv2의 사이즈를 합한 만큼의 크기로 iv3을 만듦
	merge(iv1.begin(), iv1.end(), iv2.begin(), iv2.end(), iv3.begin());	// 동일한 기준으로 정렬되어 있으므로 합병 가능
	cout << "The result of merging vector 1 and vector 2 : ";
	for (auto i : iv3)													// 벡터1과 벡터2를 합병한 결과
		cout << i << " ";
	cout << endl;

	GREATER<int> greaterThan;											// greaterThan은 객체임 - 객체 내의 함수를 함수객체처럼 사용하기 위해서는 GREATER 클래스에 () 연산자가 다중정의되어 있어야 함
	if (greaterThan(20, 10))											// 함수객체를 사용하였기 때문에 마치 함수를 호출한 것과 같이 작성함
		cout << "20 is greater than 10" << endl;

	sort(iv3.begin(), iv3.end(), GREATER<int>());						// 정렬 시 콜백 함수로 함수객체를 전달
	cout << "as a result of sorting vector 3 in descending order : ";
	for (auto i : iv3)													// 벡터3을 내림차순으로 정렬한 결과
		cout << i << " ";
	cout << endl;

	map<string, string> addrbook;
	addrbook.insert(make_pair("Kim", "서울시 종로구"));					// 데이터 쌍을 삽입. pair는 first와 second라는 2개의 데이터 멤버를 포함하는 템플릿 구조체. make_pair는 pair 객체를 반환하는 함수 템플릿
	addrbook.insert({ "Hong", "서울시 중구" });
	// addrbook.insert({ "Kim", "서울시 성동구" });						// 동일한 키가 이미 존재하므로 에러

	cout << "addrbook['Hong'] : " << addrbook["Hong"] << endl;			// "서울시 중구" 가 출력됨
	addrbook["Park"] = "대전시 동구";									// "Park", "대전시 동구" 데이터가 삽입됨
	cout << "addrbook['Park'] : " << addrbook["Park"] << endl;
	addrbook["Kim"] = "서울시 성동구";									// "Kim" 값이 "서울시 성동구"로 변경됨
	cout << "addrbook['Kim'] : " << addrbook["Kim"] << endl;

	auto it1 = addrbook.find("Park");									// 반복자 선언. auto 는 map<string, string>::iterator 와 같음. it는 pair 객체("박영식", "대전시 동구")를 가리킴
	auto it2 = addrbook.find("Lee");									// 찾을 키가 없으므로 it에 addrbook.end() 가 저장됨. end() 는 맨 끝의 데이터 다음 위치임. it의 값이 end()와 같다면 데이터가 검색되지 않았다는 것을 알 수 있음

	addrbook.erase(it1);												// it1 이라는 반복자가 가리키는 데이터 삭제
	addrbook.erase("Kim");												// 키가 가리키는 항목 삭제

	map<string, string, LESS_T<string>> pBook{							// LESS_T 기준으로 정렬
		{"Han", "010-2233-4354"},
		{"Park", "010-2233-4455"}
	};
	pBook["Kim"] = "010-1234-5678";										// 기존 항목이 없으므로 새로운 항목 추가됨
	pBook.insert(make_pair("Choi", "010-7531-3456"));					// 새로운 항목 추가됨
	pBook.insert({ "Park", "010-1357-2468" });							// 이미 있는 키 이므로 insert 되지 않고 무시됨
	for (auto pb = pBook.begin(); pb != pBook.end(); ++pb)
		cout << pb->first << " " << pb->second << endl;					// pb->first는 첫번째 값이므로 이름이, pb->second는 두번째 값이므로 전화번호가 키 순서대로 출력됨
	cout << pBook.size() << "person is registered." << endl;

	string strMap;
	cout << "enter only one of the names Kim, Park, Choi, and Han to find. : ";
	cin >> strMap;
	auto result = pBook.find(strMap);									// find 함수는 검색된 항목의 반복자 제공
	if (result != pBook.end()) {
		cout << result->first << "'s phone number is ";					// result->first는 첫번째 값이므로 이름 출력됨
		cout << result->second << "." << endl;							// result->second는 두번째 값이므로 전화번호 출력됨
	}
	else
		cout << strMap << ": can't find it" << endl;

	double xt, yt, zt;
	char cFlag = 'y';
	while (cFlag != 'n') {												// cFlag 가 n 이면 종료됨
		cout << "Enter a number twice : ";
		cin >> xt >> yt;
		try {															// 예외 발생 가능성이 있는 코드
			zt = hmean3(xt, yt);
			cout << "harmonic mean = " << zt << endl;					// 조화평균 값 출력
		}
		catch (const char* s) {											// 예외처리
			cout << s << endl;
		}
		cout << "Do you want to continue? (Enter y to continue. / Enter n to interrupt.) : ";
		cin >> cFlag;
	}

	unique_ptr<int> pu1{ new int };										// 스마트 포인트 중 유니크 포인트
	unique_ptr<int> pu2;
	*pu1 = 10;
	cout << "* pu1 : " <<  *pu1 << endl;
	pu2 = move(pu1);													// pu2 = pu1; 의 형태는 불가. unique_ptr은 대입은 불가, 이동만 가능
	cout << "* pu2 : " << *pu2 << endl;
	pu2 = nullptr;														// 가리키고 있던 메모리는 자동 반납되어 해제됨
	// cout << *pu2 << endl;											// pu2은 nullptr 상태이므로 실행 시 오류 발생
	// cout << *pu1 << endl;											// pu1은 nullptr 상태이므로 실행 시 오류 발생

	IntArray1 arrE(10);																// 사용자 정의 객체 오류 처리 예제
	try {
		for (int i = 0; i <= 10; i++)												// i의 범위는 0 ~ 9이지만 조건에 10보다 작거나 같도록 설정해놨으므로 오류 발생함
			arrE[i] = i;
	}
	catch (IntArray1::BadIndex1 e) {												// 예외객체 받음 
		cerr << "index range error - Used Subscript : " << e.wrongIndex << endl;	// 오류 내용 출력
	}
	cout << "arrE[0] : " << arrE[0] << endl;

	return 0;
}

// 화씨온도를 섭씨온도로 변환하는 함수 
float FahrToC(float fahr) {
	return (fahr - 32) * 5 / 9;
}

// 참조된 두 인수의 값을 서로 바꿔주는 함수
void SwapValues(int& x, int& y) {
	int temp = x;
	x = y;
	y = temp;
}

// const 한정어로 실 매개변수 보호 - SaleRec 구조체는 main 함수보다 먼저 정의되어 있어야 함
void PrSalesRec(const SalesRec& srec)
{
	cout << "Item code : " << srec.pID << endl;
	cout << "Delivery date : " << " Year : " << srec.dYear;
	cout << " / Month : " << srec.dMonth;
	cout << " / Date : " << srec.dDate << endl;
	cout << "Delivery address : " << srec.deliverAddr << endl;
}

// 반올림 함수
double Round(double x, int d) {					// d 자리에서 반올림함
	double a = x >= 0 ? 0.5 : -0.5;				// 양수면 0.5 더하고, 음수면 -0.5 더함
	double pow10 = pow(10, d);					// pow는 어떤 값의 몇 제곱을 의미함 -> 여기서는 10에 d제곱임
	return trunc(x * pow10 + a) / pow10;		// trunc는 소수점 이하의 값을 자르는 역할
}

// 시간을 더하는 함수 1
void AddTime(TimeRec& t1, const TimeRec& t2) {
	t1.minutes += t2.minutes;
	t1.hours += t2.hours + t1.minutes / 60;
	t1.minutes %= 60;
}

// 시간을 더하는 함수 2
void AddTime(TimeRec& t, int minutes) {
	t.minutes += minutes;
	t.hours += t.minutes / 60;
	t.minutes %= 60;
}
{% endhighlight %}
