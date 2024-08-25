---
layout: post
title:  "Multimedia System: Data - Image, Graphics"
date:   2023-08-05 09:00:00 +0900
categories: [Multimedia System]
---

## Image   
   
### Overview of the image   
   
- Image and Graphic   
  - Image   
    - Visual information, such as pictures, entered through devices such as scanners or digital cameras   
  - Graphic   
    - Artificial drawing created through computer software   
<br />
- Image   
  - Used interchangeably with the terms video or image.   
  - There are various ways to express images or process images.   
  - Image files come in various forms depending on the data compression method.   
   
#### Pixel (Picture Element)   
   
- Pixel is the basic unit that makes up the screen.   
  - Expressed as a pixel, it refers to each dot that appears on the screen.   
<br />
- The image is   
  - It is expressed and stored as a set of pixels.   
  - This is called the bitmap method.   
<br />
- Images expressed as bitmaps   
  - When displayed on a monitor, each pixel displays the values ​​of red, green, and blue in an appropriate combination.   
  - At this time, the type of color that each pixel can have depends on how many bits are allocated to each pixel.   
<br />
- Relationship between number of bits and color   
   
  |Number of bits|Number of colors|Note|
  |:---:|:---|:---|
  |1|2 (2<sup>1</sup>)|Gray-scale|
  |4|16 (2<sup>4</sup>)|Use Palette (Index Color)|
  |8|256 (2<sup>8</sup>)|Use Palette (Index Color)|
  |16|65,536 (2<sup>16</sup>)|High color (R : G : B = 5 : 5 : 5)|
  |24|16,777,216 (2<sup>24</sup>)|True Color (R : G : B = 8 : 8 : 8)|
  |32|16,777,216 + 8-bit alpha channel|True color + alpha channel|
   
- Alpha channel   
  - It refers to 256 levels of transparency as a channel other than RGB, and does not contain color information.   
  - Transparency 0 means 100% opaque, transparency 255 means 100% transparent.   
   
#### Resolution   
   
- A numerical expression of the clarity of the image.   
- Number of pixels or dots that can be displayed per unit length.   
- The unit is dpi (dot per inch).   
- Distinguish between device resolution and image resolution.   
  - Device resolution: Number of pixels that an output device can express in unit area   
  - Image resolution: Resolution of the image itself   
   
<br />
### Expression of images   
   
- Raster method   
  - Express images in pixels.   
  - Also called bitmap method.   
  - File size is proportional to resolution.   
  - When the screen is enlarged, the image quality deteriorates and a staircase phenomenon occurs.   
<br />
- Vector method   
  - Create and store objects in a mathematically described set form.   
  - Takes up less memory compared to the raster method.   
  - The resolution of the image is independent of the output device.   
  - Provides high-resolution display and printing functions.   
   
<br />
### Color model   
   
- A color model is a way to express color in a digital environment.   
- It refers to a color space that can define and reproduce each color on a computer.   
  - Color space: The three properties of color, hue, brightness, and saturation, are expressed as coordinates in three-dimensional space.   
- Therefore, the color model expresses color by corresponding color properties to a three-dimensional coordinate system.   
<br />
- Types of color models   
  - RGB model   
  - CMY(K) model   
  - HSV (HSB) model, HSL model, HIS model   
  - YIQ model, YUV model, YCbCr model, etc.   
<br />
- List of color coordinates   
  - Red (1, 0, 0)   
  - Green (0, 1, 0)   
  - Blue (0, 0, 1)   
  - Cyan (0, 1, 1)   
  - Magenta (1, 0, 1)   
  - Yellow (1, 1, 0)   
  - White (1, 1, 1)   
  - Black (0, 0, 0)   
   
#### RGB (Red, Green, Blue) model   
   
- A model that implements color based on the three primary colors of light, red, green, and blue, and based on the color of the monitor.   
- It is called an additive mixing method because it uses the principle that lightness increases as light is added.   
- When red, green, and blue are added - cyan, magenta, and yellow are created.   
- Mainly used in places where color is expressed through light, such as in monitors.   
   
#### CMY (Cyan, Magenta, Yellow) model   
   
- Based on cyan, magenta, and yellow.   
- It is called a subtractive mixing method because the brightness decreases as colors are mixed.   
- It is used for color printers and printing because it uses the properties of paint or ink.   
   
