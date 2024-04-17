---
layout: post
title:  "Python: Concept"
date:   2024-04-14 09:00:00 +0900
categories: [Python]
---

### Overview of Python   
// 파이썬의 개요   
   
#### The Birth of Python 1   
// 파이썬의 탄생 1   
   
// 히도 판로쉼 (Guido van Rossum) 1991년 개발   
// - 네덜란드 암스테르담 대학에서 컴퓨터 전공   
// - 좋아하는 코미디 'Monty Python's Flying Circus'를 따라 명명   
// - 크리스마스 주 연구실이 잠겨 할일이 없어 만든 프로그래밍 언어   
// - 히도 판로쉼은 이미 10년 전부터 파이썬의 빅 픽쳐를 그리고 있었음   
- Developed by Guido van Rossum in 1991   
  - Computer major at the University of Amsterdam, Netherlands   
  - Named after his favorite comedy, "Monty Python's Flying Circus"   
  - The programming language created by Guido van Rossum, who had nothing to do because his lab was locked down on Christmas   
  - Guido van Rossum has been drawing Python's big picture for 10 years   
   
// 분산 운영 체제 (아메바) 의 시스템 관리를 위한 쉘 스크립팅 언어로 개발   
// - 쉘 (Shell) : 사용자가 입력한 명령어를 해석해서 운영체제 내부의 커널 (Kernel) 에 전달하는 명령 해석기 창   
// - 스크립트 (Script) : 명령어를 순차적으로 나열해서 운영체제가 어떤 순서로 동작해야 하는지 명령어를 집합으로 만들어놓은 형태   
// 파이썬은 이 목적을 위해 만들어진 언어임   
- Developed as a shell scripting language for system management in distributed operating systems (Amoeba)   
  - Shell : Command interpreter window that interprets user-entered commands and delivers them to the kernel inside the operating system   
  - Script : A set of instructions for which the operating system should operate in which order by sequentially listing the instructions   
- Python is a language created for this purpose   
   
#### The Birth of Python 2   
// 파이썬의 탄생 2   
   
// 다중 프로그래밍 패러다임 채용   
// - 정의 : 프로그램을 생성하는 접근 방식   
// - 명령형 프로그래밍, 절차적 프로그래밍, 객체지향 프로그래밍, 함수형 프로그래밍 지원   
// -- 패러다임 (Paradigm) : 현실 세계를 어떠한 방식으로 모델링하는 것에 대한 여러 관점들이 있고, 그 관점들을 규칙화하여 만든 것이 패러다임임   
- Multi-programming paradigm adoption   
  - Definition : Approaches to creating programs   
  - Imperative programming, Procedural programming, Object-oriented programming, Functional programming support   
    - Paradigm : There are many perspectives on modeling the real world in some way, and it is a paradigm created by regularizing those perspectives   
   
// 다목적 활용   
// - 응용 프로그램과 웹, 백 엔드 개발, 사물 인터넷 분야 뿐만 아니라 교육적인 목적으로도 활용   
- Multi-purpose application   
  - Application and Web, Backend Development, Internet of Things, and Educational Purpose   
   
#### Python's Development Process   
// 파이썬의 발전 과정   
   
// 1991년 ABC의 후속 프로그래밍 언어로 시작 (히도 판로쉼이 참여 했음)   
// 1999년 미국 국방고등연구계획국 산하의 다르파 (DARPA : Defense Advanced Research Projects Agency) 에 'Computer Programming for Everybody' 제안서 제출   
// 2000년 파이썬 2.0 출시 : 커뮤니티를 통한 개발 체계 시작   
// 2008년 파이썬 3.0 출시 : 비 하위 호환성을 갖는 메이저 업데이트   
// - 현재도 2.0 버전의 소스코드가 많이 사용되고 있음   
- Starting in 1991 as ABC's subsequent programming language (with Guido van Rossum)   
- 1999 Submission of 'Computer Programming for Everybody' proposal to DARPA (Defense Advanced Research Projects Agency)   
- 2000 Python 2.0 Release : Start the development system through the community   
- 2008 Python 3.0 Release : Major updates with incompatibility   
  - 2.0 version of source code is still widely used   
   
// 파이썬 3.0 을 예로 들면, 정수쪽 3이 업데이트 되는 경우 메이저 업데이트라고 하고, 소수쪽 .0이 업데이트 되는 경우 마이너 업데이트라고 함   
// - 큰 변화가 있는 경우 메이저 업데이트로 하고, 소소한 변화가 있는 경우 마이너 업데이트로 함   
- For example, Python 3.0 is called a major update if the integer side 3 is updated, and a minor update if the decimal side .0 is updated   
  - Major update if there is a big change, minor update if there is a small change   
   
