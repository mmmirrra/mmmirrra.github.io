---
layout: post
title:  "C: File Processing Function & File Opening Mode"
date:   2024-02-21 09:00:00 +0900
categories: [C]
---

#### File   
// 보조기억장치에 저장된 데이터들의 모임   
// 일련의 바이트(byte)들로 구성   
// 파일 포인터를 사용하여 파일 입출력 수행   
- A collection of data stored on an auxiliary memory device   
- Consisting of a series of bytes   
- Use the File Pointer to perform File input and output   
   
<br />
#### Type of File   
// 텍스트 파일 : 화면에 출력되는 문자들로 구성된 파일   
// 2진 파일 : 텍스트 파일을 포함한 모든 종류의 자료를 다루는 파일. 컴파일 되어 있어 기계어에 가까우므로 내용을 이해하거나 인쇄가 불가능   
- Text File : A File consisting of characters that are displayed on the screen   
- Binary File : A File that covers all kinds of material, including Text File. Compiled and close to machine language, making it impossible to understand or print content.   
   
<br />
#### File Pointer   
// 파일이 어디에 있는지를 가리키는 포인터   
// 모든 파일 입출력 함수는 파일 포인터를 사용   
- A Pointer to where the File is located   
- All File input/output functions use File Pointers   
   
<br />
#### Buffer   
// 기억 공간과 디스크 사이에 존재하는 임시 기억 공간   
// 파일 입출력 시 디스크에 저장된 자료를 기억 공간으로 읽어들이거나, 기억 공간에서 처리된 자료를 디스크에 저장할 때 사용   
- Temporary storage space between storage space and disk   
- Used to read data stored on disk into storage space during File input and output, or to store data processed on disk space   
   
<br />
#### Stream   
// 자료의 입출력을 위한 논리적인 통로   
// 스트림 생성 : 'fopen()' 함수 사용. 파일과 프로그램과의 통로(논리적인 접속)를 구성함. 통로 역할은 파일 포인터가 수행함   
// 스트림 소멸 : 'fclose()' 함수 사용   
- Logical channels for data input and output   
- Stream generation: using `fopen()` function. constructing a path (logical connection) between File and program. The path role is played by a File Pointer   
- Stream destruction: using `fclose()` function   
   
<br />
#### Record   
// 레코드는 파일 입출력처리에 사용되는 논리적인 기본 단위임   
// 각 레코드들은 필드(field)들로 구성됨   
// 파일은 레코드 단위로 구성됨   
- A record is a logical basic unit used for File input/output processing   
- Each record consists of fields   
- File are organized on a record basis   
   
<br />
#### File classification based on how File are organized using File processing functions   
// 파일처리함수를 이용하여 파일을 편성하는 방법에 따라 구분   
// 순차파일 : 레코드의 길이가 일정하지 않은 파일. 파일의 처음부터 자료를 차례로 읽고, 기록하는 파일. 레코드의 길이가 일정하지 않기 때문에 레코드들의 구분이 필요. CR/LF를 사용하여 구분   
// 랜덤파일 : 레코드의 길이가 일정한 파일. 파일의 임의의 위치에서 자료를 읽고, 기록하는 파일   
- Categorized by how File are organized using File processing functions   
- Sequential File: A File whose length is not constant. A File that reads and records data from the beginning of a File. Because the length of the record is not constant, it is necessary to separate the records. Use CR/LF to distinguish   
- Random File : A File of constant length of the record. A File that reads and records data at any location in the File   
   
<br />
#### Output function & input function of Sequential File : A function that records data in a created File and a function that reads stored data   
- `putc()` & `getc()`   
- `fputc()` & `fgetc()`   
- `fputs()` & `fgets()`   
- `fprintf()` & `fscanf()`   
   
<br />
### File Processing Function   
   
