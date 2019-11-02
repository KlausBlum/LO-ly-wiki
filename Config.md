This page is heavily under construction!  ;-)

# Configuration dialogue

This dialogue window offers the settings to customize OLy to your needs.

## Appearance

### Language file

The language of the user interface can be changed by selecting a language file in the <em>Config</em> dialog.

<a href="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-Language01.gif"><img src="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-Language01-300x297.gif" alt="OLy02-Language01" class="aligncenter size-medium wp-image-4790" width="300" height="297"></a>

At the moment, English, French and German are available, and we have a partial translation into Spanish. OLy will offer you all files that it can find in the [language file path](https://github.com/openlilylib/LO-ly/wiki/Config/_edit#language-file-path) (its location can be found below in the <em>Config</em> dialog). Those language files contain all the strings that OLy needs for dialogs and messages.

In case you think that your native language is missing here, and you feel like contributing some work, you can translate one of [those files](https://github.com/openlilylib/LO-ly/tree/master/extension/Language) into your language. They contain some helpful comments (that don't need to be translated), so you will easily find your way.
If you are interested in doing such a work, you can contact me via <a href="http://lilypond.1069038.n5.nabble.com/user/SendEmail.jtp?type=user&amp;user=4585">lilypond.1069038.n5.nabble.com/user/SendEmail.jtp?type=user&amp;user=4585</a> or open an [issue](https://github.com/openlilylib/LO-ly/issues) here on GitHub.

### Editor font name & size

Here you can specify what font will be used in the editor pane of OLy's main window. Unfortunately, LibreOffice does not offer a dialogue to comfortably choose fonts. However, you can use the dropdown box in LibreOffice Writer to choose a font and copy-paste its name here. 

## Paths, executables etc.

### Include statement(s)

Despite being designed for "small" snippets that don't exceed one page, OLy can be used for demanding tasks.

Using <a href="http://lilypond.org/doc/v2.19/Documentation/notation/including-lilypond-files.de.html">include files</a> helps keeping your main LilyPond file clear and comprehensible. If you have definitions for functions or variables that you use in multiple LilyPond documents, it's always a good option to have them in a separate include file. For example, <em><a href="https://github.com/openlilylib">openLilyLib</a></em> entirely relies on include files.

When including a file that is <em>not</em> located in the same folder as the main <code>.ly</code> file (or in one of LilyPond's default folders), its path must be specified. Apart from providing the absolute path in every include statement, there is a more elegant solution: LilyPond allows to specify a list of folders where it looks for include files. IDEs like Frescobaldi make use of that option.

In the OLy Config dialog, you can specify a string containing one or more of such paths. That string may contain one or multiple include statements as described in the <a href="http://lilypond.org/doc/v2.18/Documentation/usage/command_002dline-usage#basic-command-line-options-for-lilypond">LilyPond usage manual</a>: <code>-I"<em>path</em>"</code>

For example, if I need to specify two paths <code>C:\Users\Klaus\Documents\MyScores</code> and <code>D:\MyLibrary</code>, the resulting string reads:
<code>-I"C:/Users/Klaus/Documents/MyScores/" -I"D:/MyLibrary/</code>
(Note that LilyPond expects the paths to be written with forward slashes, even in Windows. Don't worry, if you use backward slashes, OLy will replace them for you.)

In addition, OLy will automatically look for include files in the folder where your LibreOffice document is located.

### Language File Path

The path where OLy looks for [language files](https://github.com/openlilylib/LO-ly/wiki/Config/_edit#language-file). Usually, there is no need to change the default setting. 

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