---
layout: post
title:  "Multimedia System: Data - Text"
date:   2023-08-03 09:00:00 +0900
categories: [Multimedia System]
---

### Multimedia data   
   
- Text, sound, images, graphics, video, animation   
<br />
- Differences between each multimedia data   
  - How to obtain   
    - Acquired via computer: Text, graphics, animation   
    - Acquire from the real world: Sound, images, video   
  - Spatio-temporal aspects   
    - Continuous characteristics: Sound, video, animation   
    - Non-continuous characteristics: Text, images, graphics   
   
### Overview of the text   
   
- Information printed on paper as document data or displayed on a screen such as a monitor   
- Data aimed at conveying meaning to the other party   
- Also used as a character designating the Internet communication path.   
- It does not provide audio-visual interest like other multimedia data, but is used to convey important and elaborate information.   
   
#### Characteristics of text   
   
- Requires less storage capacity compared to other multimedia data.   
- Different characteristics depending on the language used.   
  - Depending on the language, specific tools are required to support that language.   
  - This is because the character set that represents text is different depending on the language used.   
   
<br />
### Expression of text   
   
- Text is composed of a set of characters inside the computer.   
<br />
- Character encoding   
  - All characters are expressed as binary codes inside the computer, and each character is assigned one number.   
  - Therefore, if the language is different, the code used is also different.   
   
#### Character set and encoding   
   
- Character set   
  - Defining and ordering the characters to be expressed.   
<br />
- CCS (Coded Character Set)   
  - Character set expressed in code form.   
    - ASCII   
    - EBCDIC   
    - Western European character set   
    - Hangul code   
    - Unicode   
   
#### ASCII (American Standard Code for Information Interchange)   
   
- Standard established in the United States as the English character set.   
- The most common format for text files on a computer or on the Internet.   
- Alphabets, numbers, and special characters are expressed as 7-bit binary numbers.   
- A total of 128 characters are defined.   
   
#### EBCDIC (Extended Binary Coded Decimal for Interchange Code)   
   
- Code system developed by IBM   
- Mainly used in IBM's large computers.   
- 8-bit binary numbers are used.   
- Can express twice as many symbols and control functions compared to ASCII.   
   
#### Western European character set   
   
- It is not enough to express European languages ​​in 7-bit ASCII.   
- A new character set incorporating Western European characters into ASCII.   
- Also called "Western European Character Set" or "ISO Latin-1".   
- Uses 8-bit code system as an extension of ASCII.   
<br />
- ISO: International Organization for Standardization   
   
#### Hangul code   
   
- English or European languages ​​can be expressed with 256 8-bit codes.   
- Hangul cannot express all Hangul combinations in 8 bits.   
- Therefore, combined and completed Hangul codes were created.   
  - Combined type: Based on the principle of Hangul, codes are assigned to each elementary, middle, and final consonant.   
  - Completed type: Assign codes to complete characters such as '가' and '각'.   
- The completed Hangul code is the Hangul standard.   
  - The completed type has the disadvantage of not being able to express all Hangul characters, but it was adopted as a standard because it causes fewer problems in computer communications.   
   
#### Unicode   
   
- Introduced due to limitations in character expression of ASCII.   
- An industry standard that allows all languages ​​around the world to be expressed consistently on computers.   
- Unicode's representative character encoding method   
  - UTF-8 (UCS Transformation Format-8bit)   
    - To reduce the file size, ASCII is encoded into 1 byte, and other characters are encoded into 2 bytes or more. - Compatible with ASCII.   
  - UTF-16 (UCS Transformation Format-16bit)   
    - A method of encoding all characters into 2 bytes - There is no limit to the number of characters.   
   
#### Markup text   
   
- Text expressed by inserting special characters that specify the format of the document or reveal structural boundaries.   
- In other words, text that contains markup information that instructs the computer to specify the document format, search, etc., or how to connect to other documents in addition to the document content.   
<br />
- Markup   
  - Additional information defined to define or express the document structure.   
  - Representative markup languages: HTML, SGML   
   
#### Structured text   
   
- Text using tags with structural information   
- Linear sequential structure   
- Structural information of text refers to titles, clauses, paragraphs, etc., and structural information has a proprietary expression method for document processing and document design.   
<br />
- ODA (Office Document Architecture)   
  - An international standard that specifies how logical structures and design components are organized and relate to each other.   
   
#### Hypertext   
   
- Text with a non-sequential development principle.   
- Meaning multiple linked documents.   
- Unlike general text, links to a specific location in another document.   
- Therefore, a new concept of document connection form that allows arbitrary connections beyond physical and logical space.   
<br />
- Principles of hypertext   
  - Non-linear graph-like structure   
  - Structural method of information using nodes and links as units   
    - Nodes are small chunks of text, connected by links.   
<br />
- Hyperlink   
  - How to connect data to data   
   
<br />
### Text file format   
   
- File storage method for text data   
  - English: ASCII   
  - Hangul: Completed Hangul code   
  - Various document editing applications: Different storage methods   
<br />
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
   
- File format created in an editor following the ASCII system.   
- The format of the document editor provided by default in the operating system.   
- Readable in any text editor or word processor.   
- Graphs or formulas are not provided.   
   
#### DOC (Document)   
   
