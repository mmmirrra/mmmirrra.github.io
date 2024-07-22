---
layout: post
title:  "Java: java.nio Package"
date:   2024-05-24 09:00:00 +0900
categories: [Java]
---

### java.nio Package   
// java.nio 패키지   
   
// 'NIO'는 'New Input Output'의 약자   
// - 기존 `java.io` 패키지를 개선한 새로운 입출력 패키지   
// 'JdK 7' 부터는 '파일 I/O'를 개선한 'NIO2'도 등장   
// - `java.nio`와 그것의 서브 패키지 형태   
// -- `java.nio.file, java.nio.channels, java.nio.charset` 등   
// - File 클래스보다 다양한 기능을 제공하는 Path   
// - Files의 static 메소드를 통한 파일 / 디렉토리의 조작, 파일의 읽기 / 쓰기   
// - 파일 입력과 파일 출력이 모두 가능한 `FileChannel 클래스`   
// -- 버퍼링 기능, 멀티스레드에 안전   
// - 비동기식 파일 입출력을 위한 `AsynchronousFileChannel 클래스`   
// -- 'non-blocking' 방식 파일 입출력   
- 'NIO' stands for 'New Input Output'   
  - New I/O package that improves existing `java.io` package   
- From 'JdK 7', 'NIO2' which improved 'File I/O' also appeared   
  - `java.nio` and its sub-package form   
    - `java.nio.file, java.nio.channels, java.nio.charset`, etc.   
  - Path provides more functionality than File class   
  - File/directory manipulation and file read/write via the static method of Files   
  - `FileChannel class` that allows both file input and file output   
    - Buffering, multi-threaded safe   
  - `AsynchronousFileChannel Class` for asynchronous file input/output   
    - File input/output using 'non-blocking' method   
   
<br />
### Path Interface   
// Path 인터페이스   
   
// `java.nio.file` 패키지에 존재하며 `java.io.File` 클래스를 대신함   
// 파일시스템에 존재하는 파일이나 디렉터리에 해당하는 경로를 표현   
// - 절대 경로 또는 상대 경로로 표현됨   
// 경로의 생성, 경로의 비교, 경로 정보 추출, 경로 요소 조작 기능 등을 제공   
// `java.nio.file.Files` 클래스의 static 메소드를 이용해 Path 객체에 대한 다양한 실제 조작 (생성, 읽기, 쓰기, 복사, 이동 등) 이 가능함   
// Path 객체의 생성 방법   
// - `Path p = Paths.get("c:\\tmp\\foo");`   
// - 파일이나 디렉터리의 절대 또는 상대 경로를 명시해야 함   
- Exists in `java.nio.file` package and replaces `java.io.File` class   
- Represents the path that corresponds to a file or directory that exists in the file system   
  - Expressed as an absolute path or relative path   
- Provides path creation, path comparison, path information extraction, path element manipulation, etc.   
- Various real operations (creating, reading, writing, copying, moving, etc.) on Path objects are possible using the static method of the `java.nio.file.Files` class   
- How to create a Path object   
  - `Path p = Paths.get("c:\\tmp\\foo");`   
  - Absolute or relative path of file or directory must be specified   
   
// 주요 메소드   
- Key Methods   
   
|Method|Description|
|:---|:---|
|int compareTo(Path other)|// 두 경로를 비교하여 같으면 0을 반환<br />- Compare the two paths and return the same 0|
|Path getFileName()|// 디렉터리 또는 파일의 이름을 Path 객체로 리턴<br />- Return the name of the directory or file to the Path object|
|FileSystem getFileSystem()|// Path 객체를 만들어 준 FileSystem 객체를 리턴<br />- Return the FileSystem object that created the Path object|
|Path getName(int index)|// 경로에서 index에 해당하는 이름을 Path 객체로 리턴<br />- Return the name corresponding to index to the Path object in the path|
|int getNameCount()|// 경로에 포함된 원소의 개수를 리턴<br />- Return the number of elements in the path|
|Path getParent()|// 부모 경로를 Path 객체로 리턴<br />- Return parent path to Path object|
|Path getRoot()|// 루트 디렉터리를 Path 객체로 리턴<br />- Return root directory to Path object|
|Iterator＜Path＞ iterator()|// 경로에 존재하는 모든 디렉터리 또는 파일의 이름을 Iterator 객체로 리턴<br />- Return the name of all directories or files that exist in the path to the Iterator object|
|File toFile()|// Path 객체를 File 객체로 변환하여 리턴<br />- Return Path object by converting it to File object|
|String toString()|// Path 객체를 문자열로 변환하여 리턴<br />- Return Path object by converting it into a string|
   
// Path 인터페이스 사용 예시   
- Path Interface Use Example   
   
