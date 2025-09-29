# notification-3
In-layout slide in notification widget

<img width="600" height="400" alt="preview" src="https://github.com/user-attachments/assets/212fe280-d253-44a1-aceb-1bddcb3b229a" />


Add a clean slide-in notification panel to FileMaker layouts. This widget smoothly slides in from the right and displays color-coded alerts (Grey, Green, Orange, Red) with dynamic updates.
- Slide-in notification panel that animates from the right
- Three severity levels: 0 = Grey, 1 = Green, 2 = Orange, 3 = Red
- Customisable text, colors, and auto-dismiss timing
- Trigger updates dynamically via FileMaker scripts
- Lightweight, responsive, and easy to integrate
- Ideal for alerts, reminders, or status messages

## displayNotificationWidget Script

### Script parameter payload example
```
JSONSetElement ( "" ; 

	[ "notification.title" ; "Greetings!" ; 1 ] ;
	[ "notification.message" ; installer::d_addOnName_T & " " & JSONGetElement ( $$TRANSLATIONS ; installer::d_language_T & ".installed" ) & ¶ & JSONGetElement ( $$TRANSLATIONS ; installer::d_language_T & ".restart" ) ; 1 ] ;
	[ "notification.type" ; 0 ; 2 ] ; // 0 : Green | 1 : Orange | 2 : Red
	[ "notification.autoDismissTime" ; 5 ; 2 ] ; // Number of seconds until dismiss
	[ "notification.autoDismiss" ; True ; 5 ] // Dismiss after x seconds

)
```
