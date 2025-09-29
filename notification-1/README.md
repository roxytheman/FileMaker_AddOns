# notification-1
In-layout slide in notification widget

<img width="600" height="400" alt="492757282-3ec4bca4-2cd7-4208-bad8-7cc5567f00d4" src="https://github.com/user-attachments/assets/4754cca0-2848-4cb0-b004-01c01021db66" />

Add a clean slide-in notification panel to FileMaker layouts. This widget smoothly slides in from the right and displays color-coded alerts (Green, Orange, Red) with dynamic updates.
- Slide-in notification panel that animates from the right
- Three severity levels: 0 = Green, 1 = Orange, 2 = Red
- Customisable text, colors, and auto-dismiss timing
- Trigger updates dynamically via FileMaker scripts
- Lightweight, responsive, and easy to integrate
- Ideal for alerts, reminders, or status messages

## displayNotificationWidget Script

### Script parameter payload example
```
JSONSetElement ( "" ; 

	[ "notification.message" ; installer::d_addOnName_T & " " & JSONGetElement ( $$TRANSLATIONS ; installer::d_language_T & ".installed" ) & ¶ & JSONGetElement ( $$TRANSLATIONS ; installer::d_language_T & ".restart" ) ; 1 ] ;
	[ "notification.type" ; 0 ; 2 ] ; // 0 : Green | 1 : Orange | 2 : Red
	[ "notification.autoDismissTime" ; 5 ; 2 ] ; // Number of seconds until dismiss
	[ "notification.autoDismiss" ; True ; 5 ] // Dismiss after x seconds

)
```