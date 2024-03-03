---
layout: post
title:  "Database Systems: Concept"
date:   2024-03-03 09:00:00 +0900
categories: [Database Systems]
---

### The role of the Database   
// 데이터베이스의 역할   
   
// 사회 트렌드의 변화 : 현대까지도 남아 쓰이는 기술, 스마트 기기, 소셜 미디어, 다양한 센서   
- Change in social trends   
  - Legacy Systems   
  - Smart Devices   
  - Social Media   
  - IoT Sensors   
   
// 하루동안의 데이터 단위   
// - 2013년 하루에 생산되는 데이터의 양은 4.4 ZETTABYTES   
// - 2020년 하루에 생산되는 데이터의 양은 60 ZETTABYTES   
- Data units for the day   
  - The amount of Data produced per day in 2013 is 4.4 ZETTABYTES   
  - The amount of Data produced per day in 2020 is 60 ZETTABYTES   
   
// 빅데이터 처리   
Big Data Processing   
   
|Data Flow|
|:---:|
|AI : Data-based Learning<br />↑<br />Big Data : Capture, Storage, Analysis of Data<br />↑<br />IoT : Data Collection through IoT|
   
<br />
#### Why Data Management is necessary   
// 데이터 관리의 필요   
   
// 대량의 데이터를 저장 및 관리하고 필요한 데이터를 신속히 검색할 수 있도록 보조하는 장치   
- Devices that store and manage large amounts of Data and assist in fast retrieval of required Data   
  - Data → (save) → [Data Management Device] → (search) → Required Data   
   
#### History of Data Management   
// 데이터 관리의 역사   
   
1946 : Created a computer   
→ 1956 : Introducing storage devices   
→ Early 1960s : File Processing System   
→ 1970s : IBM's SQL   
→ 1980s : Data Warehouse   
→ 1990s : Appearance of the web   
→ Mid-2000s : Cloud Computing   
→ Late 2000s : Big Data Analysis   
→ 2015 ~ : Appearance of IoT and AI   
   
#### File Processing System   
// 파일 처리 시스템   
   
// 데이터베이스가 개발되기 전에 데이터 관리에 사용   
// 업무별 애플리케이션이 개별 데이터를 데이터 파일에 저장, 관리하는 시스템   
- Used for Data management before a Database is developed   
- Systems where business-specific applications store and manage individual data in data files   
   
// 발생 가능한 문제   
// - 데이터 종속의 문제 : 물리적 데이터 종속. 논리적 데이터 종속. 저장된 데이터가 특정 Hardware에서 또는 사용자 및 Software에서만 사용될 수 있도록 제한되는 문제   
// - 데이터 중복의 문제 : 동일한 사항에 대한 중복 데이터는 일관성, 보안성, 경제성 측면에서 문제 발생   
// -- 일관성 : 한 사실에 대해 한 개의 데이터 값을 유지   
// -- 보안성 : 같은 데이터에 같은 수준의 보안 유지   
// -- 경제성 : 데이터에 대해 최소한의 저장공간만을 점유   
// - 무결성 훼손의 문제 : 실세계의 데이터는 데이터가 가질 수 있는 가능 범위를 포함함(제약조건)   
// -- 데이터 무결성 : 데이터의 정확성 보장. 데이터의 값과 값에 대한 제약조건을 동시에 만족   
// -- 파일 시스템은 데이터 무결성을 보장하기 위한 기능을 제공하지 않음   
// - 동시 접근의 문제 : 동일 데이터에 다수 사용자의 접근 허용 시 일관성이 훼손   
- A possible problem   
  - Data dependency problem : Physical Data Dependency. Logical Data Dependency. Issues that restrict stored data to be used on specific hardware or only on specific users and specific software   
  - Data duplication problem : Overlapping Data for the same issue poses consistency, security, and affordability challenges   
    - Consistency : Keep one Data value for one fact   
    - Security : Keep the same level of security on the same data   
    - Affordability : Occupy minimal storage space for Data   
  - Integrity compromise problem : Real-world data includes the possible range of data (Constraints)   
    - Data Integrity : Ensuring the accuracy of the Data. Satisfy the value of the Data and its constraints at the same time   
    - File systems do not provide the capabilities to ensure data integrity   
  - Simultaneous connection problem : Disregarding consistency when allowing multiple users to access the same Data   
   
