---
layout: post
title:  "Introduction to Computer: Computer Architecture"
date:   2024-03-07 09:00:00 +0900
categories: [Computer]
---

### Hardware and Software   
// 하드웨어와 소프트웨어   
   
// 컴퓨터 = 하드웨어 + 소프트웨어   
Computer = Hardware + Software   
   
#### Hardware   
// 하드웨어   
   
// 컴퓨터를 구성하고 있는 물리적 부품   
// 기능에 따라 입력장치, 기억·저장장치, 제어장치, 연산장치, 출력장치로 구분   
- The physical parts that make up the computer   
- Depending on the function, it is divided into input device, memory/storage device, control device, arithmetic device, and output device   
   
|Hardware|
|:---:|
|Control → Operation<br />↑ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ↓<br />Commands and Data<br />(Main Memory Device)<br />↑ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ↓<br />Input device &nbsp;&nbsp; Output device|
   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/computerHardwareArchitecture.png)
<br />
<br />
#### Software   
// 소프트웨어   
   
// 다양한 장치들을 동작시켜 특정 작업을 해결하는 프로그램   
// 각각의 고유한 기능을 수행하는 하드웨어가 언제 어떻게 동작하여 문제를 해결할 수 있는지 지시하는 명령어 집합   
// 알고리즘을 프로그래밍 언어로 구현한 결과물   
- A program that operates a variety of devices to solve a particular task   
- A set of instructions that instructs when and how hardware performing each unique function can work to resolve the issue   
- Results of implementing algorithms in programming languages   
   
// 응용 소프트웨어 : 사용자의 업무나 목적에 맞게 문제 해결을 위한 처리 절차를 표현한 명령어 집합   
// 시스템 소프트웨어 : 하드웨어를 제어·관리하여 응용 소프트웨어를 실행할 수 있는 환경을 제공   
- Application software : A set of instructions that represent the processing procedures for troubleshooting for the user's job or purpose   
- System software : Provides an environment where hardware can be controlled and managed to run application software   
   
<br />
### Understanding Hardware   
// 하드웨어의 이해   
   
#### Input device   
// 입력장치   
   
// 사람 → 컴퓨터   
// 명령과 데이터를 컴퓨터에 전달하는 장치   
// 입력한 명령과 데이터를 컴퓨터가 처리할 수 있는 2진수로 변환하는 과정이 필요   
- Person → Computer   
- A device that delivers instructions and data to a computer   
- Input commands and data must be converted into binary digits that the computer can handle   
   
// 입력장치의 종류 : 키보드, 마우스, 스캐너, 터치스크린   
- Type of input device : keyboard, mouse, scanner, touchscreen   
   
// 특수 입력장치 : 마이오(Myo), 립 모션(Leap Motion)   
- Special input Device : Myo, Leap Motion   
   
#### Output device   
// 출력장치   
   
// 사람 ← 컴퓨터   
// 정보 처리 결과를 인간이 인식 가능한 형태의 데이터로 내보내는 장치   
// 2진수 형태의 데이터를 문자, 숫자, 도형, 음성, 영상 등의 형태로 변환   
- Person ← Computer   
- Devices that export information processing results as human-recognizable forms of data   
- Converting binary data into characters, numbers, figures, voices, images, etc.   
   
// 출력장치의 종류 : 모니터, 스피커, 프린터, 초 지향성 스피커, 3D 프린터   
- Type of output device : monitor, speaker, printer, ultra-directional speaker, 3D printer   
   
// 특수 출력장치 : HUD(Head-Up Display) - AR(증강현실), HMD(Head-Mounted Display) - VR(가상현실)   
- Special output device : HUD(Head-Up Display) - AR(Augmented Reality), HMD(Head-Mounted Display) - VR(Virtual Reality)   
   
#### Memory (storage) device   
// 기억(저장)장치   
   
// 명령과 데이터를 기억(저장)하는 하드웨어   
// 역할에 따라 주기억장치(기억장치), 보조기억장치(저장장치)로 구분   
- Hardware that stores (stores) commands and data   
- Depending on the role, it is divided into main memory device (memory device) and auxiliary memory device (storage device)   
   
