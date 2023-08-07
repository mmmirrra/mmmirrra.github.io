---
layout: post
title:  "Eclipse: shortcut keys, hot keys"
date:   2023-08-04 09:00:00 +0900
categories: [Eclipse]
thumbnail: /assets/profile.png
---

### 단축키 변경 메뉴   
`Window >> Preferences >> General >> Keys` : 이클립스의 모든 단축키를 확인 및 변경할 수 있음   
   
<br />
### 단축키 힌트 보기   
`Ctrl + Shift + L` : See hints for Eclipse shortcuts (Eclipse 바로 가기의 힌트 보기)   
   
<br />
### 편집   
`Tab` : 들여쓰기   
`Shift + Tab` : 내어쓰기   
`Ctrl + Z` : 실행취소   
`Ctrl + Y` : 실행취소 되돌리기   
`Ctrl + D` : 한줄 삭제   
`Ctrl + Shift + Del` : 줄 끝까지 삭제   
`Ctrl + Del` : 다음 요소 삭제   
`Ctrl + Backspace` : 이전 요소 삭제   
`Ctrl + Shift + Enter` : 현재 줄에 새줄 추가   
`Shift + Enter` : 다음줄에 새줄 추가   
`Alt + 방향키 ↑/↓` : 현재라인(선택된 블럭)을 한단계 위로/아래로 이동 (위/아래 줄과 바꾸기)   
`Ctrl + Alt + 방향키 ↑/↓` : 현재라인(선택된 블럭) 복사하여 위로/아래로 붙여넣기   
`Ctrl + Shift + X` : 대문자로 변경   
`Ctrl + Shift + Y` : 소문자로 변경   
`Ctrl + +/-` : 폰트 사이즈 한단계 크게/작게 수정   
`Alt + Shift + A` : 세로 편집모드 집입/해제   
`Alt + Shift + R` : 같은 변수 이름 한꺼번에 변경 (rename)   
`Ctrl + 2 + R` : 로컬 파일에서 이름 바꾸기 Rename 리팩토링   
`Ctrl + 2 + L or F` : 새 지역 변수 또는 필드에 명령문 할당   
   
<br />
### 자동완성   
`Ctrl + Space` : 코드 자동완성 어시스트 (Content Assistance) (입력하는 도중엔 언제라도 강제 호출 가능함)   
`Ctrl + Shift + O` : 해당 소스에 필요한 패키지를 자동 import 추가, 안쓰는 import 삭제   
`Ctrl + Shift + M` : 해당 객체에 커서를 놓고 키를 누르면 필요한 특정 클래스 Import 구문 자동 생성   
   
<br />
### 자동완성 템플릿 이용   
자동완성 키워드 등록 위치 : `윈도우 - 환경설정 - 자바 - 편집기 - 템플리트` (`Window - Preferences - Java - Editor - Templates`)   
(예시) sysout 입력후 'Ctrl + Space'를 누르면 'System.out.println();' 으로 변경됨   
(예시) try 입력 후 'Ctrl + Space'를 누르면 'try-catch 문' 자동완성   
(예시) for 입력 후 'Ctrl + Space'를 누르면 'for 문' 자동완성   
(예시) switch 입력 후 'Ctrl + Space'를 누르면 'switch 문' 자동완성   
(예시) while 입력 후 'Ctrl + Space'를 누르면 'while 문' 자동완성   
(예시) do 입력 후 'Ctrl + Space'를 누르면 'do-while 문' 자동완성   
   
<br />
### 자동완성 어시스트 트리거 문자 등록 위치   
`Window - Preferences - Java - Editor - Content Assist - Auto Activation - Auto activation triggers for java → .abcdefghijklmnopqrstuvwxyz`   
   
<br />
### 메소드 쉽게 생성하는 방법   
1. 클래스의 멤버를 일단 먼저 생성   
2. override 메소드를 구현하려면 : 소스->메소드대체/구현 에서 해당 메소드를 체크   
3. 기타 클래스의 멤버가 클래스의 오브젝트라면 : 소스->위임메소드 생성에서 메소드를 선택   
   
<br />
### 해결방법   
`Ctrl + 1` : 빨간줄(에러) 해결방법 도우미 (컴파일 에러가 발생한 곳에서 Ctrl + 1을 누르면 컴파일 에러에 대한 해결책을 제시)  
`F2` : 컴파일 에러 줄에 커서를 놓고 이 키를 누르면 에러 힌트 표시   
`Shift + F2` : 선택한 유형/클래스/메서드에 대한 Javadoc 표시   
   
<br />
### 정렬   
`Ctrl + Shift + F` : 자동 코드 정렬   
`Ctrl + i` : 선택된 블럭내 코드 자동 들여쓰기   
   
