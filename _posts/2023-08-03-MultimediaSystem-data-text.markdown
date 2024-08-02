---
layout: post
title:  "Multimedia System: Data - Text"
date:   2023-08-03 09:00:00 +0900
categories: [Multimedia System]
---

### Multimedia data   
   
- Text, sound, images, graphics, video, animation   
   
- Differences between each multimedia data   
  - How to obtain   
    - Acquired via computer : text, graphics, animation   
    - Acquire from the real world : sound, images, video   
  - Spatio-temporal aspects   
    - Continuous characteristics : sound, video, animation   
    - Non-continuous characteristics : text, images, graphics   
   
### Overview of the text   
   
- Information printed on paper as document data or displayed on a screen such as a monitor   
- Data aimed at conveying meaning to the other party   
- Also used as a character designating the Internet communication path   
- It does not provide audio-visual interest like other multimedia data, but is used to convey important and elaborate information   
   
#### Characteristics of text   
   
- Requires less storage capacity compared to other multimedia data   
- Different characteristics depending on the language used   
  - Depending on the language, specific tools are required to support that language   
  - This is because the character set that represents text is different depending on the language used   
   
<br />
### Expression of text   
   
- Text is composed of a set of characters inside the computer   
   
- Character encoding   
  - All characters are expressed as binary codes inside the computer, and each character is assigned one number   
  - Therefore, if the language is different, the code used is also different   
   
#### Character set and encoding   
   
- Character set   
  - Defining and ordering the characters to be expressed   
   
- CCS : Coded Character Set   
  - Character set expressed in code form   
    - ASCII   
    - EBCDIC   
    - Western European character set   
    - Hangul code   
    - Unicode   
   
#### ASCII (American Standard Code for Information Interchange)   
   
- Standard established in the United States as the English character set   
- The most common format for text files on a computer or on the Internet   
- Alphabets, numbers, and special characters are expressed as 7-bit binary numbers   
- A total of 128 characters are defined   
   
#### EBCDIC (Extended Binary Coded Decimal for Interchange Code)   
   
- Code system developed by IBM   
- Mainly used in IBM's large computers   
- Use 8-bit binary numbers   
- Can express twice as many symbols and control functions compared to ASCII   
   
#### Western European character set   
   
- It is not enough to express European languages ​​in 7-bit ASCII   
- A new character set incorporating Western European characters into ASCII   
- Also called "Western European Character Set" or "ISO Latin-1"   
- Uses 8-bit code system as an extension of ASCII   
   
- ISO : International Organization for Standardization   
   
#### Hangul code   
   
- English or European languages ​​can be expressed with 256 8-bit codes   
- Hangul cannot express all Hangul combinations in 8 bits   
- Therefore, combined and completed Hangul codes were created   
  - Combined type : Based on the principle of Hangul, codes are assigned to each elementary, middle, and final consonant   
  - Completed type : Assign codes to complete characters such as '가' and '각'   
- The completed Hangul code is the Hangul standard   
  - The completed type has the disadvantage of not being able to express all Hangul characters, but it was adopted as a standard because it causes fewer problems in computer communications   
   
#### Unicode   
   
- Introduced due to limitations in character expression of ASCII   
- An industry standard that allows all languages ​​around the world to be expressed consistently on computers   
- Unicode's representative character encoding method   
  - UTF-8 (UCS Transformation Format-8bit)   
    - To reduce the file size, ASCII is encoded into 1 byte, and other characters are encoded into 2 bytes or more - Compatible with ASCII   
  - UTF-16 (UCS Transformation Format-16bit)   
    - A method of encoding all characters into 2 bytes - There is no limit to the number of characters   
   
#### Markup text   
   
- Text expressed by inserting special characters that specify the format of the document or reveal structural boundaries   
- In other words, text that contains markup information that instructs the computer to specify the document format, search, etc., or how to connect to other documents in addition to the document content   
   
- Markup   
  - Additional information defined to define or express the document structure   
  - Representative markup languages : HTML, SGML   
   
#### Structured text   
   
- Text using tags with structural information   
- Linear sequential structure   
- Structural information of text refers to titles, clauses, paragraphs, etc., and structural information has a proprietary expression method for document processing and document design   
   
