---
layout: post
title:  "JScript: FileSystemObject Concept"
date:   2024-03-19 09:00:00 +0900
categories: [JScript]
---

### FileSystemObject 개체 모델   
   
- Active Server Pages, Windows Scripting Host, 또는 스크립팅을 사용할 수 있는 다른 응용 프로그램에서 스크립트를 쓸 경우 웹 서버 상에서 폴더(디렉터리)와 파일을 추가, 이동, 변동, 작성, 삭제하는 일이 중요함   
- 웹 서버에 연결된 드라이브에 관한 정보를 보고 해당 드라이브를 조작하는 일이 필요한 경우도 있음   
- 스크립팅으로 FileSystemObject(FSO) 개체 모델을 사용하여 드라이브, 폴더, 파일을 처리할 수 있음   
   
<br />
### FileSystemObject와 Scripting 런타임 라이브러리 참조   
   
- FileSystemObject(FSO) 개체 모델을 사용하면 폴더와 파일을 처리하는데 사용할 수 있는 풍부한 속성, 메서드, 이벤트와 더블어 잘 알고 있는 object.method 구문을 사용할 수 있음   
   
- 이 개체 기반 도구는 아래의 도구들과 함께 사용함   
  - 웹 페이지를 만드는 HTML   
  - Microsoft Windows용 일괄 처리 파일을 만드는 Windows Scripting Host   
  - 다른 언어로 개발한 응용 프로그램에 스크립팅 기능을 제공하는 Script Control   
   
- 클라이언트 측에서 FSO를 사용하면 클라이언트의 로컬 파일 시스템에 원하지 않는 엑세스가 이루어지는 심각한 보안 문제가 발생할 수 있기 때문에 이 설명서에서는 인터넷 웹 페이지에서 실행되는 스크립트를 만드는 FSO 개체 모델을 서버 측에서 사용하는 것으로 가정함   
- 서버 측에서 사용되기 때문에 Internet Explorer 기본 보안 설정에서는 FileSystemObject 개체의 클라이언트 측 사용을 허용하지 않음   
- 이런 기본값을 무시하면 로컬 컴퓨터가 파일 시스템에 원치 않는 엑세스를 할 수 있어서 결국 파일 시스템 무결성이 전체적으로 손상되거나 데이터가 손실될 수 있음   
   
- FSO 개체 모델을 사용하면 서버 측 응용 프로그램에서 폴더를 작성, 변경, 이동, 삭제하거나 특정 폴더의 존재 여부와 위치를 검색할 수 있음   
- 또한 폴더 이름이나 만든 날짜, 마지막으로 수정한 날짜 등 폴더에 관한 정보를 찾을 수도 있음   
   
- FSO 개체 모델을 사용하면 파일을 더 쉽게 처리할 수 있음   
- 파일을 처리할 때의 주된 목표는 공간과 리소스를 효율적으로 사용하며 엑세스하기 쉬운 형식으로 데이터를 저장하는 것임   
- 사용자는 파일을 만들고, 데이터를 삽입, 변경, 출력할 수 있어야 함   
- 데이터를 Access나 SQL Server 등의 데이터베이스에 저장하면 응용 프로그램에 상당한 양의 오버헤드를 추가하기 때문에 데이터는 이진 형식이나 텍스트 형식으로 저장하는 것이 가장 효율적임   
- 사용자가 이런 오버헤드를 피할 수도 있고, 데이터 엑세스 요건에 기능을 모두 갖춘 데이터베이스에 연결된 추가 기능을 요청하지 않을 수도 있음   
   
- Scripting 형식 라이브러리(Scrrun.dll)에 포함되어 있는 FSO 개체 모델은 TextStream 개체를 통해 텍스트 파일 작성과 조작 기능을 지원함   
- 이진 파일 작성과 조작 기능은 지원하지 않음   
   
<br />
### FileSystemObject 개체   
   
- FileSystemObject(FSO) 개체 모델에는 아래 개체와 컬렉션이 포함됨   
   
