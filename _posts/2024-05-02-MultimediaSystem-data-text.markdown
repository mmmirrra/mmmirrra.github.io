---
layout: post
title:  "Multimedia System: Data - Text"
date:   2024-05-02 09:00:00 +0900
categories: [Multimedia System]
---

### Multimedia Data   
// 멀티미디어 데이터   
   
// 텍스트, 사운드, 이미지, 그래픽, 비디오, 애니메이션   
- text, sound, images, graphics, video, animation   
   
// 각 멀티미디어 데이터들의 차이점   
// - 획득방법   
// -- 컴퓨터를 통해 획득 : 텍스트, 그래픽, 애니메이션   
// -- 실세계에서 획득 : 사운드, 이미지, 비디오   
// - 시공간적인 측면   
// -- 연속적인 특성 : 사운드, 비디오, 애니메이션   
// -- 비연속적인 특성 : 텍스트, 이미지, 그래픽   
- The difference between each multimedia data   
  - Acquisition method   
    - Acquired via computer : text, graphics, animation   
    - Acquired in the real world : sound, image, video   
  - A space-time aspect   
    - Continuous properties : sound, video, animation   
    - Non-continuous properties : text, images, graphics   
   
### Overview of text   
// 텍스트의 개요   
   
// 문서 데이터로 종이 위에 인쇄되거나 모니터 등의 화면상에 표시되는 정보   
// 상대방에게 의미를 전달하는 것을 목적으로 하는 데이터   
// 인터넷의 통신경로를 지정하는 문자로도 사용   
// 다른 멀티미디어 데이터와 같이 시청각적 흥미를 제공하지는 않지만 중요하고 정교한 정보를 옮기는데 사용   
- Information printed on paper as document data or displayed on a screen such as a monitor   
- data aimed at communicating meaning to the other party   
- Also used as a character to specify the Internet's communication path   
- It does not provide audio-visual interest like other multimedia data, but it is used to move important and sophisticated information   
   
#### Characteristics of Text   
// 텍스트의 특성   
   
// 다른 멀티미디어 데이터에 비해 적은 기억장치 용량 필요   
// 사용 언어에 따라 서로 다른 특성   
// - 사용 언어에 따라 해당 언어를 지원하는 특정 도구 필요   
// - 사용 언어에 따라 텍스트를 표현하는 문자집합이 다르기 때문   
- Requires less memory capacity than other multimedia data   
- Characteristics of different texts depending on the language used   
  - Requires specific tools to support that language, depending on the language   
  - This is because the set of characters expressing text is different depending on the language   
   
<br />
### Representation of a Text   
// 텍스트의 표현   
   
// 텍스트는 컴퓨터 내부에서 문자집합으로 구성   
- Text consists of a set of characters inside the computer   
   
// 문자 인코딩   
// - 모든 문자는 컴퓨터 내부에서 2진수 코드로 표현되고, 각각의 문자는 1개의 숫자로 할당되는 것   
// - 따라서 언어가 다르면 서로 사용하는 코드도 다름   
- Character encoding   
  - All characters are represented by binary code inside the computer, and each character is assigned as one number   
  - Therefore, if the languages are different, the codes used by each other are also different   
   
#### Character Set and Encoding   
// 문자집합과 인코딩   
   
// 문자집합   
// - 표현해야 할 문자를 정의하고 순서를 지정하는 것   
- Character Set   
  - Defining and ordering characters to be expressed   
   
// 코드화된 문자집합 (CCS : Coded Character Set)   
// - 문자집합을 코드형태로 표기한 것   
// -- ASCII   
// -- EBCDIC   
// -- 서유럽 문자집합   
// -- 한글코드   
// -- 유니코드   
- CCS : Coded Character Set   
  - A code representation of a set of characters   
    - ASCII   
    - EBCDIC   
    - Western European Character Set   
    - Korean code   
    - Unicode   
   
#### ASCII (American Standard Code for Information Interchange)   
   