#### The popularity of Python   
// 파이썬의 인기   
   
// 2022년부터 프로그래밍 언어 중 인기 순위 1위를 차지함   
// 데이터 과학분야, 인공지능 분야에서 대부분 파이썬을 사용   
- Ranked No. 1 in popularity among programming languages from 2022   
- Data Science, Artificial Intelligence Most Use Python   
   
<br />
### Characteristics of Python   
// 파이썬의 특징   
   
// 파이썬답다 == 파이써닉 (Pythonic) 하다   
- It's like Python == Pythonic   
   
// 독립적 : 특정 조직에 귀속되지 않음. 특정 플랫폼 (운영체제) 에 종속되지 않음   
// 오픈소스 : 소스 뿐만 아니라 인터프리터도 오픈되어 있음   
// 인간적 : 사람이 사용하는 자연어와 굉장히 유사함   
// 신속성 : 여러 라이브러리와 프레임워크들이 만들어져 있어서 가져와서 바로 프로그래밍하여 사용할 수 있음   
// 직관적 : 생각을 곧바로 어렵지 않게 코드화 할 수 있음   
- Independent : Not attributed to a particular organization. Not dependent on a particular platform (operating system)   
- Open source : Not only the source but also the interpreter is open   
- Human : Very similar to the natural language used by humans   
- Speed : Multiple libraries and frameworks can be brought in and programmed and used immediately   
- Intuitive : You can code your thoughts immediately without difficulty   
   
#### Open Source : Proposals for Python-Related Improvements (PEP : Python Enhance Proposal)   
// 오픈소스 : 파이썬 관련 개선을 위한 제안 (PEP : Python Enhance Proposal)   
   
// 많은 개발자의 의견을 수용하고 토론하며 발전한 언어   
// 새로운 파이썬의 기능, 파이썬 프로세스, 환경에 대해 커뮤니티에 설계 문서나 정보를 제공   
// 파이썬 기능의 간결한 기술적 사양과 기능을 위한 근거들을 제공   
// 커뮤니티의 의견을 수집, 합의 도출, 반대의견 청취   
- A language developed by accepting and discussing the opinions of many developers   
- Provide design documents or information to the community about the features, Python processes, and environment of the new Python   
- Provides a concise technical specifications of Python functionality and grounds for functionality   
- Gather community opinions, reach consensus, and listen to dissenting opinions   
   
// PEP 8 (스타일 가이드) 이 대표적인 PEP 예시임   
- PEP 8 (Style Guide) is a representative example of PEP   
   
#### Human and intuitive   
// 인간적 & 직관적   
   
// 실행할 수 있는 의사 코드 (Executable pseudocode) 수준의 문법   
// 얼핏 보았을 때에도 어느 정도 해석이 가능   
- Executable pseudocode level grammar   
- It can be interpreted at first glance   
   
- Example   
   
```python
# If the list [1, 3, 5, 7] contains 3, print out "There is 3 in it"
if 3 in[1, 3, 5, 7]: print("There is 3 in it")
```
   
#### Productivity & Speed   
// 생산성 & 신속성   
   
- Example   
- C code   
   
```c
int i, n;
int sum = 0;

printf("Input : ");
scanf("%d", &n);

for(i = 0; i < n; i++)
{
    sum += i;
}

print("The sum is %d", sum);
```
   
- Example   
- Python code   
   
```python
n = int(input("Input : "))
sum = 0

for i in range(1, n+1)
    sum += i

print("The sum is" + sum)
```
   
#### A large developer community   
// 대형 개발자 커뮤니티   
   
// 프로그램에서 오류가 발생했는데 해결 방법을 찾지 못했다면 검색을 통해 신속히 해결책을 찾을 수 있음   
- If your program fails and you can't find a solution, search for a solution quickly   
   
#### Libraries and frameworks   
// 라이브러리와 프레임워크   
   
// 숫자를 관리할 수 있는 라이브러리 : NumPy, Numba, SymPy   
// 파이썬 개발 환경 제공 : IPython, jupyter, lab   
// 대형 프로젝트 시 특정 순서대로 개발할 수 있게 해주는 프레임워크 제공 : Flask, dj   
// 수치와 함수 등으로 데이터 결과를 만들어 내고 그래프로 나타낼 수 있게 하는 라이브러리 : matplotlib, Bokeh, pandas   
// 과학기술 분야에서 특화되어 사용할 수 있는 라이브러리 : astropy, biopython, sunpy   
// 딥러닝을 위한 라이브러리 : PyTorch, TensorFlow, scikit-learn, SciPy   
- Library for managing numbers : NumPy, Numba, SymPy   
- Providing Python Development Environment : IPython, jupyter, lab   
- Provides a framework that enables development in a specific order for large projects : Flask, dj   
- A library that allows you to generate and graph data results from numbers and functions, etc. : matplotlib, Bokeh, pandas   
- A library that can be specialized and used in the field of science and technology : astropy, biopython, sunpy   
- Library for deep learning : PyTorch, TensorFlow, scikit-learn, SciPy   
   