```java
import java.util.*;
import java.nio.file.*;

public class Main {
    public static void main(String args[]) {
        try {
            Path.path = Paths.get("c:\\windows\\system32\\drivers\\etc\\hosts");
            System.out.println("File Name : " + path.getFileName());
            System.out.println("Parent Folder : " + path.getParent().getFileName());
            System.out.println("Path Length : " + path.getNameCount());

            System.out.print("Current Path : ");
            for (int i = 0; i < path.getNameCount(); i++)
                System.out.print(path.getName(i) + "\\");

            Iterator<Path> it = path.iterator();
            System.out.print("\nCurrent Path : ");
            while (it.hasNext())
                System.out.print(it.next().getFileName() + "\\");
        }  catch (Exception e) {
            System.out.println(e);
        }
    }
}
```
   
- Result   
   
```
File Name : hosts
Parent Folder : etc
Path Length : 5
Current Path : windows\system32\drivers\etc\hosts\
Current Path : windows\system32\drivers\etc\hosts\
```
   
<br />
### FileSystem Classes and FileStore Classes   
// FileSystem 클래스와 FileStore 클래스   
   
// FileSystem 클래스의 메소드   
// - FileSystem은 파일 시스템에 대한 인터페이스를 제공   
// -- `FileSystems.getDefault()` 은 기본 파일 시스템을 리턴함   
// - `Iterable <FilseStore> getFileStores()`   
// -- 하나 이상의 파일 스토어로 구성됨   
// - `WatchService newWatchService()`   
// FileStore 클래스의 메소드   
// - FileStore 는 저장소 (파티션 또는 볼륨) 를 표현함   
// - `String name(), String type()`   
// - `long getTotalSpace()`   
// - `long getUnallocatedSpace(), long getUsableSpace()`   
- FileSystem class methods   
  - FileSystem provides an interface to the file system   
    - `FileSystems.getDefault()` returns the default file system   
  - `Iterable <FilseStore> getFileStores()`   
    - Consists of one or more file stores   
  - `WatchService newWatchService()`   
- FileStore class methods   
  - FileStore represents storage (partition or volume)   
  - `String name(), String type()`   
  - `long getTotalSpace()`   
  - `long getUnallocatedSpace(), long getUsableSpace()`   
   
// FileSystem 객체로 디스크 정보 출력하기   
- Output disk information using the FileSystem object   
   
```java
import java.nio.file.*;

public class Main {
    public static void main(String args[]) {
        FileSystem fs = FileSystems.getDefault();
        // 향상된 for 문
        // Enhanced for statement
        for (FileStore store : fs.getFileStores()) {
            System.out.println("Drive name : " + store.name());
            System.out.println("File system : " + store.type());
            long total = store.getTotalSpace();
            long free = store.getUnallocatedSpace();
            System.out.println("Total space : " + total + " bytes");
            System.out.println("Space in use : " + (total - free) + " bytes");
            System.out.println("Free space : " + free + " bytes");
            System.out.println();
        }
    }
}
```
   
- ReSult   
   
```
Drive name : drive C
File system : NTFS
Total space : 499431501824 bytes
Space in use : 462690144256 bytes
Free space : 36741357568 bytes
```
   
<br />
### Files Class   
// Files 클래스   
   
// 파일 조작 기능을 제공하는 static 메소드를 제공함   
// - 메소드는 Path 객체를 인자로 가지고 작업함   
// 파일의 읽기와 쓰기 메소드   
// - `byte[] readAllBytes(Path), Path write(Path, byte[])`   
// 파일이나 디렉터리의 검사/생성/삭제/복사/이동/속성관리 메소드   
// - `boolean isDirectory(Path), boolean isRegularFile(Path)`   
// - `Path createFile(Path), Path createDirectory(Path), void delete(Path)`   
// - `Path copy(Path, Path), Path move(Path, Path)`   
// - `long size(Path), UserPrincipal getOwner(Path)`   
- Provides a static method that provides file manipulation capabilities   
  - Method works with Path objects as arguments   
- Method of reading and writing files   
  - `byte[] readAllBytes(Path), Path write(Path, byte[])`   
- A method to examine/create/delete/copy/move/attributes a file or directory   
  - `boolean isDirectory(Path), boolean isRegularFile(Path)`   
  - `Path createFile(Path), Path createDirectory(Path), void delete(Path)`   
  - `Path copy(Path, Path), Path move(Path, Path)`   
  - `long size(Path), UserPrincipal getOwner(Path)`   
   
// 디렉터리 내용 확인하기   
- Check the contents of the directory   
   
```java
import java.nio.file.*;

public class Main {
    public static void main(String args[]) {
        Path path = Paths.get("c:\\Java");

        DirectoryStream<Path> ds = Files.newDirectoryStream(path);
        for (Path p : ds) {
            if (Files.isDirectory(p)) {
                System.out.println("[directory] " + p.getFileName());
            } else {
                System.out.print("[file] " + p.getFileName());
                System.out.println(" (" + Files.size(p) + ")");
            }
        }
    }
}
```
   
- Result   
   
```
[directory] Example
[file] FileInputStreamTest.java (434)
[file] FilesTest1.java (808)
[directory] temp
[file] winhlp.exe (9728)
[file] winhlp32.exe (9728)
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
