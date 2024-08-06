---
layout: post
title:  "Multimedia System: Data - Sound"
date:   2023-08-04 09:00:00 +0900
categories: [Multimedia System]
---

### Concept of sound   
   
- Sound   
  - Refers to music, voices, simple sounds, etc.   
  - The concept of sound waves as physical vibrations   
- Audio   
  - The sound part of radio, television, record players, etc.   
  - Common term for devices for listening to music, etc. with effective sound   
   
#### Analog sound   
   
- Sounds heard in the real world   
- Sound consists of tone, sound size, and sound pitch   
- Concept of sound waves   
  - Sound waves (Vibration of sound) are composed of amplitude and period   
   
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/multimediaSystemSound1.png)
   
<br />
  - Amplitude : The height of the waveform between the highest or lowest point of the waveform and the center line   
  - Period : The time it takes for one cycle to start at the center line, pass through the top and bottom of the waveform, and reach the center line again   
  - Frequency : Number of cycles per unit time, unit called Hertz (Hz)   
    - Frequency = <sup>1</sup> / <sub>cycle</sub>   
   
#### Characteristics of analog sound   
   
- Sound is displayed as a continuous analog waveform   
- Expressed as sound size (Amplitude), sound pitch (Frequency : cycle), and tone   
   
<br />
![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/multimediaSystemSound2.png)
   
<br />
- Three characteristics of analog sound   
  - Sound size (Amplitude)   
    - The larger the amplitude, the louder the sound   
    - The unit is decibel (dB)   
    - 0 dB : The quietest sound a person can hear   
    - 50 ~ 70 dB : Loudness when having a conversation   
  - Sound pitch (Frequency)   
    - Number of cycles per second   
    - The higher the frequency, the higher the sound   
    - 10 kHz : 10,000 cycles occur per second   
    - Audible frequency : 20 ~ 20 kHz   
  - Tone   
    - Features that help our ears distinguish sounds from each other   
    - Determined by frequency and amplitude   
   
#### Digital sound   
   
- This means that sound is expressed and stored digitally   
- Sound : Original analog signal   
- Digital sound : Conversion of analog signals to digital signals   
   
#### Characteristics of digital sound   
   
- Analog sound preserves its original form in all signal processing, but digital sound completely breaks down the basic form, preserves it in a completely new form, and then returns it to its original form   
- Therefore, even if there is loss of the original sound, it is not a problem as the loss is compensated for through various methods   
   
<br />
### Converting sound   
   
- Converting analog signals to digital signals   
<br />
- Analog signals   
  - Continuous signals with linear values ​​such as sound, current, and voltage   
  - The advantage of being able to adjust the size of the signal in minute increments   
  - However, the disadvantage is that the signal changes due to noise   
<br />
- Digital signals   
  - Signals with values ​​in discrete steps   
  - Express the case by a combination of 0 and 1   
  - Digital equipment such as computers cannot process anything other than digital signals   
   
#### Analog → Digital / Digital → Analog   
   
- Using ADC (Analog-to-Digital Converter) and DAC (Digital-to-Analog Converter) conversion devices   
- Through an ADC device, analog signals are converted into digital signals through sampling, quantization, and encoding processes   
- Convert digital signals to analog signals through a DAC device for playback   
<br />
- Sound conversion process   
  - [Analog signal] → Sampling → Quantization → [Encoding] → [Digital signal]   
   
#### Sampling   
   
- To digitize the sound and play it again   
    - The analog waveform of the sound is divided into small pieces at regular intervals and the values ​​are recorded one by one. When playing back, the waveform is redrawn according to the recorded values   
<br />
- Sampling   
    - The process of dividing the waveform into small pieces at regular intervals and extracting the values ​​of each point one by one   
    - At this time, the value expressed as each value is called a sample   
   
#### Sampling rate   
   
- Number of samples taken in 1 second   
- The unit is Hz, also called sampling frequency   
- The larger the sampling rate, the higher quality sound can be produced   
- In other words, the sound quality improves when more samples are stored per unit time   
- However, the disadvantage is that a higher sampling rate increases the amount of data   
   
