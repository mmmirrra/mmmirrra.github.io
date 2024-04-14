---
layout: post
title:  "Excel: Use Excel to send bulk emails"
date:   2024-01-12 09:00:00 +0900
categories: [Excel]
---

### Practice sending bulk emails through Outlook   
#### 1. Creating a Code   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails1-1.png)
   
#### 2. Creating email List   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails1-2.png)
   
#### 3. Create email content   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails1-3.png)
   
#### 4. Open Macro   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails1-4.png)
   
#### 5. Select a macro   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails1-5.png)
   
<br />
#### Full Code   
```visualbasic
Sub SendMail()

    'Outlook 메일 발송 변수 설정
    Dim M_Add As String
    Dim eEmail As String
    Dim M_name As String
    Dim W_Row, i, pos As Integer
    Dim MyOutlook As Object
    Dim N_Email As Object
    Dim Subject As String
    Dim Body As String
    Dim Response As String
    
    'Outlook 메일 발송 확인 메시지 박스
    Response = MsgBox("Are you sure you want to send email?", vbYesNo)
    
    '### Outlook 메일 발송 시작 - 메일 발송 Yes 인 경우에만 실행
    If Response = vbYes Then
        
        W_Row = Sheet1.Range("A60000").End(xlUp).Row                '끝 행 찾기
        Subject = Sheet2.Cells(1, 1).Value                          '메일 제목 Sheet2의 A1 셀 내용
        Body = Sheet2.Cells(2, 1).Value                             '메일 본문 Sheet2의 A2 셀 내용
        
        If W_Row < 2 Then
            MsgBox ("Enter email address")                          '입력된 메일주소 없을 경우 메시지 박스 오픈
        
        ElseIf Subject = "" Then
            MsgBox ("Enter email title")                            '입력된 메일 제목이 없을 경우 메시지 박스 오픈
        
        ElseIf Body = "" Then
            MsgBox ("Enter the body of email")                       '입력된 메일 본문이 없을 경우 메시지 박스 오픈
        
        Else
            For i = 2 To W_Row                                      'Sheet1의 2번째 행부터 끝 행인 W_Row 까지 실행
                M_Add = ""                                          '메일 주소 초기화
                M_name = ""                                         '이름 초기화
    
                '엑셀 셀 표기 방법 -> (1,1)=(1,A)=A1
                M_Add = Sheet1.Cells(i, 1)                          '메일주소가져오기 (2,1)=A2=(2,A)
                M_name = Sheet1.Cells(i, 2)                         '이름가져오기 (2,2)=B2=(2, B)
    
                '메일주소만 추출하기
                pos = InStr(M_Add, "@")                             'abc@naver.com 메일주소에서 @가 있는 자리수 찾기
                eEmail = Left(M_Add, pos - 1)                       '@ 있는 자리수에서 -1만큼 뺀 자리수까지만 데이터 가져오기
                
                '아웃룩 오픈
                If M_Add <> "" Then
                    Set MyOutlook = CreateObject("Outlook.Application")
                    Set N_Email = MyOutlook.CreateItem(olMailItem)
    
                    With N_Email
                        .To = M_Add                                 '수신인 메일주소
                        .Subject = Subject                          '메일 제목
                        .Body = Body                                '메일 본문
                        .send
                    End With
                End If
            Next i
            
            MsgBox ((W_Row - 1) & " email has been sent")
        
        End If

    End If
    '### Outlook 메일 발송 종료
    
End Sub
```
   