- ODA (Office Document Architecture)   
  - An international standard that specifies how logical structures and design components are organized and relate to each other   
   
#### Hypertext   
   
- Text with a non-sequential development principle   
- Meaning multiple linked documents   
- Unlike general text, links to a specific location in another document   
- Therefore, a new concept of document connection form that allows arbitrary connections beyond physical and logical space   
   
- Principles of hypertext   
  - Non-linear graph-like structure   
  - Structural method of information using nodes and links as units   
    - Nodes are small chunks of text, connected by links   
   
- Hyperlink   
  - How to connect data to data   
   
<br />
### Text file format   
   
- File storage method for text data   
  - English : ASCII   
  - Hangul : Completed Hangul code   
  - Various document editing applications : Different storage methods   
   
- Text file format   
  - TXT   
  - DOC   
  - HWP   
  - RTF   
  - HTML   
  - XML   
  - XHTML   
  - PDF   
  - TeX/LaTeX   
   
#### TXT (Text)   
   
- File format created in an editor following the ASCII system   
- The format of the document editor provided by default in the operating system   
- Readable in any text editor or word processor   
- Graphs or formulas are not provided   
   
#### DOC (Document)   
   
// 마이크로 소프트사의 MS워드 문서 형식   
// TXT 형식에 비해 그래픽 효과, 그리기 및 특수기호, 수식과 같은 다양한 문자열 서식과 문자열 맞춤, 탭, 줄 간격 등을 지원하는 장점   
// 같은 텍스트를 저장하더라도 파일 용량이 커지는 단점   
- Microsoft's MS Word Document Format   
- Compared to TXT format, it is strength to support various character string formats such as graphic effects, drawing and special symbols, and formulas, as well as character string customization, tap, and line spacing   
- Saving the same text has the weakness of increasing file capacity   
   
#### HWP (Hangul Word Processor)   
   
// 한글 워드 프로세서에서 사용하는 문서 형식   
// 다른 워드 프로세서는 완성형 코드로 저장하는데 반해, 이 파일 형식은 조합형 코드 체계로 저장   
// 상위 버전에서 만든 파일을 하위 버전에서 못 읽을 수 있음   
// 파일을 저장할 때 암호를 지정하거나 압축하여 용량을 줄일 수 있음   
- Document formats used by Korean word processors   
- While other word processors are stored as complete code, this file format is stored as a combination code system   
- Files created in the parent version may not be read in the child version   
- HWP files can be saved by specifying a password, or can be compressed to reduce capacity   
   
#### RTF (Rich Text Format)   
   
// 마이크로소프트사가 중심이 되어 표준화한 문서 형식   
// 서로 다른 운영체제와 워드 프로세서 사이에서도 텍스트 파일을 교환할 수 있도록 하기 위해 만든 형식   
// IBM PC와 호환 기종의 PC, 매킨토시와 같은 다른 기종과 다른 운영체제에서도 문서 교환   
- Standardized documentation format centered on Microsoft   
- Formats created to enable text files to be exchanged between different operating systems and word processors   
- Interchange documents on IBM PCs and compatible PCs and other operating systems such as Macintosh   
   
#### HTML (Hyper Text Markup Language)   
   
// 일반 TXT의 문서 형식   
// 일반 문서 편집기에서 편집이 가능   
// 인터넷 웹 문서의 표준 형식   
// RTF 형식보다 호환성이 높은 문서 형식   
- Document formats for regular TXT   
- Editable in the general document editor   
- Standard format for Internet Web documents   
- More compatible document formats than RTF formats   
   
#### XML (eXtensible Markup Language)   
   
// HTML을 대체할 목적으로 탄생   
// W3C에서 제안하고 표준화한 페이지 기술언어   
// 웹 상에서 구조화된 문서를 전송 가능하도록 설계된 텍스트 형식   
// 파일은 TXT 형식이며, 일반 에디터를 이용하여 편집 가능   
// HTML과 SGML의 장점을 모두 가지도록 규정   
- Born to replace HTML   
- page description language proposed and standardized by W3C   
- Text format designed to transfer structured documents over the web   
- The file is TXT format and can be edited using a regular editor   
- Have the strengths of both HTML and SGML   
   
