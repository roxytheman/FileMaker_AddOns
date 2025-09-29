# ProgressBarSingle
Progress Bar Single Webwidget add-on for Claris FileMaker
<img width="600" height="400" alt="483065028-d132cdf3-f626-4b4d-9fc9-9bc02bdf3673" src="https://github.com/user-attachments/assets/949135fd-e0ec-4984-ad1a-2bc9b28926b1" />

Easily visualise progress or status with this sleek and customisable single-fill progress bar for FileMaker Pro.
- Displays percentage-based progress with rounded corners
- Fully customisable colours, dimensions, and corner radius
- Accepts dynamic input to update progress via simple payload
- Base64-encoded SVG for fast Web Viewer rendering or conversion
- Easy integration with accompanying FileMaker script
- Ideal for visualising status, progress, or completion indicators in FileMaker solutions

## progressBarSingle Function

Generates a horizontal progress bar based on a single percentage value, using two custom colours to indicate completed and remaining progress.

**Function Name** : progressBarSingle  
**Parameters** : width ; height ; radius ; colorBackground ; colorFilled ; pctFilled  
**Use example** : progressBarSingle ( 400 ; 16 ; 5 ; "#FFFFFF" ; "#CDCDCD" ; 70 )  

This function produces a horizontal SVG-based progress bar that visually represents a percentage complete value between 0 and 100. The bar is rendered with two colours: one for the completed portion and another for the remaining segment. Rounded corners are applied, and the bar scales responsively to the size of the layout object if configured accordingly. 

The output is Base64-encoded and intended for use in web viewers or for conversion into a PNG graphic.

### WebViewer function example

```
progressBarSingle ( 

	GetLayoutObjectAttribute ( "wv_progressBarSingle_5DED0789-927F-4441-8A76-853B2341038B" ; "width" ) ; // Width
	GetLayoutObjectAttribute ( "wv_progressBarSingle_5DED0789-927F-4441-8A76-853B2341038B" ; "height" ) ; // Height
	0 ; // Radius
	"#e8deee" ; // Background colour
	"#7962a8" ; // Fill colour
	60 // Filled percentage

)
```