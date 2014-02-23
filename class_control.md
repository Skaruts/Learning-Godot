##  Control  
**Inherits:** [[canvasitem|CanvasItem]]\\
**Category:** Core\\
##  Brief Description  
Control is the base node for all the GUI components.
##  Member Functions 
  * void [[#_input_event|_input_event]]**(** [InputEvent](class_inputevent) event **)** virtual
  * [bool](class_bool) [[#can_drop_data|can_drop_data]]**(** [Vector2](class_vector2) pos, var data **)** virtual
  * void [[#drop_data|drop_data]]**(** [Vector2](class_vector2) pos, var data **)** virtual
  * [Object](class_object) [[#get_drag_data|get_drag_data]]**(** [Vector2](class_vector2) pos **)** virtual
  * [Vector2](class_vector2) [[#get_minimum_size|get_minimum_size]]**(****)** virtual
  * void [[#accept_event|accept_event]]**(****)**
  * [Vector2](class_vector2) [[#get_minimum_size|get_minimum_size]]**(****)** const
  * [Vector2](class_vector2) [[#get_combined_minimum_size|get_combined_minimum_size]]**(****)** const
  * [bool](class_bool) [[#is_window|is_window]]**(****)** const
  * [Object](class_object) [[#get_window|get_window]]**(****)** const
  * void [[#set_anchor|set_anchor]]**(** [int](class_int) margin, [int](class_int) anchor_mode **)**
  * [int](class_int) [[#get_anchor|get_anchor]]**(** [int](class_int) margin **)** const
  * void [[#set_margin|set_margin]]**(** [int](class_int) margin, [real](class_real) offset **)**
  * void [[#set_anchor_and_margin|set_anchor_and_margin]]**(** [int](class_int) margin, [int](class_int) anchor_mode, [real](class_real) offset **)**
  * void [[#set_begin|set_begin]]**(** [Vector2](class_vector2) pos **)**
  * void [[#set_end|set_end]]**(** [Vector2](class_vector2) pos **)**
  * void [[#set_pos|set_pos]]**(** [Vector2](class_vector2) pos **)**
  * void [[#set_size|set_size]]**(** [Vector2](class_vector2) size **)**
  * void [[#set_custom_minimum_size|set_custom_minimum_size]]**(** [Vector2](class_vector2) size **)**
  * void [[#set_global_pos|set_global_pos]]**(** [Vector2](class_vector2) pos **)**
  * [real](class_real) [[#get_margin|get_margin]]**(** [int](class_int) margin **)** const
  * [Vector2](class_vector2) [[#get_begin|get_begin]]**(****)** const
  * [Vector2](class_vector2) [[#get_end|get_end]]**(****)** const
  * [Vector2](class_vector2) [[#get_pos|get_pos]]**(****)** const
  * [Vector2](class_vector2) [[#get_size|get_size]]**(****)** const
  * [Vector2](class_vector2) [[#get_custom_minimum_size|get_custom_minimum_size]]**(****)** const
  * [Vector2](class_vector2) [[#get_parent_area_size|get_parent_area_size]]**(****)** const
  * [Vector2](class_vector2) [[#get_global_pos|get_global_pos]]**(****)** const
  * [Rect2](class_rect2) [[#get_rect|get_rect]]**(****)** const
  * [Rect2](class_rect2) [[#get_global_rect|get_global_rect]]**(****)** const
  * void [[#set_area_as_parent_rect|set_area_as_parent_rect]]**(** [int](class_int) margin=0 **)**
  * void [[#show_modal|show_modal]]**(** [bool](class_bool) exclusive=false **)**
  * void [[#set_focus_mode|set_focus_mode]]**(** [int](class_int) mode **)**
  * [bool](class_bool) [[#has_focus|has_focus]]**(****)** const
  * void [[#grab_focus|grab_focus]]**(****)**
  * void [[#release_focus|release_focus]]**(****)**
  * [Control](class_control) [[#get_focus_owner|get_focus_owner]]**(****)** const
  * void [[#set_h_size_flags|set_h_size_flags]]**(** [int](class_int) flags **)**
  * [int](class_int) [[#get_h_size_flags|get_h_size_flags]]**(****)** const
  * void [[#set_stretch_ratio|set_stretch_ratio]]**(** [real](class_real) ratio **)**
  * [real](class_real) [[#get_stretch_ratio|get_stretch_ratio]]**(****)** const
  * void [[#set_v_size_flags|set_v_size_flags]]**(** [int](class_int) flags **)**
  * [int](class_int) [[#get_v_size_flags|get_v_size_flags]]**(****)** const
  * void [[#set_theme|set_theme]]**(** [Theme](class_theme) theme **)**
  * [Theme](class_theme) [[#get_theme|get_theme]]**(****)** const
  * void [[#add_icon_override|add_icon_override]]**(** [String](class_string) name, [Texture](class_texture) texture **)**
  * void [[#add_style_override|add_style_override]]**(** [String](class_string) name, [StyleBox](class_stylebox) stylebox **)**
  * void [[#add_font_override|add_font_override]]**(** [String](class_string) name, [Font](class_font) font **)**
  * void [[#add_color_override|add_color_override]]**(** [String](class_string) name, [Color](class_color) color **)**
  * void [[#add_constant_override|add_constant_override]]**(** [String](class_string) name, [int](class_int) constant **)**
  * [Texture](class_texture) [[#get_icon|get_icon]]**(** [String](class_string) name, [String](class_string) type="" **)** const
  * [StyleBox](class_stylebox) [[#get_stylebox|get_stylebox]]**(** [String](class_string) name, [String](class_string) type="" **)** const
  * [Font](class_font) [[#get_font|get_font]]**(** [String](class_string) name, [String](class_string) type="" **)** const
  * [Color](class_color) [[#get_color|get_color]]**(** [String](class_string) name, [String](class_string) type="" **)** const
  * [int](class_int) [[#get_constant|get_constant]]**(** [String](class_string) name, [String](class_string) type="" **)** const
  * [Control](class_control) [[#get_parent_control|get_parent_control]]**(****)** const
  * void [[#set_tooltip|set_tooltip]]**(** [String](class_string) tooltip **)**
  * [String](class_string) [[#get_tooltip|get_tooltip]]**(** [Vector2](class_vector2) atpos=Vector2(0,0) **)** const
  * void [[#set_default_cursor_shape|set_default_cursor_shape]]**(** [int](class_int) shape **)**
  * [int](class_int) [[#get_default_cursor_shape|get_default_cursor_shape]]**(****)** const
  * [int](class_int) [[#get_cursor_shape|get_cursor_shape]]**(** [Vector2](class_vector2) pos=Vector2(0,0) **)** const
  * void [[#set_focus_neighbour|set_focus_neighbour]]**(** [int](class_int) margin, [NodePath](class_nodepath) neighbour **)**
  * [NodePath](class_nodepath) [[#get_focus_neighbour|get_focus_neighbour]]**(** [int](class_int) margin **)** const
  * void [[#set_ignore_mouse|set_ignore_mouse]]**(** [bool](class_bool) ignore **)**
  * [bool](class_bool) [[#is_ignoring_mouse|is_ignoring_mouse]]**(****)** const
  * void [[#force_drag|force_drag]]**(** var data, [Object](class_object) preview **)**
  * void [[#set_stop_mouse|set_stop_mouse]]**(** [bool](class_bool) stop **)**
  * [bool](class_bool) [[#is_stopping_mouse|is_stopping_mouse]]**(****)** const
  * void [[#grab_click_focus|grab_click_focus]]**(****)**
  * void [[#set_drag_preview|set_drag_preview]]**(** [Control](class_control) control **)**
##  Signals  
  * **focus_enter****(****)**
  * **mouse_enter****(****)**
  * **resized****(****)**
  * **minimum_size_changed****(****)**
  * **size_flags_changed****(****)**
  * **focus_exit****(****)**
  * **input_event****(****)**
  * **mouse_exit****(****)**
##  Numeric Constants  
  * **ANCHOR_BEGIN** = **0** - X is relative to MARGIN_LEFT,  Y is relative to MARGIN_TOP,
  * **ANCHOR_END** = **1** - X is relative to -MARGIN_RIGHT,  Y is relative to -MARGIN_BOTTOM,
  * **ANCHOR_RATIO** = **2** - X and Y are a ratio (0 to 1) relative to the parent size 0 is left/top, 1 is right/bottom.
  * **FOCUS_NONE** = **0** - Control can't acquire focus.
  * **FOCUS_CLICK** = **1** - Control can acquire focus only if clicked.
  * **FOCUS_ALL** = **2** - Control can acquire focus if clicked, or by pressing TAB/Directionals in the keyboard from another Control.
  * **NOTIFICATION_RESIZED** = **40** - Control changed size (get_size() reports the new size).
  * **NOTIFICATION_MOUSE_ENTER** = **41** - Mouse pointer entered the area of the Control.
  * **NOTIFICATION_MOUSE_EXIT** = **42** - Mouse pointer exited the area of the Control.
  * **NOTIFICATION_FOCUS_ENTER** = **43** - Control gained focus.
  * **NOTIFICATION_FOCUS_EXIT** = **44** - Control lost focus.
  * **NOTIFICATION_THEME_CHANGED** = **45** - Theme changed. Redrawing is desired.
  * **NOTIFICATION_MODAL_CLOSE** = **46** - Modal control was closed.
  * **CURSOR_ARROW** = **0**
  * **CURSOR_IBEAM** = **1**
  * **CURSOR_POINTING_HAND** = **2**
  * **CURSOR_CROSS** = **3**
  * **CURSOR_WAIT** = **4**
  * **CURSOR_BUSY** = **5**
  * **CURSOR_DRAG** = **6**
  * **CURSOR_CAN_DROP** = **7**
  * **CURSOR_FORBIDDEN** = **8**
  * **CURSOR_VSIZE** = **9**
  * **CURSOR_HSIZE** = **10**
  * **CURSOR_BDIAGSIZE** = **11**
  * **CURSOR_FDIAGSIZE** = **12**
  * **CURSOR_MOVE** = **13**
  * **CURSOR_VSPLIT** = **14**
  * **CURSOR_HSPLIT** = **15**
  * **CURSOR_HELP** = **16**
  * **SIZE_EXPAND** = **1**
  * **SIZE_FILL** = **2**
  * **SIZE_EXPAND_FILL** = **3**
##  Description  
Control is the base class Node for all the GUI components. Every GUI component inherits from it, directly or indirectly. In this way, sections of the scene tree made of contiguous control nodes, become user interfaces.
	Controls are relative to the parent position and size by using anchors and margins. This ensures that they can adapt easily in most situation to changing dialog and screen sizes. When more flexibility is desired, [[container|Container]] derived nodes can be used.
	Anchors work by defining which margin do they follow, and a value relative to it. Allowed anchoring modes are ANCHOR_BEGIN, where the margin is relative to the top or left margins of the parent (in pixels), ANCHOR_END for the right and bottom margins of the parent and ANCHOR_RATIO, which is a ratio from 0 to 1 in the parent range.
	Input device events ([[inputevent|InputEvent]]) are first sent to the root controls via the [[node#_input|Node._input]], which distribute it through the tree, then delivers them to the adequate one (under cursor or keyboard focus based) by calling [Node._input_event]. There is no need to enable input processing on controls to receive such events. To ensure that no one else will receive the event (not even [[node#_unhandled_input|Node._unhandled_input]]), the control can accept it by calling [[#accept_event|accept_event]].
	Only one control can hold the keyboard focus (receiving keyboard events), for that the control must define the focus mode with [[#set_focus_mode|set_focus_mode]]. Focus is lost when another control gains it, or the current focus owner is hidden.
	It is sometimes desired for a control to ignore mouse/pointer events. This is often the case when placing other controls on top of a button, in such cases. Calling [[#set_ignore_mouse|set_ignore_mouse]] enables this function.
	Finally, controls are skinned according to a [[theme|Theme]]. Setting a [[theme|Theme]] on a control will propagate all the skinning down the tree. Optionally, skinning can be overrided per each control by calling the add_*_override functions, or from the editor.
##  Member Function Description  
==  _input_event  ==
  * void [[#_input_event|_input_event]]**(** [InputEvent](class_inputevent) event **)** virtual
\\
Called when an input event reaches the control.
==  get_minimum_size  ==
  * [Vector2](class_vector2) [[#get_minimum_size|get_minimum_size]]**(****)** virtual
\\
Return the minimum size this Control can shrink to. A control will never be displayed or resized smaller than its minimum size.
==  accept_event  ==
  * void [[#accept_event|accept_event]]**(****)**
\\
Handles the event, no other control will receive it and it will not be sent to nodes waiting on [[node#_unhandled_input|Node._unhandled_input]] or [[node#_unhandled_key_input|Node._unhandled_key_input]].
==  get_minimum_size  ==
  * [Vector2](class_vector2) [[#get_minimum_size|get_minimum_size]]**(****)** const
\\
Return the minimum size this Control can shrink to. A control will never be displayed or resized smaller than its minimum size.
==  is_window  ==
  * [bool](class_bool) [[#is_window|is_window]]**(****)** const
\\
Return wether this control is a //window//. Controls are considered windows when their parent [[node|Node]] is not a Control.
==  get_window  ==
  * [Object](class_object) [[#get_window|get_window]]**(****)** const
\\
Return the //window// for this control, ascending the scene tree (see [[#is_window|is_window]]).
==  set_anchor  ==
  * void [[#set_anchor|set_anchor]]**(** [int](class_int) margin, [int](class_int) anchor_mode **)**
\\
Change the anchor (ANCHOR_BEGIN, ANCHOR_END, ANCHOR_RATIO) type for a margin (MARGIN_LEFT, MARGIN_TOP, MARGIN_RIGHT, MARGIN_BOTTOM). Changing the anchor mode converts the current margin offset from the previos anchor mode to the new one, so margin offsets ([[#set_margin|set_margin]]) must be done after setting anchors, or at the same time ([[#set_anchor_and_margin|set_anchor_and_margin]]).
==  get_anchor  ==
  * [int](class_int) [[#get_anchor|get_anchor]]**(** [int](class_int) margin **)** const
\\
Return the anchor type (ANCHOR_BEGIN, ANCHOR_END, ANCHOR_RATIO) for a given margin (MARGIN_LEFT, MARGIN_TOP, MARGIN_RIGHT, MARGIN_BOTTOM).
==  set_margin  ==
  * void [[#set_margin|set_margin]]**(** [int](class_int) margin, [real](class_real) offset **)**
\\
Set a margin offset. Margin can be one of (MARGIN_LEFT, MARGIN_TOP, MARGIN_RIGHT, MARGIN_BOTTOM). Offset value being set depends on the anchor mode.
==  set_anchor_and_margin  ==
  * void [[#set_anchor_and_margin|set_anchor_and_margin]]**(** [int](class_int) margin, [int](class_int) anchor_mode, [real](class_real) offset **)**
\\
Change the anchor (ANCHOR_BEGIN, ANCHOR_END, ANCHOR_RATIO) type for a margin (MARGIN_LEFT, MARGIN_TOP, MARGIN_RIGHT, MARGIN_BOTTOM), and also set its offset. This is a helper (see [[#set_anchor|set_anchor]] and [[#set_margin|set_margin]]).
==  set_begin  ==
  * void [[#set_begin|set_begin]]**(** [Vector2](class_vector2) pos **)**
\\
Sets MARGIN_LEFT and MARGIN_TOP at the same time. This is a helper (see [[#set_margin|set_margin]]).
==  set_end  ==
  * void [[#set_end|set_end]]**(** [Vector2](class_vector2) pos **)**
\\
Sets MARGIN_RIGHT and MARGIN_BOTTOM at the same time. This is a helper (see [[#set_margin|set_margin]]).
==  set_pos  ==
  * void [[#set_pos|set_pos]]**(** [Vector2](class_vector2) pos **)**
\\
Move the Control to a new position, relative to the top-left corner of the parent Control, changing all margins if needed and without changing current anchor mode. This is a helper (see [[#set_margin|set_margin]]).
==  set_size  ==
  * void [[#set_size|set_size]]**(** [Vector2](class_vector2) size **)**
\\
Changes MARGIN_RIGHT and MARGIN_BOTTOM to fit a given size. This is a helper (see [[#set_margin|set_margin]]).
==  set_global_pos  ==
  * void [[#set_global_pos|set_global_pos]]**(** [Vector2](class_vector2) pos **)**
\\
Move the Control to a new position, relative to the top-left corner of the //window// Control, and without changing current anchor mode. (see [[#set_margin|set_margin]]).
==  get_margin  ==
  * [real](class_real) [[#get_margin|get_margin]]**(** [int](class_int) margin **)** const
\\
Return a margin offset. Margin can be one of (MARGIN_LEFT, MARGIN_TOP, MARGIN_RIGHT, MARGIN_BOTTOM). Offset value being returned depends on the anchor mode.
==  get_end  ==
  * [Vector2](class_vector2) [[#get_end|get_end]]**(****)** const
\\
Returns MARGIN_LEFT and MARGIN_TOP at the same time. This is a helper (see [[#set_margin|set_margin]]).
==  get_pos  ==
  * [Vector2](class_vector2) [[#get_pos|get_pos]]**(****)** const
\\
Returns the Control position, relative to the top-left corner of the parent Control and independly of the anchor mode.
==  get_size  ==
  * [Vector2](class_vector2) [[#get_size|get_size]]**(****)** const
\\
Returns the size of the Control, computed from all margins, however the size returned will **never be smaller than the minimum size reported by [[#get_minimum_size|get_minimum_size]]**. This means that even if end position of the Control rectangle is smaller than the begin position, the Control will still display and interact correctly. (see description, [[#get_minimum_size|get_minimum_size]], [[#set_margin|set_margin]], [[#set_anchor|set_anchor]]).
==  get_global_pos  ==
  * [Vector2](class_vector2) [[#get_global_pos|get_global_pos]]**(****)** const
\\
Returns the Control position, relative to the top-left corner of the parent Control and independent of the anchor mode.
==  get_rect  ==
  * [Rect2](class_rect2) [[#get_rect|get_rect]]**(****)** const
\\
Return position and size of the Control, relative to the top-left corner of the parent Control. This is a helper (see [[#get_pos|get_pos]],[[#get_size|get_size]]).
==  get_global_rect  ==
  * [Rect2](class_rect2) [[#get_global_rect|get_global_rect]]**(****)** const
\\
Return position and size of the Control, relative to the top-left corner of the //window// Control. This is a helper (see [[#get_global_pos|get_global_pos]],[[#get_size|get_size]]).
==  set_area_as_parent_rect  ==
  * void [[#set_area_as_parent_rect|set_area_as_parent_rect]]**(** [int](class_int) margin=0 **)**
\\
Change all margins and anchors, so this Control always takes up the same area as the parent Control. This is a helper (see [[#set_anchor|set_anchor]],[[#set_margin|set_margin]]).
==  show_modal  ==
  * void [[#show_modal|show_modal]]**(** [bool](class_bool) exclusive=false **)**
\\
Display a Control as modal. Control must be a subwindow (see [[#set_as_subwindow|set_as_subwindow]]). Modal controls capture the input signals until closed or the area outside them is accessed. When a modal control loses focus, or the ESC key is pressed, they automatically hide. Modal controls are used extensively for popup dialogs and menus.
==  set_focus_mode  ==
  * void [[#set_focus_mode|set_focus_mode]]**(** [int](class_int) mode **)**
\\
Set the focus access mode for the control (FOCUS_NONE, FOCUS_CLICK, FOCUS_ALL). Only one Control can be focused at the same time, and it will receive keyboard signals.
==  has_focus  ==
  * [bool](class_bool) [[#has_focus|has_focus]]**(****)** const
\\
Return wether the Control is the current focused control (see [[#set_focus_mode|set_focus_mode]]).
==  grab_focus  ==
  * void [[#grab_focus|grab_focus]]**(****)**
\\
Steal the focus from another control and become the focused control (see [[#set_focus_mode|set_focus_mode]]).
==  release_focus  ==
  * void [[#release_focus|release_focus]]**(****)**
\\
Give up the focus, no other control will be able to receive keyboard input.
==  get_focus_owner  ==
  * [Control](class_control) [[#get_focus_owner|get_focus_owner]]**(****)** const
\\
Return which control is owning the keyboard focus, or null if no one.
==  set_h_size_flags  ==
  * void [[#set_h_size_flags|set_h_size_flags]]**(** [int](class_int) flags **)**
\\
Hint for containers, set horizontal positioning flags.
==  get_h_size_flags  ==
  * [int](class_int) [[#get_h_size_flags|get_h_size_flags]]**(****)** const
\\
Hint for containers, return horizontal positioning flags.
==  set_stretch_ratio  ==
  * void [[#set_stretch_ratio|set_stretch_ratio]]**(** [real](class_real) ratio **)**
\\
Hint for containers, set the stretch ratio. This value is relative to other stretch ratio, so if this control has 2 and another has 1, this one will be twice as big.
==  get_stretch_ratio  ==
  * [real](class_real) [[#get_stretch_ratio|get_stretch_ratio]]**(****)** const
\\
Hint for containers, return the stretch ratio. This value is relative to other stretch ratio, so if this control has 2 and another has 1, this one will be twice as big.
==  set_v_size_flags  ==
  * void [[#set_v_size_flags|set_v_size_flags]]**(** [int](class_int) flags **)**
\\
Hint for containers, set vertical positioning flags.
==  get_v_size_flags  ==
  * [int](class_int) [[#get_v_size_flags|get_v_size_flags]]**(****)** const
\\
Hint for containers, return vertical positioning flags.
==  set_theme  ==
  * void [[#set_theme|set_theme]]**(** [Theme](class_theme) theme **)**
\\
Override whole the [[theme|Theme]] for this Control and all its children controls.
==  get_theme  ==
  * [Theme](class_theme) [[#get_theme|get_theme]]**(****)** const
\\
Return a [[theme|Theme]] override, if one exists (see [[#set_theme|set_theme]]).
==  add_icon_override  ==
  * void [[#add_icon_override|add_icon_override]]**(** [String](class_string) name, [Texture](class_texture) texture **)**
\\
Override a single icon ([[texture|Texture]]) in the theme of this Control. If texture is empty, override is cleared.
==  add_style_override  ==
  * void [[#add_style_override|add_style_override]]**(** [String](class_string) name, [StyleBox](class_stylebox) stylebox **)**
\\
Override a single stylebox ([Stylebox]) in the theme of this Control. If stylebox is empty, override is cleared.
==  add_font_override  ==
  * void [[#add_font_override|add_font_override]]**(** [String](class_string) name, [Font](class_font) font **)**
\\
Override a single font (font) in the theme of this Control. If font is empty, override is cleared.
==  add_constant_override  ==
  * void [[#add_constant_override|add_constant_override]]**(** [String](class_string) name, [int](class_int) constant **)**
\\
Override a single constant (integer) in the theme of this Control. If constant equals Theme.INVALID_CONSTANT, override is cleared.
==  set_tooltip  ==
  * void [[#set_tooltip|set_tooltip]]**(** [String](class_string) tooltip **)**
\\
Set a tooltip, which will appear when the cursor is resting over this control.
==  get_tooltip  ==
  * [String](class_string) [[#get_tooltip|get_tooltip]]**(** [Vector2](class_vector2) atpos=Vector2(0,0) **)** const
\\
Return the tooltip, which will appear when the cursor is resting over this control.
==  set_default_cursor_shape  ==
  * void [[#set_default_cursor_shape|set_default_cursor_shape]]**(** [int](class_int) shape **)**
\\
Set the default cursor shape for this control. See enum CURSOR_* for the list of shapes.
==  get_default_cursor_shape  ==
  * [int](class_int) [[#get_default_cursor_shape|get_default_cursor_shape]]**(****)** const
\\
Return the default cursor shape for this control. See enum CURSOR_* for the list of shapes.
==  get_cursor_shape  ==
  * [int](class_int) [[#get_cursor_shape|get_cursor_shape]]**(** [Vector2](class_vector2) pos=Vector2(0,0) **)** const
\\
Return the cursor shape at a certain position in the control.
==  set_focus_neighbour  ==
  * void [[#set_focus_neighbour|set_focus_neighbour]]**(** [int](class_int) margin, [NodePath](class_nodepath) neighbour **)**
\\
Force a neighbour for moving the input focus to. When pressing TAB or directional/joypad directions focus is moved to the next control in that direction. However, the neighbour to move to can be forced with this function.
==  get_focus_neighbour  ==
  * [NodePath](class_nodepath) [[#get_focus_neighbour|get_focus_neighbour]]**(** [int](class_int) margin **)** const
\\
Return the forced neighbour for moving the input focus to. When pressing TAB or directional/joypad directions focus is moved to the next control in that direction. However, the neighbour to move to can be forced with this function.
==  set_ignore_mouse  ==
  * void [[#set_ignore_mouse|set_ignore_mouse]]**(** [bool](class_bool) ignore **)**
\\
Ignore mouse events on this control (even touchpad events send mouse events).
==  is_ignoring_mouse  ==
  * [bool](class_bool) [[#is_ignoring_mouse|is_ignoring_mouse]]**(****)** const
\\
Return if the control is ignoring mouse events (even touchpad events send mouse events).