<br />
### The downside of Python   
// 파이썬의 단점   
   
// C나 자바 등으로 작성된 프로그램보다 속도가 느림   
- Slower than programs written in C or Java, etc.   
   
// 완전한 애플리케이션 단독 개발이 불가능   
// - 쉘 스크립트 언어 용으로 개발   
// - 모바일 앱 등 응용 애플리케이션 개발 불가능   
- Unable to develop complete applications alone   
  - Developed for Shell Script Language   
  - Unable to develop applications such as mobile apps   
   
<br />
### Running a Python Program   
// 파이썬 프로그램의 실행   
   
#### Python Running Environment   
// 파이썬 실행 환경   
   
// 플랫폼에 독립적   
// - 윈도우, 리눅스, 유닉스, 맥OS 등 다양한 운영체제 (플랫폼) 에서 별도의 컴파일 없이 실행 가능   
// 인터프리터식   
// - CPython, PyPy, Cython, Jython 등 다양한 인터프리터 환경에서 사용 가능. 목적에 따라 사용   
// 객체지향적   
// - 프로그램을 객체로 모델링   
// 동적 타이핑 (dynamically typed)   
// - 변수의 자료형을 지정하지 않음   
// 대화형 언어   
// - 작성한 코드에 대한 수행 결과를 바로 확인하고 디버깅하면서 코드 작성 가능   
- Platform-independent   
  - Runs on a variety of operating systems (platforms) including Windows, Linux, Unix, and macOS without separate compilation   
- Interpreter-style   
  - Available in various interpreter environments such as CPython, PyPy, Cython and Jython. Use according to purpose   
- Object-oriented   
  - Modelling a program as an object   
- Dynamically Typed   
  - Do not specify a data type for a variable   
- Interactive language   
  - You can write the code while checking and debugging the results of the code you created   
   
#### CPython Interpreter   
// CPython 인터프리터   
   
// C 언어로 개발된 파이썬 인터프리터 (소스 대 소스 컴파일러)   
// - C 구현 라이브러리와의 연동을 통한 확장에 최적   
- Python Interpreter Developed in C Language (source-to-source compiler)   
  - Best for expansion through interworking with C implementation library   
   
// 소스 코드를 기계어로 바꾸어주는 방법 두 가지   
// 1. 컴파일러   
// 2. 인터프리터   
- Two ways to turn source code into machine language   
    1. Compiler   
    2. Interpreter   
   
// 컴파일러의 유형 두 가지   
// 1. 셀프 호스팅 컴파일러 : 부트스트래핑 단계를 통해 자신의 언어로 작성한 컴파일러   
// 2. 소스 대 소스 컴파일러 : 타 언어로 작성한 컴파일러   
- Two Types of Compilers   
    1. Self-Hosting Compiler : Compilers written in their own language through bootstrapping steps   
    2. Source-to-source compiler : Compiler written in another language   
   
// 오픈소스이며 커뮤니티의 기여로 지속적 발전   
// - https://github.com/python/cpython   
- Open source and continuous development with community contributions   
  - https://github.com/python/cpython   
   
#### Python program execution process   
// 파이썬 프로그램 실행과정   
   
// 파이썬 애플리케이션은 소스 코드 형태로 배포   
// - CPython이 컴파일 후 바이트코드 .pyc 파일 생성   
// - 파이썬 가상머신은 바이트코드를 한 라인씩 실행   
// - 변경없이 재실행 시 바이트코드로 빠르게 실행   
- Python applications are deployed in the form of source code   
  - CPython generates byte code .pyc file after compilation   
  - Python virtual machines run byte code line by line   
  - Run fast with byte code when rerun without change   
   
// 코드 작성 → 컴파일러 (CPython) → 바이트코드 (.pyc 파일) → 파이썬 가상 머신 (PVM) → 기계어 코드   
- Code writing → Compiler (CPython) → byte code (.pyc file) → Python virtual machine (PVM) → machine language code   
   
<br />
### Python programming environment   
// 파이썬 프로그래밍 환경   
   
#### IDLE   
   
