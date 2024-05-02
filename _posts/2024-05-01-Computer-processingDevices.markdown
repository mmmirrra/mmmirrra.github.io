---
layout: post
title:  "Introduction to Computer: Processing devices and data processing"
date:   2024-05-01 09:00:00 +0900
categories: [Computer]
---

### Processing devices   
// 처리장치   
   
- CPU (Central Processing Unit) and Main Memory   
   
#### CPU   
// 중앙처리장치   
   
// 제어장치 (control unit) 와 레지스터, 산술논리연산장치 (ALU : Arithmetic and Logic Unit)   
// 처리를 실행하는 전자회로, 레지스터가 들어 있음   
// 프로그램의 명령어를 해석하고 명령어가 명시한 대로 계산하고 데이터를 이동시키며, 시스템의 입력과 출력을 제어   
- control unit, register, and ALU (Arithmetic and Logic Unit)   
- Contains electronic circuits and registers that execute the processing   
- Interpret the program's instructions, calculate and move data as specified, and control the input and output of the system   
   
// - 산술논리연산장치 : 가감승제 및 논리명령 (논리, 비교, Shift) 을 수행하는 전자회로가 있음   
// - 제어장치 : 컴퓨터시스템 전체를 지시 감독하며 조정. 입력과 출력의 제어, 연산 제어, 데이터 이동   
// - 프로세서 레지스터 : 처리할 명령어 저장   
  - ALU (Arithmetic and Logic Unit) : There is an electronic circuit that performs addition and subtraction and logic commands (logic, comparison, shift)   
  - Control unit : Directed and supervised the entire computer system and coordinated. control of input and output, control of operations, data movement   
  - Processor register : Save commands to process   
   
// Microprocessor : 연산장치와 제어장치를 1개의 작은 실리콘 칩에 집적시킨 처리장치   
- Microprocessor : A processing device integrating the ALU and the control unit into a single small silicon chip   
   
// 중앙처리장치와 주기억장치의 발달로 인터넷, 멀티미디어, 통신, 방송 등 모든 형태의 정보기술이 하나로 통합   
// 1971년 인텔사의 마이크로프로세서 4004 : 크기는 3x4mm. 성능은 ENIAC의 10배   
// - 1946년 ENIAC : 무게 30톤. 길이 25m. 높이 2.5m. 폭 1m   
// 1998년 컴팩사 (Compaq) 의 알파 21264 : 1990년대 슈퍼컴퓨터의 성능. UNIVAC I 보다 10억대 1의 가격 및 성능   
// 2000년대 인텔의 고성능 멀티 코어 i2 ... i7   
// 2022년 현재 12세대 i9 프로세서까지 발전   
// - 성능 향상, 메모리 지원, 전력소비량 감소, 그래픽 향상 등   
- With the development of central processing units and main memory devices, all forms of information technology such as the Internet, multimedia, telecommunications, and broadcasting are integrated into one   
- Intel's microprocessor 4004 in 1971 : 3x4 mm in size. 10x the performance of ENIAC   
  - ENIAC in 1946 : Weight 30 tons. Length 25 m. Height 2.5 m. Width 1 m   
- Compaq's Alpha 21264 in 1998 : The performance of supercomputers in the 1990s. price and performance of 1 billion to 1 over UNIVAC I   
- Intel High Performance Multi-Core i2... i7 in the 2000s   
- Advances to 12th Gen i9 processors as of 2022   
  - Improve performance, support for memory, reduce power consumption, improve graphics, etc.   
   
<br />
### Representation of numerical data   
// 수치 데이터의 표현   
   
#### Storage of data   
// 데이터의 저장   
   
// 컴퓨터 시스템의 전자회로는 전자신호인 임펄스 (impulse) 의 유무를 감지함   
// 데이터의 기본단위는 비트 (bit : binary digit)   
// 1 (on 상태) 또는 0 (off 상태) 으로 저장   
// 전류가 흐르면 1, 흐르지 않으면 0   
- Electronic circuits in computer systems detect the presence or absence of an electronic signal, impulse   
- The basic unit of data is bits (bit : binary digit)   
- Save as 1 (on state) or 0 (off state)   
- 1 if current flows, 0 if not   
   
|Binary number|Current|States|
|:---:|:---:|:---:|
|1|○|ON|
|0|●|OFF|
   
// 보통 8개의 비트 (1바이트 1byte) 를 모아 정보를 표현   
- Usually, 8 bits (1 byte) are gathered to express information   
   
#### Numeral system   
// 진법   
   