|Object/Collection|Description|
|:---|:---|
|FileSystemObject|- 기본 개체<br>- 드라이브, 폴더 및 파일에 관한 정보를 만들고, 삭제하고, 확보할 수 있을 뿐만 아니라 일반적으로 이를 조작할 수 있는 메서드와 속성이 포함되어 있음<br>- 이 개체와 연결된 많은 메서드들은 다른 FSO 개체에 이들 메서드를 복사함<br>- 이런 메서드는 편의를 위해 마련된 것임|
|Drive|- 개체<br>- 드라이브 공유 이름과 사용할 수 있는 공간 크기 등 시스템에 연결된 드라이브에 관한 정보를 볼 수 있는 메서드와 속성이 포함되어 있음<br>- "드라이브"가 꼭 하드 디스크를 의미하는 것은 아니고, CD-ROM이나 RAM 디스크 등도 드라이브에 해당될 수 있음<br>- 드라이브가 실제로 시스템에 연결되어 있을 필요는 없음<br>- 네트워크를 통해 논리적으로 연결되어 있어도 좋음|
|Drives|- 컬렉션<br>- 실제로 또는 논리적으로 시스템에 연결되어 있는 드라이브 목록을 제공함<br>- Drives 컬렉션에는 형식에 관계없이 모든 드라이브가 포함됨<br>- 이동식 매체 드라이브는 매체가 삽입되어 있지 않아도 이 컬렉션에 나타남|
|File|- 개체<br>- 파일을 만들거나, 삭제하거나, 이동하는데 사용할 수 있는 메서드와 속성이 포함되어 있음<br>- 또한 시스템 쿼리를 통해 파일 이름, 경로, 기타 다양한 속성을 가져올 수 있음|
|Files|- 컬렉션<br>- 폴더에 포함되어 있는 모든 파일 목록을 제공|
|Folder|- 개체<br>- 폴더를 만들거나, 삭제하거나, 이동하는데 사용할 수 있는 메서드와 속성이 포함되어 있음<br>- 또한 시스템 쿼리를 통해 폴더 이름, 경로, 기타 다양한 속성을 가져올 수 있음|
|Folders|- 컬렉션<br>- Folder에 있는 모든 폴더 목록을 제공함|
|TextStream|- 개체<br>- 텍스트 파일을 읽고 쓸 수 있음|

<br />
### FileSystemObject 프로그래밍   
   
- FileSystemObject(FSO) 개체 모델로 프로그래밍하려면   
  - CreateObject 메서드를 사용하여 FileSystemObject 개체를 만듦   
  - 새로 만든 개체에 적절한 메서드를 사용함   
  - 개체 속성에 엑세스함   
   
- FSO 개체 모델은 Scrrun.dll 파일에 있는 Scripting 형식 라이브러리에 포함되어 있음   
- 따라서 FSO 개체 모델을 사용하려면 웹 서버의 적절한 시스템 디렉터리에 Scrrun.dll 이 있어야 함   
   
#### FileSystemObject 개체 작성   
   
- 먼저, CreateObject 메서드를 사용하여 FileSystemObject 개체를 만듦   
- VBScript에서는 아래 코드를 사용하여 FileSystemObject 인스턴스를 만듦   
   
```vbscript
Dim fso
Set fso = CreateObject("Scripting.FileSystemObject")
```
   
- 예제 코드를 보면 FileSystemObject 인스턴스를 만드는 방법을 알 수 있음   
   
- JScript에서는 아래 코드를 사용하여 같은 결과가 나옴   
   
```javascript
var fso;
fso = new ActiveXObject("Scripting.FileSystemObject");
```
   
- 두 예제 모두에서 Scripting은 형식 라이브러리의 이름이고 FileSystemObject는 만들려는 개체의 이름임   
- 다른 개체를 만드는 횟수와는 관계없이 FileSystemObject 개체 인스턴스는 하나만 만들 수 있음   
   
#### 적절한 메서드 사용   
   
- 둘째, FileSystemObject 개체의 적절한 메서드는 사용함   
- 예를 들어, 새 개체를 만들려면 CreateTextFile 이나 CreateFolder를 사용함 (FSO 개체 모델은 드라이브를 만들거나 삭제하는 기능은 지원하지 않음)   
   
- 개체를 삭제하려면 FileSystemObject 개체의 DeleteFile 메서드와 DeleteFolder 메서드 또는 File 개체와 Folder 개체의 Delete 메서드를 사용해야 함   
- 적절한 메서드를 사용하면 파일을 복사하거나 이동할 수도 있음   
   