- W3C (World Wide Web Consortium)   
// - 웹 표준을 제공하는 등 웹의 장기적인 발전을 위해 1994년에 창립된 인터넷 관련 국제 컨소시엄   
  - Internet-related international consortium founded in 1994 for the long-term development of the Web, including providing web standards   
   
#### XHTML (eXtensible Hyper Text Markup Language)   
   
// HTML 버전-4에 XML에 적용하여 재구성   
// 웹에서 데이터를 공유할 수 있도록 정의하였고, 다양한 목적에 사용되는 확장성과 이동성이 강한 언어   
// 수학적 표현, 벡터 도형 처리, 멀티미디어 등의 새로운 표현이 가능   
- Reorganize HTML version-4 by applying it to XML   
- A highly scalable and mobile language that is defined to share data on the Web and is used for a variety of purposes   
- New expressions such as mathematical expressions, vector graphic processing, multimedia, etc. are possible   
   
#### PDF (Potable Document Format)   
   
// Adobe Systems 에서 개발한 전자문서 형식   
// 컴퓨터 환경에 관계없이 같은 표현을 하기 위한 목적으로 개발   
// 온-오프라인 환경에서도 여러 전송 수단을 통하여 문서정보의 공유 및 전송 등이 가능   
- Electronic document formats developed by Adobe Systems   
- Developed for the purpose of expressing the same regardless of computer environment   
- It is possible to share and transmit document information through various transmission methods even in online and offline environments   
   
// 다른 문서 형식과 비교되는 장점   
// - 대부분의 문서가 표현 가능   
// - 암호화 및 압축기술로 인해 변조의 어려움   
// - 다양한 프로그램에서 지원 가능   
- Strengths over other document formats   
  - Most documents can be represented   
  - Encryption and compression technology make modulation difficult   
  - Available in a wide range of programs   
   
// 인쇄상태의 모양을 그대로 컴퓨터에서 보여주므로 전자책이나 CD출판 등의 디지털 출판에 적합   
- Since the computer shows the shape of the print state as it is, it is suitable for digital publication such as e-book or CD publication   
   
#### TeX/LaTeX   
   
- TeX   
// - 상세 지정이 가능한 문서 정형 또는 조판 시스템   
// - 태그의 문법에 따라 텍스트 편집기 상에서 소스를 기술하고, 컴파일함으로써 문서를 정형하거나 조판할 수 있음   
// - 공개 소프트웨어   
// - 유닉스, 도스, 윈도, 매킨토시 등 모든 컴퓨터시스템에서 동작   
  - Document formatting or typewriting systems with detailed designation   
  - TeX can format or type documents by creating and compiling sources on the text editor according to the grammar of the tag   
  - Public software   
  - Works on all computer systems, including Unix, DOS, Windows, Macintosh, etc.   
   
- LaTeX   
// - TeX가 갖고 있는 불편한 사용자 인터페이스를 개선한 시스템   
  - A system that improves TeX's uncomfortable user interface   
   
// TeX/LaTeX는 간단한 명령어 (태그) 를 문법에 맞게 작성한 다음 이 파일을 컴파일하게 되면 글씨체나 수학적인 공식을 아주 예쁘게 작성할 수 있다는 장점이 있음   
- TeX/LaTeX has the strength of being able to write simple commands (tags) according to grammar and then compile these files to make very pretty handwriting or mathematical formulas   
   
<br />
### Electronic Book and publishing   
// 전자도서 및 출판   
   
#### Electronic Book   
// 전자도서   
   
// 전자책 또는 e-Book (Electronic Book)   
// 온라인 전자출판의 일종   
// 책 내용을 디지털 파일로 만들어 전용 뷰어 (viewer) 를 통해 컴퓨터나 전용 단말기로 읽음   
// 일반적으로 전자책을 구성하는 콘텐츠와 소프트웨어, 하드웨어를 구분 없이 e-Book이라 부르기도 함   
- Electronic Book or e-Book   
- A form of online electronic publishing   
- Make the contents of a book into a digital file and read it on a computer or a dedicated terminal through a dedicated viewer   
- In general, the contents, software, and hardware that make up e-books are sometimes called e-Book without distinction   
   
#### Electronic Publishing, ePublishing   
// 전자출판   
   