#### CMY(K) model   
   
- The CMYK model uses black in addition to the CMY model.   
- If all three colors of CMY are used, it becomes black, but it cannot produce ideal black, and black ink is used separately due to wastage of ink.   
   
#### Other models   
   
- HSV (HSB) model, HSL model, HSI model   
  - A color model created based on human intuitive vision.   
    - HSV (HSB) model   
      - Composed of Hue, Saturation, and Value.   
      - Also known as HSB (Hue, Saturation, Brightness).   
    - HSL model   
      - Composed of Hue, Saturation, and Lightness.   
    - HSI model   
      - A model that uses I (Intensity) instead of V (Value) in the HSV model.   
      - Mainly used in image processing field.   
<br />
- YIQ, YUV model   
  - Model suitable for TV broadcasting using lighting.   
    - YIQ model: Applied to NTSC method.   
    - YUV model: Applied to PAL method.   
<br />
- YCbCr model   
  - Model using color difference information Cb and Cr   
    - Cb: Color difference information indicating blueness.   
    - Cr: Color difference information indicating redness.   
  - Used in compression methods such as JPEG.   
   
<br />
### Image processing (Video processing)   
   
#### Concept of image processing (Video processing)   
   
- A field of study that processes pictures using computer technology   
  - Video analysis   
  - Video improvement   
  - Video synthesis and restoration   
  - Video recognition and understanding, etc.   
<br />
- Distinct from computer graphics.   
  - Computer graphics is about creating composite images.   
  - Image processing manipulates images that have already been acquired or created.   
   
#### Image processing techniques   
   
- Point processing   
  - Changes pixel values ​​based on the pixel's original value or location.   
  - Adjusting the brightness value of the image (Inverted image).   
    - In case of gray image   
      - Pixel values ​​are classified into levels from 0 to 255.   
      - To make the image brighter, adjust it closer to white 255, and to make it darker, adjust it closer to 0.   
      - In case of an inverted image, set it to '255 - pixel value'.   
  - Histogram   
    - Shows the contrast value of the image.   
      - The x-axis is the brightness of the pixel from 0 to 255.   
      - The y-axis is the frequency of the pixel.   
    - Histogram equalization   
      - Uniformly distributes brightness values ​​in the image to improve image quality.   
<br />
- Area processing   
  - Change pixel value based on pixel's original value and neighboring pixel values.   
  - Blurring   
    - Used to remove noise from video.   
    - Remove details from images using masks.   
    - The outer part of the image becomes unclear as fine information in the original image is lost.   
  - Edge detection   
    - It is a method to extract the outline of an image.   
    - Used as the first step in image segmentation.   
    - First-order differential operators and second-order differential operators are used.   
      - First-order differential operators - prewitt, sobel operators   
      - Second-order differential operator - Laplacian operator   
<br />
- Geometric processing   
  - Transforms the position or arrangement of pixels.   
<br />
- Frame processing   
  - Generates pixel values ​​based on operations on two or more images.   
   
<br />
## Graphics   
   
<br />
### Computer graphics   
   
#### Definition of computer graphics   
   
"Graphics created using a computer, or the representation and manipulation of graphic data by a computer"   
   
#### How to create computer images   
   
- 2D computer graphics (2D graphics)   
  - Manipulate images on the computer screen using a tablet pen or mouse.   
- 3D computer graphics (3D graphics)   
  - Use the screen as a window in a virtual environment and create a 3D image using a computer program.   
   
#### Computer graphics techniques   
   
- Raster graphics   
  - Originates from the raster scanning method of CRT, which displays images on a monitor one line at a time.   
  - Raster graphics video   
    - Express pixels or colors in the form of coordinates on a square grid.   
    - Resolution is expressed as the product of the number of horizontal and vertical pixels that make up the image, and color precision is determined by the number of bits required to express the color for each pixel.   
    - When enlarged, it becomes rough or blurred (aliasing phenomenon).   
  - Raster graphics are practical when dealing with photographs or near-photographic images.   
<br />
- Vector graphics   
  - Expressing objects such as points, straight lines, curves, and polygons based on mathematical equations.   
  - For example, when you want to express a straight line   
    - Raster graphics   
      - Stores information on all pixels that make up a straight line.   
    - Vector graphics   
      - Save only the start and end point information.   
      - Can be expressed with only small information.   
      - The advantage is that the image quality does not deteriorate even when enlarged.   
   
