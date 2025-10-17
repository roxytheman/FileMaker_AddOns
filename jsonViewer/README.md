# JSONViewer
<img width="600" height="400" alt="preview" src="https://github.com/user-attachments/assets/fe92fd56-79f3-4502-bee6-9db0cd9b16ae" />

JSON Viewing WebWidget add-on for Claris FileMaker.
A self-contained web component Add-On for FileMaker that displays structured JSON data. Expand objects individually or all at once by holding the Option key. Supports light and dark mode, custom background colors, and adjustable font size in points. Compatible with FileMaker 22+.
- Display and explore JSON arrays and objects
- Expand individual or all objects by holding the Option key
- Supports light and dark mode with customisable background color
- Adjustable font size in points
- Self-contained and easy to integrate web component

## loadJSONViewer

Loads JSON Viewing tool into a webviewer object. Pass the JSON array in a variable or text field. Set optional background colour to match UI.  
**Note: REQUIRES FILEMAKER 22+**

### Script parameter array example

```
JSONSetElement ( "" ; 

	[ "jsonPayload" ; $myJSONArray ; 0 ] ; // JSON array to display in viewer, can also be a field or global variable
	[ "fontSize" ; 10 ; 2 ] ; // font size in pt
	[ "darkMode" ; False ; 5 ] ; // True/False toggle between dark and light mode
	[ "target" ; "jsonViewer_964A92EE-845A-4F8F-A519-622CEAA19552" ; 1 ] ; // name of target webViewer on layout
	[ "backgroundColor" ; "#D9D9D9" ; 1 ] // optional override

)
```
