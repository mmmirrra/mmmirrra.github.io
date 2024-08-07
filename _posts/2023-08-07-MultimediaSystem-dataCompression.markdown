---
layout: post
title:  "Multimedia System: Data compression"
date:   2023-08-07 09:00:00 +0900
categories: [Multimedia System]
---

## Overview of data compression

<br />
### data compression

- Technology for efficiently recording data in a smaller space
- If the amount of data is large
  - Difficult to store efficiently on storage devices
  - Difficulties in transmitting using a communication network
- Therefore, compression technology that reduces large amounts of data is needed

<br />
### Basic principles of data compression

- Removing redundancy contained in data
<br />
- Data redundancy
  - Statistical redundancy
  - Subjective redundancy
  - Spatial redundancy
  - Temporal redundancy

<br />
### How to eliminate redundancy in data

- Statistical redundancy
  - Remove statistical redundancy in data statistics based on information theory
- Subjective redundancy
  - Removal of visible subjective redundant data based on human visual structure
- Spatial redundancy
  - Remove spatial duplication by using correlations that appear between data
- Temporal redundancy
  - Remove temporal overlap such as differences between video frames

<br />
### Data Compression Techniques

- Depending on the degree of information loss when compressing
  - Lossless compression : Reversible compression
  - Losy compression : Irreversible compression
  - Hybrid compression : Lossless and lossy compression used together
- Depending on the nature used for compression
  - Entropy Compression : Lossless Compression
    - Compression technique that does not consider the properties of the object to be compressed
  - Target-based compression : Lossy compression
    - Compress using the characteristics of the target information to be compressed

### Requirements for data compression techniques

- Compression / restoration should not be significantly different from the original data
- The compression algorithm itself should not be complicated
- The delay time during compression / restoration should not be too long
- It must be possible to compress various types of data
- Both hardware and software implementation must be possible

<br />
## Technique using lossless compression

<br />
### Lossless compression

- When compressed information is restored, it has the same content as before compression (Reversible compression)
- The compression rate is lower than lossy compression, and the compression algorithm has many limitations
- Used in fields where data cannot be lost, such as medical images and design drawings

<br />
### Lossless compression technique

- Run Length Coding
- Huffman Coding
- LZW Coding (Lempel-Ziv-Welch Coding)

<br />
### Repeat Length Coding

- Suppress the use of frequently repeated codes in one data as much as possible
  - Example : Repeated data is expressed as one value and the number of repetitions of that value
    - Data to compress → (730000000)
    - Data after compression → (730n7)
  - Since '0' is repeated 7 times in the above sequence, it is indicated by 'O', a flag (n) that can indicate the number of repetitions, and the number of repetitions '7'
  - 9 bytes of data can be compressed into 5 bytes of data
<br />
- Videos such as cartoons and graphics are compressed with good compression ratios

<br />
### Huffman coding

- A technique that uses codes of different lengths depending on the frequency of characters appearing in the data
- Variable length coding method is widely used in video coding
  - Example : If there is a string 'AABBAC'
    - The frequency of each letter is A 3 times, B 2 times, and C 1 time
    - If you assign '0' to A, '10' to B, and '11' to C,
    - The above string is 'A(0)A(0)B(10)B(10)A(0)C(11)', so it can be expressed as '001010011'
    - In the end, the string 'AABBAC', originally composed of 6 bytes (48 bits), is reduced to 9 bits, which is '001010011', and is compressed by about 20 %

<br />
### LZW coding

- Technique applying Huffman coding
- While reading the file, create a table for consecutive strings, and compress it by referring to this table the next time the same string is found
- Used in GIF or TIFF file format

<br />
## Technique using lossy compression

<br />
### Lossy compression

- If the compressed information is restored, it does not have the same content as before compression
- Irreversible compression
<br />
- Lossy compression focuses on increasing compression ratio
  - Accept information loss by deleting a lot of information to the extent that it does not significantly affect recognition of the content
  - Although the compression rate is high, image quality deteriorates and it is difficult to restore accurate images
<br />
- There are no restrictions on compression algorithms and is widely used in the multimedia field

<br />
### Lossy compression techniques

- Transformation techniques
- Forecasting techniques
- Vector quantization
- Interpolation techniques

<br />
### Conversion Technique

- A technique to reduce the number of unit information that constitutes data by moving one area of ​​data to another area through appropriate transformation
<br />
① PCM conversion
  - The most basic conversion technique
  - Technique for converting analog signals into digital signals through sampling, quantization, and encoding
② Discrete Cosine Transform (DCT)
  - DCT is a method of converting image data defined as a two-dimensional matrix from the spatial domain to the frequency domain
  - Mainly used for encoding JPEG, MPEG, H.261, etc.

<br />
### Forecasting Techniques

- A technique based on the fact that the original information can be restored by predicting the next information from previous information and correcting errors caused by the prediction using a small amount of error correction information
<br />
① DPCM (Differential PCM)
  - The simplest prediction technique used to compress data encoded through PCM
    - Predict the information to be encoded using the value of the previous information
    - Capacity can be reduced by using the difference between adjacent values, but there is a disadvantage in that efficiency decreases if the change in amplitude is large
② ADPCM (Adaptive DPCM)
  - How to solve the problems of DPCM
    - Slope overload problem : A problem that occurs when the amplitude changes significantly, i.e. due to a sudden change in slope
  - If the difference between adjacent values ​​is large, the steps for dividing the amplitude are increased, and if the difference is small, the steps for dividing the amplitude are made small
