---
layout: post
title:  "Eclipse: shortcut keys, hot keys"
date:   2023-08-04 09:00:00 +0900
categories: [Eclipse]
---

### Keys Change Menu // 단축키 변경 메뉴   
`Window >> Preferences >> General >> Keys` : All keys in Eclipse can be checked and changed   
// 이클립스의 모든 단축키를 확인 및 변경할 수 있음   
   
<br />
### Show Key Assist // 단축키 힌트 보기   
`Ctrl + Shift + L` : Show Key Assist   
// 단축키 힌트 보기   
   
<br />
### Editing // 편집   
`Tab` : Indent   
// 들여쓰기   
`Shift + Tab` : Outdent   
// 내어쓰기   
`Ctrl + Z` : Undo   
// 실행취소   
`Ctrl + Y` : Redo   
// 실행취소 되돌리기   
`Ctrl + D` : Delete Line   
// 한줄 삭제   
`Ctrl + Shift + Delete` : Delete to End of Line // 줄 끝까지 삭제   
`Ctrl + Delete` : Delete Next Word // 다음 요소 삭제   
`Ctrl + Backspace` : Delete Previous Word // 이전 요소 삭제   
`Ctrl + Shift + Enter` : Insert Line Above Current Line // 현재 줄에 새줄 추가   
`Shift + Enter` : Insert Line Below Current Line // 다음줄에 새줄 추가   
`Alt + arrow keys ↑/↓ up/down` : Move Lines up/down // 현재라인(선택된 블럭)을 한단계 위로/아래로 이동 : 위/아래 줄과 바꾸기   
`Ctrl + Alt + arrow keys ↑/↓ up/down` : Copy and Paste the Line (selected blocks) up/down // 현재라인(선택된 블럭) 복사하여 위로/아래로 붙여넣기   
`Ctrl + Shift + X` : To Upper Case // 대문자로 변경   
`Ctrl + Shift + Y` : To Lower Case // 소문자로 변경   
`Ctrl + +/-` : Modify font size one step larger/smaller // 폰트 사이즈 한단계 크게/작게 수정   
`Alt + Shift + A` : Enter edit mode to select vertical blocks // 세로 블럭 드래그 가능한 편집모드 집입/해제   
`Alt + Shift + R` : Rename - Refactoring : Rename the same variable at once : Preview allows you to preview variables that change // 같은 변수의 이름을 한번에 변경 : 변경되는 변수를 Preview로 미리볼 수 있음   
`Ctrl + 2 + R` : Quick Assist - Rename in file // 로컬 파일에서 이름 바꾸기   
`Ctrl + 2 + L` : Quick Assist - Assign to local variable // 새 지역 변수에 명령문 할당   
`Ctrl + 2 + F` : Quick Assist - Assign to field // 새 지역 필드에 명령문 할당   
   
<br />
### Alignment // 정렬   
`Ctrl + Shift + F` : Format : Format the contents of the code according to the grammar template : Automatic code alignment, such as indent // 코드 자동 정리 : 코드 내용을 문법 템플릿에 맞게 포맷팅 함 : 들여쓰기 등 자동 코드 정렬   
`Ctrl + i` : Indent Line // 선택된 블럭내 코드 자동 들여쓰기   
   
<br />
### Automatic completion // 자동완성   
`Ctrl + Space` : Content Assist : It can be enforced at any time while the code is being entered // 코드 자동완성 어시스트 : 입력하는 도중엔 언제라도 강제 호출 가능함   
`Ctrl + Shift + O` : Organize Imports // 해당 소스에 필요한 패키지를 자동 Import 추가, 안쓰는 Import 삭제   
`Ctrl + Shift + M` : Add Import : Position the cursor on the object and press the key to automatically generate the required Specific Class Import // 해당 객체에 커서를 놓고 키를 누르면 필요한 특정 클래스 Import 구문 자동 생성   
   