|Function|Description|
|:---|:---|
|`fopen("fileName", "Mode")`|// 파일을 지정된 모드로 열기<br />// 입출력이 정상이면 지정된 파일의 파인포인터에 시작주소 값을 리턴. 파일이 개방되지 않을 때는 에러 값 NULL 리턴<br />It is used to create a File or to open a File.|
|`fclose()`|// 파일을 닫기<br />It is used to close a File.|
|`fgetc()`|// 파일로부터 한 문자 읽기<br />Reads a single character from the File.|
|`fputc()`|// 파일에 한 문자 쓰기<br />Prints a single character into the File.|
|`getc()`|// 파일로부터 한 문자 읽기<br />It is used to read a single character to a File.|
|`putc()`|// 파일에 한 문자 쓰기<br />It is used to write a single character to a File.|
|`fgets()`|// 파일로부터 문자열 읽기<br />Input the whole line from the File.<br />It is used to read a File.|
|`fputs()`|// 파일에 문자열 쓰기<br />Prints the whole line in the File and a newline at the end.|
|`fgetw()`|Reads a number from a File.|
|`fputw()`|Prints a number to the File.|
|`putw()`|It is used to write an integer to a File.|
|`getw()`|It is used to read an integer from a File.|
|`fscanf()`|// 파일로부터 정해진 형식에 따라 읽기<br />Use formatted string and variable arguments list to take input from a File.<br />It is used to read blocks of data from a File.|
|`fprintf()`|// 파일에 정해진 형식에 따라 쓰기<br />Similar to printf(), this function use formatted string and varible arguments list to print output to the File.<br />It is used to write blocks of data into a File.|
|`fread()`|// 파일로부터 정해진 크기의 자료를 정해진 개수만큼 읽기<br />Reads the specified bytes of data from a Binary File.|
|`fwrite()`|// 파일에 정해진 크기의 자료를 정해진 개수만큼 쓰기<br />This functions write the specified amount of bytes to the Binary File.|
|`fseek()`|// 파일에서 입출력 위치를 이동<br />It is used to set the position of a File Pointer to a mentioned location.|
|`rewind()`|It is used to set the File Pointer to the beginning of a File.|
|`ftell()`|It is used to return the current position of a File Pointer.|
|`feof()`|// 파일의 끝인가를 판별<br />Determines if it is the end of the File.|
|`ferror()`|// 파일의 입출력 시 에러 발생 유무 조사<br />Check for errors when entering or outputting File|
   
<br />
### File Opening Mode   
   
#### Enable (Open) Mode = File Access Mode + Data Input/Output Mode   
// 사용(개방)모드 = 파일 접근 모드 + 데이터 입출력 모드   
- File Access Mode : `r`, `r+`, `w`, `w+`, `a`, `a+`   
- Data Input/Output Mode : `t`, `b`   
  // 생략 시 Text Mode로 지정됨   
  // t : 텍스트 모드 : 프로그램에서 파일로 자료를 입출력 할 때 변환이 일어나는 입출력 모드. 문자 변환이 필요(￦n <-> CR/LF)   
  // b : 2진 모드 : 변환이 일어나지 않는 입출력 모드. 문자 변환이 불필요   
  - If omitted, it is designated as Text Mode   
  - `t` : Text Mode : Input/output Mode in which conversion occurs when data is input/output from a program to a File. Character conversion is required (￦n <-> CR/LF)   
  - `b` : Binary Mode : Input/output Mode without conversion; no character conversion required   
   
<br />
#### Basic Mode of use of fopen() function   
// fopen() 함수의 기본적인 사용모드   
   
|Mode|Description|
|`r`|// 파일 읽기<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />- Text Mode<br />- Searches File. If the File is opened successfully fopen( ) loads it into memory and sets up a Pointer that points to the first character in it. If the File cannot be opened fopen( ) returns NULL.|
|`rb`|// 파일 읽기<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />- Binary Mode<br />- Open for reading in Binary Mode. If the File does not exist, fopen( ) returns NULL.|
|`w`|// 파일 쓰기<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />- Text Mode<br />- Open for writing in Text Mode. If the File exists, its contents are overwritten. If the File doesn’t exist, a new File is created. Returns NULL, if unable to open the File.|
|`wb`|// 파일 쓰기<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />- Binary Mode<br />- Open for writing in Binary Mode. If the File exists, its contents are overwritten. If the File does not exist, it will be created.|
|`a`|// 파일 추가<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />- Text Mode<br />- Searches File. If the File is opened successfully fopen( ) loads it into memory and sets up a Pointer that points to the last character in it. It opens only in the append Mode. If the File doesn’t exist, a new File is created. Returns NULL, if unable to open the File.|
|`ab`|// 파일 추가<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />- Binary Mode<br />- Open for append in Binary Mode. Data is added to the end of the File. If the File does not exist, it will be created.|
|`r+`|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />- Text Mode<br />- Searches File. It is opened successfully fopen( ) loads it into memory and sets up a Pointer that points to the first character in it. Returns NULL, if unable to open the File.|
|`rb+`|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />- Binary Mode<br />- Open for both reading and writing in Binary Mode. If the File does not exist, fopen( ) returns NULL.|
|`w+`|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />- Text Mode<br />- Searches File. If the File exists, its contents are overwritten. If the File doesn’t exist a new File is created. Returns NULL, if unable to open the File.|
|`wb+`|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />- Binary Mode<br />- Open for both reading and writing in Binary Mode. If the File exists, its contents are overwritten. If the File does not exist, it will be created.|
|`a+`|// 파일 읽기, 추가 겸용<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />- Text Mode<br />- Searches File. If the File is opened successfully fopen( ) loads it into memory and sets up a Pointer that points to the last character in it. It opens the File in both reading and append Mode. If the File doesn’t exist, a new File is created. Returns NULL, if unable to open the File.|
|`ab+`|// 파일 읽기, 추가 겸용<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />- Binary Mode<br />- Open for both reading and appending in Binary Mode. If the File does not exist, it will be created.|