|category|memory device<br />(main memory device)|storage device<br />(auxiliary memory device)|
|:---:|:---:|:---:|
|// 접근속도<br />access speed|// 빠름<br />fast|// 느림<br />slowness|
|// 제조단가<br />manufacturing unit price|// 높음<br />High|// 낮음<br />Low|
|// 용량<br />capacity|// 작음<br />little|// 큼<br />big|
|// 전원 차단 시<br />When the power is cut off|// ROM : 기억내용 보존<br />// RAM : 모든 내용 초기화<br />ROM : Preserving the contents of the memory<br />RAM : Initialize all content|// 기억내용 보존<br />Preserving the contents of the memory|
   
// 기억(저장)장치의 종류 : ROM(주기억장치. 한번 저장하면 변경불가. mainboard), RAM(주기억장치. Random Access Memory. 임시저장. 전원이 꺼지면 정보 소실됨), 자기디스크(보조기억장치), 광학디스크(보조기억장치), 플래시 드라이브(보조기억장치)   
// 특수기억(저장)장치 : SSD, nvm : Solid State Drive. RAM을 이용한 저장장치. 빠른 속도, 외부 충격에 강함, 적은 전력소모가 강점   
- Types of memory (storage) devices : ROM (main memory device. cannot be changed once saved. mainboard), RAM (main memory device. Random Access Memory. Temporary storage. Information lost when powered off), magnetic disks (auxiliary memory device), optical disks (auxiliary memory device), flash drives (auxiliary memory device)   
- Special memory (storage) device : SSD, nvm : Solid State Drive. A storage device using RAM. High speed, strong against external shocks and low power consumption   
   
#### Control device and Calculating device   
// 제어장치와 연산장치   
   
// 현대의 컴퓨터는 제어장치와 연산장치가 별도로 구분되어 있지 않음   
// 명령어와 데이터를 읽고 데이터를 연산 또는 처리하는 장치   
- Modern computers have no distinction between control and computational devices   
- A device that reads instructions and data and calculates or processes data   
   
CPU   
// 제어와 연산의 기능을 모두 수행하는 회로를 가지고 있음   
// 대부분 3개의 서브유닛(레지스터, 제어 유닛, 연산 논리 유닛)으로 구성되어 있음   
- It has a circuit that performs both control and operation functions   
- It consists mostly of three subunits(Register, Control Unit, ALU(Arithmetic Logic Unit))   
   
// 레지스터 : 고속으로 동작하는 저장장치. CPU 내부에서 초고속으로 데이터를 저장하거나 읽어냄. 주기억장치 메모리보다 훨씬 비쌈   
// 제어 유닛 : 레지스터의 명령어를 읽어서 연산 논리 유닛에 명령어 전달   
// 연산 논리 유닛 : 제어 유닛으로부터 받은 명령어를 처리하기 위해 레지스터에서 값을 가지고 오고, 연산 결과를 레지스터에게 보내줌   
- Register : A high-speed storage device. Store or read data inside the CPU at high speed. It's much more expensive than the main memory   
- Control Unit : Read the commands in the register and pass the commands to the computational logic unit   
- ALU(Arithmetic Logic Unit) : The value is taken from the register to process the instructions received from the control unit and the operation result is sent to the register   
   
<br />
### Understanding Software   
// 소프트웨어의 이해   
   
// 소프트웨어는 고유한 기능을 수행하는 하드웨어가 언제 어떻게 동작하여 문제를 해결할 수 있는지 절차를 지시하는 명령어 집합   
// 응용 소프트웨어, 시스템 소프트웨어로 구분함   
- Software is a set of instructions that directs procedures for when and how hardware performing unique functions can operate to troubleshoot problems   
- Separated into application software, system software   
   
#### System software   
// 시스템 소프트웨어   
   