<br />
### How to use AutoComplete templates // 자동완성 템플릿 이용   
Menu to register auto-complete keywords : `Window - Preferences - Java - Editor - Templates` // (예시) 자동완성 키워드 등록 위치 : `윈도우 - 환경설정 - 자바 - 편집기 - 템플리트`   
(Example) Type 'sysout' and press 'Ctrl + Space' to change to 'System.out.println();' // (예시) sysout 입력 후 'Ctrl + Space'를 누르면 'System.out.println();' 자동완성   
(Example) Type 'try' and press 'Ctrl + Space' to auto-complete to 'try-catch function' // (예시) try 입력 후 'Ctrl + Space'를 누르면 'try-catch 문' 자동완성   
(Example) Type 'for' and press 'Ctrl + Space' to auto-complete to 'for function' // (예시) for 입력 후 'Ctrl + Space'를 누르면 'for 문' 자동완성   
(Example) Type 'switch' and press 'Ctrl + Space' to auto-complete to 'switch function' // (예시) switch 입력 후 'Ctrl + Space'를 누르면 'switch 문' 자동완성   
(Example) Type 'while' and press 'Ctrl + Space' to auto-complete to 'while function' // (예시) while 입력 후 'Ctrl + Space'를 누르면 'while 문' 자동완성   
(Example) Type 'do' and press 'Ctrl + Space' to auto-complete to 'do-while function' // (예시) do 입력 후 'Ctrl + Space'를 누르면 'do-while 문' 자동완성   
   
<br />
### Menu to register auto activation assist triggers keywords // 자동완성 어시스트 트리거 문자 등록 위치   
`Window - Preferences - Java - Editor - Content Assist - Auto Activation - Auto activation triggers for java → .abcdefghijklmnopqrstuvwxyz`   
   
<br />
### How to easily create a method // 메소드 쉽게 생성하는 방법   
1. First, create a member of the class // 클래스의 멤버를 일단 먼저 생성   
2. To implement an Override method : check the method in 'Source - Method replacement/implementation' // Override 메소드를 구현하려면 : '소스 - 메소드대체/구현'에서 해당 메소드를 체크   
3. If the member of the other class is an object of the class : select the method from 'Source - Create Delegation Method' // 기타 클래스의 멤버가 클래스의 오브젝트라면 : '소스 - 위임메소드 생성'에서 메소드를 선택   
   
<br />
### How to set the source code format and common comment // 소스 코드 형식 및 공통 주석 설정 방법   
1. `Window - Preferences - Java - Code Style - Code Formatter - Import - profile.xml` // `환경설정 - 자바 - 코드 스타일 - 코드 포멧터 - 가져오기 - 프로파일.xml 을 불러서 사용`   
2. To apply a profile to many Java files, select a package in the Package Explorer and select 'Source - Format' to use // 다수의 자바파일에 프로파일을 적용하려면 패키지 탐색기에서 패키지를 선택한 후 '소스 - 형식화'를 선택하여 사용   
3. `Window - Preferences - Java - Code Style - Code Templates - Import - template.xml` // `환경설정 - 자바 - 코드 스타일 - 코드 템플리트 - 가져오기 - 템플리트.xml 을 불러서 사용`   
   