#### Nyquist theorem   
   
- According to sampling theory, in order to reproduce the original analog signal, more than twice the highest frequency of the analog signal must be sampled   
- As an example, to sample a sound we can hear   
  - A sampling period of 40 kHz or more is required, which is twice the maximum audible frequency of 20 kHz   
  - To maintain high quality, use a sampling cycle of 4 times or more   
   
#### Quantization   
   
- Signals obtained through sampling must be quantized   
  - Quantization refers to the operation of expressing a certain value as a finite, discrete value   
  - In other words, the process of discretely approximating the magnitude of the sampled signal   
   
#### Quantization error   
   
- Occurs when approximating a continuous signal to a discrete signal   
- Refers to the error between the original signal and the quantized signal   
- It is also called quantization noise, and it needs to be kept as small as possible as it causes quality deterioration following digitization   
   
#### Encoding   
   
- Expressing quantized analog signals as binary information in digital form   
  - What is 8-bit encoding?   
    - Quantizing with 8 bits per sample, that is, 256 steps   
    - This means dividing the sample's highest and lowest points into 256 intervals   
  - Determine the number of sample bits considering quality and economy   
    - Typically 8-bit, 16-bit encoding   
<br />
- Since voice signals are converted using the PCM (Pulse Code Modulation) method, the number of sample bits is also called a PCM word   
   
#### Three characteristics of digital sound (Numerical standards)   
   
- Sampling size   
  - Expressing the size (Amplitude) of the sound as a digital number   
  - The larger the number of sample bits, the more detailed the size of the sound is expressed   
<br />
- Sampling rate   
  - Also called sampling frequency   
  - The smaller the sampling interval (Larger the sampling rate), the more precisely the analog waveform can be expressed as digital sound   
<br />
- Number of channels   
  - Number of sounds heard simultaneously   
  - There are mono and stereo   
    - Mono : Uses only one single channel   
    - Stereo : Uses two channels, twice the storage capacity compared to mono   
   
#### Sound quality and use according to the characteristics of digital sound   
   
|Sampling rate|Sample beat|Mode|Size of data per minute|Sound quality and use|
|:---|:---:|:---:|:---:|:---|
|44.1 kHz|16 bit|Stereo|10.5 Mb|CD sound quality, music standard|
|44.1 kHz|16 bit|Mono|5.25 Mb|High-quality recording of instruments or voices|
|44.1 kHz|8 bit|Stereo|5.25 Mb|Highest quality sound recording on Windows or PC|
|44.1 kHz|8 bit|Mono|2.6 Mb|Suitable sound quality for recording mono sources|
|22.05 kHz|16 bit|Stereo|5.25 Mb|The sound quality is at FM radio level. The sound quality is a bit muddy, but it is good enough to enjoy music with high resolution and stereo|
|22.05 kHz|16 bit|Mono|2.5 Mb|Suitable for voice or sound effects, but it is desirable to lower the sample bit to reduce the burden on the system|
|22.05 kHz|8 bit|Stereo|2.6 Mb|AM radio-level sound quality, can't reproduce all bands of audible frequencies, but is great for game music, etc.|
|22.05 kHz|8 bit|Mono|1.3 Mb|The sound quality is similar to TV sound, and the file size is not large, so it is very useful. Excellent for recording midrange and human voices|
|11 kHz|16 bit|Stereo|1.3 Mb|Phone level sound quality, little stereo effect|
|11 kHz|16 bit|Mono|650 kb|The sound is very muddy and has a sound quality that feels like being surrounded by thick cloth. It is still widely used for system warning sounds, etc.|
|5.5 kHz|8 bit|Stereo|650 kb|Doesn't suit stereo at all|
|5.5 kHz|8 bit|Mono|325 kb|The sound quality is similar to that of a phone with very poor sensitivity|
   
<br />
### How to convert sound   
   
#### PCM (Pulse Code Modulation)   
   
- Representative methods used to digitize sound   
  - How to save the entered value as is   
  - The analog waveform is continuously divided into small time intervals (Sampling), each is displayed in a rectangular size (Quantization), and its height is numbered (Encoding)   
   
