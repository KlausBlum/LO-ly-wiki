This page is heavily under construction!  ;-)

# Config

This dialogue window offers the settings to customize OLy to your needs.

## Paths, executables etc.

### External PDF to SVG conversion command

(WIP)

## Format

This dropdown box lets you choose which graphic file format OLy will use to insert musical snippets into your document. 
Each format has its specific advantages and disadvantages. 
Currently, OLy supports the following formats: 

**PNG**

**+** works immediately, no further preparations required

**-**  being a bitmap format, image quality is limited. 

**EPS**

**+** good image quality (vector format)

**-**  only usable in OpenOffice (not in LibreOffice)

**-**  images are not displayed on screen (only in printout and PDF export).

**SVG**

**+** good image quality (vector format)

**+** displayed on screen (although there is a bug in LO as of version 6.2 that prevents correct preview at smaller zoom levels)

**-**  only usable in LibreOffice (not in OpenOffice)

**-**  numerous preparations required (dedicated SVG templates, further editing, installing additional fonts)

**PDF to SVG**

(PDF output from LilyPond, externally converted to SVG format for import into LibreOffice)

**+** good image quality (vector format)

**+** no dedicated templates and no additional fonts required

**-**  requires third-party conversion software

**-**  only usable in LibreOffice (not in OpenOffice)

### PNG

### EPS

### SVG

### PDF to SVG
With this option selected, OLy will call LilyPond to produce a PDF file. 
Unlike with the SVG option, this works with any template, no restrictions apply. 
Also, no additional fonts have to be installed. 

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

**For Windows**, 