// 10진법 : 10은 기저 (base) 를 나타냄   
// -- 253 = 2 x 100 + 5 x 10 + 3 x 1 = 2 x 10² + 5 x 10¹ + 3 x 10<sup>0</sup>   
// -- 10 = 1 x 10¹ + 0 x 10<sup>0</sup>   
// 2진법 : 2는 기저 (base) 를 나타냄   
// - 2진수를 10진수로 바꿀 수 있음   
// -- (1010)₂ = 1 x 2³ + 0 x 2² + 1 x 2¹ + 0 x 2<sup>0</sup> = 1 x 8 + 0 x 4 + 1 x 2 + 0 x 1 = 8 + 0 + 2 + 0 = (10)<sub>10</sub>   
- Decimal system : 10 represents the base   
    - 253 = 2 x 100 + 5 x 10 + 3 x 1 = 2 x 10² + 5 x 10¹ + 3 x 10<sup>0</sup>   
    - 10 = 1 x 10¹ + 0 x 10<sup>0</sup>   
- Binary system : 2 represents the base   
  - Binary numbers can be changed to decimal numbers   
    - (1010)₂ = 1 x 2³ + 0 x 2² + 1 x 2¹ + 0 x 2<sup>0</sup> = 1 x 8 + 0 x 4 + 1 x 2 + 0 x 1 = 8 + 0 + 2 + 0 = (10)<sub>10</sub>   
   
// 진법 대비표   
- A table of comparisons to the Numeral System   
   
|Decimal system|Binary system|Hexadecimal |Octal|
|:---:|:---:|:---:|:---:|
|0|0000|0|0|
|1|0001|1|1|
|2|0010|2|2|
|3|0011|3|3|
|4|0100|4|4|
|5|0101|5|5|
|6|0110|6|6|
|7|0111|7|7|
|8|1000|8|10|
|9|1001|9|11|
|10|1010|A|12|
|11|1011|B|13|
|12|1100|C|14|
|13|1101|D|15|
|14|1110|E|16|
|15|1111|F|17|
   
#### Integer representation   
// 정수 표현   
   
- Total bits 32 = Sign bit 1 + Integer bits 31   
- 2<sup>31</sup> - 1 = 2,147,483,647   
- 1 word = 4 bytes = 32 bits   
   
<br />
### Representation of character data   
// 문자 데이터의 표현   
   
// 문자 'A' 는 1 byte (8 bits) 로 표현 : 2진법 10000001   
- The character 'A' is expressed in 1 byte (8 bits) : binary system 10000001   
   
- 6 bits : 64 expressions (2<sup>6</sup>)   
- 7 bits : 128 expressions (2<sup>7</sup>)   
- 8 bits : 256 expressions (2<sup>8</sup>)   
   
- 6 bits BCD (Binary Coded Decimal)   
- ASCII (American Standard Code for Information Interchange) : 1 byte = 7 bits + 1 bit (verification)   
   
#### ASCII (American Standard Code for Information Interchange)   
// 미국 정보교환 표준코드   
   
// 개인용 컴퓨터 및 데이터 통신용으로 가장 많이 사용   
- Most used for personal computers and data communication   
   
#### UNICODE   
   
// 16 bits (2 bytes) 로 확장   
// 세계의 모든 언어들을 표현   
- Expanded to 16 bits (2 bytes)   
- Expression of all languages in the world   
   
// 1991년 IBM, 마이크로소프트 등 유명 컴퓨터업체들로 구성된 컨소시엄이 개발한 16비트 인코딩 시스템   
// 2<sup>16</sup> = 65,536개   
// 한글, 한자, 히브리어, 일본어, 그리스어의 대소문자 등과 같은 세계의 모든 언어들을 표현   
// 세계의 모든 국가들이 국제적인 통신교류가 가능   
// 언어의 한계없이 소프트웨어를 개발할 수 있음   
- A 16-bit encoding system developed in 1991 by a consortium of well-known computer companies such as IBM and Microsoft   
- 2<sup>16</sup> = 65,536   
- Express all the languages in the world, such as Korean, Chinese, Hebrew, Japanese, and Greek case letters   
- All countries in the world can communicate internationally   
- Can develop software without language limitations   
   
<br />
### Main memory address and data storage   
// 주기억장치 주소와 데이터 저장   
   
#### Memory capacity unit   
// 기억용량단위   
   
- bit, byte, word, etc.   
   