- DOC (Document) is Microsoft's MS Word document format.   
- Compared to the TXT format, it has the advantage of supporting various string formats such as graphic effects, drawing and special characters, formulas, and supporting string alignment, tabs, line spacing, etc.   
- The disadvantage is that the file size increases even if the same text is saved.   
   
#### HWP (Hangul Word Processor)   
   
- Document format used in Hangul word processors   
- While other word processors save as complete code, this file format saves as a combined code system.   
- Files created in a higher version may not be readable in a lower version.   
- When saving a file, you can reduce its capacity by specifying a password or compressing it.   
   
#### RTF (Rich Text Format)   
   
- RTF (Rich Text Format) is a document format standardized by Microsoft.   
- A format created to allow text files to be exchanged between different operating systems and word processors.   
- Document exchange is possible on PCs compatible with IBM PCs, other PCs such as Macintosh, and other operating systems.   
   
#### HTML (Hyper Text Markup Language)   
   
- HTML (Hyper Text Markup Language) is a general TXT document format.   
- Editable in a general document editor.   
- Standard format for Internet web documents.   
- Document format with higher compatibility than RTF format.   
   
#### XML (eXtensible Markup Language)   
   
- XML (eXtensible Markup Language) was created with the purpose of replacing HTML.   
- Page description language proposed and standardized by W3C   
- Text format designed to transmit structured documents on the web.   
- The file is in TXT format and can be edited using a general editor.   
- Prescribed to have the advantages of both HTML and SGML.   
<br />
- W3C (World Wide Web Consortium)   
  - An international consortium related to the Internet founded in 1994 for the long-term development of the web, including establishing web standards.   
   
#### XHTML (eXtensible Hyper Text Markup Language)   
   
- Reorganize HTML Version-4 with XML.   
- A highly scalable and portable language that is defined to share data on the web and is used for various purposes.   
- New expressions such as mathematical expressions, vector shape processing, and multimedia are possible.   
   
#### PDF (Potable Document Format)   
   
- PDF (Potable Document Format) is an electronic document format developed by Adobe Systems.   
- Developed for the purpose of providing the same expression regardless of computer environment.   
- Sharing and transmitting document information is possible through various transmission methods in both online and offline environments.   
<br />
- Advantages compared to other document formats   
  - Most documents can be expressed.   
  - Difficult to tamper with due to encryption and compression technology.   
  - Available for application in various programs.   
<br />
- It is suitable for digital publishing such as e-book or CD publishing because it displays the printed state as is on the computer.   
   
#### TeX/LaTeX   
   
- TeX   
  - Document formatting or typesetting system that allows detailed specifications.   
  - Documents can be formatted or typeset by describing and compiling the source on a text editor according to the grammar of the tag.   
  - Open software   
  - Operates on all computer systems including Unix, DOS, Windows, Macintosh, and etc.   
<br />
- LaTeX   
  - A system that improves the inconvenient user interface of TeX   
<br />
- TeX/LaTeX has the advantage of being able to write very pretty fonts or mathematical formulas by writing simple commands (Tags) according to the grammar and compiling this file.   
   
<br />
### Electronic books and publishing   
   
#### Electronic books   
   
- Electronic Book or e-Book   
- A type of online electronic publishing   
- The contents of the book are converted into a digital file and read on a computer or dedicated terminal using a dedicated viewer.   
- In general, the content, software, and hardware that make up an e-book are sometimes referred to as an e-Book.   
   
#### Electronic publishing, ePublishing   
   
- Methods and techniques for producing publications in a digitized manner using computers   
- It developed with the development of a new editing system called DTP (Desk Top Publishing) (1985, USA) and the advent of CD-ROM, an electronic publication.   
- Also called online publishing or web publishing.   
<br />
- DTP   
  - Desk Top publishing   
  - The task of designing publications such as books or dictionaries using a computer   
   
#### Online electronic publishing   
   
- With the development of the Internet, electronic publishing became established and services were provided through the web.   
<br />
- Characteristics of online electronic publishing   
  - Because it provides information through a network, it provides a variety of information, including text, pictures, moving images, and even human voices.   
  - Compared to existing paper publications, it has advantages such as speed, ease of search, convenience of storage, cost reduction, and interactivity.   
<br />
- Examples of online electronic publishing   
  - Webzine   
    - Magazines published on the Internet   
  - POD (Publishing On Demand)   
    - A service that produces books upon customer request   
   
#### Format of online electronic publishing   
   
- HTML, PDF, XML, etc. are used.   
  - As HTML shows limitations in handling multimedia data, alternatives such as XML and HTML5 are used.   
  - The PDF format is also widely used because it has the advantage of various editing layouts and can implement various multimedia.   
   
#### Terms related to electronic publishing   
   
- EPUB (Electronic Publication)   
  - An open and free electronic book standard established by the International Digital Publishing Forum (IDPF).   
    - It provides automatic space adjustment and font size conversion, the ability to contain raster or vector images inside, DRM and CSS functions, and includes metadata.   
<br />
- DRM (Digital Rights MAnagement)   
  - Refers to any technology used by publishers or copyright holders to control the use of digital data or hardware they distribute and limit their use to only those for which they are intended.   
<br />
- CSS (Cascading Style Sheet)   
  - It is a language that describes how a markup language is actually displayed, and is mainly used in HTML and XHTML, and is also used in XML.   
   
<br />
<cite>Source: Department of Computer Science, Korea National Open University</cite>