- FileSystemObject 개체 모델 기능 중 일부는 중복됨   
- 예를 들어, 파일을 복사할 때 FileSystemObject 개체의 CopyFile 메서드를 사용할 수도 있고 File 개체의 Copy 메서드를 사용할 수도 있음   
- 두 메서드는 사용 방식이 똑같으며 프로그래밍의 융통성을 위해 제공됨   
   
#### 기존 드라이브, 파일, 폴더 엑세스   
   
- 기존 드라이브, 파일, 폴더에 엑세스하려면 FileSystemObject 개체의 "get" 메서드를 사용함   
  - GetDrive   
  - GetFolder   
  - GetFile   
   
- VBScript에서 기존 파일에 엑세스하려면 아래와 같이 함   
   
```vbscript
Dim fso, f1
Set fso = CreateObject("Scriptiong.FileSystemObject")
Set f1 = fso.GetFile("c:\test.txt")
```
   
- JScript에서 기존 파일에 엑세스하려면 아래 코드를 사용함   
   
```javascript
var fso, f1;
fso = new ActiveXObject("Scripting.FileSystemObject");
f1 = fso.GetFile("c:\\test.txt");
```
   
- "create" 함수는 개체에 대한 핸들을 반환하기 때문에 새로 만든 개체에는 "get" 메서드를 사용해서는 안됨   
- 예를 들어, CreateFolder 메서드로 새 폴더를 만든 경우에는 Name, Path, Size 등의 속성에 엑세스하기 위해 GetFolder 메서드를 사용해서는 안됨   
- 새로 만든 폴더에 대한 핸들을 가져오려면 CreateFolder 함수에 변수를 설정한 후 속성, 메서드, 이벤트 등에 엑세스해야 함   
- VBScript에서 이 작업을 하려면 아래 코드를 사용함   
   
```javascript
Sub CreateFolder
    Dim fso, fldr
    Set fso = CreateObject("Scripting.FileSystemObject")
    Set fldr = fso.CreateFolder("C:\MyTest")
    Response.Write "만든 폴더 : " & fldr.Nam;
End Sub
```
   
- JScript에서 CreateFolder 함수에 변수를 설정하려면 아래 구문을 사용함   
   
```javascript
function CreateFolder()
{
    var fso, fldr;
    fso = new ActiveXObject("Scripting.FileSystemObject");
    fldr = fso.CreateFolder("C:\\MyTest");
    Response.Write("만든 폴더 : " + fldr.Name);
}
```
   
#### 개체 속성 엑세스   
   
- 개체에 대한 핸들이 있으면 개체의 속성에 엑세스할 수 있음   
- 예를 들어, 특정 폴더의 이름을 가져오려면 먼저 개체 인스턴스를 만든 후 적절한 메서드로(이 경우에는 폴더가 이미 존재하기 때문에 GetFolder 메서드임) 핸들을 가져옴   
   
- VBScript에서 GetFolder 메서드에 대한 핸들을 가져오려면 아래 코드를 사용함   
   
```vbscript
Set fldr = fso.GetFolder("C:\")
```
   
- JScript에서 같은 결과를 내려면 아래 코드를 사용함   
   
```javascript
var fldr = fso.GetFolder("C:\\");
```
   
- 이제 Folder 개체에 대한 핸들을 가져왔기 때문에 Name 속성을 확인할 수 있음   
- VBScript에서 이 속성을 확인하려면 아래 코드를 사용함   
   
```vbscript
Response.Write "폴더 이름 : " & fldr.Name
```
   
- JScript에서 Name 속성을 확인하려면 아래 구문을 사용함   
   
```javascript
Response.Write("폴더 이름 : " + fldr.Name);
```
   
- VBScript에서 파일을 마지막으로 수정한 시간을 찾으려면 아래 구문을 사용함   
   
```vbscript
Dim fso, f1
Set fso = CreateObject("Scripting.FileSystemObject")
' 쿼리에 사용할 File 개체를 가져옴
Set f1 = fso.GetFile("C:\detlog.txt")
' 정보를 인쇄
Response.Write "마지막으로 파일을 수정한 시간 : " & f1.DateLastModified
```
   
- JScript에서 같은 내용을 찾으려면 아래 코드를 사용함   
   
```javascript
var fso, f1;
fso = new AcriveXObject("Scripting.FileSystemObject");
// 쿼리에 사용할 File 개체를 가져옴
f1 = fso.GetFile("C:\\detlog.txt");
// 정보를 인쇄
Response.Write("마지막으로 파일을 수정한 시간 : " + f1.DateLastModified);
```
   