- 1 Byte = 8 bits (One-character expression, excluding Unicode)   
- 1 KB (kilobyte) = 2<sup>10</sup> bytes (1,024 Bytes)   
- 1 MB (megabyte) = 2<sup>20</sup> bytes (1,024 KB)   
- 1 GB (gigabyte) = 2<sup>30</sup> bytes (1,024 MB)   
- 1 TB (terabyte) = 2<sup>40</sup> bytes (1,024 GB)   
- 1 PB (petabyte) = 2<sup>50</sup> bytes (1,024 TB)   
   
#### Call time unit : Speed of the computer   
// 호출시간 단위 : 컴퓨터의 속도   
   
// 예시 : μsec : 초당 100만 개의 자료를 호출   
- Example : μsec : Calling 1 million data per second   
   
- 1 msec (millisecond) = <sup>1</sup> / <sub>10<sup>3</sup></sub> second   
- 1 μsec (microsecond) = <sup>1</sup> / <sub>10<sup>6</sup></sub> second   
- 1 nsec (nanosecond) = <sup>1</sup> / <sub>10<sup>9</sup></sub> second   
- 1 psec (picosecond) = <sup>1</sup> / <sub>10<sup>12</sup></sub> second   
- 1 fs (femtosecond) = <sup>1</sup> / <sub>10<sup>15</sup></sub> second   
- 1 as (attosecond) = <sup>1</sup> / <sub>10<sup>18</sup></sub> second   
   
// 좋은 기억소자 : 비트 당 가격이 저렴하고, 호출시간이 짧고, 부피가 작고, 가볍고, 전력의 소모가 적고, 비트 상태의 안전성이 좋아야 함   
- Good memory : affordable per bit, low call times, low volume, lightweight, low power consumption, and good bit-state safety   
   
#### Data Storage   
// 데이터 저장   
   
// 주기억장치의 각 바이트는 단일 주소를 갖음   
// 숫자, 영문자, 특수문자가 입력장치에서 읽혀 주기억장치로 보내지면 비트의 형태로 바뀌어 기억됨   
// 한 번 데이터가 수록되면 그 내용이 바뀔 때까지 남아있게 됨   
- Each byte in the main memory has a single address   
- Numbers, English characters, and special characters are read from the input device and sent to the main memory device, which changes to the form of bits and is stored   
- Once the data is included, it remains until the content changes   
   
// 고급 언어로 작성한 프로그램의 실행 순서   
// - 기계어로 번역 (컴파일러) → 주기억장치에 저장 → 처리기 전자회로가 해석하고 실행   
- Order of execution of programs written in high-level languages   
  - Translated into machine code (compiler) → Stored in main memory → Interpreted and executed by processor electronic circuit   
   
#### The format of a Machine Code   
// 기계어 명령어의 형식   
   
// 기계어 명령어 = 명령부 + 오퍼랜드부 (주소부)   
// - 명령부 : 실행될 동작을 명시   
// - 오퍼랜드부 : 레지스터 명칭, 데이터 주소, 데이터 길이 등   
- Machine Code = Command + Operand Department (Address Department)   
  - Command : Specify the action to be executed   
  - Operand Department : register name, data address, data length, etc.   
   
// 예시   
// - `SUM := A + B;` 를 실행하는 순서를 어셈블리어로 표현하면   
// -- 1. MOV AX, A ⇒ MOV는 명령부, AX는 레지스터, A는 데이터 변수 주소 ⇒ A의 데이터를 가져와서 AX 레지스터에 넣어라   
// -- 2. ADD AX, B ⇒ ADD는 명령부, AX는 레지스터, B는 데이터 변수 주소 ⇒ B의 데이터를 가져와서 AX 레지스터에 더하라   
// -- 3. MOV SUM, AX ⇒ MOV는 명령부, SUM은 데이터 변수 주소, AX는 레지스터 ⇒ AX 레지스터의 데이터를 SUM 데이터 변수에 넣어라   
- Example   
  - To represent the sequence of executing `SUM := A + B;` in an assembly   
    1. MOV AX, A ⇒ MOV is command, AX is register, A is data variable address ⇒ Take A's data and put it in the AX register   
    2.  ADD AX, B ⇒ ADD is command, AX is register, B is data variable address ⇒ Take B's data and add it to the AX register   
    3. MOV SUM, AX ⇒ MOV is command, SUM is data variable address, AX is register ⇒ Put the data from the AX register into the SUM data variable   
   
<br />
### Development Process of Main Memory and Semiconductor Memory   
// 주기억장치의 발달과정과 반도체 기억장치   
   
#### Development Process of Main Memory   
// 주기억장치의 발달과정   
   