#### PCM signal generation process   
   
- First, the analog signal is quantized to create a PAM (Pulse Amplitude Modulation) signal, which is then converted into a binary code string with a number of bits equal to the number of digital level bits of the pulse   
<br />
- In the PCM method, the higher the sampling rate, the better the sound quality, but since there is no compression process, the memory capacity increases   
   
#### DPCM (Differential PCM)   
   
- DPCM method is an improved PCM method   
  - A method based on the fact that analog signals do not change significantly when comparing waveforms at adjacent sampling points   
  - In other words, the PCM method stores the sound waveform value as is, but the DPCM method stores only the difference from the previous value   
  - The amount of data is reduced compared to the PCM method   
   
#### ADPCM (Adaptive DPCM)   
   
- ADPCM method improves the DPCM method   
  - The DPCM method stores the difference from the immediately preceding signal, but when the signal difference is large, there is a problem that the efficiency of DPCM decreases   
- The ADPCM method is a predictive coding method that was created to solve the problems of DPCM   
  - The width of the quantization step in DPCM is adaptively changed according to the amplitude of the signal   
  - In other words, if the difference from adjacent values ​​is large, the amplitude step width is increased, and if the difference is small, the amplitude step width is made small to express the difference variably and precisely   
   
<br />
### Creation and storage of digital audio   
   
#### How to create digital audio   
   
- Extract sound from a music CD or sound effect CD using the computer's CD driver   
- Connect computer's sound card to audio system to record sound from CDs, tapes, radio, etc.   
- Example) Using a Windows sound recording program   
  - When the analog signal, which is a sound wave, is transmitted to the microphone, the thin membrane inside the microphone vibrates   
  - Analog signal of vibration is digitized by sound card   
  - Digitized signals are stored as digital data in RAM   
   
#### Storage of digital audio   
   
- Recorder provided by Windows   
  - Easy to use, can record up to 1 minute   
  - Through the microphone, sound is converted into sound data in wave format   
  - In other words, the sound recorder writes files in Microsoft's wave format   
<br />
- Digital sounds are saved as digital audio files   
   
#### File size of digital audio   
   
- Size of audio file = Sampling size (byte) x Sampling rate x Number of channels x Time (Seconds)   
<br />
- Example) What if you save stereo sound at 16 bit, 44.1 KHz for 1 minute?   
  - Size of audio file = 2 (byte) x 44100 × 2 × 60 (Seconds) = 10,584,000 ≒ 10 Mbyte   
    - Therefore, one 3-minute piece of music requires approximately 30 Mbytes of storage space   
    - Also, in order to transmit audio files, it is essential to keep the file size small   
    - Therefore, data compression is necessary to reduce the size of the audio file   
    - An efficient compression method that can maintain sound quality while increasing the compression rate should be considered   
   
#### Format of audio files   
   
- Digital audio quality   
  - Proportional to the amount of data and determined by the sampling rate and number of sample bits   
  - Increasing the amount of data improves sound quality   
    - Same as the original sound : Audio data must not be compressed   
    - Similar to the original sound : Compresses and uses audio data   
<br />
- Compression of audio data   
  - Lossy compression : Take the loss of information and minimize the amount of data   
  - Lossless compression : Suppresses information loss as much as possible and maintains the highest sound quality   
<br />
- Various audio file formats   
  - Digital audio data exists in various file formats depending on the compression method for storage or transmission on a storage medium   