<br />
### 드라이브와 폴더 작업   
   
- FileSystemObject(FSO) 개체 모델을 사용하면 Windows 탐색기에서 대화형으로 할 수 있는 작업을 프로그램에서 드라이브와 폴더로 할 수 있음   
   
#### 드라이브 정보 보기   
   
- Drive 개체를 사용하면 실제로 또는 네트워크를 통해 시스템에 연결되어 있는 다양한 드라이브에 관한 정보를 볼 수 있음   
- 이 개체의 속성을 사용하면 아래와 같은 정보를 볼 수 있음   
  - 바이트 단위로 나타낸 드라이브 전체 크기(TotalSize 속성)   
  - 바이트 단위로 나타낸 사용 가능한 드라이브 공간 크기(AvailableSpace 또는 FreeSpace 속성)   
  - 드라이브에 지정한 문자(DriveLetter 속성)   
  - 이동식, 고정식, 네트워크, CD-ROM, RAM 디스크 등의 드라이브 형식(DriveType 속성)   
  - 드라이브 일련 번호(SerialNumber 속성)   
  - FAT, FAT21, NTFS 등 드라이브에서 사용하는 파일 시스템 형식(FileSystem 속성)   
  - 드라이브 사용 가능 여부(IsReady 속성)   
  - 공유 이름 또는 볼륨 이름(ShareName과 VolumeName 속성)   
  - 드라이브의 경로 또는 루트 폴더(Path와 RootFolder 속성)   
   
- 예제 코드를 보면 FileSystemObject에서 이런 속성을 사용하는 방법을 알 수 있음   
   
#### Drive 개체 사용 예제   
   
- Drive 개체는 드라이브에 관한 정보를 모으는데 사용함   
- 아래 코드에서는 실제 Drive 개체에 대한 참조가 없는 대신 GetDrive 메서드를 사용하여 기존 Drive 개체(이 경우에는 drv)에 대한 참조를 가져옴   
   
- 아래 예제는 VBScript에서 Drive 개체를 사용하는 방법을 보여줌   
   
```vbscript
Sub ShowDriveInfo(drvPath)
    Dim fso, drv, s
    Set fso = CreateObject("Scripting.FileSystemObject")
    Set drv = fso.GetDrive(fso.GetDriveName(drvPath))
    s = "드라이브 " & UCase(drvPath) & " - "
    s = s & drv.VolumeName & "<br>"
    s = s & "전체 공간 : " & FormatNumber(drv.TotalSize / 1024, 0)
    s = s & " KB" & "<br>"
    s = s & "사용 가능한 공간 : " & FormatNumber(drv.FreeSpace / 1024, 0)
    s = s & " KB" & "<br>"
    Response.Write s
End Sub
```
   
- 아래 코드는 JScript의 같은 기능을 보여줌   
   
```javascript
function ShowDriveInfo(drvPath)
{
    var fso, drv, s = "";
    fso = new ActiveXObject("Scripting.FileSystemObject");
    drv = fso.GetDrive(fso.GetDriveName(drvPath));
    s += "드라이브 " + drvPath.toUpperCase() + " - ";
    s += drv.VolumeName + "<br>";
    s += "전체 공간 : " + drv.TotalSize / 1024;
    s += " KB" + "<br>";
    s += "사용 가능한 공간 : " + drv.FreeSpace / 1024;
    s += " KB" + "<br>";
    Response.Write(s);
}
```
   
#### 폴더 작업   
   
- 아래 표에는 일반적인 폴더 작업과 이런 작업에 사용되는 메서드가 설명되어 있음   
   
|Task|Method|
|:---|:---|
|폴더 만듦|FileSystemObject.CreateFolder|
|폴더 삭제|Folder.Delete 또는 FileSystemObject.DeleteFolder|
|폴더 이동|Folder.Move 또는 FileSystemObject.MoveFolder|
|폴더 복사|Folder.Copy 또는 FileSystemObject.CopyFolder|
|폴더 이름 검색|Folder.Name|
|드라이브에서 폴더의 존재를 찾음|FileSystemObject.FolderExists|
|기존 Folder 개체의 인스턴스를 가져옴|FileSystemObject.GetFolder|
|폴더의 상위 폴더 이름을 찾음|FileSystemObject.GetParentFolderName|
|시스템 폴더의 경로를 찾음|FileSystemObject.GetSpecialFolder|
   
