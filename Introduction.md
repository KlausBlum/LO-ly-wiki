# Introduction

<h2>Launching for the first time</h2>

Here we go: Create a new Writer document and click the OLy button. 
 
<a href="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Toolbar-01.gif"><img class="aligncenter size-full wp-image-4673" src="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Toolbar-01.gif" alt="OLy-Toolbar-01" width="181" height="118" /></a>

(Don't worry if you get two message boxes telling you that some folders ("language" and "templates") have been created. Just click "OK" to close the message boxes. Next time they won't show up again.)

Now you should see the OOoLilyPond Editor window.

First, let's open the configuration dialog by clicking the "Config" button at the bottom:

<a href="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Editor-Window-01.gif" target="_blank"><img class="aligncenter wp-image-4650 size-medium" src="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Editor-Window-01-300x233.gif" alt="OLy-Editor-Window-01" width="300" height="233" /></a>

A new window will pop up:

<a href="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Config-Window-01.gif"><img class="aligncenter size-medium wp-image-4653" src="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Config-Window-01-300x297.gif" alt="OLy-Config-Window-01" width="300" height="297" /></a>

Of course, you need to have LilyPond installed on your system. In the "LilyPond Executable" field, you need to specify the executable file for LilyPond. On startup, OLy has tried to guess its correct (default) location. If that didn't work, you will have to correct it manually.

For a Windows system, you need to know the program folder (probably <code>C:\Program Files (x86)\LilyPond</code> on 64-bit Windows or <code>C:\Program Files\LilyPond</code> on 32-bit Windows systems).
In the subfolder <code>\usr\bin</code> you will find the executable file <code>lilypond.exe</code>.

If you are working with Linux, relax and smile. Usually, you simply need to specify <code>lilypond</code> as command, without any path settings. As far as I know, that also applies for the Mac OS family which is based on Unix as well.

On the left side, there are two frames titled "Insert Images". Depending on the Office version you are using (OpenOffice or LibreOffice), you should click the appropriate options.

For the moment, all remaining settings can be left at their default values. In case you've messed up anything, there's also a "Reset to Default" button.

At the right bottom, click "OK" to apply the settings and close the dialog. 

(If this results in an error message "LilyPond cannot be executed", you should re-open the Config dialog by clicking the "Config" button again and make sure that "LilyPond Executable" provides the correct command.)

<h2>How to work with OLy</h2>

Now you are back in the main Editor window. It contains some sample code, so just click the "LilyPond" button at the bottom right.

In the background, LilyPond is now translating the code into a <code>*.png</code> graphic file which will be inserted into Writer. The code itself is invisibly saved inside the document.

After a few seconds, the editor window should disappear, and a newly created image should show up.

If you want to modify an existing OLy object, click on it to select it in Writer. Then, hit the "OLy" button.

<a href="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Editor-Window-02-1.gif"><img class="aligncenter wp-image-4674 size-medium" src="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Editor-Window-02-1-300x276.gif" width="300" height="276" /></a>

