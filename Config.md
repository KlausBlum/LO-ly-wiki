This page is heavily under construction!  ;-)

# Configuration dialogue

This dialogue window offers the settings to customize OLy to your needs.

## Paths, executables etc.

### External PDF to SVG conversion command

As of Version 0.5.11, OLy supports calling an external PDF-to-SVG conversion software. Its command line can be configured here. 

A detailed explanation can be found in the [PDF to SVG section](https://github.com/openlilylib/LO-ly/wiki/Config#pdf-to-svg) of this page. 

## Format

This dropdown box lets you choose which graphic file format OLy will use to insert musical snippets into your document. 
Each format has its specific advantages and disadvantages. 
Currently, OLy supports the following formats: 

**[PNG](https://github.com/openlilylib/LO-ly/wiki/Config#png)**
* `+` works immediately, no further preparations required
* `-`  being a bitmap format, image quality is limited. 

**[EPS](https://github.com/openlilylib/LO-ly/wiki/Config#eps)**
* `+` good image quality (vector format)
* `-`  only usable in OpenOffice (not in LibreOffice)
* `-`  images are not displayed on screen (only in printout).

**[SVG](https://github.com/openlilylib/LO-ly/wiki/Config#svg)**
* `+` good image quality (vector format)
* `+` displayed on screen (although there is a bug in LO as of version 6.2 that prevents correct preview at smaller zoom levels)
* `-`  only usable in LibreOffice (not in OpenOffice)
* `-`  numerous preparations required (dedicated SVG templates, further editing, installing additional fonts)

**[PDF to SVG](https://github.com/openlilylib/LO-ly/wiki/Config#pdf-to-svg)** (recommended)
* `+` good image quality (vector format)
* `+` no dedicated templates and no additional fonts required
* `-`  requires third-party conversion software
* `-`  only usable in LibreOffice (not in OpenOffice)

### PNG

This file format is used by default, because it works equally in LibreOffice and OpenOffice, on Windows, Linux or Mac. 
No additional steps have to be taken before using it. 

However, it's not the best choice with regard to image quality: [File formats - bitmap vs. vector](https://github.com/openlilylib/LO-ly/wiki/File-formats:-bitmap-vs.-vector#file-formats-bitmap-vs-vector)

### EPS
At the moment, EPS is the only vector format available for OpenOffice. LibreOffice cannot handle it. 

EPS images are printed correctly, but OpenOffice does not display them on screen. It's helpful to use PNG format at first. Once the musical snippets look as indended, they can be recompiled using the EPS format.

EPS images also are missing in PDF export. At least on Windows, there is a workaround for that: Printing the document with a "print to pdf" driver leads to correct results. 

### SVG
This file format is only supported by LibreOffice (and not by OpenOffice). 
Using it also requires two important preparations that are described in detail here: 
[SVG requirements](https://github.com/openlilylib/LO-ly/wiki/SVG-requirements#svg-requirements).

### PDF to SVG
(This feature is available as of OLy v. 0.5.11)

With this option selected, OLy will call LilyPond to produce a PDF file. 
Unlike with the SVG option, this works with any template, no restrictions apply. 
Also, no additional fonts have to be installed. _Therefore, this is the file format I'd currently recommend to choose._

However, as a second step, this PDF file has to be converted into an SVG file which then will be inserted into your LO document. 
That means, you will have to install an additional conversion software and specify the exact command line to be called. 

**For Linux and Mac**, this is easy: You can install the "pdf2svg" package via your package manager. 

The default settings for the command line to be called should already be visible. 

The resulting command line will look similar to this (replace "klaus" with your actual user name): 

`pdf2svg "/home/klaus/.cache/ooolilypond/tmp/OOoLilyPond.pdf" OOoLilyPond.svg`

The filename OOoLilyPond.pdf preceeded by the correct path (without quotation marks) will be inserted by OLy, so you have
`pdf2svg "`
(notice the quotation mark at the end) as first part and
`"`
(only the quotation mark)
as second part of the command. 

You will already find this as default settings in your config dialogue.

**For Windows**, a suitable third-party tool has to be installed at your own risk. 
At the moment, the only one I know of can be found here: 

http://blog.alivate.com.au/poppler-windows/

Direct download: http://blog.alivate.com.au/wp-content/uploads/2018/10/poppler-0.68.0_x86.7z

(While I don't know if I should recommend a software I barely know, all I can say is, I've tried it and to me it performs allright.) 

There is no installation, you just unpack its contents to a location of your choice (for example `C:\Portable\`).
In my case ("Klaus" is my user name) the resulting command line is:

`"C:\Portable\poppler-0.68.0\bin\pdftocairo.exe" -svg "C:\Users\Klaus\AppData\Local\Temp\OOoLilyPond.pdf"`

As above, OLy inserts the PDF file name including path. 
Hence the first part reads

`"C:\Portable\poppler-0.68.0\bin\pdftocairo.exe" -svg "`
(again, notice the quotation marks, eventually adapt the path to the location you've chosen above)

and the second part is just 
`"`
(only the quotation mark).

That's it. 

If you know any other tools for that conversion task, I'd be happy to mention them here. 