<br />
### Comment // 주석   
`Ctrl + /` : Toggle Line Comment (`//`) : Comment to the current line // 라인주석 (`//`) : 현재 라인(선택된 블럭)에 주석 적용/해제   
`Ctrl + Shift + /` : Apply Block Comment (`/* */`) : Block Comment to the selected blocks // 블럭주석 (`/* */`) : 현재 선택된 블럭에 블럭주석 적용   
`Ctrl + Shift + \` : Remove Block Comment (`/* */`) // 블럭주석 해제   
`Alt + Shift + J` : Add Javadoc Comment : Create an Comment template for that method/class, or automatically apply the default Comment you have set up (Press with focus on method or member variables) // 해당 메서드/클래스에 대한 주석 템플릿 생성, 설정해 둔 기본주석을 자동으로 달기 (메소드나 멤버변수에 포커스를 두고 실행)   
   
<br />
### Select Block // 블록 설정   
`Shift + Home` : Select Line Start // 현재 커서부터 처음까지 블록 설정   
`Shift + End` : Select Line End // 현재 커서부터 끝까지 블록 설정   
`Ctrl + A` : Select All // 전체 블록 설정   
`Alt + Shift + arrow keys ←/↑/→/↓ left/up/right/down` : Select Next/Previous Element // 이미 선택되어 있는 블록을 방향키로 늘림   
`Alt + Shift + Z` : Surround With Quick Menu : A menu appears that surrounds the block for a try/catch function or for function, do function, while function, etc function // try/catch 문이나 for , do, while 등을 해당 블록에 감싸주는 메뉴가 나타남   
   
<br />
### How to Fix it // 해결 방법   
`Ctrl + 1` : Quick Fix : If you press 'Ctrl + 1' in the code where the compilation error occurred, it will provide a solution to the compilation error // 빨간줄(에러) 해결 방법 도우미 : 컴파일 에러가 발생한 곳에서 Ctrl + 1을 누르면 컴파일 에러에 대한 해결책을 제시   
`F2` : Show Tooltip Description : If you place the cursor on the code where the compilation error occurred and press this key, an error hint is displayed // 컴파일 에러 줄에 커서를 놓고 이 키를 누르면 에러 힌트 표시   
`Shift + F2` : Open External Documentation // 선택한 유형/클래스/메서드에 대한 Javadoc 표시   
   
<br />
### Show View // 보기   
`Ctrl + M` : Maximize Active View or Editor // 전체 화면으로 보기   
`F4` : Open Type Hierarchy : Select the class and press F4 to see the inheritance hierarchy for that class // 클래스 계층 보기 : 클래스명을 선택하고 F4를 누르면 해당 클래스의 상속 계층 확인   
`Ctrl + T` : Quick Hierarchy : Convenient for moving between classes with interfaces // 상속 계층 팝업 창 보기 : 인터페이스 구현 클래스간 이동 시 편리   
`Ctrl + O` : Quick Outline // 해당 소스의 클래스 구조 트리 Outline 창 보기   
`Ctrl + Shift + Space` : Context Information // 메소드 괄호에 커서를 놓고 이 키를 누르면 파라미터 힌트 보여줌   
`Alt + Shift + S` : Show Source Quick Menu : Add import, add comment, generator menu, etc // 실행 가능한 메뉴 목록 창 보기 : Import 추가, Comment 추가, Generator 메뉴 등   
`Shift + F10` : View the context menu list : Keyboard corresponding to Mouse2 // 상황에 맞는 메뉴 목록 창 보기 : Mouse2에 해당하는 키보드   
`Ctrl + F10` : Show Ruler Context Menu // 현재 보기에 대한 메뉴 목록 창 보기   
`Ctrl + 3` : Quick Access : View all the actions available in Eclipse // 빠른 액세스 : 이클립스에서 사용 가능한 모든 작업 보기   
`Press Alt + Enter in the project` : View Project Properties // `해당 프로젝트에서 Alt + Enter 누르기` : 프로젝트 속성 보기   
`Alt + Shift + W` : Show In Menu : Project Explorer, Terminal, Coverage, Package Explorer, Outline, System Explorer, Properties // 각종 탐색 메뉴 목록 보기   
`Alt + Shift + Q + P` : Java Package Explorer // 패키지 탐색기 표시   
`Alt + Shift + Q + C` : Console // 콘솔 표시   
   
<br />
### Find // 찾기   
`Ctrl + F` : Find and Replace : Find only from that source // 찾기/변경 : 해당 소스에서만   
`Ctrl + H` : Find and Replace : Open Search Dialog : Search all files, across projects // 찾기/변경 : 찾기 창 열림 : 모든 파일, 프로젝트 전체에서 검색   
`Ctrl + Shift + R` : Open Resource : Find files from all resources in all projects // 모든 프로젝트의 전체 리소스에서 파일 찾기   
`Ctrl + Shift + T` : Open Type : Find classes in all files, including Jar // Jar 포함 클래스 찾기   
`Ctrl + Alt + H` : Open Call Hierarchy // 특정 클래스 호출 위치 찾기   
`Ctrl + Alt + G` : Find Text in Workspace // Workspace 에서 문자 찾기   
`Ctrl + Shift + G` : References in Workspace // 현재 커서가 위치한 특정 메서드나 객체, 필드를 쓰는 곳, 참조하는 곳 표시   
`Ctrl + K` : 'Find Next' or 'Select the text you want to find and find it' // 앞으로 찾기 (현재 라인 밑으로 찾기) 또는 찾고자 하는 문자열을 블록으로 지정하고 찾기   
`Ctrl + Shift + K` : Find Previous // 뒤로 찾기 (현재 라인 위로 찾기)   
`Ctrl + J` : Incremental Find : The status bar displays 'Incremental find', pressing one letter at a time moves to a matching string within the code, pressing Ctrl + J again to navigate to the matching string with the up/down arrow keys // 검색할 단어를 입력하면서 실시간으로 검색 : 이클립스 하단 상태 표시줄에 Incremental find 라고 표시되어 한 글자씩 누를 때 마다 코드내의 일치하는 문자열로 이동, 다시 Ctrl + J 를 누르면 그 문자열과 일치하는 부분을 위/아래 방향키로 탐색이 가능   
`Ctrl + Shift + J` : Incremental Find Reverse // 검색할 단어를 입력하면서 실시간으로 거꾸로 검색   
   
<br />
### Move // 이동   
`Ctrl + arrow keys ←/→ left/right` : Next/Previous Word // 다음/이전 문자로 이동   
`Alt + arrow keys ←/→ left/right` : Backward/Forward History // 이전/다음 작업 위치로 이동   
`Ctrl + .` : Next Error or Warning or Annotation // 다음 오류, 에러, 워닝, 북마트로 이동   
`Ctrl + ,` : Previous Error or Warning or Annotation // 이전 오류, 에러, 워닝, 북마트로 이동   
`Ctrl + Shift + P` : Go to Matching Bracket // 일치하는 괄호 ( '{', '}' ) 여는/닫는 부분으로 이동   
`Ctrl + Shift + arrow keys ↓ down` : Go to Next Member // Java Editor의 클래스 내에서 다음 멤버로 이동   
`Ctrl + Click or F3` : Open Structure // 변수나 메소드 선언부로 이동   
`F3` : Open Declaration // 해당 메서드나 클래스가 정의된 곳으로 이동   
`Ctrl + L` : Go to Line // 특정 줄 번호로 이동   
`Ctrl + Q` : Last Edit Location // 마지막 편집 위치로 이동   
`Ctrl + E` : Quick Switch Editor // 에디터 안에서 열린 파일 목록을 미니창으로 확인 후 원하는 파일로 이동   
`Ctrl + Shift + E` : Switch to Editor // 에디터 안에서 열린 파일 목록을 큰 창으로 확인 후 원하는 파일로 이동   
`Ctrl + F6` : Next Editor : Move one by one each time F6 is pressed // 에디터 안에 열린 파일간 이동 : F6을 누를 때마다 하나씩 순차적으로 이동   
`Ctrl + PageUp/PageDown` : Next Editor // 이전/다음에 열린 편집기 Edit로 이동   
`F12` : Activate Editor // 컴파일 중 에러 등 으로 포커스가 다른데로 갔을 때 Editor 창으로 커서 이동   
   
<br />
### Move Windows // 윈도우 이동   
`Ctrl + F7` : Next View // 다음 뷰로 이동   
`Ctrl + Shift + F7` : Previous View // 이전 뷰로 이동   
`Ctrl + F8` : Next Perspective // 다음 퍼스펙티브로 이동   
`F10` : Activate the menu list // 메뉴창을 활성화   
`Ctrl + N` : New File or Project // 새로운 파일 및 프로젝트 생성   
   
<br />
### Save // 저장   
`Ctrl + S` : Save : Save Current Files Only // 소스코드 저장 : 현재 파일만   
`Ctrl + Shift + S` : Save All : Save all open source code // 열려진 모든 소스코드 저장   
   
<br />
### Close // 닫기   
`Ctrl + W` : Close User Assistance Tray // 파일 닫기   
`Ctrl + Shift + F4` : Close All // 열린 파일을 모두 닫음   
   
<br />
### Build // 빌드   
`Ctrl + B` : Build All // 빌드   
   
<br />
### Run // 실행   
`Ctrl + F11` : Run Last Launched : Do not debug when errors occur // 소스 실행 : 에러가 났을 때 디버깅 하지 않음   
`Alt + Shift + X + R` : Run on Server // 서버 실행   
   
<br />
### Debugging // 디버깅   
`Concept 1` : You can modify the source while debugging, and continue debugging without having to restart the program. However, if you add a method or field, you must restart the program // `개념 1` : 디버깅 하면서 소스를 수정하고 프로그램을 다시 시작할 필요 없이 계속 디버깅을 진행 할 수 있음. 단, 메소드를 추가하거나 필드를 추가하면 프로그램을 다시 시작해야 함   
`Concept 2` : When debugging, you can attach the source code to the library if you do not attach the source code for that library and cannot see the progress : `project - properties - Java Build Path - Libraries - Source - Attach by pressing the edit button` // `개념 2` : 디버깅 할 때 해당 라이브러리의 소스코드를 첨부하지 않으면 진행상황을 볼 수 없는 경우 해당 라이브러리에 소스코드를 첨부할 수 있음 : `해당 프로젝트 - 특성 - Java 빌드경로 - 라이브러리 - 소스참조 - 편집 버튼을 눌러서 첨부`   
`F11` : Debug Last Launched : Debug when error occurs // 디버깅 실행 : 에러가 났을 때 디버깅 함   
`F8` : Resume // 멈추어 있던 디버깅을 다시 계속 실행   
`F7` : Step Return // 현재 메소드에서 리턴한 직후에 다시 멈춤   
`F6` : Step over : Run the current function and stop again just before running the next function // 한 줄씩 디버깅 : 현재 명령문을 실행하고 다음 명령문 직전에 다시 멈춤   
`F5` : Step into : When debugging one line at a time, Debug it to the inside of the function if it is a function : Because it reaches the Java library class level, checking 'Use Step Filter' (Shift+F5) performs the same function as Step Over for the class where you set the filter // 한 줄씩 디버깅할 때 함수인 경우 함수 내부까지 디버깅 : 자바 라이브러리 클래스 수준까지 들어가므로 단계필터 사용을 체크(Shift+F5) 하면 필터를 설정한 클래스에 대해서는 Step Over 기능과 같은 기능을 수행   
`Ctrl + Shift + B` : Toggle Line Breakpoint // 커서 줄에 중단점 설정/해제   
`Ctrl + Alt + B` : Enable debug mode for code reload, skipped all breakpoints // 코드 재로딩을 위해 디버그 모드를 사용하고 모든 중단점을 건너뜀   
`Ctrl + R` : Run to Line // 현재 라인까지 실행   
`Alt + Shift + X + J` : Run Java Application // 현재 선택한 클래스를 Java 응용 프로그램으로 실행   
`Alt + Shift + X + T` : Run JUnit Test // JUnit 테스트 실행   
`Alt + Shift + X + P` : Run JUnit Plug-in Text // JUnit 플러그인 테스트 실행   
`Display view` : 'Window - Show View - Other - Debug - Display' Lets you select the required parts of the source and try to run them : Can be viewed when only one moment's value is needed // '창 - 보기표시 - 기타 - 디버그 - 표시' 선택하여 소스상에서 필요한 부분을 선택해서 실행시켜 볼 수 있음 : 한 순간의 값만 필요할 때 볼 수 있음   
`Expression view` : Select 'Right mouse button - Add Watch Expression' in the Expressions window to continue to see values changing while debugging complex expressions or objects. Select 'Preferences - Java - Debug - Detail Formatters' and edit it in a viewable way to view the results in real time in Expression View // 표현식 창에서 '마우스 오른쪽 버튼 - 감시 표시식 추가' 선택하여 복잡한 식 혹은 객체를 디버깅 하면서 값이 변하는 것을 계속 볼 수 있음. '환경설정 - 자바 - 디버그 - 세부사항 포멧터' 선택 후 보기 편한 식으로 편집하면 Expression View 에서 결과를 실시간으로 확인 할 수 있음   
   
<br />
### Scrapbook // 스크랩북   
`Concept 1` : Using a scrapbook, you can easily test a Java file without having to test it : `Package Explorer - New - Etc - Java - Java Run/Debug - Select a scrapbook page` // `개념 1` : 스크랩북을 이용하면 자바파일을 만들어 테스트 해보지 않고도 간단하게 테스트 해 볼 수 있음 : `패키지 탐색기에서 신규 - 기타 - 자바 - 자바 실행/디버그 - 스크랩북 페이지 선택`   
   
<br />
### Refactoring // 리팩토링   
`Concept 1 : Pull Down` : Lowering a member or method of a super class to a lower class // `개념 1 : Pull Down` : 슈퍼 클래스의 멤버나 메소드를 하위 클래스로 내리는 행위   
`Concept 2 : Push Up` : Raising a member or method of a lower class to a higher class // `개념 2 : Push Up` : 하위 클래스의 멤버나 메소드를 상위 클래스로 올리는 행위   
`Alt + Shift + Alphabet` : Keys for Refactoring // `Alt + Shift + 알파벳` : 리팩토링을 위한 단축키   
`Alt + Shift + T` : Show Refactor Quick Menu(Example : Display) // 상황에 맞는 실행 가능한 리펙토링 메뉴 보기(예시 : 디스플레이)   
   
<br />
### Maven // 메이븐   
`Alt + F5` : Maven Update Project   
`Ctrl + Alt + P` : Select Maven Profiles...   
   
<br />
### Download Keys Excel // 단축키 엑셀 다운로드   
[Eclipse_keys_20210820.xlsx](https://github.com/mmmirrra/mmmirrra.github.io/raw/main/_assets/Eclipse_keys_20210820.xlsx)   