<br />
- Representative audio file format with lossless compression   
  - WAV (Waveform Audio Format)   
    - File format jointly developed by Microsoft and IBM   
    - Used on Windows-based PC   
    - Can be used without a separate plugin   
    - The sound quality is relatively excellent and editing is easy   
    - The file size is so large that it is often used for short music or sound effects   
    - Starting with Windows Vista, it is changed to WMA (Window Media Audio)   
  - AU (Audio)   
    - File format developed by Sun Microsystems   
    - Used in Unix systems   
    - It is similar to WAV, but the sampling rate is slightly lower, so the sound quality is slightly lower than WAV files   
  - AIFF (Audio Interchange File Format)   
    - File format developed by Apple   
    - Mainly used on Macintosh   
    - Extensions are `*.aiff`, `*.aif`   
  - RealAudio   
    - Developed by Real Network   
    - Streaming audio format created for real-time transmission over the Internet   
    - To listen to real audio, a plug-in must be installed   
    - Extensions are `*.ra`, `*.ram`   
  - ASF (Advanced Streaming Format)   
    - Developed by Microsoft   
    - Streaming media containing digital sound and video   
    - Files can be downloaded and played simultaneously   
   
<br />
### Digital audio editing software   
   
#### Sound Forge   
   
- Developed by Sony creative software   
- Real-time sample-level wave editing software   
- Sound Forge can burn music files directly to CD and capture audio in its original form   
- Supports various file formats (WAV, AVI, AIFF, MP3, AA3, AU, FLAC, etc.)   
   
#### GoldWave   
   
- Developed by GoldWave   
- Sound can be expressed in real-time amplitude and spectrum through an oscilloscope   
- Various editing, various effects, and file conversion of large files are possible   
- It has the advantage of supporting various file formats and being easy to use   
   
<br />
### MIDI   
   
#### Overview   
   
- International standard for digital music established in 1982   
- Summary of communication protocols between hardware, cables, and equipment that connect computers and electronic instruments from different manufacturers   
- It does not contain actual sounds, but contains information about how to play the instrument   
<br />
```
[ Sequencing program ]        [ MIDI devices (sampler, etc.) ]
          |                                 |
     [ Computer ]────────[ MIDI interface card ]
                                            |
[ Amplifier (speaker) ]──[ MIDI devices (synthesizers, etc.) ]
```
   
<br />
### MIDI editing program   
   
- To play and create professional MIDI files, you must use a MIDI editing program   
<br />
- If you use a MIDI editing program,   
  - When you play using an electronic instrument, the results are input in the form of sheet music,   
  - If your performance or notes are wrong, you can correct them   
  - You can listen to the sound of the violin played on the piano   
<br />
- To use MIDI on a computer   
  - Pentium MMX or higher computer,   
  - Operating system Windows 95 or higher,   
  - Essential equipment for MIDI music,   
  - MIDI software, etc. required   
   
#### Sequencer   
   
- A program that simulates a multitrack recorder   
  - A program that records music played on a musical instrument in units called tracks and plays several recorded tracks simultaneously, giving the effect of playing an orchestra   
<br />
- Using a sequencer program   
  - Just by playing the instrument, you can record and save individual MIDI data, making music creation easy and efficient   
<br />
- Types of sequencer programs   
  - Cakewalk by CMS Technologies   
  - Sequencer Plus mk I, mk II, mk III, etc. by Voyetra   
   
#### Notation program   
   
- A music score writing program that converts MIDI signals entered by hand and then displays them as sheet music using computer graphics   
- Also called score program   
- A type of compiler that converts sequencer data into score data   
- Types of notation programs   
  - Copyist 6.0, Personal Composer, Score, Encore, etc.   
   
#### Voicing Program   
   
- A program that uses a computer to more efficiently create or edit the tones of a specific synthesizer   
- Provides a convenient tone creation environment using the computer’s relatively large screen and graphics   
   
<br />
### MIDI file format   
   
- MIDI files   
  - Unlike WAV files, waveform information is not stored, so the file size is relatively small and editing such as adding and deleting instruments is easy   
   
#### SMF (Standard MIDI File)   
   
- As a standard MIDI file, the extensions are `*.mid`, `*.smf`   
   
#### RMI (RIFF MIDI File)   
   
- Standard format of MIDI data file used in Windows, extension `*.rmi`   
   
#### MOD (MODules)   
   
- Sound file format developed by Amiga Systems   
- It has music score information like MIDI, and also has built-in sound source information like WAV   
- Extension is `*.mod`   
   
<br />
<cite>Source : Department of Computer Science, Korea National Open University</cite>
