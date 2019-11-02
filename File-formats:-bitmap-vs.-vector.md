# File formats: bitmap vs. vector

PNG files are easy to handle, but being a bitmap format, they don't offer the best image quality:

<a href="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-png150-e1491491286329.gif"><img src="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-png150-e1491491286329-300x254.gif" alt="OLy02 - png150" class="aligncenter size-medium wp-image-4732" width="300" height="254"></a>

Bitmap images have a certain resolution given in dpi (dots per inch). The above picture is an excerpt of a 150dpi <code>.png</code> file that shows a simple <code>{bes'4}</code> at a staff size of 20 (LilyPond's default value).
When magnified like this, the quality drawbacks are obvious.

In its <em>config</em> dialog, OLy lets you specify a resolution for <code>.png</code> files.
Increasing the image resolution will also increase its quality. By default, a value of 300dpi is used, which will make the same excerpt look like this:

<a href="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-png300.gif"><img src="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-png300-300x241.gif" alt="OLy02 - png300" class="aligncenter size-medium wp-image-4733" width="300" height="241"></a>

Modern printers have a resolution of at least 600dpi. Therefore, this would be the minimal value to get usable print results:

<a href="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-png600.gif"><img src="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-png600-300x244.gif" alt="OLy02 - png600" class="aligncenter size-medium wp-image-4734" width="300" height="244"></a>

But still you can see that it is a rastered image. The transitions from black to white look somewhat blurred.
Better quality can be achieved with vector file formats. They use polygons and curves to describe the outline of every object contained in the file. Therefore they provide perfectly sharp edges at any level of magnification:

<a href="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-svg-e1491491229526.gif"><img src="http://lilypondblog.org/wp-content/uploads/2017/04/OLy02-svg-e1491491229526-300x241.gif" alt="OLy02 - svg" class="aligncenter size-medium wp-image-4735" width="300" height="241"></a>

To keep up with that high quality, one would have to further increase png resolution, which, however, would make the file size explode. The tiny examples above had 2248 bytes (150dpi), 4395 bytes (300dpi) and 9076 bytes (600dpi) as their file sizes, whereas the <code>.svg</code> version had 3568 bytes: Only the worst of the above <code>.png</code> files was smaller.

LilyPond can produce various vector file formats: Apart from <code>.pdf</code>, certainly its most important format, also <code>.ps</code>, <code>.eps</code> and <code>.svg</code> are available. However, LibreOffice cannot handle all of them:

<code>.eps</code> images can only be used in OpenOffice, with the further limitation that they are not visible on screen and in pdf output (at least, for Windows there's a workaround). In LibreOffice, they cannot be used at all.
Neither LibreOffice nor OpenOffice can import <code>.ps</code> files.

As a more interesting alternative, there are <code>.svg</code> files which are easily mastered by LibreOffice (not by OpenOffice - another reason to switch to LO). However, using this format with OLy requires two additional actions: Installing some fonts and preparing special templates. This task is explained on a dedicated page: [SVG requirements](https://github.com/openlilylib/LO-ly/wiki/SVG-requirements#svg-requirements).

<code>.pdf</code> images can be imported into LibreOffice, but currently (November 2019) they are hereby converted to bitmap previews - with the quality drawbacks explained above. Now OLy supports calling an external converter to transform LilyPond's <code>.pdf</code> output into an <code>.svg</code> file. The latter can be imported into LibreOffice without further restrictions. If you don't mind installing such a third-party converter, this might be the preferred option. 