<br />
### Samples with attachments   
```visualbasic
'첨부파일 유무 체크하는 함수
Function FileChk(sFileName As String)
    '변수 설정
    Dim sChkFile As String

    sChkFile = Dir(sFileName)
    If (Len(sChkFile) > 0) Then
        FileChk = True
    Else
        FileChk = False
    End If
End Function


'Outlook 메일 발송하는 함수
Sub SendMail()

    'Outlook 메일 발송 변수 설정
    Dim F_dir As FileDialog
    Dim F_Name As String
    Dim M_Add As String
    Dim File_N As String
    Dim eEmail As String
    Dim M_name As String
    Dim W_Row, i, pos As Integer
    Dim MyOutlook As Object
    Dim N_Email As Object
    Dim Response As String
    Dim Response2 As String
    
    'Outlook 메일 발송 확인 메시지 박스
    Response = MsgBox("Are you sure you want to send an email?", vbYesNo)
    
    '### Outlook 메일 발송 시작 - 메일 발송 Yes 인 경우에만 실행
    If Response = vbYes Then
            
        Response2 = MsgBox("Do you have any attachments?", vbYesNo)     '첨부파일 유무 체크
        
            If Response2 = vbYes Then              '첨부 파일이 있을 경우에만 실행
                Set F_dir = Application.FileDialog(msoFileDialogFolderPicker)   '첨부파일이 있는 위치를 지정하기 위한 다이얼로그
                F_dir.AllowMultiSelect = False
                F_dir.Title = "Select the location where the attachment is located."
                F_dir.Show
                F_Name = F_dir.SelectedItems(1)    '파일 경로 가져오기
            End If

            W_Row = Sheet1.Range("A60000").End(xlUp).Row            '끝 행 찾기

            For i = 2 To W_Row                    'Sheet1의 2번째 행부터 끝 행인 W_Row 까지 실행
                M_Add = ""                        '메일 주소 초기화
                M_name = ""                       '이름 초기화

                '엑셀 셀 표기 방법 -> (1,1)=(1,A)=A1
                M_Add = Sheet1.Cells(i, 1)        '메일주소가져오기 (2,1)=A2=(2,A)
                M_name = Sheet1.Cells(i, 2)       '이름가져오기 (2,2)=B2=(2, B)

                '메일주소만 추출하기
                pos = InStr(M_Add, "@")           'abc@naver.com 메일주소에서 @가 있는 자리수 찾기
                eEmail = Left(M_Add, pos - 1)     '@ 있는 자리수에서 -1만큼 뺀 자리수까지만 데이터 가져오기

                If F_Name <> "" Then             '첨부파일이 있을 경우 실행
                    File_N = F_Name & "\" & eEmail & "_" & M_name & "_" & "첨부파일.pdf"    '첨부파일 경로 및 이름
                End If
                                
               '아웃룩 오픈
               If M_Add <> "" Then
                    Set MyOutlook = CreateObject("Outlook.Application")
                    Set N_Email = MyOutlook.CreateItem(olMailItem)

                    With N_Email
                        .To = M_Add                               '수신인 메일주소
                        .CC = ""                                  '참조 메일주소
                        .Subject = "제목"                         '메일 제목
                        .Body = Sheet2.Cells(1, 1).Value          'Sheet2의 A1 셀의 내용 가져오기
                        If Response2 = vbYes Then
                            If (FileChk(File_N)) Then            '첨부파일이 있을 경우 첨부 (첨부파일이 없을 경우 첨부하지 않습니다.)
                                .Attachments.Add File_N           '첨부파일 첨부
                            End If
                        End If
                        .Send
                    End With
                End If
            Next i
        
        MsgBox "끝"

    End If
    '### Outlook 메일 발송 종료

 End Sub
```
   
<br />
### Practice sending bulk emails through CDO   
#### 1. Creating a Code   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails2-1.png)
   
#### 2. Creating email List   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails2-2.png)
   
#### 3. Create email content   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails2-3.png)
   
#### 4. Open Macro   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails2-4.png)
   
#### 5. Select a macro   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelBulkEmails2-5.png)
   
