# chartDoughnut
WebWidget add-on for Claris FileMaker displaying doughnut chart using SVG.
<img width="600" height="400" alt="preview" src="https://github.com/user-attachments/assets/06906f64-b4d4-4ec2-a86f-351f61544855" />

Render multi-segment doughnut charts with configurable styling and data-driven arc segments using this scalable SVG add-on for FileMaker Pro.
- Display multiple segments proportionally around a circular ring
- Customise stroke, colours, radius, segment gaps and cap style via JSON
- Scales responsively based on Web Viewer dimensions
- Update dynamically via script and JSON payload
- No HTML or plugins required in FileMaker Pro or WebDirect
- Compatible with FileMaker Go using embedded HTML wrapper

## chartDoughnut function

Displays a multi-segment doughnut chart using SVG, with support for custom colours, stroke width, segment padding, and end caps.

**Function Name** : chartDoughnut  
**Parameters** : width ; height ; defaultArray ; dataArray  
**Use example** : chartDoughnut ( 400 ; 400 ; $defaultArray ; $dataArray )  

The chartDoughnut function renders a scalable, circular doughnut chart with multiple segments, each defined by value and colour. Segments are proportionally distributed across the ring based on value totals, with optional padding between slices. 

Stroke thickness, background fill, and end cap style (round, square, or butt) are fully customisable. Works seamlessly across FileMaker Pro, WebDirect, and FileMaker Go using responsive SVG.

### Default Array Example

```
JSONSetElement ( "" ; 

	[ "stroke" ; 40 ; 2 ] ;
	[ "endCap" ; "round" ; 1 ] ;
	[ "padding" ; 20 ; 2 ] ; // degrees between segments
	[ "background.fill" ; "#FFFFFF" ; 1 ] ;
	[ "color.background" ; "#FFFFFF" ; 1 ] ;
	[ "radius" ; 150 ; 2 ]

)
```

### Data Array Example

```
JSONSetElement ( "" ; 

	[ "segments[+]value" ; 30 ; 2 ] ;
	[ "segments[:]color" ; "#DF2F5D" ; 1 ] ;
	[ "segments[+]value" ; 50 ; 2 ] ;
	[ "segments[:]color" ; "#67BD46" ; 1 ] ;
	[ "segments[+]value" ; 20 ; 2 ] ;
	[ "segments[:]color" ; "#01B1DE" ; 1 ] 

)
```