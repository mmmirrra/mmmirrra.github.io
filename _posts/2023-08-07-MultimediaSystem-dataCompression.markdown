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

- Repeat Length Coding
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
  - ① The data stream is first divided into blocks called 'Vectors'
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
    - Compared to MP3, the capacity can be reduced by up to 30 %
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
### JPEG (Joint Photographic Experts Group)

#### Overview

- As the name of the organization, it is used as a compression standard for color still images
- Established under ISO / TC97 / SC2 / WG8
- Standards that form the basis of MPEG
- Used in storage systems such as digital electronic still cameras and image databases, transmission systems such as still image transmission devices and video conferencing, and printing systems such as color printers

#### JPEG Algorithm

- Mixed compression method using lossy compression and lossless compression
<br />
- lossy compression
  - Compression using DCT transform and quantization
  - Practical decoding image quality can be obtained even at high compression rates
  - Divided into basic and extended methods
    - Basic method (Lossy sequential DCT-based mode)
      - Basic essential functions in the JPEG system
      - A method of encoding each element of the image according to the order in which it is scanned
    - Expanded lossy DCT-based mode
      - Method of encoding an image into multiple scans
<br />
- Lossless compression
  - Perform lossless compression using a prediction method
    - Entropy coding is performed using Huffman coding or arithmetic coding
    - Compared to DCT conversion, the compression rate is lower, but the advantage is that there is no deterioration in image quality
<br />
- Mixed compression
  - Uses a hierarchical approach
    - Encode video in multiple resolutions so that video can be played or output in various environments
    - Encoding is performed repeatedly while gradually increasing the resolution of the video
    - Encoding at each stage uses either lossy compression or lossless compression

#### JPEG algorithm process

① Image segmentation process
② DCT conversion process
③ Quantization process
④ Entropy encoding process
<br />
- JPEG compression process
  - [ Original video (8 × 8 pixel block) ] → [ DCT ] → [ Quantization (Quantization table) ] → [ Encoder (Huffman Table) ] → [ Compressed video ]

#### ① Image segmentation process

- Image segmentation is achieved by color model conversion and blocking
<br />
- Color model conversion
  - Convert RGB model to YIQ color model
  - Because human vision is more sensitive to brightness than color
<br />
- Blockification
  - To compress the entire video by blocking it into 8 x 8 blocks, divide each component for Y, I, and Q into 8 x 8 blocks

#### ② DCT conversion process

- Perform DCT operation on blocks divided by blockification
  - After DCT conversion, 64 DCT coefficients are obtained (8 × 8 blocks)
  - Among these, the first value obtained is the DC (Direct Current) component, and the remaining 63 are AC (Alternating Current) components.

#### ③ Quantization process

- Quantization is performed on the DC and AC components obtained during the DCT conversion process
  - Quantization is the process of rounding DCT coefficients to integers within a range that is imperceptible to humans.
  - In the quantization process, each DCT coefficient is divided using a predefined quantization table, and the result is rounded and calculated

#### ④ Entropy encoding process

- As a lossless compression process, the quantized DCT coefficients are further compressed according to spatial characteristics
- The encoding process scans the quantized DCT coefficients in a zigzag pattern and encodes them from low to high frequencies
- The encoding method mainly uses Huffman coding
  - Huffman coding is a method of reducing the total length by assigning short-length codes to frequently appearing values ​​and long-length codes to infrequently appearing values

<br />
### MPEG (Moving Picture Experts Group)

#### Overview

- Compression standards for video
- A group of video experts responsible for developing standards for multimedia such as video and audio established under ISO / IEC

#### MPEG standard

- ① MPEG-1
  - The first video and audio standard to include the MP3 audio compression format
- ② MPEG-2
  - Standards for Television Broadcasting
- ③ MPEG-3
  - It was originally designed for HDTV broadcasting, but was discontinued when content was incorporated into MPEG-2
- ④ MPEG-4
  - A standard that extends MPEG-2 and was developed for use in multimedia communications
- ⑤ MPEG-7
  - A formal system for describing multimedia content
- ⑥ MPEG-21
  - Described as a 'multimedia framework' as a future standard

#### MPEG algorithm

- Development of the JPEG algorithm and H.261 compression algorithm
  - JPEG performs frame-by-frame compression of video, while MPEG compresses video using the correlation between frames
- MPEG is an algorithm that compresses using prediction and interpolation techniques by taking advantage of the high correlation between adjacent frames
  - However, since random access must be possible, frames that can be restored with only the information contained in the current frame must be inserted regularly
- Therefore, the types of frames inserted are
  - I frame : Compressed frame
  - P frame : Frame for prediction only
  - B frame : Frame for interpolation
<br />
- Frames of MPEG video
  - GOP (Group Of Picture)
    - A set of frames between one I frame and the next I frame
  - GOP structure of video
    - [] ... [P][B][I][B][B][P][B][B][P][B][B][P][B][B][I] → t
      - [I] ~ [I] ⇔ GOP
<br />
- Frames of MPEG video
  - I Frame (Intra-coded Frame)
    - It is an independent image and can be placed anywhere in the video data
    - Frames essential for random access to video
    - It is compressed by itself without reference to other frames
    - Has the lowest compression rate among other frames
  - P Frame (Predictive-coded Frame)
    - Use previous I frame or P frame information when compressing
    - Compresses only the difference by taking advantage of the small difference between the previous frame and the current frame
  - B Frame (Bidirectional-coded Frame)
    - When compressing, use information on previous and subsequent I frame or P frame
    - Has the best compression ratio