<br />
### 주석   
`Ctrl + /` : 현재라인(선택된 블럭) 주석 적용/해제 (//) (Word Completion)   
`Ctrl + Shift + /` : 선택된 블럭 블럭주석(Block Comment) 적용 (/* */)   
`Ctrl + Shift + \` : 블럭주석(Block Comment) 해제   
`Alt + Shift + J` : 해당 메서드/클래스에 대한 주석 템플릿 생성, 설정해 둔 기본주석을 자동으로 달기 (메소드나 멤버변수에 포커스를 두고 실행)   
   
<br />
### 블록 설정   
`Shift + End` : 현재 커서부터 끝까지 블록 설정   
`Shift + Home` : 현재 커서부터 처음까지 블록 설정   
`Ctrl + A` : 전체 블록 설정   
`Alt + Shift + 방향키(←/↑/→/↓)` : 이미 선택되어 있는 블록을 방향키로 늘림   
`Alt + Shift + Z` : 구문 블록을 감싸는 메뉴 제공 (예시: try/catch)   
   
<br />
### 보기   
`Ctrl + M` : 전체 화면으로 보기   
`F4` : 클래스 계층 (Hierarchy) 보기 (클래스명을 선택하고 F4를 누르면 해당 클래스의 상속 계층 확인)   
`Ctrl + T` : 상속 계층 팝업 창 보기 (인터페이스 구현 클래스간 이동 시 편리)   
`Ctrl + O` : 해당 소스의 클래스 구조 트리 Outline 창 보기   
`Ctrl + Shift + Space` : 메소드 괄호에 커서를 놓고 이 키를 누르면 파라미터 힌트 보여줌   
`Alt + Shift + S` : 실행 가능한 메뉴 목록 창 보기(Import 추가, Comment 추가, Generator 메뉴 등)   
`Shift + F10` : 상황에 맞는 메뉴 목록 창 보기(Mouse2에 해당하는 키보드)   
`Ctrl + F10` : 현재 보기에 대한 메뉴 목록 창 보기   
`Ctrl + 3` : 빠른 액세스 (Quick Access) (Eclipse에서 사용 가능한 모든 작업 보기)   
`해당 프로젝트에서 Alt + Enter` : Project 속성 보기   
`Alt + Shift + Q + P` : 패키지 탐색기 표시   
`Alt + Shift + Q + C` : 콘솔 표시   
   
<br />
### 찾기   
`Ctrl + F` : 찾기/변경 (fine/replace) (해당 소스에서만)   
`Ctrl + H` : 찾기/변경 (fine/replace) (모든 파일, 프로젝트 전체에서 검색)   
`Ctrl + Shift + R` : 모든 프로젝트의 전체 리소스에서 파일 찾기   
`Ctrl + Shift + T` : Jar 포함 클래스 찾기   
`Ctrl + Alt + H` : 특정 클래스 호출 위치 찾기   
`Ctrl + Shift + G` : 현재 커서가 위치한 특정 메서드나 객체, 필드를 쓰는 곳, 참조하는(Reference) 곳 표시   
`Ctrl + K` : 앞으로 찾기 (현재 라인 밑으로 찾기) 또는 찾고자 하는 문자열을 블록으로 지정하고 찾기   
`Ctrl + Shift + K` : 뒤로 찾기 (현재 라인 위로 찾기)   
`Ctrl + J` : 검색할 단어를 입력하면서 실시간으로 검색   
`Ctrl + Shift + J` : 검색할 단어를 입력하면서 실시간으로 거꾸로 검색   
   
<br />
### 이동
`Ctrl + 방향키 ←/→` : 다음/이전 문자로 이동   
`Alt + 방향키 ←/→` : 이전/다음 작업 위치로 이동   
`Ctrl + .` : 다음 오류, 에러, 워닝, 북마트 (annotation)로 이동   
`Ctrl + ,` : 이전 오류, 에러, 워닝, 북마트 (annotation)로 이동   
`Ctrl + Shift + P` : 일치하는 괄호로 이동   
`Ctrl + Shift + Down` : Java Editor의 클래스 내에서 다음 멤버로 이동   
`Ctrl + 클릭 or F3` : 변수나 메소드 선언부로 이동   
`F3` : 해당 메서드나 클래스가 정의된 곳으로 이동   
`Ctrl + L` : 특정 줄 번호로 이동   
`Ctrl + Q` : 마지막 편집 위치로 이동   
`Ctrl + E` : 열려져 있는 파일목록 미니창으로 보기 → 선택시 해당 파일로 이동   
`Ctrl + Shift + E` : 에디터 안에서 열린 파일간의 이동   
`Ctrl + F6` : 에디터 안에 열린 파일간 이동, F6을 누를 때마다 하나씩 순차적으로 이동   
`Ctrl + PageUp/PageDown` : 이전/다음에 열린 편집기 Edit로 이동   
`F12` : 컴파일 중 에러 등 으로 포커스가 다른데로 갔을 때 Editor 창으로 커서 이동   
   
<br />
### 윈도우 window 이동   
`Ctrl + F7` : 다음 View로 이동   
`Ctrl + Shift + F7` : 이전 View로 이동   
`Ctrl + F8` : 다음 퍼스펙티브 Perspective로 이동   
`F10` : 메뉴창을 활성화   
`Ctrl + N` : 새로운 파일 및 프로젝트 생성   
   
<br />
### 저장   
`Ctrl + S` : 소스코드 저장 (현재 파일만)   
`Ctrl + Shift + S` : 열려진 모든 소스코드 저장   
   
<br />
### 닫기   
`Ctrl + W` : 파일 닫기   
`Ctrl + Shift + F4` : 열린 파일을 모두 닫음   
   
<br />
### 빌드   
`Ctrl + B` : 빌드   
   
<br />
### 실행   
`Ctrl + F11` : 소스 실행 run (에러가 났을 때 디버깅 하지 않음)   
`Alt + Shift + X + R` : 서버 실행 (Run on Server)   
   
<br />
### 디버깅   
디버깅 하면서 소스를 수정하고 프로그램을 다시 시작할 필요 없이 계속 디버깅을 진행 할 수 있음. 단, 메소드를 추가하거나 필드를 추가하면 프로그램을 다시 시작해야 함   
디버깅 할 때 해당 라이브러리의 소스코드를 첨부하지 않으면 진행상황을 볼 수 없는 경우 해당 라이브러리에 소스코드를 첨부할 수 있음 : `해당 프로젝트 -> 특성 -> Java 빌드경로 -> 라이브러리 -> 소스참조 -> 편집 버튼을 눌러서 첨부`   
`F11` : 디버깅 실행 (에러가 났을 때 디버깅 함)   
`F8` : Resume 멈추어 있던 디버깅을 다시 계속 실행   
`F7` : Step Return 현재 메소드에서 리턴한 직후에 다시 멈춤   
`F6` : 한 줄씩 디버깅 step over (현재 명령문을 실행하고 다음 명령문 직전에 다시 멈춤)   
`F5` : 한 줄씩 디버깅할 때 함수인 경우 함수 내부까지 디버깅 step into (자바 라이브러리 클래스 수준까지 들어가므로 단계필터 사용을 체크(Shift+F5)를 하면 필터를 설정한 클래스에 대하서는 Step Over 기능과 같은 기능을 수행)   
`Ctrl + Shift + B` : 커서 줄에 중단점(Break point) 설정/해제   
`Ctrl + Alt + B` : 코드 재로딩을 위해 디버그 모드를 사용하고 모든 중단점을 건너뜀   
`Ctrl + R` : 현재 라인까지 실행 Run to Line   
`Alt + Shift + X + J` : 현재 선택한 클래스를 Java 응용 프로그램으로 실행   
`Alt + Shift + X + T` : JUnit 테스트 실행   
`Alt + Shift + X + P` : JUnit 플러그인 테스트 실행   
`Display view(표시)` : '창 -> 보기표시 -> 표시' 선택하여 소스상에서 필요한 부분을 선택해서 실행시켜 볼 수 있음 (한 순간의 값만 필요할 때 볼 수 있음)   
`Expression view(표현식)` : '마우스 오른버튼 -> 감시 표시식 추가' 선택하여 복잡한 식 혹은 객체를 디버깅 하면서 값이 변하는 것을 계속 볼 수 있음. '환경설정 -> 자바 -> 디버그 -> 세부사항 포멧터 선택' 후 보기 편한 식으로 편집하면 Expression View 에서 결과를 실시간으로 확인 할 수 있음   
   
<br />
### 스크랩북   
스크랩북을 이용하면 자바파일을 만들어 테스트 해보지 않고도 간단하게 테스트 해 볼 수 있음 : `패키지 탐색기에서 신규 -> 기타 -> 자바 -> 자바 실행/디버그 -> 스크랩북 페이지 선택`   
   
<br />
### 리팩토링 Refactoring   
Pull Down : 수퍼클래스의 멤버나 메소드를 하위 클래스로 내리는 행위   
Push Up : 하위 클래스의 멤버나 메소드를 상위 클래스로 올리는 행위   
`Alt + Shift + 알파벳` : Refactoring을 위한 단축키 임   
`Alt + Shift + T` : 상황에 맞는 실행 가능한 리펙토링 메뉴 보기(예시: 디스플레이)   
   

https://www.crocus.co.kr/1614   
   
https://yooniron.tistory.com/44   
   
https://jhnyang.tistory.com/entry/%EC%9D%B4%ED%81%B4%EB%A6%BD%EC%8A%A4-%EB%8B%A8%EC%B6%95%ED%82%A4   
   
https://nhj12311.tistory.com/402   
   
https://iamfreeman.tistory.com/entry/Eclipse-%EB%8B%A8%EC%B6%95%ED%82%A4-%EB%AA%A8%EC%9D%8C-%EC%9D%B4%ED%81%B4%EB%A6%BD%EC%8A%A4-Effective-Eclipse-Shortcut-Keys#google_vignette   
   
assets의 엑셀 내용 업데이트 하기   