- 예제 코드를 보면 FileSystemObject에서 사용되는 메서드 수와 속성 수를 알 수 있음   
   
- 아래 예제는 VBScript에서 폴더를 조작하고 정보를 보는데 사용되는 Folder 개체와 FileSystemObject 개체의 사용법을 보여줌   
   
```vbscript
Sub ShowFolderInfo()
    Dim fso, fldr, s
    ' FileSystemObject의 인스턴스를 가져옴
    Set fso = CreateObject("Scripting.FileSystemObject")
    ' Drive 개체를 가져옴
    Set fldr = fso.GetFolder("C:")
    ' 상위 폴더 이름 인쇄
    Response.Write "상위 폴더 이름 : " & fldr & "<br>"
    ' 드라이브 이름 인쇄
    Response.Write "드라이브 이름 : " & fldr.Drive & "<br>"
    ' 루트 파일 이름 인쇄
    If fldr.IsRootFolder = true Then
        Response.Write "루트 폴더임" & "<br><br>"
    Else
        Response.Write "루트 폴더 아님" & "<br><br>"
    End If
    ' FileSystemObject 개체로 새 폴더를 만듦
    fso.CreateFolder ("C:\Bogus")
    Response.Write "만든 폴더 C:\Bogus" & "<br>"
    ' 폴더의 기본 이름을 인쇄
    Response.Write "기본 이름 = " & fso.GetBaseName("C:\bogus") & "<br>"
    ' 새로 만든 폴더를 삭제
    fso.DeleteFolder ("C:\Bogus")
    Response.Write "삭제한 폴더 C:\Bogus" & "<br>"
End Sub
```
   
- 아래 예제는 JScript에서 Folder 개체와 FileSystemObject 개체의 사용법을 보여줌   
   
```javascript
function ShowFolderInfo()
{
    var fso, fldr, s = "";
    // FileSystemObject의 인스턴스를 가져옴
    fso = new ActiveXObject("Scripting.FileSystemObject");
    // Drive 개체를 가져옴
    Set fldr = fso.GetFolder("C:");
    // 상위 폴더 이름 인쇄
    Response.Write("상위 폴더 이름 : " + fldr + "<br>");
    // 드라이브 이름 인쇄
    Response.Write("드라이브 이름 : " + fldr.Drive + "<br>");
    // 루트 파일 이름 인쇄
    If(fldr.IsRootFolder)
        Response.Write("루트 폴더임");
    else
        Response.Write("루트 폴더 아님");
    Response.Write("<br><br>");
    // FileSystemObject 개체로 새 폴더를 만듦
    fso.CreateFolder("C:\\Bogus");
    Response.Write("만든 폴더 C:\Bogus" + "<br>");
    // 폴더의 기본 이름을 인쇄
    Response.Write("기본 이름 = " + fso.GetBaseName("C:\\bogus") + "<br>");
    // 새로 만든 폴더를 삭제
    fso.DeleteFolder ("C:\Bogus");
    Response.Write("삭제한 폴더 C:\Bogus" + "<br>");
}
```
   
<br />
### 파일 작업   
   
- 파일 작업은 크게 두 범주로 구분됨   
  - 파일 만들기, 데이터 추가와 삭제, 파일 읽기   
  - 파일 이동, 복사, 삭제   
   
#### 파일 만들기   
   
- 빈 텍스트 파일("텍스트 스트림"이라고도 함)을 만드는 방법에는 세 가지가 있음   
   
- 하나는 CreateTextFile 메서드를 사용하는 것임   
- 아래 예제는 VBScript에서 이 메서드를 사용하여 텍스트 파일을 작성하는 방법을 보여줌   
   
```vbscript
Dim fso, f1
Set fso = CreateObject("Scripting.FileSystemObject")
Set f1 = fso.CreateTextFile("C:\testfile.tet", true)
```
   
- JScript에서 이 메서드를 사용하려면 아래 코드를 사용함   
   
```javascript
var fso, f1;
fso = new ActiveXObject("Scripting.FileSystemObject");
f1 = fso.CreateTextFile("C:\\testfile.txt", true);
```
   