③ DM (Delta Modulation)
  - A special form of DPCM encoding
    - Encode the difference between the previous value and the current value with just 1 bit
    - Therefore, the signal value increases by one step or decreases by one step compared to the previous value
  - It is suitable for encoding signals whose values ​​do not change drastically with respect to the sampling rate because they only have a one-step difference

<br />
### Vector Quantization

- How to map a vector with multiple input values ​​into a simple vector
<br />
- Vector quantization process
  - ① The data stream is first divided into blocks called 'vectors'
  - ② Create a reference table that is a code book
    - A lookup table is a set of patterns, each consisting of v bytes
  - ③ Find patterns that match each vector in the codebook
  - ④ If a matching pattern is found, describe the vector value with the corresponding index value
<br />
- Problems with vector quantization
  - The problem of creating an optimal codebook that can make good use of the actual data frequency
  - The problem of implementing an optimal algorithm to find the most similar code pattern in the codebook
<br />
- Example of vector quantization
  - Fractal transform
<br />
- Suitable for voice encoding

<br />
### Interpolation Techniques

- Interpolation originally refers to an approximate calculation method that calculates the function value between several points based on the function value given to those points
- Interpolation Compression at the pixel level is a method of transmitting pixels sparsely and recovering the pixels between them through interpolation techniques
  - A method called color subsampling is used, and is useful in images of YUV and YIQ color models
  - For example, in a YUV image system, color subsampling can be done by skipping the U and V components by one pixel each on both the horizontal and vertical sides

<br />
## Technique using mixed compression

- Mixed compression is a method of using lossy compression and lossless compression together
- Mixed compression is often used in actual multimedia data compression
<br />
- Mixed compression stage
  - ① Data preparation step to convert analog signals into digital data
  - ② Reducing the number and size of information units that make up the prepared data using conversion techniques, etc.
  - ③ Step of organizing low and high importance information using quantization technology
  - ④ Step of using lossless compression techniques such as Huffman coding or repetition length coding
<br />
- JPEG and MPEG use mixed compression methods

<br />
## Compression of digital sound

<br />
### Overview

- Overview of digital sound compression
  - Digital sound stored on storage media has a large capacity
    - 3 minutes of music ⇒ CD quality requires approximately 30 MB or more
  - In order for such large-capacity digital sounds to be freely transmitted and received on the Internet, low-capacity, high-quality compression is required
  - Various digital sound compression formats for low-capacity, high-quality compression
    - MP3, AAC, Dolby Digital, WMA, Real Audio
<br />
- Recent trends in digital sound compression
  - Supports various compression formats
  - Supports audio streaming function
  - Anti-piracy technology
  - Music encoding tool support
  - Music DB management technology, etc.

<br />
### Types of compression codecs

- MP3
  - Abbreviation for 'MPEG-1 Audio Layer-3'
    - Meaning of 'Audio Layer-3', one of the standards for audio data in the MPEG standard
    - It is a compression method developed to increase efficiency by compressing relatively large audio signals
<br />
- Layer of MPEG Audio
  - Layer-1 : Simplest layer, suitable for general users
  - Layer-2 : Higher compression rate compared to Layer-1, used for professional audio such as broadcasting
  - Layer-3 : Sound quality no different from the original, standard for more professional audio
<br />
- AAC
  - The official name is MPEG-2 AAC (Advanced Audio Coding)
    - MPEG-2 is used in video and has excellent performance, including 4 times higher image quality and multi-language support compared to MPEG-1
  - Advantages of AAC
    - AAC data has a variable structure, so the size changes depending on the compression rate, which reduces the overall file capacity
      - MP3 structure is fixed
    - Compared to MP3, the capacity can be reduced by up to 30%
    - To improve sound quality, quantization correction technology is applied to reduce noise and make it closer to the original sound
  - Disadvantages of AAC
    - Lack of compatibility between players due to copyright copy protection system
    - It takes up to 10 times more time to encode the original sound than MP3
<br />
- Dolby Digital
  - Dolby Digital or Dolby AC-3
    - Dolby AC-3 is an abbreviation for 'Audio Coding-3', meaning it is the third digital audio coding developed by Dolby Research Institute
    - It was developed for audio compression and voice encoding used in movies, HDTV, etc., and the term is currently unified as 'Dolby Digital'
  - Dolby Digital
    - Stereoscopic sound support format with 5.1 channels (5 audio channels and 1 low-frequency effect channel) (MP3 or AAC are compression formats based on 2 channels)
    - The advantage is that compared to existing analog surround systems, each channel is completely separated, allowing clear sound to be delivered without signal interference
    - The disadvantage is that since it is used as a movie soundtrack, the sound quality is lower than that of a CD
  - Designated as an official sound source for the DVD-Video standard
<br />
- WMA (Windows Media Audio)
  - High-quality audio codec developed by Microsoft for multimedia compression
  - In terms of capacity, it is about half that of MP3, but the sound quality is the same
  - Much faster encoding time due to improved encoding algorithm
<br />
- Real Audio
  - Real Audio format : RA, RAM, RM
    - One of the streaming technologies that transmits multimedia data in real time over a network
    - Fast transfer rate and high compression rate
<br />
- Real Media format
  - A mixed format of Real Audio, which supports only audio, and Real Video, which supports only video
  - Supports both voice and video
  - Because it was developed to be able to encode at a fast speed while minimizing the server load to improve encoding speed, the sound quality is relatively poor compared to MP3, etc.

<br />
## Compression of digital images

<br />
### JPEG














<br />
### MPEG













<br />
### H.26x











<br />
<cite>Source : Department of Computer Science, Korea National Open University</cite>
