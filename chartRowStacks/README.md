# chartRowStacks
WebWidget add-on for Claris FileMaker displaying stacked row chart using SVG.
<img width="600" height="400" alt="preview" src="https://github.com/user-attachments/assets/cd95294f-6699-43d9-beb2-b869936f7c6d" />

Scalable horizontal progress bar widget with full JSON customization for FileMaker Pro.
- Horizontally stacked bar segments with customizable size and alignment
- Define colours, thickness, caps and padding per segment using JSON
- Uses native FileMaker calculations — no plug-ins required
- Adapts to container size and platform, including WebDirect and Go

## chartRowStacks function

Draws stacked horizontal rows based on range and value input using SVG. Customisable with JSON for appearance, padding, stroke, and alignment.

**Function Name** : chartRowStacks  
**Parameters** : width ; height ; defaultArray ; dataArray  
**Use example** : chartRowStacks ( 400 ; 400 ; $defaultArray ; $dataArray )  

Row Stacks Chart is a stacked column chart widget for FileMaker layouts, styled and rendered using scalable SVG. Each column can define its own height, stroke, color, and cap style, while shared defaults like padding, stroke width, and background fill are set centrally. Rows align left, center, or right based on layout needs. Perfect for visualising multi-part progress or distribution metrics. Optimised for FileMaker Pro, Go, and WebDirect.

### Default Array Example

```
JSONSetElement ( "" ; 

	[ "min" ; 0 ; 2 ] ;
	[ "max" ; 50 ; 2 ] ;
	[ "padding" ; 10 ; 2 ] ;
	[ "stroke" ; 20 ; 2 ] ;
	[ "endCap" ; "round" ; 1 ] ;
	[ "background.fill" ; "#FFFFFF" ; 1 ] ;
	[ "color.background" ; "#CCCCCC" ; 1 ] ;
	[ "color.foreground" ; "#CB4400" ; 1 ] ;
	[ "align" ; "center" ; 1 ]

)
```

### Data Array Example

```
JSONSetElement ( "" ; 

	[ "columns[+]value" ; 30 ; 2 ] ;
	[ "columns[:]color" ; "#F4511E" ; 1 ] ;
	[ "columns[:]stroke" ; 10 ; 2 ] ;
	[ "columns[:]cap" ; "" ; 1 ] ;

	[ "columns[+]value" ; 25 ; 2 ] ;

	[ "columns[+]value" ; 45 ; 2 ] ;
	[ "columns[:]color" ; "#F4511E" ; 1 ] ;
	[ "columns[:]cap" ; "square" ; 1 ]  ;

	[ "columns[+]value" ; 15 ; 2 ] ;
	[ "columns[:]color" ; "#F4511E" ; 1 ] ;
	[ "columns[:]stroke" ; 18 ; 2 ] ;
	[ "columns[:]cap" ; "" ; 1 ] ;

	[ "columns[+]value" ; 32 ; 2 ] ;
	[ "columns[:]color" ; "#F4511E" ; 1 ] ;

	[ "columns[+]value" ; 22 ; 2 ] ;
	[ "columns[:]color" ; "#F4511E" ; 1 ] ;
	[ "columns[:]cap" ; "" ; 1 ] 

)
```