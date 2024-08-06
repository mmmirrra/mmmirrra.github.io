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
- Video is structured multimedia (consisting of video and audio)
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

|Broadcast format|Nation|Number of horizontal lines (line)|Frame rate (frame/sec)|
|:---:|:---|:---:|:---:|
|NTSC|USA, Canada, Korea, Japan, Mexico|525|29.97|
|PAL|Australia, China, European countries, South Africa|625|25|
|SECAM|France, Middle East, African countries|625|25|

<br />
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
- Codec (compressor / decompressor)
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
  - The file size is large, making it unsuitable for use on the web (because it takes time to play after all files are loaded)
<br />
- Most modern website videos use streaming format

#### MOV

19.jpge








<br />
### Video editing software














<br />
## Animation

<br />
### Overview















<br />
### Types of animation















<br />
### Animation authoring tools and file formats















<br />
<cite>Source : Department of Computer Science, Korea National Open University</cite>
