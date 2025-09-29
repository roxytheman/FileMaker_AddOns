# ColorisWidget
Coloris colour picker Webwidget add-on for Claris FileMaker
<img width="600" height="400" alt="483048965-9aee44ad-bfbc-4389-8003-bea89d3cdabb" src="https://github.com/user-attachments/assets/5696abea-9a9f-42d2-9a0c-75c66fbcd655" />

This FileMaker add-on integrates the Coloris.js color picker into a WebViewer, allowing users to select colors with a smooth interface and customizable swatches.
- colorpicker

## coloris button object

**Target**: Variable

```
Let ( [

		~target = Evaluate ( Substitute ( "$$COLORIS_3652F7EF-9ED6-40C7-9FFC-1D91BB50B9F6" ; "-" ; "" ) ) ; // or GetField ( "myTable::myField" )
		~colour = color_convert_hex ( If ( IsEmpty ( ~target ) ; "#000000" ; ~target ) ; "rgb" ) ;
		~iconChar = Char ( 9673 ) ;
		~iconSize = 28

	] ;

		TextColor ( TextSize ( ~iconChar ; ~iconSize ) ; RGB ( GetValue ( ~colour ; 1 ) ; GetValue ( ~colour ; 2 ) ; GetValue ( ~colour ; 3 ) ) )

)
```

**Target**: Field
```
Let ( [

		~target = GetField ( "myTable::myField" ) ; // when target is a field reference
		~colour = color_convert_hex ( If ( IsEmpty ( ~target ) ; "#000000" ; ~target ) ; "rgb" )
		~iconChar = Char ( 9673 ) ;
		~iconSize = 28

	] ;

		TextColor ( TextSize ( ~iconChar ; ~iconSize ) ; RGB ( GetValue ( ~colour ; 1 ) ; GetValue ( ~colour ; 2 ) ; GetValue ( ~colour ; 3 ) ) )

)

```

## coloris colourPicker webviewer object

## coloris function

```
Let ( [

	~var = Evaluate ( Substitute ( "$$COLORIS_3652F7EF-9ED6-40C7-9FFC-1D91BB50B9F6" ; "-" ; "" ) ) ; // or GetField ( "myTable::myField" )
	~default = If ( IsEmpty ( ~var ) ; "#000000" ; ~var ) ;
	~tints = While ( [ 
			
					~tintBase = ~default ; 
					~count = 6 ;
					~factor = 20 ;
					~result = "" ;
					~i = 1 
			
				] ; 
			
					~i ≤ ~count
			
				; [ 
			
					~factor = ~factor * ~i ;
					~result = List ( ~result ; "'" & ColorTint ( ~tintBase ; ~factor ; "hex" ) & "'," ) ;
					~i = ~i + 1
			
				] ; 
			
					Substitute ( ~result ; "¶" ; "" )
			
			)

] ; 

coloris ( 

	~default // default colour when widget is opened
	
	 ; 
	
	"'#923296','#F0419F','#D82E42','#F08128','#F9C933','#68BE48', 
	" & ~tints & " 
	'#FFFFFF','#CCCCCC','#999999','#666666','#333333','#000000'" // 3 rows of preset colour swatches in widget
	
	; 
	
	"setColorisColor" // target script to send selected colour to
	
	)

)


/*

~var : grabs default colour or currently selected colour from a variable, this can be changed to a field reference if preferred
~default : safeguards empty or faulty values and returns a black default colour
~tins : calculates 6 swatches of currently selected colour and populates the 2nd row of presets in widget with these

Left ( ~var ; 1 ) = "?"

*/
```