// 영어의 문자집합으로 미국에서 제정한 표준   
// 컴퓨터나 인터넷상에서 텍스트 파일을 위한 가장 일반적인 형식   
// 알파벳과 숫자, 그리고 특수문자들이 7비트 2진수로 표현   
// 총 128개의 문자가 정의   
- A set of English characters established in the United States   
- The most common format of text files on a computer or the Internet   
- alphabets, numbers, and special characters are represented in 7-bit binary numbers   
- A total of 128 characters are defined   
   
#### EBCDIC (Extended Binary Coded Decimal for Interchange Code)   
   
// IBM사에서 개발한 코드 체계   
// IBM의 대형 컴퓨터에서 주로 사용   
// 8비트 2진수 사용   
// ASCII에 비해 두 배의 기호와 제어기능을 표현할 수 있음   
- Code system developed by IBM   
- Used primarily on IBM's large computers   
- Use an 8-bit binary number   
- Can express twice as many symbols and controls as ASCII   
   
#### Western European Character Set   
// 서유럽 문자집합   
   
// 유럽어를 7비트 ASCII로 표현하기는 부족   
// 서유럽의 문자들을 ASCII에 포함시킨 새로운 문자집합   
// "서유럽 문자집합" 또는 "ISO Latin-1"이라 함   
// ASCII의 확장으로 8비트 코드체계 사용   
- Not enough to express European in 7-bit ASCII   
- A new set of characters incorporating Western European characters into ASCII   
- "Western European Character Set" or "ISO Latin-1"   
- Extensions of ASCII use of 8-bit code systems   
   
- ISO : International Organization for Standardization   
   
#### Korean code   
// 한글코드   
   
// 영어나 유럽어는 8비트 256개의 코드로 표현 가능   
// 한글은 8비트로 모든 한글 조합을 표현할 수 없음   
// 따라서 조합형과 완성형 한글코드가 만들어짐   
// - 조합형 : 한글의 제작 원리에 기반하여 초성, 중성, 종성에 각각 코드 할당   
// - 완성형 : '가', '각'과 같은 완성형 문자에 코드를 할당   
// 완성형 한글코드가 한글 표준안   
// - 완성형은 모든 한글을 표현할 수 없다는 단점이 있으나 컴퓨터 통신에서 문제점이 덜 생기는 장점으로 표준안 채택   
- English or European can be expressed in 8 bits and 256 codes   
- Hangul cannot express all Hangul combinations with 8 bits   
- Consequently, a combination type and a complete Korean code are created   
  - Combination type : Based on the principle of making Hangul, code is assigned to the initial sound, middle sound, and final sound, respectively   
  - Complete Type : Assign codes to complete characters such as '가' and '각'   
- The complete Korean code is Korean standard plan   
  - The completion type has the weakness of not being able to express all Korean characters, but the standard is adopted as an strength of less problems in computer communication   
   
#### Unicode   
// 유니코드   
   
// ASCII가 갖는 문자표현의 한계 때문에 도입   
// 전세계 모든 언어를 컴퓨터에서 일관되게 표현할 수 있는 산업표준   
// 유니코드의 대표적인 문자 인코딩 방법   
// - UTF-8 (UCS Transformation Format-8bit)   
// -- 파일 사이즈를 작게 하기 위해 ASCII는 1바이트로 인코딩 하고, 다른 문자들은 2바이트나 그 이상으로 인코딩 하는 방식 - ASCII와 호환   
// - UTF-16 (UCS Transformation Format-16bit)   
// -- 모든 문자를 2바이트로 인코딩 하는 방식 - 글자 개수에 제한이 없음   
- Introduction due to the limitations of character expression in ASCII   
- Industrial standards for consistent computer representation of all languages in the world   
- Unicode's representative character encoding method   
  - UTF-8 (UCS Transformation Format-8bit)   
    - To reduce file size, ASCII encodes into 1 byte and other characters encodes into 2 bytes or more - compatible with ASCII   
  - UTF-16 (UCS Transformation Format-16bit)   
    - Encode all characters to 2 bytes - no limit on the number of characters   
   