// 파이썬 인터프리터 설치 시 기본으로 설치되는 파이썬의 통합 개발 환경   
// - 파이썬과 Tkinter GUI 툴킷 (윈도우즈 GUI 환경에서 앱을 만들 수 있는 툴킷) 으로 개발   
// - 구문 강조, 자동 완성, 스마트 들여쓰기 등이 포함된 단순한 IDE 지향   
// - stepping, breakpoint, call stack을 확인할 수 있는 통합 디버거 환경 제공   
- Python's integrated development environment installed by default when installing Python interpreters   
  - Developed as a Python and Tkinter GUI toolkit (a toolkit to create apps in a Windows GUI environment)   
  - Simple IDE orientation with syntax emphasis, auto-completion, smart indentation, etc.   
  - Provides an integrated debugger environment where you can check stepping, breakpoint, and call stack   
   
// 파이썬 공식 홈페이지에서 다운로드 가능   
// - http://www.python.org   
- Available for download on Python's official website   
  - http://www.python.org   
   
#### Jupiter Notebook   
// 주피터 노트북   
   
// 오픈소스 기반의 웹 플랫폼   
// - 파이썬을 비롯한 40여개의 프로그래밍 언어 지원   
// - 전통적인 소스코드-컴파일-실행 방식에서 벗어나 웹 기반 대화형 개발 및 실행 환경   
// - 문서화하여 다른 사람과 공유하기가 편리   
// - 마크다운 (Markdown) 을 이용하여 코드 관련 타이틀, 설명 등 작성 가능   
- Open source-based web platform   
  - Support for more than 40 programming languages, including Python   
  - Web-based interactive development and execution environment away from the traditional source code-compile-execution method   
  - Easy to document and share with others   
  - Jupiter Notebook can write code-related titles, descriptions, etc. using the Markdown   
   
// 아나콘다 설치 후 설치 가능. 파이썬 공식 홈페이지에서도 설치 가능   
// - http://www.anaconda.com/   
- Can be installed after installing anaconda. It can also be installed on Python's official website   
  - http://www.anaconda.com/   
   
#### Google Colab   
// 구글 Colab   
   
// Collaboration의 앞글자를 따서 Colab이라는 이름을 만듦   
// 설치를 하지 않고 서버에 다 구축되어 있어서 그저 접속해서 사용하기만 하면 됨   
// 2017년 과학 연구와 교육을 목적으로 개발   
// 클라우드 기반의 주피터 노트북 개발 환경   
// - 주피터 노트북 + 구글 드라이브를 결합한 서비스   
// - 데이터 분석 및 딥러닝 연산 등 고성능 컴퓨팅 리소스 활용 가능   
- Named Colab after the initials of Collaboration   
- Colab is built into the server without installing it, so you just have to connect and use it   
- Developed for Scientific Research and Education in 2017   
- Cloud-based Jupiter Notebook development environment   
  - Jupiter Notebook + Google Drive Combined Services   
  - Leverage high-performance computing resources such as data analysis and deep learning operations   
   
// 사용자 ↔ 웹 브라우저 ↔ Colab (↔ 구글 클라우드) ↔ 구글 드라이브 저장공간 제공   
- User ↔ Web Browser ↔ Colab (↔ Google Cloud) ↔ Google Drive Storage   
   
// 권장하는 웹 브라우저 : Google Chrome, Microsofr Edge 등 크로미움 (chromium) 기반의 브라우저   
- Recommended Web Browser : Chromium-based browsers such as Google Chrome and Microsoft Edge   
   
