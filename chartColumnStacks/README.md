# chartColumnStacks
WebWidget add-on for Claris FileMaker displaying column chart using SVG.
<img width="600" height="400" alt="483049816-9fe0c9ce-d2ac-47df-b092-c3b1d161d9bc" src="https://github.com/user-attachments/assets/bea0f6e3-0a8a-407f-80be-596fe001af91" />

Render multi-column vertical bar widgets using this scalable and customisable SVG add-on for FileMaker Pro.
- Stacked vertical columns defined by value within a range
- Customise stroke width, alignment, cap style and color via JSON
- Dynamic scaling using SVG — no plug-ins or images required
- Perfect for visualising grouped values and progress distribution
- Responsive to Web Viewer width and height

## chartColumnStacks function
Draws stacked vertical columns based on range and value input using SVG.  Customisable with JSON for appearance, padding, stroke, and alignment.

**Function Name** : chartColumnStacks  
**Parameters** : width ; height ; defaultArray ; dataArray  
**Use example** : chartColumnStacks ( 400 ; 400 ; $defaultArray ; $dataArray )  

Column Stacks Chart is a stacked column chart widget for FileMaker layouts, styled and rendered using scalable SVG. Each column can define its own height, stroke, color, and cap style, while shared defaults like padding, stroke width, and background fill are set centrally. Columns align left, center, or right based on layout needs. Perfect for visualising multi-part progress or distribution metrics. Optimised for FileMaker Pro, Go, and WebDirect.

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