#### Markup text   
// 마크업 텍스트   
   
// 문서의 서식작성을 지정하거나 구조적 경계를 밝히는 특수문자를 삽입하여 표현하는 텍스트   
// 즉, 문서 내용 이외에 문서 서식을 지정하거나, 찾아보기 등을 지정하거나, 다른 문서와의 연결방법을 지정하여 컴퓨터에게 지시하는 마크업 정보가 들어있는 텍스트   
- Text that specifies the formatting of a document or incorporates special characters that reveal structural boundaries   
- In other words, text containing markup information instructing the computer by designating a document format, searching, etc., or designating a method of connection with other documents other than the contents of the document   
   
// 마크업 (markup)   
// - 문서 구조를 정의하거나 표현하기 위해 정의된 부가 정보   
// - 대표적인 마크업 언어 : HTML, SGML   
- markup   
  - Additional information defined to define or represent document structures   
  - Representative Markup Language : HTML, SGML   
   
#### Structural text   
// 구조적 텍스트   
   
// 구조적 정보를 갖는 태그가 사용된 텍스트   
// 선형의 순차적인 구조   
// 텍스트의 구조적 정보는 타이틀, 절, 단락 등을 말하며, 구조적 정보는 문서 처리와 문서 설계를 위해 독점적인 표현방법을 갖음   
- Text with tags with structural information   
- A linear sequential structure   
- Structural information of text refers to titles, clauses, paragraphs, etc., and structural information has a proprietary method of expression for document processing and document design   
   
- ODA (Office Document Architecture)   
// - 논리적 구조와 설계 구성요소가 어떻게 구성되고 서로 관계를 맺는지를 명시하는 국제 표준   
  - International standards specifying how logical structures and design components are structured and related to each other   
   
#### Hypertext   
// 하이퍼 텍스트   
   
// 비순차적인 전개원리를 갖는 텍스트   
// 여러 개의 연결된 문서라는 의미   
// 일반적인 텍스트와는 달리 다른 문서의 특정 위치로 연결   
// 따라서 물리적이고 논리적인 공간을 뛰어넘는 임의의 연결이 가능한 새로운 개념의 문서연결 형태   
- Text with non-sequential development principles   
- Meaning multiple linked documents   
- Connect to a specific location in another document, as opposed to normal text   
- Thus, a new conceptual form of document connection that allows arbitrary connections beyond physical and logical space   
   
// 하이퍼텍스트의 원리   
// - 비선형으로 그래프와 같은 구조   
// - 노드와 링크를 단위로 하는 정보의 구조화 방식   
// -- 노드는 텍스트의 작은 덩어리이며 링크로 연결   
- Principles of Hypertext   
  - non-linearly graph-like structure   
  - Structuring of information with nodes and links as units   
    - A node is a small chunk of text, linked by a link   
   
// 하이퍼링크 (hyperlink)   
// - 자료와 자료를 연결해 주는 방법   
- hyperlink   
  - How to link data to data   
   
<br />
### File Type of Text   
// 텍스트의 파일 형식   
   
// 텍스트 데이터의 파일 저장방식   
// - 영문 : ASCII   
// - 한글 : 완성형 한글코드   
// - 각종 문서 편집 응용 프로그램 : 각기 다른 저장 방식   
- How to save a file of text data   
  - English : ASCII   
  - Hangul : Complete Korean Code   
  - Various document editing applications : Different storage methods   
   
// 텍스트 파일 형식   
- Text File Format   
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
   
// ASCII 체계를 따른 편집기에서 작성한 파일 형식   
// 운영체제에서 기본적으로 제공하는 문서 편집기의 형식   
// 모든 텍스트 편집기나 워드 프로세서에서 읽을 수 있음   
// 그래프나 수식은 제공하지 않음   
- File types created by editors that follow ASCII schemes   
- The format of the document editor that the operating system provides by default   
- Readable from any text editor or word processor   
- Do not provide graphs or formulas   
   
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
