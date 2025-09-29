# ProgressBarStacked
Progress Bar Stacked Webwidget add-on for Claris FileMaker
<img width="600" height="400" alt="483058492-0f1b4e0a-2aa5-481e-8ff3-01ddb9f4216e" src="https://github.com/user-attachments/assets/a9c950c7-90d5-42a1-b64a-d6b7326e1c3f" />

Track multiple stages or categories in a single bar with this dynamic stacked progress component for FileMaker Pro.
- Displays multi-segment progress bars with individual colours and values
- Each segment defined via a JSON payload for maximum flexibility
- Supports rounded corners on outer segments
- Includes background fill behind partial progress bars
- Easy to update dynamically using a script or JSON expression
- Ideal for project tracking, workflows, or category-based progress


## progressBarStacked function

Creates a horizontal progress bar composed of multiple coloured segments, defined by a JSON input with individual percentage values.
NOTE : The segments are stacked, so make sure to order the array starting with the lowest percentages 

**Function Name** : progressBarStacked  
**Parameters** : width ; height ; radius ; backgroundColor ; segmentArray  
**Use example** : progressBarStacked ( 500 ; 16 ; 5 ; "#f4f4f4" ; $jsonArray )  

This function renders a horizontal, stacked-style SVG progress bar where each segmentrepresents a distinct stage or category of progress. The segments are defined via a JSON object that specifies a colour and percentage for each part. The function calculates the relative widths and assembles each segment in sequence. A background colour fills the bar behind the segments, and rounded corners are applied through SVG clipping. 

### JSON ARRAY EXAMPLE

```
JSONSetElement ( "" ; 

	[ "stack[+]color" ; "#211732" ; 1 ] ; 
	[ "stack[:]percent" ; 10 ; 2 ] ; 
	[ "stack[+]color" ; "#ad9fcd" ; 1 ] ; 
	[ "stack[:]percent" ; 20 ; 2 ] ; 
	[ "stack[+]color" ; "#7962a8" ; 1 ] ; 
	[ "stack[:]percent" ; 40 ; 2 ] ; 
	[ "stack[+]color" ; "#e8deee" ; 1 ] ; 
	[ "stack[:]percent" ; 70 ; 2 ] 

)
```

The result is Base64-encoded and suitable for use in container fields or web viewers within FileMaker solutions.