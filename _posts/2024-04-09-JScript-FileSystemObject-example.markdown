---
layout: post
title:  "JScript: FileSystemObject Example"
date:   2024-04-09 09:00:00 +0900
categories: [JScript]
---

- 이 부분에 나와있는 예제코드는 FileSystemObject 개체 모델에서 사용할 수 있는 여러 기능을 실제로 적용한 예입니다. 이 코드에서는 개체 모델의 모든 기능을 함께 사용하여 작업하는 방법과 이러한 기능을 코드에서 효율적으로 사용하는 방법을 보여줍니다.   
   
- 여기에 있는 코드는 포괄적으로 만들었기 때문에 이 코드를 컴퓨터에서 실제로 실행하려면 다른 코드를 추가하고 일부를 변경해야 합니다. Active Server Pages와 Windows Scripting Host 사이에는 사용자에 대한 입력 및 출력 방법이 다양하기 때문에 이런 변경은 필수적입니다.   
   
- Active Server Pages에서 이 코드를 실행하려면 아래 단계를 사용하십시오.   
   
    1. .asp 확장자명을 사용하여 표준 웹 페이지를 만듭니다.   
    2. 아래 예제 코드를 파일의 <BODY>...</BODY> 태그 사이에 복사합니다.   
    3. 코드 전체를 <%...%> 태그로 묶습니다.   
    4. Option Explicit 문을 코드의 현재 위치에서 HTML 페이지의 맨 위 즉, <HTML> 태그보다 위쪽에 놓습니다.   
    5. Option Explicit 문 앞 뒤에 <%...%> 태그를 추가하여 이 내용이 서버 측에서 실행되도록 합니다.   
    6. 아래 코드를 예제 코드 끝에 추가합니다.   
   
```javascript
Sub Print(x)
    Response.Write "<PRE><FONT FACE=""Courier New"" SIZE=""1"">"
    Response.Write x
    Response.Write "</FONT></PRE>"
End Sub
Main
```
   
- 위의 코드는 서버 측에서 실행한 후 결과를 클라이언트 측에 표시하는 인쇄 프로시저를 추가합니다. 이 코드를 Windows Scripting Host에서 실행하려면 예제 코드 끝에 아래 코드를 추가하십시오.   
   
```javascript
Sub Print(x)
    WScript.Echo x
End Sub
Main
```
   
코드에는 다음 부분이 포함되어 있습니다.   
   
<br /><br />
<hr>
   
### FileSystemObject 예제 코드   
   
- Copyrigth 1998 Microsoft Corporation. All Rights Reserved.   
   
<br />
### Option Explicit   
   
- 코드 품질 관련 사항   
  1. 아래 코드에서는 "&" 연산자로 짧은 문자열을 연결하여 문자열을 조작하는 일이 많습니다. 문자열 연결은 리소스가 많이 필요한 작업이기 때문에 문자열 연결을 사용하여 코드를 쓰는 것은 비효율적인 방법입니다. 하지만 코드 쓰기를 관리하는 데는 적절합니다. 이 프로그램에서는 디스크 작업을 많이 수행할 뿐만 아니라 디스크가 문자열 연결에 필요한 메모리 작업보다는 훨씬 느리기 때문에 문자열 연결을 사용했습니다. 이 코드는 설명용 코드이지 제품용 코드가 아닙니다.   
  2. 선언된 변수 액세스가 선언되지 않은 변수 액세스보다 약간 빠르기 때문에 "Option Explicit"을 사용했습니다. 이렇게 하면 DriveTypeCDROM을 DriveTypeCDORM으로 잘못 입력하는 것처럼 코드에 버그가 포함되는 것도 방지할 수도 있습니다.   
  3. 코드를 읽기 쉽도록 하기 위해 이 코드에는 오류 처리 부분이 없습니다. 코드가 일반적인 상황에서 오류를 일으키지 않도록 미리 주의를 기울이기는 했지만 파일 시스템이 예기치 않은 결과를 보일 수도 있습니다. 제품 코드에서는 On Error Resume Next와 Err 개체를 사용하여 발생할 수 있는 오류를 잡아야 합니다.   
   
<br />
### 편리한 전역 변수   
   