// 진공관 : 크고, 약하고, 열이 많이 발생하고, 신뢰성이 떨어지고, 많은 전류를 필요로 함   
// 자기코어 기억장치   
// - 1950년대 포레스터 (Jay W. Forrester) 가 개발. 20년 동안 사용. 컴퓨터의 발전에 큰 공헌   
// - 지름이 0.3 ~ 0.5mm인 작은 고리 모양의 자성 물질임. 주로 페라이트로 제작   
// - 전류가 오른쪽으로 흐르면 1, 왼쪽으로 흐르면 0   
// - 전원이 꺼진 후에도 기억됨   
- Vacuum tube : large, weak, heat-generating, unreliable, requiring a lot of current   
- Magnetic-core memory device   
  - Developed by Jay W. Forrester in the 1950s. Use for 20 years. A great contribution to the development of computers   
  - Small ring-shaped magnetic material with a diameter of 0.3 to 0.5 mm. Made primarily of ferrite   
  - 1 if current flows to the right, 0 if current flows to the left   
  - It's still stored after the power is turned off   
   
#### Semiconductor Memory   
// 반도체 기억장치   
   
// 반도체 칩 속에 집적회로로 만들어 넣은 기억장치   
// 빠르며 경제적이고 열을 많이 발산하지 않음   
// 신뢰성이 높으며 간편함   
// 경제적이고 많은 용량을 갖는 기억장치는 반도체 기술에 의해 실현되었음   
// 트랜지스터의 발명 후 소형화 추세가 시작됨   
- A memory device made of an integrated circuit in a semiconductor chip   
- Fast, economical, and less heat dissipation   
- Reliable and simple   
- Economical and high-capacity memory devices have been realized by semiconductor technology   
- The trend of miniaturization began after the invention of transistors   
   
// 1960년대 중반 : 한 칩에 1,000개 회로소자 집적   
// 1970년대 중반 : 한 칩에 15,000개 이상의 회로소자 집적   
// 1980년대 : <sup>1</sup> / <sub>4</sub> 인치 칩에 100만개 회로소자 집적   
// 2000년대 : 한 칩에 1,000억개 이상의 회로소자 집적   
- Mid-1960s : 1,000 circuit elements in one chip   
- Mid-1970s : more than 15,000 circuit elements integrated on a chip   
- 1980s : 1 million circuit elements integrated on a <sup>1</sup> / <sub>4</sub>-inch chip   
- 2000s : More than 100 billion circuit elements are integrated on a chip   
   
// 전자현미경, 다이아몬드 톱, 섭씨 0.5도 등의 제반 기술 여건으로 경제적이고 신뢰성 있게 대형 생산 체제 칩을 만들 수 있음   
- Large production system chips can be made economically and reliably with various technical conditions such as electron microscopes, diamond saws, and 0.5 degrees Celsius   
   
// 앞으로 광소자나 조셉슨소자, 갈륨비소소자 등의 사용으로 집적도는 더욱 높아질 예상   
// 자기코어에 기억된 데이터에 대한 접근속도 : 마이크로초 (<sup>1</sup> / <sub>10<sup>6</sup></sub>)   
// 반도체 기억장치에 기억된 데이터에 대한 접근속도는 나노초 (<sup>1</sup> / <sub>10<sup>9</sup></sub>)   
// 자기코어에 비해 반도체 기억장치는 계속적으로 일정한 전류의 공급이 필요함   
- In the future, integration is expected to increase further with the use of optical elements, Josephson elements, and gallium arsenide elements   
- Speed of access to data stored in magnetic-core : microsecond (<sup>1</sup> / <sub>10<sup>6</sup></sub>)   
- The speed of access to data stored in semiconductor memory devices is nanoseconds (<sup>1</sup> / <sub>10<sup>9</sup></sub>)   
- Compared to the magnetic-core, semiconductor memory devices require a constant supply of current   
   
// 단점 : 전기가 꺼지거나 방해를 받는 경우 데이터를 잃어버림   
- Disadvantage : Loss of data if electricity is turned off or interrupted   
   
#### RAM (Random Access Memory)   
   
// SRAM (Static RAM) : 전원이 공급되는 한 내용이 그대로 유지됨   
// DRAM (Dynamic RAM) : 전원이 공급되더라도 내용의 소멸을 방지하기 위해 계속적으로 리프레싱 (refreshing) 을 해야 함   
// SRAM은 캐시메모리 (Cache Memory) 로 이용됨   
// DRAM은 주기억장치로 많이 이용됨   
- SRAM (Static RAM) : Content remains the same as long as it is powered on   
- DRAM (Dynamic RAM) : Even if the power is supplied, it is necessary to continuously refresh to prevent the disappearance of the content   
- SRAM is used as cache memory   
- DRAM is widely used as the main memory device   
   
