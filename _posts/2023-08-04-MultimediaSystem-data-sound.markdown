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

![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/multimediaSystemSound1.png)

  - Amplitude : The height of the waveform between the highest or lowest point of the waveform and the center line
  - Period : The time it takes for one cycle to start at the center line, pass through the top and bottom of the waveform, and reach the center line again
  - Frequency : Number of cycles per unit time, unit called Hertz (Hz)
    - Frequency = <sup>1</sup> / <sub>cycle</sub>

#### Characteristics of analog sound

- Sound is displayed as a continuous analog waveform
- Expressed as sound size (Amplitude), sound pitch (Frequency : cycle), and tone

![](https://raw.githubusercontent.com/mmmirrra/mmmirrra.github.io/main/_assets/multimediaSystemSound2.png)

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

- Analog signals
  - Continuous signals with linear values ​​such as sound, current, and voltage
  - The advantage of being able to adjust the size of the signal in minute increments
  - However, the disadvantage is that the signal changes due to noise

- Digital signals
  - Signals with values ​​in discrete steps
  - Express the case by a combination of 0 and 1
  - Digital equipment such as computers cannot process anything other than digital signals

#### Analog → Digital / Digital → Analog

- Using ADC (Analog-to-Digital Converter) and DAC (Digital-to-Analog Converter) conversion devices
- Through an ADC device, analog signals are converted into digital signals through sampling, quantization, and encoding processes
- Convert digital signals to analog signals through a DAC device for playback

- Sound conversion process
  - [Analog signal] → Sampling → Quantization → [Encoding]
 → [Digital signal]

#### Sampling

- To digitize the sound and play it again
    - The analog waveform of the sound is divided into small pieces at regular intervals and the values ​​are recorded one by one. When playing back, the waveform is redrawn according to the recorded values

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

- Since voice signals are converted using the PCM (Pulse Code Modulation) method, the number of sample bits is also called a PCM word

#### Three characteristics of digital sound (Numerical standards)

- Sampling size
  - Expressing the size (Amplitude) of the sound as a digital number
  - The larger the number of sample bits, the more detailed the size of the sound is expressed

- Sampling rate
  - Also called sampling frequency
  - The smaller the sampling interval (Larger the sampling rate), the more precisely the analog waveform can be expressed as digital sound

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

- Digital sounds are saved as digital audio files

#### File size of digital audio

- Size of audio file = Sampling size (byte) x Sampling rate x Number of channels x Time (Seconds)

- Example) What if you save stereo sound at 16 bit, 44.1 KHz for 1 minute?
  - Size of audio file = 2(byte) x 44100 × 2 × 60 (Seconds) = 10,584,000 ≒ 10 Mbyte
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

- Compression of audio data
  - Lossy compression : Take the loss of information and minimize the amount of data
  - Lossless compression : Suppresses information loss as much as possible and maintains the highest sound quality

- Various audio file formats
  - Digital audio data exists in various file formats depending on the compression method for storage or transmission on a storage medium

- Representative audio file format with lossless compression
  - WAV (Waveform Audio Format)
  - AU (Audio)
  - AIFF (Audio Interchange File Format)
  - RealAudio
  - ASF (Advanced Streaming Format)

31.jpg






<br />
### Digital audio editing software


















   
<br />
<cite>Source : Department of Computer Science, Korea National Open University</cite>