```javascript
Dim TabStop
Dim NewLine

Const TestDrive = "C"
Const TestFilePath = "C:\Test"
```
   
<br />
### Drive.DriveType에서 반환하는 상수   
   
```javascript
Const DriveTypeRemovable = 1
Const DriveTypeFixed = 2
Const DriveTypeNetwork = 3
Const DriveTypeCDROM = 4
Const DriveTypeRAMDisk = 5
```
   
<br />
### File.Attributes에서 반환하는 상수   
   
```javascript
Const FileAttrNormal = 0
Const FileAttrReadOnly = 1
Const FileAttrHidden = 2
Const FileAttrSystem = 4
Const FileAttrVolume = 8
Const FileAttrDirectory = 16
Const FileAttrArchive = 32
Const FileAttrAlias = 64
Const FileAttrCompressed = 128
```
   
<br />
### 파일을 여는 데 필요한 상수   
   
```javascript
Const OpenFileForReading = 1
Const OpenFileForWriting = 2
Const OpenFileForAppending = 8
```
   
<br />
### ShowDriveType   
   
- 목적 : 주어진 Drive 개체의 드라이브 형식을 설명하는 문자열을 만듭니다.   
- 다음을 보여줍니다.   
  - Drive.DriveType   
   
```javascript
Function ShowDriveType(Drive)

    Dim S

    Select Case Drive.DriveType
    Case DriveTypeRemovable
        S = "이동식"
    Case DriveTypeFixed
        S = "고정식"
    Case DriveTypeNetwork
        S = "네트워크"
    Case DriveTypeCDROM
        S = "CD-ROM"
    Case DriveTypeDisk
        S = "RAM 디스크"
    Case Else
        S = "알 수 없음"
    End Select

    ShowDriveType = S

End Function
```
   
<br />
### ShowFileAttr   
   
- 목적 : 파일이나 폴더의 특성을 설명하는 문자열을 만듭니다.   
- 다음을 보여줍니다.   
  - File.Attributes   
  - Folder.Attributes   
   
```javascript
Function ShowFileAttr(File) 'File은 파일 또는 폴더입니다.

    Dim S
    Dim Attr

    Attr = File.Attributes

    If Attr = 0 Then
        ShowFileAttr = "일반"
        Exit Function
    End If

    If Attr And FileAttrDirectory Then S = S & "디렉토리"
    If Attr And FileAttrReadOnly Then S = S & "읽기 전용"
    If Attr And FileAttrHidden Then S = S & "숨김"
    If Attr And FileAttrSystem Then S = S & "시스템"
    If Attr And FileAttrVolume Then S = S & "볼륨"
    If Attr And FileAttrArchive Then S = S & "보관"
    If Attr And FileAttrAlias Then S = S & "별칭"
    If Attr And FileAttrCompressed Then S = S & "압축"

    ShowFileAttr = S

End Function
```
   
<br />
### GenerateDriveInformation   
   
- 목적 : 사용할 수 있는 드라이브의 현재 상태를 설명하는 문자열을 만듭니다.   
- 다음을 보여줍니다.   
  - FileSystemObject.Drives   
  - Drives 컬렉션 반복   
  - Drive.Count   
  - Drive.AvailableSpace   
  - Drive.DriveLetter   
  - Drive.DriveType   
  - Drive.FileSystem   
  - Drive.FreeSpace   
  - Drive.IsReady   
  - Drive.Path   
  - Drive.SerialNumber   
  - Drive.ShareName   
  - Drive.TotalSize   
  - Drive.VolumeName   
   