The Editor window will show the code as it has been entered before. Here you can modify it, e.g. change some pitches (there's also no need to keep the comments) and click the "LilyPond" button again. OLy will generate a new image and replace the old one.

To insert a new OLy object, just make sure that no existing object is selected when hitting the "OLy" button.
<h2>Templates</h2>
In the Editor window, you might have noticed that you were not presented an entire LilyPond file, but only an excerpt of it. This is because OLy always works with a template. It allows you to quickly enter short snippets while not having to care about any other settings for layout etc.

The snippet you just created is based on the template <code>Default.ly</code> which looks (more or less) like this:

<pre class="lilypond"><span class="lilypond-command function">\transpose</span> <b><span class="lilypond-comment comment" style="background-color: #ffd2aa;"><u>%{OOoLilyPondCustom1%}</u></span><span style="background-color: #fff5aa;">c c</span><span style="background-color: #fff5aa;">'</span><span class="lilypond-comment comment" style="background-color: #ffd2aa;"><u>%{OOoLilyPondEnd%}</u></b>
</span><span class="lilypond-delimiter keyword">{
  </span><b><span style="background-color: #ffd2aa;"><u>%{OOoLilyPondCode%}</u></span><span style="background-color: #fff5aa;">
  \key </span><span style="background-color: #fff5aa;">e</span><span style="background-color: #fff5aa;"> \major 
  </span><span style="background-color: #fff5aa;">e</span><span style="background-color: #fff5aa;">8 </span><span style="background-color: #fff5aa;">fis gis e fis</span><span style="background-color: #fff5aa;">8 </span><span style="background-color: #fff5aa;">b</span><span style="background-color: #fff5aa;">,</span><span style="background-color: #fff5aa;">4. </span><span style="background-color: #fff5aa;">| 
  </span><span style="background-color: #fff5aa;">e</span><span style="background-color: #fff5aa;">2</span><span style="background-color: #fff5aa;">\fermata </span><span style="background-color: #fff5aa;">\bar </span><span style="background-color: #fff5aa;">"|."
  </span><span style="background-color: #ffd2aa;"><u>%{OOoLilyPondEnd%}</u>
</span></b><span class="lilypond-delimiter keyword">}

</span><span class="lilypond-keyword keyword">\include</span> <span class="lilypond-string string">"lilypond-book-preamble.ly"
</span><span class="scheme-scheme">#</span><span class="scheme-delimiter">(</span><span class="scheme-function function">set-global-staff-size</span> <b><span style="background-color: #ffd2aa;"><u>%{OOoLilyPondStaffSize%}</u></span><span style="background-color: #fff5aa;">20</span><span style="background-color: #ffd2aa;"><u>%{OOoLilyPondEnd%}</u></span></b><span class="scheme-delimiter">)

</span><span class="lilypond-keyword keyword">\paper</span> <span class="lilypond-delimiter keyword">{
  </span><span class="scheme-scheme">#</span><span class="scheme-delimiter">(</span><span class="scheme-keyword keyword">define</span> <span class="scheme-scheme">dump-extents #t</span><span class="scheme-delimiter">)
  </span><span class="lilypond-variable variable">ragged-right</span> = <span class="scheme-scheme">##t
  </span><span class="lilypond-variable variable">line-width</span> = <b><span style="background-color: #ffd2aa;"><u>%{OOoLilyPondLineWidth%}</u></span><span style="background-color: #fff5aa;">17</span><span style="background-color: #fff5aa;">\cm</span><span style="background-color: #ffd2aa;"><u>%{OOoLilyPondEnd%}</u>
</span></b><span class="lilypond-delimiter keyword">}

</span><span class="lilypond-keyword keyword">\layout</span> <span class="lilypond-delimiter keyword">{
  </span><span class="lilypond-variable variable">indent</span> = <span class="scheme-scheme">#</span><span class="scheme-number value">0
  </span><span class="lilypond-keyword keyword">\context</span> <span class="lilypond-delimiter keyword">{
    </span><span class="lilypond-context">\Score
    </span><span class="lilypond-keyword keyword">\remove</span> <span class="lilypond-string string">"Bar_number_engraver"
  </span><span class="lilypond-delimiter keyword">}
}
</span></pre>

In the Editor window, there are five text fields: the big "Code" area on top, and four additional small fields named "Line Width", "Staff Size", "Custom 1" and "Custom 2". They contain the template parts that are enclosed by <em>tags</em>, i.e. preceeded by <code>%{OOoLilyPond<strong>Code</strong>%}</code>, <code>%{OOoLilyPond<strong>LineWidth</strong>%}</code>, <code>%{OOoLilyPond<strong>StaffSize</strong>%}</code>, <code>%{OOoLilyPond<strong>Custom1</strong>%}</code> and <code>%{OOoLilyPond<strong>Custom2</strong>%}</code> respectively, each terminated by <code>%{OOoLilyPond<strong>End</strong>%}</code>. (Those tags themselves are ignored by LilyPond because they are comments.)

All remaining parts of the template stay "invisible" to the user and cannot be changed. Don't worry, you can modify existing templates and create your own.

A template must at least have a <em>Code</em> section, other sections are optional. There is a template <code>Direct to LilyPond</code> which only consists of a <em>Code</em> section and contains no "invisible" parts at all. You can use it to paste ordinary <code>*.ly</code> files into your document. But please keep in mind that the resulting graphic should be smaller than your paper size.

Most templates (the ones without <em>[SVG]</em> inside the file name) make use of <code>\include "lilypond-book-preamble.ly</code> which results in a cropped image. Any whitespace around the music is automatically removed.

Below the code view, there is a dropdown field that lets you choose which template to use. Of course, different templates have different default code in their <em>Code</em> sections.

When switching the template, the code field always will update to the corresponding default code as long as you haven't made any edits yet. However, this will not happen automatically if you already made any changes. To have your current code replaced anyway, click the "Default Code" checkbox.

The "Edit" button will open a new dialog where you can edit the current template. Optionally, you can save it under a new file name.

## Easier editing

Probably you are used to a particular text editor when working on LilyPond files. Of course you can use it for OLy templates as well. The path to the template files can be found (and changed) in the configuration dialog. Here you can also specify where your text editor's executable file is located. You can use any text editor like Mousepad, Notepad etc., but if you don't yet know <a href="http://frescobaldi.org/">Frescobaldi</a>, you really should give it a try.

Back in the main OLy window, another button might be useful: "Open as temp. file in Ext. Editor". It saves the <em>entire</em> snippet into a <code>*.ly</code> file - not only the contents of the "Code" field, but including the other fields and the "invisible" parts between them. This file is opened in the external editor you've specified before. If you use an IDE like Frescobaldi, you can instantly preview your changes.

As soon as editing is finished, save your changes (without changing the file name). You can now close your external editor.

Back in OLy, hit the "Import from temp. file" button to load the updated file back into OLy. In the text fields you will recognize the changes you have applied. Hit the "LilyPond" button to insert the graphic into your document.

A word of caution: Only changes to the <em>Code,</em> <em>Line Width</em>, <em>Staff Size</em>, <em>Custom 1</em> and <em>Custom 2</em> fields are recognized. Changes to the "invisible" parts of the template are ignored! If you intend to modify those sections as well, you need to create a new template.

A very last word of caution: If you use a template that is modified or created by yourself, and you share your Office document with other collaborators, you have to share your template as well.

## Graphic file formats
By default, OLy is pre-configured to produce PNG images, but there are more options for file formats. The basic difference between them is explained here: 

[File formats: bitmap vs. vector](https://github.com/openlilylib/LO-ly/wiki/File-formats:-bitmap-vs.-vector#file-formats-bitmap-vs-vector)