<br />
### Meaning of using the Database   
// 데이터베이스 사용의 의미   
   
// 데이터의 사용과 데이터의 관리 영역을 분리   
Separate Data Usage from Data Management   
   
- Data Usage ↔ Database ↔ Data Management   
   
<br />
### Features of the Database   
// 데이터베이스의 특징   
   
// 1. 데이터베이스 시스템의 자기 기술성   
// -- 데이터와 데이터의 정의 및 설명(메타데이터)을 포함   
// 2. 프로그램과 데이터의 격리 및 추상화   
// -- 사용자에게 데이터에 대한 개념적인 표현을 제공하여 접근성을 향상   
// 3. 다중 뷰 제공   
// -- 각 사용자가 관심을 갖는 데이터베이스의 일부만을 표현할 수 있는 기능 제공   
// 4. 데이터 공유와 다수 사용자 트랜잭션 처리   
// -- 다수의 데이터 조작 요청을 동시성 제어 기능을 통해 데이터의 일관성을 보장하면서 동시에 작업을 수행   
1. Self-technicality of Database Systems   
    - Include data and data definition and description (Metadata)   
2. Isolation and abstraction of programs and data   
    - Provides users with conceptual representation of data to improve accessibility   
3. Provide multiple views   
    - Provides the ability to represent only a portion of the Database that each user is interested in   
4. Data sharing and multi-user transactions   
    - Simultaneous control for multiple data manipulation requests ensures data consistency while simultaneously performing tasks   
   
#### Configuring a Database System   
// 데이터베이스 시스템의 구성   
   
|Structure|
|:---:|
|Users/Programmers<br />↓|
|Application Program 1, Application Program 2, Application Program n, ...<br />↓|
|DBMS : Software that performs queries and programs<br />↓|
|DBMS : Software to access stored data<br />↓↑|
|Metadata (Defined stored Database),<br />Saved Database|
   
#### Value, Data, Metadata   
// 값, 데이터, 메타데이터   
   
- 12 --> Value   
- 12 + Today + the highest temperature of the day --> Data   
- Today, the highest temperature of the day --> Metadata   
   
#### The three-step structure of the Database System   
// 데이터베이스 시스템의 3단계 구조   
   
|Structure|Stratum|
|:---:|:---:|
|[External Schema 1, View 1],<br />[External Schema 2, View 2],<br />[External Schema 3, View 3],<br />...|External Stratum|
|↓↑|External-Concept Thought|
|Concept Schema|Concept Stratum|
|↓↑|Concept-Internal Thought|
|Internal Schema|Internal Stratum|
   
#### Processing multi-user transactions   
// 다수 사용자 트랜잭션 처리   
   
// 트랜잭션의 정의 : 하나의 논리적 작업을 처리하기 위한 일련의 데이터베이스 명령의 집합   
- The definition of a transaction : a set of Database commands to handle a logical task   
   
<br />
### Terms related to the Database   
// 데이터베이스 관련 용어   
   
// 데이터 : 어떠한 사실에 대한 정량적, 정성적 특징을 나타낼 수 있는 값과 값에 대한 설명   
// 데이터베이스 : 특정 기관의 애플리케이션 시스템에서 사용되는 데이터의 집합   
// 데이터베이스 관리 시스템 : 데이터베이스에 저장된 데이터의 구성, 저장, 관리, 사용을 위한 소프트웨어 패키지   
// 데이터베이스 시스템 : 정보를 데이터베이스에 저장, 관리하여 사용자에게 요구된 형태의 정보로 제공하는 컴퓨터 기반 시스템   
- Data : Description of values that can represent quantitative and qualitative characteristics of certain facts and their values   
- Database : A set of data used by a particular institution's application system   
- DBMS (Database Management Systems) : Software packages for configuring, storing, managing, and using data stored in databases   
- Database Systems : A computer-based system that stores and manages information in a database and provides it in the form of information requested by the user   
   
