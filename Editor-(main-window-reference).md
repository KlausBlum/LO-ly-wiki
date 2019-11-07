# Editor (main window reference)

### Text editor

The white editor pane at the top offers a simple text editor. 

When editing an existing snippet, you will find its actual LilyPond code here. 
When creating a new snippet, the editor will contain some default code from the [template](https://github.com/openlilylib/LO-ly/wiki/Editor-(main-window-reference)#template) you've chosen. 

<a href="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Editor-Window-02-1.gif"><img class="aligncenter wp-image-4674 size-medium" src="http://lilypondblog.org/wp-content/uploads/2017/03/OLy-Editor-Window-02-1-300x276.gif" width="300" height="276" /></a>

Below the editor pane there are two buttons that support the use of an external code editor (see [Easier editing](https://github.com/openlilylib/LO-ly/wiki/Introduction#easier-editing)):

* ### Open as temp. file in Ext. Editor
saves the current code into a temporary file which is then opened in the external editor.

* ### Import from temp. file
re-imports the contents of the same file back into OLy's editor.

### Default Code
This checkbox shows if the editor still shows the unchanged default code from the selected template. The mark is removed once you apply any change to the code. 
When clicking on the checkbox, you will be asked if you want to reset your code to the template's default code. Be careful: If you confirm now, your changes will be lost. 

### Template
This dropdown box lets you choose a template on which your snippet will be based. 

Changing the template will complete the editor with the default code from the new template (only if you haven't yet applied changes in the editor pane). 

(See [Templates](https://github.com/openlilylib/LO-ly/wiki/Introduction#templates) for more information OLy's template-based concept.)

### Edit
Clicking this button opens a simple text editor that lets you modify the selected template or create a new one. Attention: Changes will affect every document on your system that uses this template, so be careful! 

* ### Line Width
* ### Staff Size
* ### Custom 1
* ### Custom 2
These four fields provide access to certain sections of the actual template. 
(See [Templates](https://github.com/openlilylib/LO-ly/wiki/Introduction#templates) for more information OLy's template-based concept.)

The "**Default**" checkboxes below will get unmarked once you apply changes to those fields. Clicking on them brings back the default contents.

## "Anchor" and "Wrap" options
(only for Writer documents)

Here you can pre-configure how LibreOffice / OpenOffice will treat the resulting image inside your text document. These options are the same as those you can apply to existing images inside the text.

## Buttons at the bottom
### < (left arrow)
### > (right arrow)
When LilyPond reported errors during compilation, they are displayed at the bottom of the editor window. The blinking cursor will be placed at the location where LilyPond has found an error. 

Use the left / right arrow buttons here to switch to the previous / next error.

### Ly Output
Every time LilyPond is called, its command line output will be stored in a file. This button opens a dialogue that display the output from the last time LilyPond has been called. 
### Config
This button opens the [Configuration dialogue](https://github.com/openlilylib/LO-ly/wiki/Config#configuration-dialogue). 
### LilyPond
This button calls LilyPond to render the contents of the editor window into musical notation. If an image file has been created, it will be inserted into the document. 

If LilyPond has reported errors or warnings, the editor will remain visible and LilyPond's messages will be displayed. As long as there are no messages from LilyPond, the editor window will disappear. In your office document, you should now see the musical snippet you've just created.