<br />
- Coding of MPEG video
  - [I] [B] [B] [P] [B] [B] [B] [P]
    - Size of compressed frame : I > P > B frame
  - I frame
    - It is placed periodically and serves as a starting point for random access and error recovery
  - P frame
    - Encodes the difference from the predicted signal estimated from the previous I or P frame
  - B frame
    - Encode the difference from the prediction signal estimated from I or P frames located before and after the screen
<br />
- Decryption of MPEG video
  - Because B frames are used, the order of MPEG data streams may differ from the actual decoding order
  - That is, the P frame to be output after the related B frame is needed when restoring the B frame, so the P frame must be restored first
  - Decryption example
    - Frame order before compression
   
      |Type of frame|B|B|I|B|B|P|B|B|P|B|B|P|
      |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
      |Frame number|0|1|2|3|4|5|6|7|8|9|10|11|
   
    - Frame order when restoring   
   
      |Type of frame|I|B|B|P|B|B|P|B|B|P|B|B|
      |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
      |Frame number|2|0|1|5|3|4|8|6|7|11|9|10|
   
  - In the example above, the I frame with frame number 2 is decoded first, and then the B frames with frame numbers 0 and 1 are decoded using the information of that I frame. In order to decode B frames 3 and 4, I frames 2 and P frames 5 are required, so P frame 5 is decoded before decoding frames 3 and 4. Decode up to B frame 10 in the same way.

#### ① MPEG-1

- With the advent of audio and video, data compression is required for storage or transmission on storage media, and standards are needed for national compatibility
- Standardized in WC11 of ISO / IEC / JTC1 (Joint Technical Committee 1)
- Combination of JPEG standard and H.261 (Established by ITU) standard
- Established standards for storing and playing video and stereo music on CD-ROM
- The transmission speed is 1.5 Mbps per second, which is insufficient to transmit video quality sufficiently

#### Characteristics of MPEG-1

- Use of ME (Motion Estimation) and MC (Motion Compensation) to reduce temporal redundancy
- Use frequency transform (DCT) that uses spatial redundancy information
- Differential coding (DPCM) used on neighboring data of the same type
- Use variable-length encoding that considers the statistical frequency of occurrence of transmitted data

#### ② MPEG-2

- Established to improve the problem that 1.5Mbps, the highest transmission speed of MPEG-1, is difficult to provide sufficient video quality
- A standard for obtaining better picture quality at a higher transmission rate than MPEG-1
- Requirements for DTV and HDTV broadcasting have been added

#### Characteristics of MPEG-2

- Process each screen on a frame-by-frame or field-by-field basis
- Image processing of progressive scanning and interlaced scanning
- Hierarchical method that allows efficient processing when the screen size or frame ratio is different

#### ④ MPEG-4

- MPEG-3 for HDTV existed before MPEG-4
  - However, HDTV can be accommodated only with MPEG-1 and MPEG-2
  - Decision to use MPEG-1 for HDTV in the US and Europe
  - So MPEG-3 was deprecated and MPEG-4 appeared
- Developed to provide digital AV (Audio / Video) to transmission channels with small transmission frequency bandwidth
  - Development of an encoding method with a very low transmission rate of less than 64 Kbps
  - A content-based encoding method was used as the encoding method
<br />
- Types of encoding methods
  - Content-based coding method
    - Encoding method based on understanding the content of the video : MPEG-4
    - Applicable to all video applications from ultra-low-speed transmission to ultra-high-speed transmission
  - Object-based encoding method
    - A method of analyzing video signals to recognize objects included in the screen by separating them from the background, then compressing and transmitting each object
  - Model-based coding method
    - A method of defining a model for an object and then encoding and restoring the object using the model information through an encoder and decoder
  - Segmentation-based coding method
    - A method of separating the border and interior of the screen, somewhat sacrificing the texture of flat parts, and clearly encoding the outline of the object
  - Fractal encoding method
    - A method of expressing multiple units through geometric transformation by utilizing the characteristic that the similarity between units is large when an image is divided into small units
  - etc.

#### Characteristics of MPEG-4

- Supports flexible encoding tools that can support both existing methods and new functions
- High compression rate and various connections possible
- Provides flexibility and scalability for related technologies
- A two-way service that provides the necessary information at the desired time according to the recipient's needs and choices

<br />
### H.26x

- Video-related standard line established by ITU-T (International Telecommunication Union Telecommunication Sector)
  - H.261, H.262, H.263, H.264 / AVC, etc.

#### H.261

- TV video compression standard for TV calls and conferences
- Supports high compression ratio and real-time compression for low-speed video phones or video conferences
- A prediction technique between images is used to remove temporal redundancy, and a DCT conversion technique is used to remove spatial redundancy (Same as MPEG method)
- Intra frame and inter frame methods are used for compression
  - Intra frame method
    - Input frame is encoded independently from other frames
      - Similar to MPEG's I frame
  - Inter frame method
    - Based on a prediction technique, using the difference between the previous frame and the current frame
      - Similar to MPEG's P frame

#### H.262

- Standardized jointly with MPEG 
- Same standard as MPEG-2

#### H.263

- Developed for low bit rate communication for video conferencing and video calling
- Improved compression performance based on H.261

#### H.264 / AVC (Advanced Video Coding)

- Standard for digital video codecs with very high compression ratios
- ITU-T and MPEG jointly formed JVT (Joint Video Team) to proceed with standardization
  - H.264 / AVC and MPEG-4 / AVC (or MPEG-4 Part 10) are the same standard
- Compared to H.263 and MPEG-4, it was developed to achieve similar or better image quality with a compression rate of less than half the bit rate

<br />
<cite>Source : Department of Computer Science, Korea National Open University</cite>
