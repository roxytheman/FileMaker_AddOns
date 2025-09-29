# codeMirror
WebWidget add-on for Claris FileMaker for codeMirror embedding.
<img width="600" height="400" alt="preview" src="https://github.com/user-attachments/assets/a8548a57-dd76-4ff6-8b65-db3549e3fb96" />

A split-pane, syntax-aware code editor for FileMaker, built with CodeMirror. Provides real-time function previews like a modern, non-modal Data Viewer when deployed on FM Server.
- Real-time function evaluation in a split view
- Syntax highlighting and auto-complete for FileMaker expressions
- Responsive and resizable code editor interface
- Built using the CodeMirror library for modern editing features
- Ideal for testing calculations and debugging in place

## codeMirrorSetCode script

Launches a single pane code mirror editor in a webviewer object. When deployed on server you can split the panes in two segments and have the server perform FileMaker functions and return the results to the second pane.
The second pane can also be used to render and edit different code by applying the same calls as pane one is targeted with. **Note**: This is a beta add-on. Features and functions may change.

### Script parameter array example

```
JSONSetElement ( "" ;

    [ "windowMode" ; JSONGetElement ( $$CODEMIRROR ; "target.code" ) ; 2 ] ;
    [ "code1" ; Evaluate ( JSONGetElement ( $$CODEMIRROR ; "target.name" ) ) ; 1 ] ;
    [ "code2" ; "" ; 6 ] ;
    [ "fontFamily" ; If ( Left ( JSONGetElement ( $$CODEMIRROR ; "codeMirror.font" ) ; 1 ) = "?" ; "Courier" ; JSONGetElement ( $$CODEMIRROR ; "codeMirror.font" ) ) ; 1 ] ;
    [ "fontSize" ; If ( Left ( JSONGetElement ( $$CODEMIRROR ; "codeMirror.fontSize" ) ; 1 ) = "?" ; 12 ; JSONGetElement ( $$CODEMIRROR ; "codeMirror.fontSize" ) ) ; 2 ]

)
```