- 예제 코드를 보면 CreateTextFile 메서드를 FileSystemObject에서 사용하는 방법을 알 수 있음   
   
- 텍스트 파일을 만드는 두번째 방법은 ForWriting 플래그를 설정하고 FileSystemObject 개체의 OpenTextFile 메서드를 사용하는 것임   
- VBScript에서 사용하는 코드는 아래 예제와 같음   
   
```vbscript
Dim fso, ts
Const ForWriting = 2
Set fso = CreateObject("Scripting.FileSystemObject")
Set ts = fso.OpenTextFile("c:\test.txt", ForWriting, true)
```
   
- JScript에서 이 메서드를 사용하여 텍스트 파일을 만들려면 아래 코드를 사용함   
   
```javascript
var fso, ts;
var ForWriting = 2;
fso = new ActiveXObject("Scripting.FileSystemObject");
ts = fso.OpenTextFile("c:\test.txt", ForWriting, true);
```
   
- 텍스트 파일을 만드는 세번째 방법은 ForWriting 플러그를 설정하고 OpenAsTextStream 메서드를 사용하는 것임   
- VBScript에서 사용하려면 아래 코드를 사용함   
   
```vbscript
Din fso, f1, ts
Const ForWriting = 2
Set fso = CreateObject("Scripting.FileSystemObject")
fso.CreateTextFile("C:\text1.txt")
Set f1 = fso.GetFile("C:\test1.txt")
Set ts = f1.OpenAsTextStream(ForWriting, true)
```
   
- JScript에서는 아래 예제와 같은 코드를 사용함   
   
```javascript
var fso, f1, ts;
var ForWriting = 2;
fso = new ActiveXObject("Scripting.FileSystemObject");
fso.CreateTextFile("C:\\text1.txt");
f1 = fso.GetFile("C:\\test1.txt");
ts = f1.OpenAsTextStream(ForWriting, true);
```
   
#### 파일에 데이터 추가   
   
- 텍스트 파일을 만든 후 아래와 같은 세 단계를 따라 데이터를 파일에 추가함   
  1. 텍스트 파일 열기   
  2. 데이터 작성   
  3. 파일 닫기   
   
- 기존 파일을 열려면 FileSystemObject 개체의 OpenTextFile 메서드나 File 개체의 OpenAsTextStream 메서드를 사용함   
   
- 열린 텍스트 파일에 데이터를 쓰려면 아래 표에 설명되어 있는 작업에 따라 TextStream 개체의 Write, WriteLine 또는 WriteBlankLines 메서드를 사용   
   
|Task|Method|
|:---|:---|
|열린 텍스트 파일에 뒤에 오는 줄 바꿈 문자 없이 데이터를 씀|Write|
|열린 텍스트 파일에 데이터와 뒤에 오는 줄 바꿈 문자를 씀|WriteLine|
|열린 텍스트 파일에 빈 줄을 하나 이상 씀|WriteBlankLines|
   
- 예제 코드를 보면 FileSystemObject에서 Write, WriteLine, WriteBlankLines 메서드를 사용하는 방법을 알 수 있음   
   
- 열린 파일을 닫으려면 TextStream 개체의 Close 메서드를 사용함   
   
- 예제 코드를 보면  FileSystemObject에서 Close 메서드를 사용하는 방법을 알 수 있음   
   
- 줄 바꿈 문자에는 커서를 다음 줄의 시작 부분으로 넘기는 문자(운영 체제에 따라 다름)가 있음(캐리지 리턴/줄 바꿈)   
- 일부 문자열의 끝에는 이미 그런 인쇄되지 않는 문자가 있는 것도 있음   
   
- 아래 VBScript 예제는 파일을 열고, 세 가지 쓰기 방법을 모두 사용하여 파일에 데이터를 추가하고, 파일을 닫는 방법을 보여줌   
   
```vbscript
Sub CreateFile()
    Dim fso, tf
    Set fso = CreateObject("Scripting.FileSystemObject")
    Set tf = fso.CreateTextFile("C:\testfile.txt", true)
    ' 줄 바꿈 문자가 있는 줄을 씀
    tf.WriteLine("테스트 중 1, 2, 3")
    ' 파일에 줄 바꿈 문자를 세 개 씀
    tf.WriteBlankLines(3)
    ' 줄을 씀
    tf.Write("테스트임")
    tf.Close
End Sub
```
   
