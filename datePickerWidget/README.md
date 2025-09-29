# datePicker
DatePicker Webwidget add-on for Claris FileMaker

<img width="600" height="400" alt="483047784-52a432eb-a31e-4fde-91a8-13568453d481" src="https://github.com/user-attachments/assets/06538612-65a4-4afd-9b9e-5ee03e081ee9" />

Effortlessly select single dates or date ranges with this customizable calendar widget designed for FileMaker Pro.
- Single and range date selection modes
- Fully customizable colors, fonts, and scale from FileMaker
- Preselect default dates and highlight the range immediately
- Seamless integration with FileMaker scripts using JavaScript
- Works in FileMaker Pro and WebDirect environments
- Ideal for date filtering, scheduling, and data entry in FileMaker solutions

## datePicker function

Select single dates or date ranges with this customizable calendar widget

**Function Name** : datePicker  
**Parameters** : fileMakerScript ; dateStart ; dateEnd ; isDateRange ; blockedDates ; isBlockedMode ; allowBlockedInRange ; targetDateStart ; targetDateEnd ; colourBackground ; colourSelected ; colourRange ; colourDates ; colourAdjacentDates ; colourWeekdays ; colourBlocked ; fontDates ; fontWeek ; scaleFactor  
**Use example** : see below  


### singleDate mode

```
Let ( [

		~value = Evaluate ( Substitute ( "$$START_" & "E6CB7642-8A48-4600-8922-FCECD4ACA074" ; [ "-" ; "" ] ) ) // substitute with field reference when applicable
	] ;

		If ( IsEmpty ( ~value ) ; "Set Dates" ; GetAsDate ( ~value ) )

)
```



### dateRange mode

```
Let ( [

		~start = Evaluate ( Substitute ( "$$START_" & "E6CB7642-8A48-4600-8922-FCECD4ACA074" ; [ "-" ; "" ] ) ) ; // substitute with field reference when applicable
		~end = Evaluate ( Substitute ( "$$END_" & "E6CB7642-8A48-4600-8922-FCECD4ACA074" ; [ "-" ; "" ] ) ) // substitute with field reference when applicable
	] ;

		If ( IsEmpty ( ~start ) ; "Set Dates" ; GetAsDate ( ~start ) & " - " & GetAsDate ( ~end ) )

)
```

**fileMakerScript** : Name of FileMaker script to launch upon selecting date(s) ( CAL_responseHandler )  
**dateStart** : Initialising start date  
**dateEnd** : Initialising end date (optional when calendar is in range mode)  
**isDateRange** : Boolean ( true or false ) passed as string  
**blockedDates** : Array of dates passed as [ "YYYY-MM-DD", "YYYY-MM-DD", "YYYY-MM-DD", "YYYY-MM-DD" ]  
**isBlockedMode** : Boolean ( true or false ) passed as string  
**allowBlockedInRange** : Boolean ( true or false ) passed as string  
**targetDateStart** : Field name in given in current context ( myTable::dateStart )  
**targetDateEnd** : Field name in given in current context ( myTable::dateEnd )  
**colourBackground** : Hexadecimal colour code ( #FFFFFF )  
**colourSelected** : Hexadecimal colour code ( #000000 )  
**colourRange** : Hexadecimal colour code ( #e6e6e6 )  
**colourDates** : Hexadecimal colour code ( #000000 )  
**colourAdjacentDates** : Hexadecimal colour code ( #CCCCCC )  
**colourWeekdays** : Hexadecimal colour code ( #000000 )  
**colourBlocked** : Hexadecimal colour code ( #FF6666 )  
**fontDates** : Fonts used to display dates in calendar ( \"Helvetica Neue\", sans-serif )  
**fontWeek** : Fonts used to display dates in calendar ( \"Helvetica Neue Bold\", sans-serif )  
**scaleFactor** : Factor used to scale the calendar widget ( 1.0 )

### Example of function called in a webviewer

```
datePicker ( 

	"CAL_responseHandler"	 ;							// fileMakerScript : Name of FileMaker script to launch upon selecting date(s) ( CAL_responseHandler )
	$$START_E6CB7642_8A48_4600_8922_FCECD4ACA074 ;		// dateStart : Initialising start date. Can be blank, fixed date or a field reference.
	"" ;												// dateEnd : Initialising end date (optional when calendar is in rangeDate mode). Can be blank, fixed date or a field reference.
	"false" ;											// isDateRange : False is singleDate mode. True is rangeDate mode. Boolean ( true or false ) passed as string
	"" ;												// blockedDates : passed as "[ '2025-03-04', '2025-03-05', '2025-03-06', '2025-03-07' ]"
	"true" ;											// isBlockedMode : True will block given blockedDates. False will block all dates except given blockedDates
	"false" ;											// allowBlockedInRange : Allows blocked dates to be inside a selection in rangeDate mode, but not start or end date.
	"$$START_E6CB7642-8A48-4600-8922-FCECD4ACA074" ;	// targetDateStart : Target field or var name in given in current context ( myTable::dateStart / $$START)
	"" ;												// targetDateEnd : Target field or var name in given in current context ( Optional : only needed in dateRange mode ) ( myTable::dateEnd / $$END )
	"#ffffff" ;											// colourBackground : Hexadecimal colour code ( Default : #FFFFFF )
	"#000000" ;											// colourSelected : Hexadecimal colour code ( Default : #000000 )
	"#cccccc" ;											// colourRange : Hexadecimal colour code ( Default : #e6e6e6 )
	"#666666" ;											// colourDates : Hexadecimal colour code ( Default : #000000 )
	"#cccccc" ;											// colourAdjacentDates : Hexadecimal colour code ( Default : #CCCCCC )
	"#666666" ;											// colourWeekdays : Hexadecimal colour code ( Default : #000000 )
	"#e3390a" ;											// colourBlocked : Hexadecimal colour code ( Default : #e3390a )
	"\"Helvetica Neue\", sans-serif" ;					// fontDates : Fonts used to display dates in calendar ( Default : \"Helvetica Neue\", sans-serif )
	"\"Helvetica Neue Bold\", sans-serif" ;				// fontWeek : Fonts used to display dates in calendar ( Default : \"Helvetica Neue Bold\", sans-serif )
	"0.9"												// scaleFactor : Factor used to scale the calendar widget ( Default : 1.0 )
														// Keys with default value options can be left blank ( "" ).
)
```