```javascript
Function GenerateDriveInformation(FSO)

    Dim Drives
    Dim Drive
    Dim S

    Set Drives = FSO.Drives

    S = "드라이브 수 : " & TabStop & Drives.Count & NewLine & NewLine

    ' 보고서의 첫째 줄을 구성합니다.
    S = S & String(2, TabStop) & "드라이브"
    S = S & String(2, TabStop) & "파일"
    S = S & TabStop & "전체"
    S = S & TabStop & "전체"
    S = S & TabStop & "전체"
    S = S & TabStop & "전체"

    ' 보고서의 둘째 줄을 구성합니다.
    S = S & "문자"
    S = S & TabStop & "경로"
    S = S & TabStop & "형식"
    S = S & TabStop & "준비?"
    S = S & TabStop & "이름"
    S = S & TabStop & "시스템"
    S = S & TabStop & "공간"
    S = S & TabStop & "공간"
    S = S & TabStop & "공간"
    S = S & String(2, TabStop) & "번호" & NewLine

    ' 구분용 줄입니다.
    S = S & String(125, "-") & NewLine

    For Each Drive In Drives

        S = S & Drive.DriveLetter
        S = S & TabStop & Drive.Path
        S = S & TabStop & ShowDriveType(Drive)
        S = S & TabStop & Drive.IsReady

        If Drive.IsReady Then
        If DriveTypeNetwork = Drive.DriveType Then
                S = S & TabStop & Drive.ShareName
            Else
                S = S & TabStop & Drive.VolumeName
            End If

            S = S & TabStop & Drive.FileSystem
            S = S & TabStop & Drive.TotalSize
            S = S & TabStop & Drive.FreeSpace
            S = S & TabStop & Drive.AvailableSpace
            S = S & TabStop & Hex(Drive.SerialNumber)

        End If

        S = S & NewLine

    Next

    GenerateDriveInformation = S

End Function
```
   
<br />
### GenerateFileInformation   
   
- 목적 : 파일의 현재 상태를 설명하는 문자열을 만듭니다.   
- 다음을 보여줍니다.   
  - File.Path   
  - File.Name   
  - File.Type   
  - File.DateCreated   
  - File.DateLastAccessed   
  - File.DateLastModified   
  - File.Size   
   
```javascript
Function GenerateFileInformation(File)

    Dim S

    S = NewLine & "경로 : " & TabStop & File.Path
    S = S & NewLine & "이름 : " & TabStop & File.Name
    S = S & NewLine & "형식 : " & TabStop & File.Type
    S = S & NewLine & "특성 : " & TabStop & ShowFileAttr(File)
    S = S & NewLine & "작성 : " & TabStop & File.DateCreated
    S = S & NewLine & "액세스 : " & TabStop & File.DateLastAccessed
    S = S & NewLine & "수정 : " & TabStop & File.DateLastModified
    S = S & NewLine & "크기 : " & TabStop & File.Size & NewLine

    GenerateFileInformation = S

End Function
```
   
<br />
### GenerateFolderInformation   
   
- 목적 : 폴더의 현재 상태를 설명하는 문자열을 만듭니다.   
- 다음을 보여줍니다.   
  - Folder.Path   
  - Folder.Name   
  - Folder.DateCreated   
  - Folder.DateLastAccessed   
  - Folder.DateLastModified   
  - Folder.Size   
   
```javascript
Function GenerateFolderInformation(Folder)

    Dim S

    S = "경로 : " & TabStop & Folder.Path
    S = S & NewLine & "이름 : " & TabStop & Folder.Name
    S = S & NewLine & "특성 : " & TabStop & ShowFileAttr(Folder)
    S = S & NewLine & "작성 : " & TabStop & Folder.DateCreated
    S = S & NewLine & "액세스 : " & TabStop & Folder.DateLastAccessed
    S = S & NewLine & " 수정 : " & TabStop & Folder.DateLastModified
    S = S & NewLine & "크기 : " & TabStop & Folder.Size & NewLine

    GenerateFolderInformation = S

End Function
```
   
<br />
### GenerateAllFolderInformation   
   
- 목적 : 폴더와 모든 파일, 하위 폴더의 현재 상태를 설명하는 문자열을 만듭니다.   
- 다음을 보여줍니다.   
  - Folder.Path   
  - Folder.SubFolders   
  - Folders.Count   
   
