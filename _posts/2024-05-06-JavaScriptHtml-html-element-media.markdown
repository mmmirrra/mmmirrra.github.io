---
layout: post
title:  "JavaScript Html: html element media"
date:   2024-05-06 09:00:00 +0900
categories: [JavaScript Html]
---

### Elements related to media   
// 미디어와 관련된 요소   
   
<br />
### Audio element that plays audio   
// 오디오를 재생하는 audio 요소   
   
// 웹 페이지에서 오디오를 재생하기 위한 요소   
- Elements for playing audio from web pages   
   
```html
Audio Play : <br /><br />
<audio src="song.ogg" controls autoplay loop>
    <!-- Alternative text for browser unsupport -->
</audio>
```
   
#### Apply Source   
   
Audio Play : <br /><br />
<audio src="song.ogg" controls autoplay loop>
    <!-- Alternative text for browser unsupport -->
</audio>
<br /><br />
   
#### audio format   
// 오디오 형식   
   
- MP3 (*.mp3)
- Wav (*.wav)
- Ogg (*.ogg, *.oga)
   
#### Property   
// 속성   
   
|Property|Description|
|:---|:---|
|autoplay|// 웹 문서 로딩 시에 오디오를 자동으로 즉시 재생 여부<br />- Whether audio is automatically played immediately when loading a Web document|
|controls|// 오디오의 제어 버튼 (재생, 일시정지, 볼륨 등) 표시 여부<br />- Display of the control button (Play, pause, volume, etc.) for audio|
|loop|// 반복 재생 여부<br />- Repeated play|
|muted|// 음소거 여부<br />- Muted or not|
|preload="value"|// 웹 페이지가 열릴 때 오디오의 로딩 방식 지정<br />// - none : 재생 전까지 오디오 파일을 미리 로드하지 않음<br />// - auto : (기본) 웹 페이지 로딩 시 바로 전체 파일을 자동으로 로드<br />// - metadta : 재생 전까지 오디오의 메타 파일 (크기, 첫 프레임 등) 만 로드<br />// - autoplay 속성이 지정되면 preload 속성은 무시됨<br />- Specify how audio is loaded when a web page is opened<br />- none : Do not preload audio files until play<br />- auto : (Basic) Automatically loads the entire file immediately upon loading a web page<br />- metadta : Load only the audio's metafiles (size, first frame, etc.) before play<br />- If the autoplay property is specified, the preload property is ignored|
|src="URL"|// 재생할 오디오 파일의 URL<br />- URL of the audio file to play|
   
#### Source element specifying various file formats   
// 다양한 파일 형식을 지정하는 source 요소   
   
// 하나의 미디어 소스에 대해 서로 다른 형식을 갖는 여러 개의 파일을 동시에 지정하기 위한 요소   
// - audio, video 요소의 src 속성의 역할을 대신하는 것   
// -- 가장 위에서 나열된 source 요소의 파일부터 차례대로 재생 가능 여부를 검사해서 재생   
- Elements for concurrently specifying multiple files with different formats for one media source   
  - Replacing the role of the src property of the audio, video   
    - Check and play the files of the source elements listed above for playability in turn   
   
// 속성   
// - src="URL" → 재생할 미디어 파일의 URL   
// - type="MIME형식" → "audio/mp3", "audio/wav", "audio/ogg"   
// - media="미디어 쿼리" → 파일을 위한 미디어 쿼리 지정   
- Property   
  - src="URL" → URL of the media file to play   
  - type="MIME format" → "audio/mp3", "audio/wav", "audio/ogg"   
  - media="media query" → Specify media queries for files   
   
```html
Audio Play : <br /><br />
<audio controls autoplay loop>
    <source src="song.ogg" type="audio/ogg">
    <source src="song.wav" type="audio/wav">
    <source src="song.mp3" type="audio/mp3">
    <!-- The current browser does not support audio elements -->
</audio>
```
   
#### Apply Source   
   
Audio Play : <br /><br />
<audio controls autoplay loop>
    <source src="song.ogg" type="audio/ogg">
    <source src="song.wav" type="audio/wav">
    <source src="song.mp3" type="audio/mp3">
    <!-- The current browser does not support audio elements -->
</audio>
<br /><br />
   
<br />
### Video element that plays video   
// 비디오를 재생하는 video 요소   
   
// 웹 페이지에서 비디오를 재생하기 위한 요소   
// - audio 요소의 사용 방법과 거의 동일   
- Elements for playing video from web pages   
  - Almost identical to how audio elements are used   
   
```html
<video src="Video File URL" property ... >
    Alternative text for browser unsupport
</video>
```
   
#### video format   
// 비디오 형식   
   
- MP4 (*.mp4)   
- WebM (*.webm)   
- Ogg (*.ogv)   
   
#### Property   
// 속성   
   
// audio 요소의 속성을 모두 그대로 사용   
- Use all the properties of audio elements as they are   
  - autoplay, controls, loop, muted, preload, src   
   
// width="픽셀", height="픽셀"   
// - 화면에서 비디오 콘텐츠가 표시될 영역의 크기 (폭, 넓이)   
- width="pixel", height="pixel"   
  - Size of area where video content will be displayed on the screen (width, height)   
   
// poster="이미지 파일의 URL"   
// - 지정한 비디오 데이터가 설정되어 있지 않거나 비디오가 로딩되는 동안에 보여 줄 이미지 지정   
- poster="Image File URL"   
  - Specify the image to show while the specified video data is not set or the video is loading   
   
```html
Video Play : <br /><br />
<video controls width="600" height="300" poster="poster.jpg">
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.webm" type="video/webm">
    <source src="movie.ogv" type="video/ogg">
    The current browser does not support video elements
</video>
```
   
#### Apply Source   
   
Video Play : <br /><br />
<video controls width="600" height="300" poster="poster.jpg">
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.webm" type="video/webm">
    <source src="movie.ogv" type="video/ogg">
    The current browser does not support video elements
</video>
<br /><br />
   
#### Specify the play section of the content   
// 콘텐츠의 재생 구간 지정   
   
// 미디어 콘텐츠를 재생할 때 특정 구간을 지정하여 재생   
// - audio, video 또는 source 요소의 src 속성 이용해서 지정   
- Play media content by specifying a specific interval   
  - Specify using src properties of audio, video, or source elements   
   
```html
src="fileName#t=[Start time][,End time]"
```
   
|`#t=[hour:minute:second][,hour:minute:second]`|Description|
|:---|:---|
|`src="a.mp4#t=1:20:32,2:05:00"`|// 1시간 20분 32초 ~ 2시간 5분 까지 재생<br />- Play for 1 hour 20 minutes 32 seconds to 2 hours 5 minutes|
|`src="a.mp4#t=20,40"`|// 20초 ~ 40초 까지 재생<br />- Play for 20 to 40 seconds|
|`src="a.mp4#t=,30"`|// 처음 ~ 30초 까지 재생<br />- Play for the first to 30 seconds|
|`src="a.mp4#t=30"`|// 30초부터 재생 시작<br />- Play from 30 seconds|
   
```html
Video Play : <br /><br />
<video src="movie.mp4#t=10,20" controls autoplay>
    The current browser does not support video elements
</video>
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
