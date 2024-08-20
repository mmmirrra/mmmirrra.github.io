---
layout: post
title:  "Excel: Importing characters from the html source"
date:   2023-09-19 09:00:00 +0900
categories: [Excel]
---

### Import using the Connect button   
#### 1. '데이터' > '쿼리 및 연결' > '연결' 선택   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-1.png)
   
#### 2. 연결 목록에서 마우스 오른쪽 버튼으로 '속성' 선택   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-2.png)
   
#### 3. '사용 현황' 탭에 옵션 설정   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-3.png)
   
#### 4. '정의' 탭에서 '쿼리 편집' 버튼 선택   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-4.png)
   
#### 5. 불러올 html 파일의 경로를 입력하고 '이동' 버튼 선택   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-5.png)
   
#### 6. 화면 아래에 있는 '가져오기' 버튼 선택   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-6.png)
   
#### 7. 연결 목록에서 '새로고침' 버튼 선   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-7.png)
   
#### 8. 화면에 가져온 텍스트를 확인할 수 있음   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-8.png)
   
#### * 연결 속성 창의 '사용 위치' 탭에서 화면내에 사용된 셀의 범위를 확인할 수 있음   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml1-9.png)
   
<br />
### Import using macro code   
#### 1. html 주소로 가져오는 매크로 작성   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml2-1.png)
   
#### 2. 매크로를 연동할 버튼에서 마우스 오른쪽 버튼으로 '매크로 지정' 선택   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml2-2.png)
   
#### 3. 연동할 매크로 선   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml2-3.png)
   
#### 4. 화면에 가져온 텍스트를 확인할 수 있음   
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/excelImportHtml2-4.png)
   
<br />
#### Full Code   
```visualbasic
Option Explicit

Sub DelEmptyCell()
    
    Dim x As Integer, x1 As Integer, y As Integer, y1 As Integer
    
    With Range(ActiveSheet.QueryTables(1).Name)
    'Calculates the number of rows and columns of the query table area.
        x1 = .Rows.Count
        y1 = .Columns.Count
    End With
    
    With Cells(1)
    
        For x = x1 To 1 Step -1
        'If any empty cells exist while cycling through a row, delete that row.
            If IsEmpty(.Offset(x)) Then .Offset(x).EntireRow.Delete shift:=xlUp
        Next
        
        For y = y1 To 1 Step -1
        'If any empty cells exist while cycling through a column, delete that column.
            If IsEmpty(.Offset(, y)) Then .Offset(, y).EntireColumn.Delete shift:=xlToLeft
        Next
    
    End With

End Sub

Sub ImportExchange()

    Dim sURL As String
    
    sURL = "http://stock.naver.com/world/exchange.html"
    
    Application.ScreenUpdating = False
    'Stop updating the screen.
        On Error Resume Next
            Cells(1).CurrentRegion.Delete shift:=xlUp
        On Error GoTo 0
        
        With ActiveSheet.QueryTables.Add("URL;" & sURL, Range("A1"))
        'Loads the specified web address into the A1 cell.
            .WebFormatting = xlWebFormattingNone
            .WebTables = """tblJisu1"""
            .Refresh BackgroundQuery:=False
        End With
        
        DelEmptyCell    'Delete all blank cells.
    Application.ScreenUpdating = True
    
End Sub
```
   
<br />
### Download Sample Excel   
// 샘플 엑셀 다운로드   
   
[excelImportHtmlLink.xls](https://github.com/mmmirrra/mmmirrra.github.io/raw/main/_assets/excelImportHtmlLink.xls)   
[excelImportHtmlMacro.xls](https://github.com/mmmirrra/mmmirrra.github.io/raw/main/_assets/excelImportHtmlMacro.xls)   
