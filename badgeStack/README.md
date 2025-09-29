# badgeStack
WebWidget add-on for FileMaker displaying progress doughnut using SVG.
<img width="600" height="400" alt="483030771-f439ad88-a364-46f6-ac3c-0b7c6db14560" src="https://github.com/user-attachments/assets/f0ea0cb2-49bb-41de-80c9-f311fa311c87" />

Easily display stacked circular badges with this fully customisable SVG badge viewer for FileMaker Pro.
- Overlapping circular badges with leftmost badge on top
- Customise colours, borders, radius, spacing, and font via JSON
- Update badges dynamically with a FileMaker script and payload
- Rendered entirely with SVG — no HTML required
- Top-aligned layout that auto-sizes to Web Viewer height
- Perfect for displaying assignees, tags, avatars or status indicators


## badgeStack function
The function is called in a FileMaker Webviewer Object to generate overlapping circular badges with custom text and styles from JSON, rendered in SVG for display in a FileMaker Web Viewer.

Function Name : badgeStack

Parameters : width ; height ; defaultArray ; badgeArray

Use example : badgeStack ( 400 ; 400 ; $defaultArray ; $pillArray )

This function produces a visually stacked row of circular badges using SVG, styled and controlled entirely via JSON. Each badge supports individual text, background and font colour, and border styles, with layout dynamically handled based on Web Viewer dimensions. The leftmost badge appears on top, enabling a clean and readable stack that’s perfect for representing users, tags, roles or assignments in FileMaker layouts.

### Default Array Example

```
JSONSetElement ( "" ; 
	
		[ "radius" ; 16 ; 2 ] ;
		[ "font.size" ; 12 ; 2 ] ;
		[ "font.weight" ; "bold" ; 1 ] ;
		[ "font.name" ; "Helvetica Neue" ; 1 ] ;
		[ "spacing.overlap" ; 6 ; 2 ] ;
		[ "border.stroke" ; 2 ; 2 ] ;
		[ "border.color" ; "#FFFFFF" ; 1 ] ;
		[ "background.fill" ; "#FFFFFF" ; 1 ]
	
)
```

### Badge Array Example

```
JSONSetElement ( "" ; 
	
		[ "badge[+]text" ; "MR" ; 1 ] ;
		[ "badge[:]color.background" ; "#F4511E" ; 1 ] ;
		[ "badge[:]color.text" ; "#FFFFFF" ; 1 ] ;
	
		[ "badge[+]text" ; "J" ; 1 ] ;
		[ "badge[:]color.background" ; "#4285F4" ; 1 ] ;
		[ "badge[:]color.text" ; "#FFFFFF" ; 1 ] 
	
)
```
