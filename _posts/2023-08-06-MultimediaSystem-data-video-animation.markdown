---
layout: post
title:  "Multimedia System: Video, Animation"
date:   2023-08-06 09:00:00 +0900
categories: [Multimedia System]
---

## Video   
   
<br />
### Overview of video   
   
- The largest and most difficult to process multimedia data   
- Video is structured multimedia (Consisting of video and audio)   
- Video is classified by screen size and number of frames per second   
  - Frame : Images that make up a video   
    - Computer or TV video : 30 frames per second   
    - Movie : 24 frames per second   
  - So the size of the video is   
    - Size of image frame × number of frames per second   
   
<br />
### Analog video and digital video   
   
#### Analog video   
   
- Analog video is an electrical signal   
- Visual information is coded according to the amplitude change of the signal   
- Coded signals are expressed as frames and horizontal scan lines   
<br />
- Characteristics of analog video   
  - Frame rate   
    - Refers to the number of frames per second produced by the video signal   
    - Typical frame rate is 25-30 frames per second   
  - Number of scan lines   
    - Number of horizontal lines that make up a TV screen   
  - Aspect ratio   
    - Width-to-height ratio of video images   
    - Broadcast video format has an aspect ratio of 4:3   
<br />
- Analog video signal format   
  - NTSC, PAL, SECAM methods   
<br />
- Video signal format and usage area   
   
|Broadcast format|Nation|Number of horizontal lines (Line)|Frame rate (frame / sec)|
|:---:|:---|:---:|:---:|
|NTSC|USA, Canada, Korea, Japan, Mexico|525|29.97|
|PAL|Australia, China, European countries, South Africa|625|25|
|SECAM|France, Middle East, African countries|625|25|
   
- Connection format for analog video (Cable connection format)   
  - Because analog video is noisy, the connection format between devices is very important   
  - Composite   
    - Simplest connection type   
    - The lowest quality because it transmits the luminance signal and the color signal together   
  - S-Video   
    - One level higher than composite   
    - The luminance signal is sent through one line, and the two color signals are sent through another line   
  - Component   
    - The best connection method   
    - Transmit each YCC signal through each cable   
   
#### Digital video   
   
- Digital video digitizes analog video and expresses the image as a set of frames   
<br />
- Characteristics of digital video   
  - Sampling method and rate   
    - Determine the digital representation form, storage capacity, and data transfer rate of the video signal   
  - Data rate and frame rate   
    - Data rate format is determined by data compression, horizontal and vertical resolution, and method of reducing frame rate   
   - Frame rate affects the depiction of motion in the video   
   
<br />
### Analog and video editing   
   
- Analog video has the advantage of being inexpensive and easily accessible, but has disadvantages in terms of picture quality, sound quality, and preservation compared to digital video   
   
#### Analog Editing   
   
- Analog editing is linear editing, digital editing is non-linear editing   
  - Linear editing   
    - Playback or editing is possible only in the recorded order   
    - Using tape as recording medium   
  - Non-linear editing   
    - Random access to specific parts of recorded video   
    - Use disk as recording medium   
   
#### Digital editing   
   
- Advantages   
  - Random access to specific parts of recorded video is possible   
  - Simple configuration of the editing system   
  - Editing without deterioration in image quality is possible   
  - Easy implementation of various effects and subtitles   
  - Excellent preservation   
<br />
- Disadvantage   
  - Rendering takes a lot of time due to software processing   
  - Lack of compatibility between each format   
  - Since the work is done using a computer, expertise is required   
   
<br />
### Video compression codec   
   
#### Video codec   
   
- Technology to compress/restore digital video data without loss of quality   
<br />
- Codec (Compressor / Decompressor)   
  - A term that includes both software that compresses or decompresses data using a data compression function, or devices and software that convert data such as audio and video into other formats   
    - When video is compressed with different codecs, the compressed data has a unique extension depending on the codec   
    - Codecs are not compatible with each other, so a codec that matches the extension is required for playback   
   
#### Types of video codecs   
   
- MPEG-4   
  - Developed by Microsoft as a complement to MPEG-2   
    - MPEG-1 : VCD quality   
    - MPEG-2 : DVD / HD quality   
      - Need to increase the capacity of storage media due to large capacity   
      - Difficulty playing in real time over the network   
  - Picture quality is similar to MPEG-2, but capacity is significantly reduced   
<br />
- MPEG (Moving Picture Experts Group)   
  - A group of video experts under ISO / IEC in charge of developing standards for multimedia such as video and audio   
  - Video compression standards   
<br />
- WMV (Window Media Video)   
  - Developed by Microsoft (Discontinued due to copyright)   
  - Excellent capacity and conversation quality   
<br />
- X.264   
  - One of several sub-codecs based on H.264   
    - H.264 is a video compression standard jointly created by MPEG and ITU   
    - Highest compression rate and highest quality picture quality among compression codecs   
    - The downside is that the encoding time is twice that of other codecs   