#### Computer graphics software   
   
- Special-purpose graphics package   
  - Provides functions and a convenient user interface to create pictures suitable for various application fields.   
  - High-quality output can be produced even if you are not a professional programmer.   
    - CAD package: Used for product design in various fields such as architecture, machinery, and electronic circuits.   
    - Paint package (Adobe Photoshop, etc.): Create or edit raster pictures, photos, etc.   
<br />
- Graphics Application Programming Interface (API)   
  - A graphics library that allows professional programmers to write programs using graphics functions in programming languages ​​such as C/C++ and Java.   
  - Low-level graphics API   
    - Consists of functions that instruct a series of processes to display basic graphics elements such as points, lines, and polygons that make up a picture on the computer screen.   
    - GL, OpenGL, DirectX, etc.   
  - High-level graphics API   
    - Provides a variety of models to make graphics work simpler and more efficient, and provides a way to easily configure them into new models.   
    - Open Inventor, VRML, Java 3D, etc.   
   
<br />
### 3D graphics   
   
- 2D graphics   
  - Display two-dimensional shapes on the screen.   
  - Focus on expressing the shape effectively.   
- 3D graphics   
  - Focuses on representing objects that exist or do not exist on a computer as close to reality as possible.   
  - In other words, the shape of the object is expressed three-dimensionally to make it more realistic.   
- 3D graphics creation process   
  - Modeling process   
  - Rendering process   
   
#### Modeling   
   
- Modeling refers to creating the geometric shape of an object.   
<br />
- Model   
  - All objects used to complete a scene in 3D graphics.   
- Modeling   
  - Creating the shapes of models.   
  - The process of expressing the shape of an object for modeling on a computer using a three-dimensional coordinate system.   
<br />
- Types of models for modeling   
  - Wire Frame Model   
    - A model that constructs the skeleton of an object based on points and lines.   
  - Polygon Surface Model   
    - Express objects using sides such as triangles or squares.   
  - Solid Model   
    - It is an improvement on the face-centered modeling method, and constructs the object in a form where the inside of the object is completely filled.   
   
#### Rendering   
   
- Rendering is converting a modeled object into an image that resembles its actual form.   
  - To make 3D modeled objects look realistic,   
    - A method of converting an image of an object closer to reality by removing the invisible side and adding light, dark, color, and texture to the visible side to give perspective.   
<br />
- Rendering Techniques   
  - Mapping techniques   
    - Texture processing technique using texture to increase the realism of objects   
      - Texture mapping: A method of simply applying materials such as photographs or drawings to the surface of an object   
      - Bump mapping: A method of forming bumps, such as irregularities, on the surface of an object   
      - Opacity mapping: A method of representing the transparency of an object   
      - Reflection mapping: A method of representing reflections on a surface   
  - Shading Technique   
    - A technique for coloring an object by calculating the brightness of each unit surface of the object, the brightness of the light source, the brightness of the surroundings, and the angle of the three-dimensional surface.   
      - Flat shading: The most basic technique.   
      - Gouraud shading: Softer contrast than flat shading.   
      - Phong shading: Suitable for objects with curved surfaces.   
  - Hidden line removal technique   
    - Technique to remove invisible lines from objects   
   
<br />
### File formats of images and graphics   
   
- Raster type files   
  - BMP (bitmap) file   
  - ICO file   
  - PCX file   
  - PNG file   
  - GIF file   
  - JPEG file   
  - TIFF file   
  - WebP file   
<br />
- Vector type files   
  - CGM file   
  - SVG file   
  - DXF file   
  - AI file   
  - CDR file   
<br />
- Mixed files   
  - PDF file   
  - PICT file   
  - SWF file   
  - EPS file   
  - WMF   
<br />
- Other files   
  - RAW file   
  - Exif file   
   
<br />
### Image and graphic editing software   
   
- Image editing tools   
  - Photoshop   
  - PaintShop Pro   
  - GIMP (GNU Image Manipulation Program)   
<br />
- 2D graphics editing tools   
  - Illustrator   
  - Corel Draw   
<br />
- 3D graphics software   
  - 3ds Max   
  - Maya   
   
<br />
<cite>Source: Department of Computer Science, Korea National Open University</cite>