<br />
### Components of the Database   
// 데이터베이스의 구성요소   
   
#### Database Language   
// 데이터베이스 언어   
   
// DBMS는 사용자가 데이터베이스를 쉽게 사용하고 다룰 수 있도록 언어 형태의 인터페이스를 제공   
// 역할에 따라 구분   
// - DDL : 데이터 정의 언어   
// - DML : 데이터 조작 언어   
// 현대 데이터베이스 언어는 자연어와 유사한 형태의 SQL (Structured Query Language)로 표준화   
- DBMS provides a language-type interface for users to easily use and handle databases   
- Categorized by role   
    - DDL : Data Definition Language   
    - DML : Data Manipulation Language   
- Modern Database Languages are standardized as SQL (Structured Query Language) in a form similar to natural language   
   
#### DDL : Data Definition Language   
// 데이터 정의 언어   
   
// 데이터베이스 객체를 생성, 수정, 삭제하기 위한 언어   
Language for creating, modifying, and deleting Database objects   
   
// DDL의 요구 기능   
// - 데이터 모델에 따라 애플리케이션 프로그램이 요구하는 데이터의 논리적 구성이나 특징을 규정   
// - 데이터가 기억장치에 저장되도록 데이터의 물리적 구성을 규정   
// - 물리적 구성을 논리적 구성으로 변환이 가능하도록 데이터의 물리적 구성과 논리적 구성 간의 사상을 규정   
- DDL's Requiring Features   
    - Define the logical composition or characteristics of the data required by the application program according to the data model   
    - Define the physical configuration of the data so that it is stored on the memory device   
    - Define the Thought between the physical and logical configurations of data to enable the conversion of physical configurations into logical configurations   
   
#### DML : Data Manipulation Language   
// 데이터 조작 언어   
   
// 구조화된 데이터에 사용자가 접근 및 조작할 수 있도록 지원하는 언어 (검색, 삽입, 삭제, 수정)   
Language that enables users to access and manipulate structured data (search, insert, delete, modify)   
   
// DMS의 요구 조건   
// - 데이터 조작이 쉽고 간편   
// - 데이터 조작 기능이 정확하고 완전   
// - 사용자의 요청을 시스템 내부에서 효율적으로 처리 가능   
- Requirements of DMS   
    - Must be easy and simple to manipulate data   
    - Data manipulation must be accurate and complete   
    - Must be able to handle user requests efficiently within the system   
   
#### Database System Architecture   
// 데이터베이스 시스템 아키텍처   
   
// 1. 중앙집중식 방식   
// - 단일 서버가 다수의 클라이언트 장치를 대신하여 작동   
// - 중앙 컴퓨터의 과부하로 전체적인 성능 저하   
// 2. 분산 시스템 방식   
// - 클라이언트 장치의 성능 향상으로 자체적인 처리 능력 보유   
// - 클라이언트-서버 데이터베이스 시스템   
// -- 애플리케이션 프로그램의 부하를 분산   
// -- 소프트웨어의 유지보수 비용을 절감 및 이식성 증가   
   
1. centralized method   
    - Single server works on behalf of multiple client devices   
    - Overall performance degrades due to central computer overload   
2. Distributed system method   
    - Increase client device performance to enable its own processing capabilities   
    - Client-Server Database System   
      - Distribute the load on the application program   
      - Reduce software maintenance costs and increase portability   
    - Layer 2 structure == Client-side (Users, Applications) ↔ Networks ↔ Server-side (Database Systems)   
    - Layer 3 structure == Client-side (Users, Application Clients) ↔ Networks ↔ Server-side (Application Server, Database Systems)   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
