<!-- default file list -->
*Files to look at*:

* [CustomRichEditCommands.cs](./CS/WindowsFormsApplication1/CustomRichEditCommands.cs) (VB: [CustomRichEditCommands.vb](./VB/WindowsFormsApplication1/CustomRichEditCommands.vb))
* [Form1.cs](./CS/WindowsFormsApplication1/Form1.cs) (VB: [Form1.vb](./VB/WindowsFormsApplication1/Form1.vb))
* [RichEditControlExtensions.cs](./CS/WindowsFormsApplication1/RichEditControlExtensions.cs) (VB: [RichEditControlExtensions.vb](./VB/WindowsFormsApplication1/RichEditControlExtensions.vb))
<!-- default file list end -->
# How to automatically determine a document format based on document content 


<p>When a document is loaded into the RuchEditControl, we analyze a file extension to determine a document format.<br>In some scenarios, a file extension cannot match the real document content (an RTF file was saved with the .DOCX extension, etc.).<br>This example demonstrates how to determine a document format based on the document content.</p>


<h3>Description</h3>

<p>The basic functionality for auto-determining a loaded document format is implemented in the&nbsp;<strong>LoadDocumentEx</strong>&nbsp;extension method. To use this method in an application,&nbsp;include&nbsp;the&nbsp;<strong>RichEditControlExtensions.cs&nbsp;</strong>(<strong>RichEditControlExtensions.vb</strong>)&nbsp;file into your project and import the&nbsp;<strong>RichEditControlExtensions&nbsp;</strong>namespace:</p>
<code lang="cs">using RichEditControlExtensions;
................................
richEditControl1.LoadDocumentEx("testDocument.txt");</code>
<code lang="vb">Imports RichEditControlExtensions
.................................
richEditControl1.LoadDocumentEx("testDocument.txt")</code>
<p>In addition, a predefined&nbsp;<strong>LoadDocumentCommand</strong>&nbsp;command was overridden in a custom&nbsp;<strong>RichEditCommandFactoryService&nbsp;</strong>to execute this extension method by default when an end-user clicks the "Open" button.<br>To&nbsp;build this functionality into an existing project,&nbsp;include&nbsp;the&nbsp;<strong>CustomRichEditCommands.cs</strong>&nbsp;(<strong>CustomRichEditCommands.vb</strong>) file into the project, import the&nbsp;<strong>RichEditControlExtensions&nbsp;</strong>namespace, and execute the&nbsp;<strong>RegisterCusomOpenFileCommand</strong>&nbsp;extension method:</p>
<code lang="cs">richEditControl1.RegisterCusomOpenFileCommand();</code>
<code lang="vb">richEditControl1.RegisterCusomOpenFileCommand()</code>
<br><br><br>

<br/>


