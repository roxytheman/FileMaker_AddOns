# progressDoughNut
WebWidget add-on for FileMaker displaying progress doughnut using SVG.
<img width="600" height="400" alt="483075863-a46363cb-b234-467a-9244-67b5a1dacef5" src="https://github.com/user-attachments/assets/cf668e43-9ed3-4421-90af-d5394921a8af" />

Render smooth, rounded progress doughnuts using this scalable and fully customisable SVG add-on for FileMaker Pro.
- Rounded doughnut-style progress arc with centre label
- Customise colours, font, arc thickness and background via JSON
- Dynamically update based on a FileMaker script and payload
- Rendered entirely with SVG — no HTML or plug-ins needed
- Responsive to Web Viewer width and height
- Perfect for visualising percentages, progress, or completion states


## progressDoughNut function

Generates a customisable, rounded progress doughnut using SVG for display in a FileMaker Web Viewer.

**Function Name** : progressDoughNut  
**Parameters** : width ; height ; defaultArray ; dataArray  
**Use example** : progressDoughNut ( 400 ; 400 ; $defaultArray ; $dataArray )  

This function creates a circular progress indicator rendered in SVG, using JSON-driven settings for colours, stroke width, font, and layout. The arc fills /based on a percentage value and features smooth, rounded ends for a polished look. Perfect for visualising completion or status inside FileMaker layouts with no HTML required.

### Default Array Example
```
JSONSetElement ( "" ; 

	[ "color.background" ; "#CCCCCC" ; 1 ] ;
	[ "color.foreground" ; "#CB4400" ; 1 ] ;
	[ "color.text" ; "#000000" ; 1 ] ;
	[ "color.complete" ; "green" ; 1 ] ;

	[ "stroke" ; 20 ; 2 ] ;
	[ "endCap" ; "" ; 1 ] ; // round, butt, square - or empty

	[ "font.size" ; 24 ; 2 ] ;
	[ "font.weight" ; "bold" ; 1 ] ;
	[ "font.name" ; "Helvetica Neue" ; 1 ] ;

	[ "background.fill" ; "#FFFFFF" ; 1 ] ;
	[ "displayValue" ; True ; 5 ] ;
	[ "text.complete" ; "Done" ; 1 ]

)
```

### Data Array Example

```
JSONSetElement ( "" ; 

	[ "value" ; 58 ; 2 ]

)
```