// 다양한 장치들을 서로 유기적으로 동작시켜 특정 작업을 수행할 수 있는 환경을 조성하는 프로그램   
// 운영체제(커널), 컴파일러, 유틸리티로 구분함   
- A program that creates an environment in which various devices can be operated organically with each other to perform specific tasks   
- Separated into operating systems (kernel), compiler, and utility   
   
// 운영체제(커널) : 사용자가 컴퓨터를 효율적으로 운영·관리·사용할 수 있도록 하드웨어를 제어하는 소프트웨어   
// 컴파일러 : 소스코드를 컴퓨터가 이해할 수 있는 기계어로 번역하는 소프트웨어   
// 유틸리티 : 부가적인 기능을 제공하여 사용자가 컴퓨터를 효율적이고 편리하게 관리할 수 있도록 지원해주는 소프트웨어   
- operating systems (kernel) : Software that controls hardware to enable users to operate, manage, and use computers efficiently   
- compiler : Software that translates source code into computer-understandable machine language   
- utility : Software that provides additional functionality to help users manage their computers efficiently and conveniently   
   
#### Concept of operating system   
// 운영체제의 개념   
   
// 하나의 소프트웨어가 기능하기 위해 함께 작동해야 하는 것들   
// 응용 소프트웨어가 효과적으로 작동할 수 있는 환경을 조성   
- Things that a piece of software needs to work together to function   
- Create an environment where your application software can work effectively   
   
|operating system X|operating system O|
|:---:|:---:|
|Task A ↔ User Task A Processing Command + System Management Command + Device Control Command ↔ Computer<br /><br />Task B ↔ User Task B Processing Command + System Management Command + Device Control Command ↔ Computer|Task A, Task B<br />↓↑<br />User Task A Processing Command, User Task B Processing Command<br />↓↑<br />System Environment Management<br />(System Management Command + Device Control Command)<br />↓↑<br />Computer|
   
#### Role of the operating system   
// 운영체제의 역할   
   
// 컴퓨터의 자원(하드웨어)을 효율적으로 관리하고 응용 프로그램에 자원을 할당   
// - 사용자 인터페이스 : 컴퓨터와 사용자를 매개하여 상호작용하는 방법을 제공 - CLI(Command Line Interface), GUI(Graphic User Interface) 등   
// - 프로세스 관리 : 프로세스는 실행되고 있는 상태의 프로그램. 프로세스 관리를 자동적으로 해주는 운영체제. 여러 프로그램이 요청되면 한정된 자원(기억장치 등)을 효과적으로 사용하도록 조율 - MS Windows 11, Apple MacOS 12 에서 제공하는 프로세스 관리   
// - 네트워크 관리, 네트워크 인터페이스 : 컴퓨터는 네트워크를 통해 상호 데이터 교환. 응용 프로그램이 통신할 수 있는 환경 제공 및 통신 장치(하드웨어) 관리 - MS Windows 11, Apple MacOS 12 에서 제공하는 네트워크 및 인터넷 관리   
// - 기억·저장장치 관리 : 보조기억장치에 저장된 컴퓨터의 프로그램은 실행되기 위해서 주기억장치에 적재. 주기억장치의 크기는 보조기억장치의 크기보다 매우 작기 때문에 효율적 관리가 요구   
// - 입출력장치 관리   
- Efficient management of computer resources (hardware) and allocation of resources to applications   
    - User interface : Provides a way for computers and users to interact - CLI(Command Line Interface), GUI(Graphic User Interface), etc.   
    - Process Management : A process is a running program. An operating system that automatically manages processes. Coordinate to effectively use limited resources (such as storage devices) when multiple programs are requested - Process management provided by MS Windows 11, Apple MacOS 12   
    - Network management, Network interface : Computers exchange data with each other over the network. Provides an environment for applications to communicate and manages communication devices (hardware) - Network and Internet management provided by MS Windows 11, Apple MacOS 12   
    - Memory and storage device management : The program of the computer stored in the auxiliary memory device is loaded in the main memory device to be executed. Efficient management is required because the size of the main memory device is much smaller than that of the auxiliary memory device   
    - Input/output device management   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
