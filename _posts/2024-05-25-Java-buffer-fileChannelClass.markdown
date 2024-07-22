---
layout: post
title:  "Java: Buffer, FileChannel Class"
date:   2024-05-25 09:00:00 +0900
categories: [Java]
---

### Buffer   
// 버퍼   
   
// 데이터 생산자로부터 프로그램으로 데이터가 입력될 때 입력 속도와 처리 속도의 차이로 인해 지연이 발생할 수 있음   
// - 프로그램으로부터 데이터 소비자로 데이터가 출력될 때도 마찬가지임   
// 버퍼를 사용하면 지연 현상을 방지할 수 있음   
// - 프로그램은 버퍼로부터 데이터를 읽음 (입력)   
// - 프로그램은 버퍼로 데이터를 출력함 (출력)   
- Delays can occur due to differences in input and processing speeds when data is entered from the data producer to the program   
  - The same is true when data is output from the program to the data consumer   
- Buffers can be used to prevent delays   
  - The program reads data from the buffer (input)   
  - The program outputs data to the buffer (output)   
   
<br />
### Buffer Class   
// Buffer 클래스   
   
// 버퍼는 기본형 값을 저장하는 데이터 보관소   
// - 채널 입출력에 사용되며 버퍼 단위로 입출력할 수 있음   
// Buffer는 추상 클래스로 java.nio 패키지에 존재   
// - 자식 클래스에서 구현해야 할 공통의 메소드를 선언   
// 실제 사용을 위해 boolean 을 제외한 모든 기본형에 대해 Buffer의 서브 클래스가 존재함   
// `ByteBuffer, CharBuffer, DoubleBuffer, FloatBuffer, IntBuffer, LongBuffer, ShortBuffer`   
- Buffers are data archives that store default values   
  - Used for channel input/output and can be input/output in buffer units   
- Buffer is an abstract class and exists in the java.nio package   
  - Declare common methods that need to be implemented in the child class   
- Buffer's sub classes exist for all base types except boolean for real-world use   
- `ByteBuffer, CharBuffer, DoubleBuffer, FloatBuffer, IntBuffer, LongBuffer, ShortBuffer`   
   
<br />
### Creating Buffers   
// 버퍼의 생성   
   
// 버퍼의 생성 방법   
- How to create a buffer   
   
```java
Buffer buffer = ByteBuffer.allocate(1024*1024);
```
   
```java
byte[] barray = new byte[100];
Buffer bbuffer = ByteBuffer.wrap(barray);
```
   
// 버퍼의 속성   
// - `(0 <= mark <= position <= limit <= capacity)`   
// -- `capacity` : 버퍼의 크기 (데이터의 개수). 생성될 때 정해짐   
// -- `position` : 읽기나 쓰기가 적용되는 위치 (position <= limit)   
// -- `limit` : 읽거나 쓸 수 없는 최초 위치 (limit <= capacity)   
// -- `mark` : `reset()` 되었을 때 `position` 이 가리킬 위치   
- Buffer properties   
  - `(0 <= mark <= position <= limit <= capacity)`   
    - `capacity` : Size of the buffer (number of data). Determined when created   
    - `position` : The position where reading or writing is applied (position <= limit)   
    - `limit` : The first location where read/write cannot be written (limit <= capacity)   
    - `mark` : When `reset()`, the position to be indicated by `position`   
   
// 주요 메소드   
- Key Methods   
   
|Method|Description|
|:---|:---|
|Buffer mark()|// mark를 position 의 값으로 설정<br />- Set mark to the value of position|
|Buffer rest()|// position을 mark 의 값으로 설정<br />- Set position to the value of mark|
|Buffer rewind()|// position을 0으로 바꾸고 mark를 삭제함.<br />// 처음부터 다시 읽기를 준비하는 것<br />- Change the position to 0 and delete the mark.<br />- Preparing to read from scratch|
|Buffer flip()|// limit를 position 값으로 설정하고, position은 0으로 변경함.<br />// 버퍼에 쓰기를 끝내고, 버퍼 읽기를 준비하는 것<br />- Set limit to position value, and change position to 0.<br />- Finishing writing to buffer and preparing to read buffer|
|Buffer clear()|// 버퍼를 초기 상태로 돌림.<br />// 새로운 쓰기를 준비하는 것<br />- Return buffer to initial state.<br />- Preparing for a new write|
|int capacity()|// 현재 capacity 값을 리턴<br />- Return current capacity value|
|int position()|// 현재 position 값을 리턴<br />- Return current position value|
|int limit()|// 현재 limit 값을 리턴<br />- Return current limit value|
   
<br />
### Buffer read and write   
// 버퍼 읽기와 쓰기   
   