<br />
- DivX (Digital internet video eXpress)   
  - Video codec using MPEG-4 technology   
  - Capacity to store one high-definition movie on 1-2 CDs   
  - Use lossy compression method   
   
<br />
### Video file formats   
   
- AVI   
- MOV   
- MPEG   
- ASF   
- RA   
   
#### AVI (Audio Video Interleave)   
   
- Developed by Microsoft   
- Record audio and video content alternately (interleave)   
<br />
- Disadvantage   
  - Requires conversion to another format outside of Windows environment due to lack of compatibility   
  - The file size is large, making it unsuitable for use on the web (Because it takes time to play after all files are loaded)   
<br />
- Most modern website videos use streaming format   
   
#### MOV   
   
- The file format for QuickTime has the extension `*.mov`   
<br />
- Quicktime   
  - Multimedia playback software for Macintosh/Windows developed by Apple   
  - You can watch videos without the help of special hardware devices   
  - Real-time streaming support   
  - Scalability (QuickTime VR that implements virtual reality is also possible)   
   
#### MPEG   
   
- The file format uses the MPEG standard and the extension is `*.mpeg`   
- Most widely used as it can be used regardless of platform   
   
#### ASF (Active Streaming Format)   
   
- Streaming media format developed by Microsoft   
- Various file formats (AVI, WAV, MOV, MPEG, MP3, etc.) can be converted to ASF format using Windows Media Tools   
   
#### RA   
   
- Real Media file format   
- Like audio RA, video RA also has a high compression rate, but the picture quality is poor   
<br />
- Real Media   
  - Developed in a format for Internet broadcasting   
  - Now streaming, including video   
   
<br />
### Video editing software   
   
- Windows Movie Maker : End of support   
<br />
- Adobe Premiere Pro   
  - Adobe's real-time, timeline-based video editing software   
  - Powerful editing capabilities such as various special effects   
<br />
- Media Composer   
  - Digital non-linear video editing system by Avid Technology   
  - Often used in movies and broadcasts   
   
<br />
## Animation   
   
<br />
### Overview of animation   
   
- Animation   
  - A film or a technique for making a film using a cartoon or doll to make it look as if it were alive   
  - Using the afterimage effect of the eyes   
    - When looking at a picture, a slightly modified picture is quickly shown while the picture is still in the eye, making it feel like a continuous picture   
<br />
- Principles of Animation   
  - It uses the same principle that a series of pictures is drawn and appears to move when you turn the page quickly   
  - This principle is used in TV and movies (Using 30 frames per second)   
    - If 10 frames per second are shown, the movement appears to be broken to the eye   
   
<br />
### Types of animation   
   
- Depending on the production method   
  - Picture animation   
    - Flipbook animation   
    - Cell animation   
  - Model animation   
    - Clay animation   
    - Silhouette animation   
  - Computer animation   
    - Web animation   
    - 3D computer animation   
   
#### Picture animation   
   
- Flip-book animation   
  - The most basic animation   
  - Express moving pictures by quickly turning the pages of books with pictures on them   
<br />
- Cell animation   
  - It is composed of each scene by overlapping several transparent cells (Celluloid) on a background and taking pictures   
   
#### Model animation   
   
- Clay animation   
  - A method of moving a model made of clay little by little to fit the frame and then taking pictures of each : Stop motion method   
  - Photographing an object while it is still and later projecting different images to create the illusion of movement   
<br />
- Silhouette animation   
  - Animation using the silhouette of a shadow seen through backlight   
  - A technique of making a flat picture look like a silhouette and then shooting it in stop motion to make the silhouette appear to be moving   
  - Enriches imagination through the harmony of emotional characters and light illuminated by halos   
   
#### Computer animation   
   
- Web animation   
  - Animation for the Internet produced using a computer   
  - A mixture of web design and animation : Webtoons   
  - Flash is widely used as production software : Flash animation   
    - Flash animation : Excellent image quality compared to small file size   
<br />
- 3D computer animation   
  - Key frame techniques, motion capture techniques, etc. are used   
<br />
- Key framing technique   
  - This is a technique that can give movement to a 3D object, and is the most central frame, such as the start and end frames of a single movement   
  - Ensure that the screen transitions between one set key frame and another key frame occur naturally   
<br />
- Motion capture techniques   
  - Difficulty expressing human characters realistically   
  - A technique of making a virtual character move in the same motion by attaching a sensor to the body and recording the human body's movements in digital form   
   
<br />
### Animation authoring tools   
   
- Flash   
  - Adobe's vector graphics processing-based animation production software   
  - Simple to use and most widely used   
  - Recently, Adobe is seeking a change to HTML5   
<br />
- etc.   
  - Most 3D graphics editing software (Maya, 3ds Max, Softimage, etc.)   
    - Supports animation production function   
   
<br />
### Animation file format   
   
- SWF (ShockWave File)   
  - It is the basic file format of Flash   
- FLIC (FLI / FLC)   
  - It is a file format of Autodesk Animator   
- Various file formats exist   
   
<br />
<cite>Source : Department of Computer Science, Korea National Open University</cite>