<br />
#### Full Code   
```visualbasic
Sub CDOMail()

    'COD 메일링 변수 설정
    Dim iMsg As CDO.Message
    Dim iConf As CDO.Configuration
    Dim from As String

    'COD 메일링 환경설정
    Set iMsg = New CDO.Message
    Set iConf = New CDO.Configuration
    from = "emailaddress@aaa.com"
    
    'CDO Source Defaults
    iConf.Load cdoDefaults
    With iConf.Fields
        .Item(cdoSMTPServer) = "aaa.com"                          'SMTP 서버
        .Item(cdoSendUsingMethod) = cdoSendUsingPort                '보내는 방법을 어떤것을 사용할 건지 선택, 포트, 픽업
        .Item(cdoSMTPServerPort) = 25                               'SMTP 서버 포트
        .Item(cdoSMTPUseSSL) = True                                 'smtp서버에서 ssl 사용 유무
        .Item(cdoSendUserName) = "emailaddress"                         '계정 ID
        .Item(cdoSendPassword) = "password"                     '계정 암호
        .Item(cdoSMTPAuthenticate) = 1
        .Update
    End With

    'CDO 메일 발송 변수 설정
    Dim M_Add As String
    Dim eEmail As String
    Dim M_name As String
    Dim W_Row, i, pos As Integer
    Dim Subject As String
    Dim Body As String
    Dim Response As String
    
    'CDO 메일 발송 확인 메시지 박스
    Response = MsgBox("Are you sure you want to send email?", vbYesNo)
    
    '### CDO 메일 발송 시작 - 메일 발송 Yes 인 경우에만 실행
    If Response = vbYes Then
        
        W_Row = Sheet1.Range("A60000").End(xlUp).Row                '끝 행 찾기
        Subject = Sheet2.Cells(3, 1).Value                          '메일 제목 Sheet2의 A1 셀 내용
        Body = Sheet2.Cells(4, 1).Value                             '메일 본문 Sheet2의 A2 셀 내용
        
        If W_Row < 2 Then
            MsgBox ("Enter email address")                           '입력된 메일주소 없을 경우 메시지 박스 오픈
        
        ElseIf Subject = "" Then
            MsgBox ("Enter email title")                             '입력된 메일 제목이 없을 경우 메시지 박스 오픈
        
        ElseIf Body = "" Then
            MsgBox ("Enter the body of email")                       '입력된 메일 본문이 없을 경우 메시지 박스 오픈
        
        Else
            For i = 2 To W_Row                                      'Sheet1의 2번째 행부터 끝 행인 W_Row 까지 실행
                M_Add = ""                                          '메일 주소 초기화
                M_name = ""                                         '이름 초기화
    
                '엑셀 셀 표기 방법 -> (1,1)=(1,A)=A1
                M_Add = Sheet1.Cells(i, 1)                          '메일주소가져오기 (2,1)=A2=(2,A)
                M_name = Sheet1.Cells(i, 2)                         '이름가져오기 (2,2)=B2=(2, B)
    
                '메일주소만 추출하기
                pos = InStr(M_Add, "@")                             'abc@naver.com 메일주소에서 @가 있는 자리수 찾기
                eEmail = Left(M_Add, pos - 1)                       '@ 있는 자리수에서 -1만큼 뺀 자리수까지만 데이터 가져오기
                
                'CDO 오픈
                If M_Add <> "" Then

                    With iMsg
                        Set .Configuration = iConf                  'SMTP 서버를 설정한 개체를 할당한다.
                        .To = M_Add                                 '메일을 받을 사람의 메일 주소
                        .from = from                                '보내는 사람 메일 주소 즉 사용하는 SMTP에 있는 메일 계정
                        .Subject = Subject                          '메일 제목
                        .TextBody = Body                            '메일 내용
                        .send
                    End With
                    
                End If
            Next i
            
            MsgBox ((W_Row - 1) & " email has been sent")
        
            Set iConf = Nothing
            Set iMsg = Nothing
        
        End If

    End If
    '### CDO 메일 발송 종료
    
End Sub
```
   
<br />
### Download Sample Excel   
// 샘플 엑셀 다운로드   
   
[excelBulkEmails.xlsm](https://github.com/mmmirrra/mmmirrra.github.io/raw/main/_assets/excelBulkEmails.xlsm)   