```javascript
Function GenerateAllFolderInformation(Folder)

    Dim S
    Dim SubFolders
    Dim SubFolder
    Dim Files
    Dim File

    S = "폴더 : " & TabStop & Folder.Path & NewLine & NewLine

    Set Files = Folder.Files

    If 1 = Files.Count Then
        S = S & "파일이 하나 있습니다." & NewLine
    Else
        S = S & "파일이 " & Files.Count & "개 있습니다." & NewLine
    End If

    If Files.Count <> 0 Then

        For Each File In Files
            S = S & GenerateFileInformation(File)
        Next
    End If

    Set SubFolders = Folder.SubFolders

    If 1 = SubFolders.Count Then
        S = S & NewLine & "하위 폴더가 하나 있습니다." & NewLine & NewLine
    Else
        S = S & NewLine & "하위 폴더가 " & SubFolders.Count & "개 있습니다." & NewLine & NewLine
    End If

    If SubFolders.Count <> 0 Then

        For Each SubFolder In SubFolders
            S = S & GenerateFolderInformation(SubFolder)
        Next

        S = S & NewLine

        For Each SubFolder In SubFolders
            S = S & GenerateAllFolderInformation(SubFolder)
        Next

    End If

    GenerateAllFolderInformation = S

End Function
```
   
<br />
### GenerateTestInformation   
   
- 목적 : C:\Test 폴더와 모든 파일, 하위 폴더의 현재 상태를 설명하는 문자열을 만듭니다.   
- 다음을 보여줍니다.   
  - FileSystemObject.DriveExists   
  - FileSystemObject.FolderExists   
  - FileSystemObject.GetFolder   
   
```javascript
Function GenerateTestInformation(FSO)

    Dim TestFolder
    Dim S

    If Not FSO.DriveExists(TestDrive) Then Exit Function
    If Not FSO.FolderExists(TestFilePath) Then Exit Function

    Set TestFolder = FSO.GetFolder(TestFilePath)

    GenerateTestInformation = GenerateAllFolderInformation(TestFolder)

End Function
```
   
<br />
### DeleteTestDirectory   
   
- 목적 : test 디렉터리를 삭제합니다.   
- 다음을 보여줍니다.   
  - FileSystemObject.GetFolder   
  - FileSystemObject.DeleteFile   
  - FileSystemObject.DeleteFolder   
  - Folder.Delete   
  - File.Delete   
   
```javascript
Sub DeleteTestDirectory(FSO)

    Dim TestFolder
    Dim SubFolder
    Dim File

    ' 파일을 삭제하는 두 가지 방법 :
    FSO.DeleteFile(TestFilePath & "\Beatles\OctopusGarden.txt")

    Set File = FSO.GetFile(TestFilePath & "\Beatles\BathroomWindow.txt")
    File.Delete

    ' 폴더를 삭제하는 두 가지 방법 :
    FSO.DeleteFolder(TestFilePath & "\Beatles")

    FSO.DeleteFile(TestFilePath & "\ReadMe.txt")

    Set TestFolder = FSO.GetFolder(TestFilePath)
    TestFolder.Delete

End Sub
```
   
<br />
### CreateLyrics   
   
- 목적 : 한 폴더에 텍스트 파일 두 개를 작성합니다.   
- 다음을 보여줍니다.   
  - FileSystemObject.CreateTextFile   
  - TextStream.WriteLine   
  - TextStream.Write   
  - TextStream.WriteBlankLines   
  - TextStream.Close   
   
```javascript
Sub CreateLyrics(Folder)
    Dim TextStream

    Set TextStream = Folder.CreateTextFile("OctopusGarden.txt")

    TextStream.Write("문어의 정권 ") ' 파일에 줄 바꿈이 추가되지 않습니다.
    TextStream.WriteLine("(노래 : 링고스타)")
    TextStream.WriteBlankLines(1)
    TextStream.WriteLine("심해의 어두운 곳에 있는 문어의 정원에 있고 싶습니다.")
    TextStream.WriteLine("그는 우리를 들여보내 줄 것이며, 우리가 어디에 있었는가를 압니다. -- 그 곳은 어두운 곳에 있는 문어의 정원입니다.)
    TextStream.WriteBlankLines(2)

    TextStream.Close

    Set TextStream = Folder.CreateTextFile("BathroomWindow.txt")
    TextStream.WriteLine("그녀는 욕실 창문으로 들어 왔습니다(레논/메카트리).")
    TextStream.WriteLine("")
    TextStream.WriteLine("그녀는 은 숟가락으로 보호 장치를 한 욕실 창문을 통하여 들어 왔습니다.")
    TextStream.WriteLine("그러나 그녀는 지금 엄지손가락을 빨며 그녀만의 호수 언덕에서 거닐고 있습니다.")
    TextStream.WriteBlankLines(2)
    TextStream.Close

End Sub
```
   
