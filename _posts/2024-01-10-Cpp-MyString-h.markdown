---
layout: post
title:  "C++: MyString.h : headerFile"
date:   2024-01-10 09:00:00 +0900
categories: [C++]
---

solution 'CppPrjs'   
project 'FirstStep'   
   
### headerFile list - MyString.h   
// 문자열을 정수처럼 계산할 수 있도록 연산자를 다중정의하는 예제   
`MyString.h` : example of multiple definitions of an operator so that a string can be computed like an integer   
   
```cpp
#pragma once
#include <ostream>

class MyString {					// 문자열을 정수처럼 계산할 수 있도록 연산자를 다중정의하는 예제
	int		len;				// 문자열의 길이를 저장
	int		bufSize;			// 최대로 저장할 수 있는 문자열의 길이를 저장
	char*	buf;					// 문자열 저장 공간
	MyString(int s) : len(s), bufSize(s) {	// 생성자(내부용으로만 사용하는 private 함수) - 저장공간 메모리 할당만 함
		buf = new char[s + 1];
		buf[s] = '\0';
	}
public:
	MyString() : len(0), bufSize(0){	// 디폴트 생성자
		buf = new char[1];		// 문자열이 없으므로 사이즈가 0이지만 null 캐릭터를 저장하기 위해 저장공간을 1 할당받아서 null 캐릭터를 저장함
		buf[0] = '\0';
	}
	MyString(const char* str) {		// 일반적인 생성자 - C스타일의 문자 자료형의 포인트 - 묵시적 형변환 가능
		len = bufSize = strlen(str);	// 문자열 길이
		buf = new char[len + 1];	// 문자열 길이만큼 저장공간 할당 - null 캐릭터가 들어갈 1 만큼의 저장공간 더해서 할당
		strcpy(buf, str);		// 문자열 복사
	}
	// explicit MyString(const char* str) {}	// 이런식으로 맨 앞에 explicit를 넣으면 묵시적인 형변환을 금지할 수 있음. 이 경우 형변환을 하려면 반드시 명시적으로 구현해야 함 ex. str = MyString{ "Programming" }; str = static cast<MyString>("Programming");
	MyString(const MyString& mstr) : len(mstr.len), bufSize(mstr.len) {	// 복사 생성자 - 딮 카피 deep copy
		buf = new char[len + 1];
		strcpy(buf, mstr.buf);
	}
	MyString(MyString&& mstr) noexcept : len(mstr.len), bufSize(mstr.bufSize), buf(mstr.buf) {	// 이동 생성자
		mstr.buf = nullptr;
	}
	~MyString() {			// 소멸자
		delete[] buf;
	}
	int length() const {		// 문자열의 길이를 반환하는 메소드
		return len;
	}
	MyString& operator = (const MyString& mstr) {		// 대입 연산자 다중정의 - strcpy 대신 사용할 수 있게 '=' 대입 연산자를 만듦
		if (bufSize < mstr.len) {			// 문자열 공간이 필요량보다 작으면
			delete[] buf;				// 기존 공간 반환
			len = bufSize = mstr.len;		// 새로운 문자열의 길이
			buf = new char[len + 1];		// 새로운 공간 할당
		}
		else				// 그렇지 않으면
			len = mstr.len;		// 문자열의 길이만 수정
		strcpy(buf, mstr.buf);
		return *this;
	}
	MyString& operator = (MyString&& mstr) noexcept {	// 이동 연산자 다중정의
		delete[] buf;
		len = mstr.len;
		bufSize = mstr.bufSize;
		buf = mstr.buf;			// 포인터만 복사해서 메모리가 이동된 것으로 처리
		mstr.buf = nullptr;		// 메모리를 반드시 nullptr로 만들어야 함. nullptr을 하지 않을 경우 소멸자에서 delete 실행시 문제가 발생함
		return *this;
	}
	MyString operator + (const MyString& mstr) const {	// 문자열 연결 연산자 '+' 다중정의 - 두 문자열을 새로운 문자열로 합함
		MyString tmstr(len + mstr.len);			// private으로 정의한 생성자 - 메모리만 확보
		strcpy(tmstr.buf, buf);				// 앞쪽에 첫번째 문자열 복사해 넣음
		strcpy(tmstr.buf + len, mstr.buf);		// 뒤쪽에 두번째 문자열 복사해 넣음
		return tmstr;
	}
	MyString& operator += (const MyString& mstr) {	// 문자열 연결 연산자 '+=' 다중정의 - 첫번째 문자열 자기자신에 피연산자인 두번째 문자열을 붙임
		if (bufSize < len + mstr.len) {			// 메모리가 부족하면 메모리를 새로 받음
			char* tbuf = new char[(bufSize = len + mstr.len) + 1];
			strcpy(tbuf, buf);			// 자기자신의 문자열을 새로운 메모리로 복사
			delete[] buf;				// 기존 메모리 반납
			buf = tbuf;				// 새로운 메모리의 주소를 기존 buf에 넣어주어 buf가 새로운 메모리 공간을 가르키도록 함
		}
		strcpy(buf + len, mstr.buf);	// 뒤쪽에 두번째 문자열 복사해 넣음
		len += mstr.len;		// 문자열의 길이에 두번째 문자열 길이를 추가
		return *this;
	}
	bool operator == (const MyString& mstr) const {		// == 관계 연산자 다중정의
		// Todo 구현 필요
	}
	bool operator > (const MyString& mstr) const {		// > 관계 연산자 다중정의
		// Todo 구현 필요
	}
	bool operator < (const MyString& mstr) const {		// < 관계 연산자 다중정의
		// Todo 구현 필요
	}
	char& operator [] (int i) {			// 배열 값을 변경할 수 있는 첨자 연산자 다중정의
		// Todo 구현 필요
	}
	char operator [] (int i) const {		// 배열 값을 읽기만 할 수 있는 첨자 연산자 다중정의
		// Todo 구현 필요
	}
	operator char* () const {			// MyString 클래스의 객체를 C스타일 문자열로 변환 - 송신 측 클래스에서 형변환 연산자 정의
		char* pt = new char[length() + 1];	// 메모리 할당 - 문자열 길이 + 1
		strcpy(pt, buf);
		return pt;
	}
	friend std::ostream& operator << (std::ostream& os, const MyString& mstr);		// 스트림 출력 연산자 다중정의 원형 - 좌측 피연산자인 cout이 ostream 클래스의 객체이기 때문에 이 MyString 클래스에서는 정의할 수 없으므로 클래스 외부에 별도로 정의함. 외부에서 클래스 내부의 멤버를 사용할 수 있게 하기 위해 friend로 설정
};

// 스트림 출력 연산자
inline std::ostream& operator << (std::ostream& os, const MyString& mstr) {		// 인라인 inline 함수는 호출 시 일반적인 호출 절차가 아니라 호출하는 위치에 함수가 그대로 들어가게 됨. inline 함수는 번역할 때 소스코드가 필요하므로 헤더 파일에 넣음. inline이 아닌 경우 별도의 cpp 파일에 넣어야 함
	os << mstr.buf;
	return os;
}
```