// 크로미움 (chromium) 기반의 브라우저   
// - 크로미엄 (영어 : Chromium, /ˈkroʊmiəm/) 또는 크로미움, 크로뮴은 브라우저 이름인 동시에 크롬에서 사용하는 소스 코드를 생성하는 오픈소스 프로젝트의 이름이기도 함   
// - 오픈소스이긴 하지만, 크로미움의 주요 지원자는 구글 (Google) 임   
// - 2008년 9월 프로젝트 자체를 시작한 것도 구글임   
// - 오픈소스 프로젝트이기 때문에 구글 직원이 아닌 사람들도 크로미움 프로젝트에 참가할 수 있음   
// - 구글 크롬은 크로미엄 코드를 사용하여 개발됨   
// - 기존 크로미움 소스 코드에서 컴파일 된 브라우저가 크로미움임   
// - 크로미엄은 주로 최신 기술을 시험하는 가늠터의 역할을 하며, 윈도우, macOS, 리눅스, 안드로이드를 지원함   
// - 구글 크롬에는 있지만 크로미엄에는 없는 것은 다음과 같음   
// -- 사용자 식별 인증키 설정 요구사항   
// -- 자동 업데이트   
// -- 사용 정보 및 오류 보고서를 구글로 보내기 선택하기   
// -- 사용 정보 추적   
// -- 구글 크롬과는 다른 별도의 오픈소스 내장 PDF 뷰어   
// -- 구글 크롬과는 다른 별도의 내장 인쇄 미리보기와 인쇄 시스템   
// -- 내장 어도비 플래시 플레이어   
// -- 구글 계정 로그인   
// - 크로미엄 기반의 다른 브라우저   
// -- 구글 크롬 : 구글의 크로미움 공식 버전   
// -- 블리스크 : 윈도우 7용 브라우저   
// -- 브레이브 : 오픈 소스 웹 브라우저   
// -- 코드위버스 크로스오버 크로미엄 : 와인 파생의 비공식 번들   
// -- 코모도 드래곤 : 윈도우 8.1, 8, 윈도우 7, 비스타 32비트 버전의 크로미엄 리브랜드 버전   
// -- Cốc Cốc : 베트남 시장에 주안을 둔 프리웨어 웹 브라우저   
// -- Dartium : 크로미엄 브라우저의 특별한 빌드   
// -- 마이크로소프트 엣지 : 마이크로소프트의 공식 크로미움 릴리즈   
// -- 에픽 브라우저 : 인도의 히든 리플렉스가 개발한 웹 브라우저   
// -- 오페라 : 버전 15부터 크로미엄의 웹 브라우저에 기반을 두기 시작함   
// -- 치후 360 시큐어 브라우저 : 중국 웹 브라우저   
// -- 삼성 인터넷 : 2013년 출시된 갤럭시 S4에 포함된 최초의 크로미엄 기반 브라우저   
// -- 슬레이프니르 : 윈도우와 macOS용 크로미엄 파생 브라우저   
// -- 슬림젯 : 크롬 기반 웹 브라우저   
// -- SR웨어 아이언 : 프리웨어 버전의 크로미엄   
// -- Torch : 윈도우용 크로미엄 기반 브라우저   
// -- 비발디 : 윈도우, macOS, 리눅스용 브라우저   
// -- 얀덱스 브라우저 : 러시아의 소프트웨어 기업 얀덱스가 개발한 브라우저   
// -- 네이버 웨일 : 대한민국의 기업 네이버가 개발한 웹 브라우저   
- Chromium-based browser   
  - Chromium (English : Chromium, /ˈkroʊmiəm/) is both a browser name and also the name of an open-source project that generates the source code used by Chromium   
  - Although open source, the main supporter of Chromium is Google   
  - Google started the project itself in September 2008   
  - Since it is an open-source project, non-Google employees can participate in the Chromium project   
  - Google Chrome is developed using Chromium code   
  - Chromium is the browser compiled from the existing Chromium source code   
  - Chromium primarily serves as a gauge to test the latest technologies, and supports Windows, macOS, Linux, and Android   
  - Here's what's on Google Chrome but not on Chromium   
    - User identification authentication key setting requirements   
    - Automatic updates   
    - Select to send usage information and error reports to Google   
    - Tracking usage information   
    - PDF viewer with a separate open-source embedded, unlike Google Chrome   
    - Separate embedded print previews and printing systems from Google Chrome   
    - Embedded Adobe Flash Player   
    - Log in to Google account   
  - Other Chromium-based browsers   
    - Google Chrome : The official version of Google's Chromium   
    - Blisk : Browser for Windows 7   
    - Brave : Open Source Web Browser   
    - Code Weverse Crossover Cromium : The Unofficial Bundle of Wine Derivatives   
    - Komodo Dragon : Chromium rebrand versions of Windows 8.1, 8, Windows 7, Vista 32-bit versions   
    - Cốc Cốc : Freeware Web browser focused on Vietnam market   
    - Dartium : Special Builds of a Chromium Browser   
    - Microsoft Edge : Microsoft's Official Chromium Release   
    - Epic Browser : Web Browser Developed by India's Hidden Reflex   
    - Opera : version 15 starts to be based on Chromium's web browser   
    - Qihoo 360 Secure Browser : Chinese Web Browser   
    - Samsung Internet : The first Chromium-based browser included in the Galaxy S4 released in 2013   
    - Sleipnir : Chromium Derived Browser for Windows and macOS   
    - SlimJet: Chrome-based Web Browser   
    - SRWare Iron: Chromium of Freeware Version   
    - Torch : Chromium-based browser for Windows   
    - Vivaldi : Browser for Windows, macOS, and Linux   
    - Yandex Browser : Browser developed by Russian software company Yandex   
    - Naver Whale : Web browser developed by South Korean company Naver   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