- 아래 예제는 JScript에서 세 가지 메서드의 사용법을 보여줌   
   
```javascript
function CreateFile()
{
    var fso, tf;
    fso = new ActiveXObject("Scripting.FileSystemObject");
    tf = fso.CreateTextFile("C:\\testfile.txt", true);
    // 줄 바꿈 문자가 있는 줄을 씀
    tf.WriteLine("테스트 중 1, 2, 3");
    // 파일에 줄 바꿈 문자를 세 개 씀
    tf.WriteBlankLines(3);
    // 줄을 씀
    tf.Write("테스트임");
    tf.Close();
}
```
   
#### 파일 읽기   
   
- 텍스트 파일에서 데이터를 읽으려면 TextStream 개체의 Read, ReadLine, 또는 ReadAll 메서드를 사용해야 함   
- 아래 표에는 여러 작업에 사용할 수 있는 메서드가 설명되어 있음   
   
|Task|Method|
|:---|:---|
|파일에서 지정한 수의 문자를 읽음|Read|
|한 줄 전체를 읽음(줄 바꿈 문자는 제외하고 줄 바꿈 문자까지)|ReadLine|
|텍스트 파일의 전체 내용을 읽음|ReadAll|
   
- 예제 코드를 보면 FileSystemObject에서 ReadAll 메서드와 ReadLine 메서드를 사용하는 방법을 알 수 있음   
   
- Read 메서드나 ReadLine 메서드를 사용하면서 데이터의 특정 부분을 건너뛰려면 Skip 메서드 또는 SkipLine 메서드를 사용함   
- 읽기 메서드의 결과로 나오는 텍스트는 문자열로 저장되며 컨트롤에 표시하거나, 문자열 함수(Left, Right, Mid)로 구문을 분석하거나, 연결하는 등의 조작을 할 수 있음   
   
- 아래 VBScript 예제는 파일을 열고, 내용을 쓰고, 다시 읽는 방법을 보여줌   
   
```vbscript
Sub ReadFiles
    Dim fso, f1, ts, s
    Const ForReading = 1
    Set fso = CreateObject("Scripting.FileSystemObject")
    Set f1 = fso.CreateTextFile("C:\testfile.txt", true)
    ' 줄을 씀
    Response.Write "파일 쓰는 중 <br>"
    f1.WriteLine "안녕하십니까?"
    f1.WriteBlankLines(1)
    f1.Close
    ' 파일 내용을 읽음
    Response.Write "파일 읽는 중 <br>"
    Set ts = fso.OpenTextFile("C:\testfile.txt", ForReading)
    s = ts.ReadLine
    Response.Write "파일 내용 = '" & s & "'"
    ts.Close
End Sub
```
   
- 아래 코드는 JScript에서 같은 작업을 하는 방법을 보여줌   
   
```javascript
function ReadFiles()
{
    var fso, f1, ts, s;
    var ForReading = 1;
    fso = new ActiveXObject("Scripting.FileSystemObject");
    f1 = fso.CreateTextFile("C:\\testfile.txt", true);
    // 줄을 씀
    Response.Write("파일 쓰는 중 <br>");
    f1.WriteLine("안녕하십니까?");
    f1.WriteBlankLines(1);
    f1.Close();
    // 파일 내용을 읽음
    Response.Write("파일 읽는 중 <br>");
    ts = fso.OpenTextFile("C:\\testfile.txt", ForReading);
    s = ts.ReadLine();
    Response.Write("파일 내용 = '" + s + "'");
    ts.Close();
}
```
   
#### 파일 이동, 복사, 삭제   
   
- FSO 개체 모델에는 아래 표에 설명되어 있는 것처럼 파일 이동, 복사, 삭제에 대해 각각 두 가지 메서드가 있음   
   
|Task|Method|
|:---|:---|
|파일 이동|File.Move 또는 FileSystemObject.MoveFile|
|파일 복사|File.Copy 또는 FileSystemObject.CopyFile|
|파일 삭제|File.Delete 또는 FileSystemObject.DeleteFile|
   
- 예제 코드를 보면 FileSystemObject에서 파일을 삭제하는 두 가지 방법을 알 수 있음   
   
