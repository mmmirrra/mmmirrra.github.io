---
layout: post
title:  "Java: WatchService Interface"
date:   2024-05-26 09:00:00 +0900
categories: [Java]
---

### WatchService Interface   
// WatchService 인터페이스   
   
// WatchService   
// - 어떤 대상을 정한 후 변화나 이벤트가 생기는 것을 감시 (watch)   
// - 감시 대상은 Watchable 객체로, register() 메드를 사용하여 WatchService 객체에 감시 대상으로 등록됨   
// - 디렉터리를 표현하는 Path 객체의 변화를 감지   
// -- 디렉터리 내의 파일 또는 서브 디렉터리의 생성, 삭제, 수정   
// - `java.nio.file` 패키지에 존재   
- WatchService   
  - Monitor changes or events after selecting an object (watch)   
  - The target is a Watchable object and is registered as a WatchService object using register() method   
  - Detects changes in Path objects representing directories   
    - Creating, deleting, or modifying files or sub directories within a directory   
  - Exists in `java.nio.file` package   
   
// 감시자의 생성   
// - 먼저 WatchService 객체를 생성함   
// -- `WatchService ws = FileSystems.getDefault().newWatchService();`   
- Creating a WatchService   
  - First, create a WatchService object   
    - `WatchService ws = FileSystems.getDefault().newWatchService();`   
   
<br />
### Monitoring procedure   
// 감시 절차   
   
// 감시 서비스를 구현하는 절차   
// - 감시 대상 디렉터리를 `WatchService`에 등록   
// -- `Path path = Paths.get("c:\\java\\temp");`   
// -- 등록 시 알림을 받고자 하는 이벤트를 명시   
// -- `path.register(ws, StandardWatchEventKinds.ENTRY_CREATE, StandardWatchEventKinds.ENTRY_DELETE, StandardWatchEventKinds.ENTRY_MODIFY);`   
// - `WatchService`는 `take()` 메소드를 호출하여 감시함   
// -- 무한 루프 안에서 이벤트가 발생할 때까지 기다림   
// -- `While(true) {`   
// -- `WatchKey key = ws.take();`   
// - 이벤트가 발생하면 `take()` 가 리턴하는 `WatchKey` 객체를 이용하여 이벤트를 처리   
// - `WatchKey`는 감시 상태, 감시 대상 디렉터리, 이벤트 정보를 가짐   
// -- `pollEvents()` 를 호출하여 `WatchEvent` 객체를 얻고 어떤 변화가 생겼는지 알 수 있음   
- Procedures for implementing monitoring services   
  - Register the monitoring directory with 'WatchService'   
    - `Path path = Paths.get("c:\\java\\temp");`   
    - Specify which events you wish to be notified of when registering   
    - `path.register(ws, StandardWatchEventKinds.ENTRY_CREATE, StandardWatchEventKinds.ENTRY_DELETE, StandardWatchEventKinds.ENTRY_MODIFY);`   
  - 'WatchService' calls `take()` method to monitor   
    - Wait for an event to occur inside an infinite loop   
    - `While(true) {`   
    - `WatchKey key = ws.take();`   
  - When an event occurs, the event is processed using the `WatchKey` object returned by `take()`   
  - `WatchKey` has monitoring status, monitoring directory, and event information   
    - Call `pollEvents()` to obtain `WatchEvent` object and know what has happened   
   
```java
for (WatchEvent<?> event : key.pollEvents()) {
    WatchEvent.Kind k = event.kind();    // Event Type
    Path p = (Path) event.context();    // File Name
    ...
}
boolean valid = key.reset();    // to keep an monitoring
if (!valid)
break;
```
   
// WatchService 인터페이스 이용하기 예시   
- Example of using the WatchService interface   
   
```java
try {
    WatchService ws;
    ws = FileSystem.getDefault().newWatchService();
    Path path = Paths.get("c:\\java\\temp");
    path.register(ws, StandardWatchEventKinds.ENTRY_CREATE, StandardWatchEventKinds.ENTRY_DELETE, StandardWatchEventKinds.ENTRY_MODIFY);
    while (true) {
        WatchKey key = ws.take();
        for (WatchEvent<?> event : key.pollEvents()) {
            WatchEvent.Kind k = event.kind();
            Path p = (Path) event.context();
            if (k == StandardWatchEventKinds.ENTRY_CREATE) {
                System.out.println("File " + p.getFileName() + " is created.");
            } else if (k == StandardWatchEventKinds.ENTRY_DELETE) {
                System.out.println("File " + p.getFileName() + " is deleted.");
            }
            ...
            boolean valid = key.reset();
            if (!valid) break;
        }
    }
}
```
   
- Result   
   
```
File file.txt is modified.
File New Text Document.txt is created.
File New Text Document.txt is deleted.
File New Document.txt is created.
...
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
