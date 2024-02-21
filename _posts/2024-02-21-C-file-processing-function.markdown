---
layout: post
title:  "C: File Processing Function & File Opening Mode"
date:   2024-02-21 09:00:00 +0900
categories: [C]
---

### File Processing Function   
   
|Function|Description|
|:---|:---|
|fopen("fileName", "Mode")|// 파일을 지정된 모드로 열기<br />It is used to create a file or to open a file.|
|fclose()|// 파일을 닫기<br />It is used to close a file.|
|fgetc()<br />getc()|// 파일로부터 한 문자 읽기<br />Reads a single character from the file.|
|fputc()<br />putc()|// 파일에 한 문자 쓰기<br />Prints a single character into the file.|
|getc()|It is used to read a single character to a file.|
|putc()|It is used to write a single character to a file.|
|fgets()|// 파일로부터 문자열 읽기<br />Input the whole line from the file.<br />It is used to read a file.|
|fputs()|// 파일에 문자열 쓰기<br />Prints the whole line in the file and a newline at the end.|
|fgetw()|Reads a number from a file.|
|fputw()|Prints a number to the file.|
|putw()|It is used to write an integer to a file.|
|getw()|It is used to read an integer from a file.|
|fscanf()|// 파일로부터 정해진 형식에 따라 읽기<br />Use formatted string and variable arguments list to take input from a file.<br />It is used to read blocks of data from a file.|
|fprintf()|// 파일에 정해진 형식에 따라 쓰기<br />Similar to printf(), this function use formatted string and varible arguments list to print output to the file.<br />It is used to write blocks of data into a file.|
|fread()|// 파일로부터 정해진 크기의 자료를 정해진 개수만큼 읽기<br />Reads the specified bytes of data from a binary file.|
|fwrite()|// 파일에 정해진 크기의 자료를 정해진 개수만큼 쓰기<br />This functions write the specified amount of bytes to the binary file.|
|fseek()|// 파일에서 입출력 위치를 이동<br />It is used to set the position of a file pointer to a mentioned location.|
|rewind()|It is used to set the file pointer to the beginning of a file.|
|ftell()|It is used to return the current position of a file pointer.|
|feof()|// 파일의 끝인가를 판별<br />Determines if it is the end of the file.|
|ferror()|// 파일의 입출력 시 에러 발생 유무 조사<br />Check for errors when entering or outputting files|
   
### File Opening Mode   
   
|Mode|Description|
|r|// 파일 읽기<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />Searches file. If the file is opened successfully fopen( ) loads it into memory and sets up a pointer that points to the first character in it. If the file cannot be opened fopen( ) returns NULL.|
|rb|// 파일 읽기<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />Open for reading in binary mode. If the file does not exist, fopen( ) returns NULL.|
|w|// 파일 쓰기<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />Open for writing in text mode. If the file exists, its contents are overwritten. If the file doesn’t exist, a new file is created. Returns NULL, if unable to open the file.|
|wb|// 파일 쓰기<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />Open for writing in binary mode. If the file exists, its contents are overwritten. If the file does not exist, it will be created.|
|a|// 파일 추가<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />Searches file. If the file is opened successfully fopen( ) loads it into memory and sets up a pointer that points to the last character in it. It opens only in the append mode. If the file doesn’t exist, a new file is created. Returns NULL, if unable to open the file.|
|ab|// 파일 추가<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />Open for append in binary mode. Data is added to the end of the file. If the file does not exist, it will be created.|
|r+|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />Searches file. It is opened successfully fopen( ) loads it into memory and sets up a pointer that points to the first character in it. Returns NULL, if unable to open the file.|
|rb+|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 정상처리<br />// 파일이 없을 경우 : NULL 값 반환<br />Open for both reading and writing in binary mode. If the file does not exist, fopen( ) returns NULL.|
|w+|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />Searches file. If the file exists, its contents are overwritten. If the file doesn’t exist a new file is created. Returns NULL, if unable to open the file.|
|wb+|// 파일 읽기, 쓰기 겸용<br />// 파일이 있을 경우 : 이전 내용 삭제<br />// 파일이 없을 경우 : 새 파일 생성<br />Open for both reading and writing in binary mode. If the file exists, its contents are overwritten. If the file does not exist, it will be created.|
|a+|// 파일 읽기, 추가 겸용<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />Searches file. If the file is opened successfully fopen( ) loads it into memory and sets up a pointer that points to the last character in it. It opens the file in both reading and append mode. If the file doesn’t exist, a new file is created. Returns NULL, if unable to open the file.|
|ab+|// 파일 읽기, 추가 겸용<br />// 파일이 있을 경우 : 이전 내용 뒤에 추가<br />// 파일이 없을 경우 : 새 파일 생성<br />Open for both reading and appending in binary mode. If the file does not exist, it will be created.|