- 아래 VBScript 예제에서는 C드라이브의 루트 디렉터리에 텍스트 파일을 만들고, 파일에 정보를 쓰고, 파일을 \tmp라는 디렉터리로 이동하고, \temp라는 디렉터리에 복사본을 만든 후에 두 디렉터리 모두에게 복사본을 삭제함   
   
- 아래 예제를 실행하려면 먼저 C드라이브의 루트 디렉터리에 \tmp와 \temp 디렉터리를 만들어야 함   
   
```vbscript
Sub ManipFiles
    Dim fso, f1, f2, s
    Set fso = CreateObject("Scripting.FileSystemObject")
    Set f1 = fso.CreateTextFile("C:\textfile.txt", true)
    Response.Write "파일 쓰는 중 <br>"
    ' 줄을 씀
    f1.Write ("테스트임")
    ' 파일을 닫음
    f1.Close
    Response.Write "파일을 C:\tmp로 이동하는 중 <br>"
    ' C:\ 루트에 있는 파일에 대한 핸들을 가져옴
    Set f2 = fso.GetFile("C:\testfile.txt")
    ' 파일을 \tmp 디렉터리로 이동
    f2.Move ("C:\tmp\testfile.txt")
    Response.Write "파일을 C:\temp로 복사하는 중 <br>"
    ' 파일을 \temp로 복사
    f2.Copy ("C:\temp\testfile.txt")
    Response.Write "파일 삭제 중 <br>"
    ' 파일의 현재 위치에 대한 핸들을 가져옴
    Set f2 = fso.GetFile("C:\tmp\testfile.txt")
    Set f3 = fso.GetFile("C:\temp\testfile.txt")
    ' 파일을 삭제
    f2.Delete
    f3.Delete
    Response.Write "완료"
End Sub
```

- 아래 코드는 JScript에서 같은 작업을 하는 방법을 보여줌   
   
```javascript
function ManipFiles()
{
    var fso, f1, f2, s;
    fso = new ActiveXObject("Scripting.FileSystemObject");
    f1 = fso.CreateTextFile("C:\\textfile.txt", true);
    Response.Write("파일 쓰는 중 <br>");
    // 줄을 씀
    f1.Write("테스트임");
    // 파일을 닫음
    f1.Close();
    Response.Write("파일을 C:\\tmp로 이동하는 중 <br>");
    // C:\ 루트에 있는 파일에 대한 핸들을 가져옴
    f2 = fso.GetFile("C:\\testfile.txt");
    // 파일을 \tmp 디렉터리로 이동
    f2.Move("C:\\tmp\\testfile.txt");
    Response.Write("파일을 C:\\temp로 복사하는 중 <br>");
    // 파일을 \temp로 복사
    f2.Copy("C:\\temp\\testfile.txt");
    Response.Write("파일 삭제 중 <br>");
    // 파일의 현재 위치에 대한 핸들을 가져옴
    f2 = fso.GetFile("C:\\tmp\\testfile.txt");
    f3 = fso.GetFile("C:\\temp\\testfile.txt");
    // 파일을 삭제
    f2.Delete();
    f3.Delete();
    Response.Write("완료");
}
```
   
<br />
### FileSystemObject Term   
   
#### run-time error   
// 런타임 오류   
   
- 코드 실행 중 발생하는 오류   
- 런타임 오류는 잘못된 연산을 수행하는 문이 있을 경우 발생함   
   
#### string expression   
// 문자식   
   
- 일련의 연속적인 문자로 평가되는 모든 식   
- 문자식의 요소에는 문자열, 문자열 리터럴, 문자열 상수, 또는 문자열 변수를 반환하는 함수를 사용할 수 있음   
   
#### array   
// 배열   
   
- 데이터 형식이 같은 요소를 순차적으로 인덱스로 묶은 집합   
- 각 배열 요소에는 고유한 확인 인덱스 번호가 있음   
- 배열 안에 있는 한 요소를 변경해도 다른 요소들은 영향을 받지 않음   
   
#### collection   
- 컬렉션   
   
- 관련된 개체 집합이 들어있는 개체   
- 컬렉션에 변경 사항이 있을 때마다 컬렉션에 있는 개체의 위치가 바뀌므로 컬렉션에 있는 특정 개체의 위치는 매번 달라질 수 있음   
   
#### type library   
// 형식 라이브러리   
   
- 노출된 개체, 속성, 메서드에 대한 표준 설명이 들어있는 다른 파일 안의 파일이나 구성 요소   
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
