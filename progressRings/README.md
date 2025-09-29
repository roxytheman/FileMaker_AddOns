# progressRings
<img width="600" height="400" alt="preview" src="https://github.com/user-attachments/assets/00291a2c-ff0e-455d-be9a-b58eba710361" />

Display multi-ring progress indicators inspired by Apple Watch activity rings using SVG. Fully configurable via JSON and responsive across FileMaker platforms.
- Displays multiple concentric progress arcs
- Each ring individually configurable: color, value, stroke, end cap
- Supports custom padding and default fallbacks
- Responsive to Web Viewer width and height
- Zoom-compensated for consistent rendering across devices
- Optimized SVG output for FileMaker Pro, Go, and WebDirect

## progressDoughNut function

Generates a customisable, rounded progress doughnut using SVG for display in a FileMaker Web Viewer.

**Function Name** : progressDoughNut  
**Parameters** : width ; height ; defaultArray ; dataArray  
**Use example** : progressDoughNut ( 400 ; 400 ; $defaultArray ; $dataArray )  

This function creates a circular progress indicator rendered in SVG, using JSON-driven settings for colours, stroke width, font, and layout. The arc fills /based on a percentage value and features smooth, rounded ends for a polished look. Perfect for visualising completion or status inside FileMaker layouts with no HTML required.

## Default Array Example
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

## Data Array Example
```
JSONSetElement ( "" ; 

	[ "value" ; 58 ; 2 ]

)
```


### Use example in a WebViewer

```
progressRings ( 

	GetLayoutObjectAttribute ( "wv_progressDoughNut_AF34E9B6-FBE2-4046-B5D0-A77BE297C17B Copy" ; "width" ) ; 
	GetLayoutObjectAttribute ( "wv_progressDoughNut_AF34E9B6-FBE2-4046-B5D0-A77BE297C17B Copy" ; "height" ) ; 

	JSONSetElement ( "" ; 
	
		[ "color.background" ; "#FFFFFF" ; 1 ] ;
	
		[ "endCap" ; "round" ; 1 ] ; // round, butt, square - or empty	
		[ "stroke" ; 14 ; 2 ] ;
		[ "padding" ; 4 ; 2 ] 
	)

	; 

	JSONSetElement ( "" ; 

	 	[ "ring[+]value" ; 64 ; 2 ] ;
		[ "ring[:]color.foreground" ; "#DF2F5D" ; 1 ] ; 
		[ "ring[:]color.background" ; "#F9D4DF" ; 1 ] ; 
		[ "ring[:]cap" ; "round" ; 1 ] ; // round, butt, square - or empty
		[ "ring[:]stroke" ; 0 ; 6 ] ;

	 	[ "ring[+]value" ; 58 ; 2 ] ;
		[ "ring[:]color.foreground" ; "#67BD46" ; 1 ] ; 
		[ "ring[:]color.background" ; "#E2F2D9" ; 1 ] ; 
		[ "ring[:]endCap" ; "" ; 1 ] ; // round, butt, square - or empty
		[ "ring[:]stroke" ; 0 ; 6 ] ;

	 	[ "ring[+]value" ; 38 ; 2 ] ;
		[ "ring[:]color.foreground" ; "#01B1DE" ; 1 ] ; 
		[ "ring[:]color.background" ; "#D6EFF7" ; 1 ] ; 
		[ "ring[:]cap" ; "" ; 1 ] ; // round, butt, square - or empty
		[ "ring[:]stroke" ; 14 ; 6 ] 
	
	)

)
```