#### ROM (Read Only Memory)   
   
// ROM (Read Only Memory) : 메모리가 제작될 때 데이터를 이 안에 기록함   
// PROM (Programmable ROM) : ROM과 같은 기능이나 이용자가 PROM을 조립해 넣기 전에 프로그램이나 데이터를 기록할 수 있음   
- ROM (Read Only Memory) : Record data in it when memory is created   
- PROM (Programmable ROM) : It's the same function as ROM, but allows users to record programs or data before assembling a PROM   
   
#### Memory technology   
// 메모리 기술   
   
// 삼성전자에서 2019년 7월 세계 최초 나노 12GB 모바일 D램 LPDDR5 양산   
// 2021년 512GB DRAM 메모리 모듈 양산   
// 플래시메모리 (flash memory) : 비파괴 메모리 기술. 전력이 필요 없는 메모리. 충격에 강함   
// 캐시메모리 : 빠르나 값이 비쌈   
- Samsung Electronics mass-produced the world's first nano 12GB mobile DRAM LPDDR5 in July 2019   
- Mass production of 512GB DRAM memory modules in 2021   
- Flash memory : Non-destructive memory technology. Power-free memory. Shock-resistant   
- Cache memory : Fast but expensive   
   
<br />
### Data processing process of input, processing, and output   
// 입력·처리·출력의 데이터 처리과정   
   
#### Data processing   
// 데이터 처리   
   
// 필드 : 데이터를 구성하는 하나의 단위   
// 레코드 : 여러 필드의 모임. 하나의 처리단위   
// 파일 : 레코드들이 모여 하나의 파일을 구성   
- Field : One unit that makes up the data   
- Record : A collection of multiple fields, one processing unit   
- File : Records are gathered to form a single file   
   
// 필드가 모여 레코드가 되고, 레코드가 모여 파일을 이룸   
// - 예시 : 편지 봉투   
// -- 필드 : 받는 사람의 우편번호, 주소, 이름 → 주소 레코드 → 주소 파일   
- Fields gather to become records, records gather to form files   
  - Example : Letter Envelope   
    - Field : Recipient's ZIP Code, Address, Name → Address Record → Address File   
   
// 기록매체 : OMR (Optical Mark Recognition), OCR (Optical Character Recognition) 카드, 자기테이프 및 자기디스크   
- Recording media : OMR (Optical Mark Recognition), OCR (Optical Character Recognition) cards, magnetic tapes, and magnetic disks   
   
// 한 번에 한 레코드씩 주기억장치로 읽어 들여짐   
- Read one record at a time into the main memory   
   
#### Basic data processing   
// 기본적인 자료 처리과정   
   
// 입력장치를 통해 수집된 데이터가 처리장치에 전달되면, 처리장치는 데이터를 가공하여 정보를 만들어 출력장치로 보냄   
- When the data collected through the input device is delivered to the processing device, the processing device processes the data to create information and sends it to the output device   
   
// 입력장치 (데이터 수집, 데이터 전달) → [ 처리장치 (데이터 가공, 정보의 검색) ↔ 보조기억장치 (정보의 축적) ] → 출력장치 (정보의 전달, 정보의 표시)   
- Input device (data collection, data transfer) → [ Processing device (data processing, information retrieval) ↔ Auxiliary memory device (information accumulation) ] → Output device (information transfer, information display)   
   
#### Input Data / Output Results   
// 데이터 입력 / 결과출력   
   
// 주기억장치에 입력하는 방법 : 음성, 키보드, 마우스, 펜, 터치스크린 (직접입력), OMR, OCR, MICR 카드, 자기테이프, 자기디스크, HDD, CD-ROM, DVD, USB 메모리 등   
// 출력방법 : 프린터 ,CRT, LCD 터미널, 자기테이프나 자기디스크, HDD, CD-ROM, DVD, USB 메모리 등   
- How to enter it into the main memory : voice, keyboard, mouse, pen, touch screen (direct input), OMR, OCR, MICR card, magnetic tape, magnetic disk, HDD, CD-ROM, DVD, USB memory, etc.   
- Output method : printer, CRT, LCD terminal, magnetic tape or magnetic disk, HDD, CD-ROM, DVD, USB memory, etc.   
   
#### The process of executing computer instructions   
// 컴퓨터 명령어의 수행과정   
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/computerDataProcessing.png)
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