<br />
### GetLyrics   
   
- 목적 : lyrics 파일의 내용을 표시합니다.   
- 다음을 보여줍니다.   
  - FileSystemObject.OpenTextFile   
  - FileSystemObject.GetFile   
  - TextStream.ReadAll   
  - TextStream.Close   
  - File.OpenAsTextStream   
  - TextStream.AtEndOfStream   
  - TextStream.ReadLine   
   
```javascript
Function GetLyrics(FSO)

    Dim TextStream
    Dim S
    Dim File

    ' 텍스트 파일을 여는 방법은 여러 가지이고, 파일에서 데이터를 읽는 방법도 여러가지입니다. 다음에는 각각에 대한 두 가지 방법이 나와 있습니다.

    Set TextStream = FSO.OpenTextFile(TestFilePath & "\Beatles\OctopusGarden.txt", OpenFileForReading)

    S = TextStream.ReadAll & NewLine & NewLine
    TextStream.Close

    Set File = FSO.GetFile(TestFilePath & "\Beatles\BathroomWindow.txt")
    Set TextStream = File.OpenAsTextStream(OpenFileForReading)
    Do    While Not TextStream.AtEndOfStream
          S = S & TextStream.ReadLine & NewLine
    Loop
    TextStream.Close

    GetLyrics = S

End Function
```
   
<br />
### BuildTestDirectory   
   
- 목적 : FileSystemObject를 보여주는 디렉터리 계층을 구성합니다.   
- 아래와 같은 순서로 계층을 구성합니다.   
  - C:\Text   
  - C:\Text\ReadMe.txt   
  - C:\Text\Beatles   
  - C:\Text\Beatles\OctopusGarden.txt   
  - C:\Text\Beatles\BathroomWindow.txt   
- 다음을 보여줍니다.   
  - FileSystemObject.DriveExists   
  - FileSystemObject.FolderExists   
  - FileSystemObject.CreateFolder   
  - FileSystemObject.CreateTextFile   
  - Folders.Add   
  - Folder.CreateTextFile   
  - TextStream.WriteLine   
  - TextStream.Close   
   
```javascript
Function BuildTestDirectory(FSO)

    Dim TestFolder
    Dim SubFolders
    Dim SubFolder
    Dim TextStream

    ' (a) 드라이브가 존재하지 않거나 (b) 구성할 디렉터리가 이미 존재하면 빠져 나옵니다.

    If Not FSO.DriveExists(TestDrive) Then
        BuildTestDirectory = false
        Exit Function
    End If

    If FSO.FolderExists(TestFilePath) Then
        BuildTestDirectory = false
        Exit Function
    End If

    Set TestFolder = FSO.CreateFolder(TestFilePath)

    Set TextStream = FSO.CreateTextFile(TestFilePath & "\ReadMe.txt")
    TextStream.WriteLine("나의 서정 가요 모음")
    TextStream.Close

    Set SubFolders = TestFolder.SubFolders

    Set SubFolder = SubFolders.Add("Beatles")

    CreateLyrics SubFolder

    BuildTestDirectory = true

End Function
```
   
<br />
### 기본 루틴   
   
- 먼저 test 디렉터리, 하위폴더, 파일을 만듭니다. 그런 다음 사용할 수 있는 디스크 드라이브와 test 디렉터리에 관한 정보를 넣고 다시 모든 것을 지웁니다.   
   
```javascript
Sub Main

    Dim FSO

    ' 전역 데이터를 설정합니다.
    TabStop = Chr(9)
    NewLine = Chr(10)

    Set FSO = CreateObject("Scripting.FileSystemObject")

    If Not BuildTestDirectory(FSO) Then
        Print "Text 디렉터리가 이미 존재하거나 만들 수 없습니다. 작업을 계속할 수 없습니다."
        Exit Sub
    End If

    Print GenerateDriveInformation(FSO) & NewLine & NewLine

    Print GenerateTestInformation(FSO) & NewLine & NewLine

    Print GetLyrics(FSO) & NewLine & NewLine

    DeleteTestDirectory(FSO)

End Sub
```
   
<br />
<cite>출처 : xFrame@DevStudio JAVAScript 도움말</cite>
