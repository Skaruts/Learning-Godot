##  AcceptDialog  
**Inherits:** [[windowdialog|WindowDialog]]\\
**Category:** Core\\
##  Brief Description  
Base dialog for user notification.
##  Member Functions 
  * [Object](class_object) [[#get_ok|get_ok]]**(****)**
  * [Object](class_object) [[#get_label|get_label]]**(****)**
  * void [[#set_hide_on_ok|set_hide_on_ok]]**(** [bool](class_bool) enabled **)**
  * [bool](class_bool) [[#get_hide_on_ok|get_hide_on_ok]]**(****)** const
  * [Button](class_button) [[#add_button|add_button]]**(** [String](class_string) text="" **)**
  * [Button](class_button) [[#add_cancel|add_cancel]]**(** [String](class_string) name **)**
  * void [[#register_text_enter|register_text_enter]]**(** [Object](class_object) line_edit **)**
  * void [[#set_text|set_text]]**(** [String](class_string) text **)**
  * [String](class_string) [[#get_text|get_text]]**(****)** const
##  Signals  
  * **confirmed****(****)**
  * **custom_action****(** [String](class_string) action **)**
##  Description  
This dialog is useful for small notifications to the user about an
	event. It can only be accepted or closed, with the same result.
##  Member Function Description  
==  get_ok  ==
  * [Object](class_object) [[#get_ok|get_ok]]**(****)**
\\
Return the OK Button.
==  get_label  ==
  * [Object](class_object) [[#get_label|get_label]]**(****)**
\\
Return the label used for built-in text.
==  set_hide_on_ok  ==
  * void [[#set_hide_on_ok|set_hide_on_ok]]**(** [bool](class_bool) enabled **)**
\\
Set whether the dialog is hidden when accepted
			(default true).
==  get_hide_on_ok  ==
  * [bool](class_bool) [[#get_hide_on_ok|get_hide_on_ok]]**(****)** const
\\
Return true if the dialog will be hidden when
			accepted (default true).
==  register_text_enter  ==
  * void [[#register_text_enter|register_text_enter]]**(** [Object](class_object) line_edit **)**
\\
Register a [[lineedit|LineEdit]] in the dialog. When the enter
			key is pressed, the dialog will be accepted.
==  set_text  ==
  * void [[#set_text|set_text]]**(** [String](class_string) text **)**
\\
Set the built-in label text.
==  get_text  ==
  * [String](class_string) [[#get_text|get_text]]**(****)** const
\\
Return the built-in label text.