// Buffer 의 서브클래스에서 제공   
// - `ByteBuffer, CharBuffer, DoubleBuffer, ...`   
// 상대적 읽기 / 쓰기 메소드 (예시 : ByteBuffer 에서)   
// - 현재 position 의 위치에서 읽기 또는 쓰기를 수행하며, 읽거나 쓴 요소만큼 position 값이 증가함   
// - `byte get()`, `ByteBuffer get(byte[])`   
// - `ByteBuffer put(byte)`, `ByteBuffer put(byte[])`   
// 절대적 읽기 / 쓰기 메소드   
// - 읽거나 쓸 위치를 매개변수 index로 지정   
// - position 값에 영향을 주지 않음   
// - `byte get(int index)`   
// - `ByteBuffer put(int index, byte b)`   
- Available in Buffer's sub class   
  - `ByteBuffer, CharBuffer, DoubleBuffer, ...`   
- Relative Read/Write Methods (e.g., from ByteBuffer)   
  - Read or write from the current position, position values increase by the number of elements read or written   
  - `byte get()`, `ByteBuffer get(byte[])`   
  - `ByteBuffer put(byte)`, `ByteBuffer put(byte[])`   
- An absolute read/write method   
  - Specify a place to read or write as a parameter index   
  - Does not affect position value   
  - `byte get(int index)`   
  - `ByteBuffer put(int index, byte b)`   
   
<br />
### FileChannel Class   
// FileChannel 클래스   
   
// java.io 패키지의 파일 관련 입출력 스트림을 대체   
// - java.nio.channels 패키지에 존재   
// - 파일에 대한 읽기와 쓰기를 모두 제공   
// - 멀티 스레드 환경에서도 안전하게 사용할 수 있음   
// 읽기와 쓰기 메소드   
// - `int read(ByteBuffer dst)`, `int write(ByteBuffer src)`   
// 객체 생성 방법   
// - `FileChannel.open(Path path, OpenOption ... options)`   
// -- 옵션은 `StandardOpenOption.READ. ㅡ` 외 `CREATE, WRITE, APPEND` 등   
// - `FileInputStream`, `FileOutputStream` 또는 `RandomAccessFile` 객체에서 `getChannel()`   
- Replacing file-related input/output streams in the java.io package   
  - Presented in java.nio.channels package   
  - Provides both read and write to files   
  - Safe to use in multi-threaded environments   
- Reading and Writing Methods   
  - `int read(ByteBuffer dst)`, `int write(ByteBuffer src)`   
- How to create objects   
  - `FileChannel.open(Path path, OpenOption ... options)`   
    - Options include `StandardOpenOption.READ. ㅡ` and other `CREATE, WRITE, APPEND`, etc.   
  - `FileInputStream`, `FileOutputStream` or `RandomAccessFile` object `getChannel()`   
   
// FileChannel 클래스로 파일 만들기 예시   
- Example of creating a file with a FileChannel class   
   
```java
public class Main {
    public static void main(String args[]) throws IOException {
        String[] data = {
            "Hi, everyone. ", 
            "Welcome to the world of Java programming languages. ",
            "Let's learn about all the methods, ",
            "from installing JDK to compiling ",
            "and running Java programs."
        };
        Path path = Paths.get("c:\\Java\\temp\\file.txt");
        Files.createDirectories(path.getParent());
        FileChannel fileChannel = FileChannel.open(path, StandardOpenOption.CREATE, StandardOpenOption.WRITE);
        Charset charset = Charset.defaultCharset();
        ByteBuffer buffer;
        int byteCount = 0;
        for (int i = 0; i < data.length; i++) {
            buffer = charset.encode(data[i]);
            byteCount = fileChannel.write(buffer);
        }
        System.out.println(byteCount);
        fileChannel.close();
    }
}
```
   
// FileChannel 클래스로 파일 읽기 예시   
- File Read with FileChannel Class Example   
   
```java
public class Main {
    public static void main(String args[]) throws IOException {
        Path path = Paths.get("c:\\java\\temp\\file.txt");
        FileChannel fileChannel = FileChannel.open(path, StandardOpenOption.READ);

        ByteBuffer buffer = ByteBuffer.allocate(1024 * 1024);    // 1 megabyte
        Charset charset = Charset.defaultCharset();

        StringBuffer sb = new StringBuffer();
        int byteCount;
        while ((byteCount = fileChannel.read(buffer)) >= 0) {
            buffer.flip();
            sb.append(charset.decode(buffer));
            buffer.clear();
        }
        System.out.println(sb);
        fileChannel.close();
    }
}
```
   
- Result   
   
```
Hi, everyone. Welcome to the world of Java programming languages. Let's learn about all the methods, from installing JDK to compiling and running Java programs.
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