// 컴퓨터를 이용하여 디지털화된 방식으로 출판물을 제작하는 방법과 기술   
// DTP (Desk Top Publishing) 라는 새로운 편집 시스템의 개발과 (1985, 미국), 전자출판물인 CD-ROM의 등장으로 발전   
// 온라인 출판 혹은 웹 출판이라고도 함   
- Methods and techniques for using computers to produce publications in a digitized manner   
- Developed with the development of a new editing system called DTP (Desk Top Publishing) (1985, USA) and the advent of the electronic publication CD-ROM   
- Also known as online publication or web publication   
   
- DTP   
// - 탁상출판   
// - 컴퓨터로 단행본이나 사전 등의 출판물을 디자인하는 작업   
  - Desk Top Publishing   
  - The work of designing publications such as books and dictionaries on a computer   
   
#### Online electronic publishing   
// 온라인 전자출판   
   
// 인터넷의 발전으로 전자출판이 정착되어 웹을 통한 서비스 제공   
- With the development of the Internet, electronic publishing has been established and services are provided through the web   
   
// 온라인 전자출판의 특징   
// - 네트워크를 통해 정보를 제공하기 때문에 문자나 그림은 물론 움직이는 영상이나 사람의 목소리까지 다양한 정보를 제공   
// - 기존의 종이로 만든 출판물에 비해 신속성, 검색의 용이성, 보관의 편리성, 원가 절감, 상호작용성 등의 장점   
- Characteristics of Online Electronic Publishing   
  - Since it provides information through the network, it provides various information from text and pictures as well as moving images and human voices   
  - It has strengths over traditional paper-based publications such as speed, ease of search, ease of storage, cost reduction, and interactivity   
   
// 온라인 전자출판의 예시   
// - 웹진 (webzine)   
// -- 인터넷 상에서 발간되는 잡지   
// - POD (Publishing On Demand)   
// -- 고객이 원하는 대로 주문을 받아 책을 제작해 주는 서비스   
- Example of Online Electronic Publishing   
  - Webzine   
    - A magazine published on the Internet   
  - POD (Publishing On Demand)   
    - A service that takes orders and creates books as customers want   
   
#### The format of Online Electronic Publishing   
// 온라인 전자출판의 형식   
   
// HTML, PDF, XML 등이 사용   
// - HTML이 멀티미디어 데이터 처리의 한계를 보임에 따라 대안으로 XML이나 HTML5 등이 사용   
// - PDF 방식 역시 다양한 편집 레이아웃의 장점을 갖고 있고, 다양한 멀티미디어를 구현할 수 있어서 많이 사용   
- HTML, PDF, XML, etc. are used   
  - XML or HTML5 is used as an alternative as HTML shows limitations in multimedia data processing   
  - The PDF method also has the strengths of various editing layouts and is widely used because it can implement various multimedia   
   
#### Terms related to electronic publication   
// 전자출판에 관련된 용어   
   
- EPUB (Electronic Publication)   
// - 국제 디지털 출판 포럼 (IDPF : International Digital Publishing Forum) 에서 제정한 개방형 자유 전자서적 표준   
// -- 자동공간 조정과 글자크기 변환, 내부에 래스터나 벡터 이미지를 담을 수 있는 기능과 DRM 및 CSS 기능을 제공하고, 메타 데이터를 포함하고 있음   
  - Open free e-book standards established by IDPF (International Digital Publishing Forum)   
    - It provides automatic space adjustment and character size conversion, the ability to contain raster or vector images inside, DRM and CSS functions, and contains metadata   
   
- DRM (Digital Rights MAnagement)   
// - 출판자 또는 저작권자가 그들이 배포한 디지털 자료나 하드웨어 사용을 제어하고 이를 의도한 용도로만 사용하도록 제한하는 데 사용되는 모든 기술들을 지칭   
  - Refers to any technology used by publishers or copyright holders to control the use of digital materials or hardware that they have distributed and to restrict it to use for intended purposes only   
   
- CSS (Cascading Style Sheet)   
// - 마크업 언어가 실제 표시되는 방법을 기술하는 언어로, HTML이나 XHTML에 주로 쓰이며, XML에서도 사용됨   
  - A language that describes how markup languages are actually displayed, commonly used in HTML and XHTML, and also used in XML   
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
