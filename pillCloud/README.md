# pillCloud
pillCloud Webwidget add-on for Claris FileMaker

<img width="600" height="400" alt="483072166-29d0b9f3-4ec1-4a0a-b82d-b4a3b1d25a49" src="https://github.com/user-attachments/assets/640ab09c-0fa2-44e7-8121-da9e08737da5" />

Effortlessly display dynamic chips or tags with this customisable SVG-based pill cloud for FileMaker Pro.
- Responsive multi-line pill layout using SVG
- Define colours, borders, spacing, and fonts via JSON
- Easily update dynamically with a FileMaker script and payload
- Fully controlled from within FileMaker — no HTML required
- Top-aligned flow that wraps based on Web Viewer size
- Ideal for tags, statuses, filters, and visual grouping in FileMaker

## pillCloud function

Generates a responsive SVG-based group of pill-shaped chips from a JSON configuration, suitable for use in a Web Viewer.

**Function Name** : pillCloud  
**Parameters** : width ; height ; defaultArray ; pillArray  
**Use example** : progressBarSingle ( 400 ; 400 ; $defaultArray ; $pillArray )  

This function builds a dynamic, multi-line set of pill-shaped chips using SVG, based on a structured JSON payload. Each chip can display custom text and support individual background colours, borders, and font styles, while inheriting defaults for easy styling. Chips are automatically laid out horizontally and wrapped onto multiple lines based on the specified Web Viewer width and height, making this ideal for flexible tag or category displays inside FileMaker solutions.

### Default Array Example

```
JSONSetElement ( "" ; 

		[ "default.border.stroke" ; 1 ; 2 ] ;
		[ "default.color.background" ; "#FFFFFF" ; 1 ] ;
		[ "default.color.fill" ; "#FFFFFF" ; 1 ] ;
		[ "default.color.border" ; "#000000" ; 1 ] ;
		[ "default.font.name" ; "Helvetica Neue" ; 1 ] ;
		[ "default.font.size" ; 12 ; 2 ] ;
		[ "default.font.weight" ; "Regular" ; 1 ] ;
		[ "default.margin.horizontal" ; 15 ; 2 ] ;
		[ "default.margin.vertical" ; 10 ; 2 ] ;
		[ "default.spacing.horizontal" ; 7 ; 2 ] ;
		[ "default.spacing.vertical" ; 7 ; 2 ] ;
		[ "default.padding.horizontal" ; 5 ; 2 ] ;
		[ "default.padding.vertical" ; 5 ; 2 ] ;
		[ "default.radius" ; 5 ; 2 ] 

)
```

### Pill Array Example

```
JSONSetElement ( "" ; 

		[ "pill[+]border.stroke" ; 1 ; 2 ] ;
		[ "pill[:]color.border" ; "#000000" ; 1 ] ;
		[ "pill[:]color.background" ; "#FFC0CB" ; 1 ] ;
		[ "pill[:]text" ; "Strawberry" ; 1 ] ;
		[ "pill[:]font.name" ; "Comic Sans" ; 1 ] ;

		[ "pill[+]border.stroke" ; 0 ; 2 ] ;
		[ "pill[:]color.background" ; "#F5DEB3" ; 1 ] ;
		[ "pill[:]text" ; "Vanilla" ; 1 ] ;
		[ "pill[:]font.size" ; 14 ; 2 ] ;
		[ "pill[:]font.weight" ; "Bold" ; 1 ] ;

		[ "pill[+]border.stroke" ; 0 ; 2 ] ;
		[ "pill[:]color.background" ; "#3E2C23" ; 1 ] ;
		[ "pill[:]text" ; "Chocolate" ; 1 ] ;
		[ "pill[:]ont.color" ; "white" ; 1 ] 
	
)
```