##  MultiMesh  
**Inherits:** [[resource|Resource]]\\
**Category:** Core\\
##  Brief Description  
Provides high perfomance mesh instancing.
##  Member Functions 
  * void [[#set_mesh|set_mesh]]**(** [Mesh](class_mesh) mesh **)**
  * [Mesh](class_mesh) [[#get_mesh|get_mesh]]**(****)** const
  * void [[#set_instance_count|set_instance_count]]**(** [int](class_int) arg0 **)**
  * [int](class_int) [[#get_instance_count|get_instance_count]]**(****)** const
  * void [[#set_instance_transform|set_instance_transform]]**(** [int](class_int) arg0, [Transform](class_transform) arg1 **)**
  * [Transform](class_transform) [[#get_instance_transform|get_instance_transform]]**(** [int](class_int) arg0 **)** const
  * void [[#set_instance_color|set_instance_color]]**(** [int](class_int) arg0, [Color](class_color) arg1 **)**
  * [Color](class_color) [[#get_instance_color|get_instance_color]]**(** [int](class_int) arg0 **)** const
  * void [[#set_aabb|set_aabb]]**(** [AABB](class_aabb) arg0 **)**
  * [AABB](class_aabb) [[#get_aabb|get_aabb]]**(****)** const
  * void [[#generate_aabb|generate_aabb]]**(****)**
##  Description  
MultiMesh provides low level mesh instancing. If the amount of [[mesh|Mesh]] instances needed goes from hundreds to thousands (and most need to be visible at close proximity) creating such a large amount of [[meshinstance|MeshInstance]] nodes may affect performance by using too much CPU or video memory. \\
For this case a MultiMesh becomes very useful, as it can draw thousands of instances with little API overhead.\\
 As a drawback, if the instances are too far away of each other, performance may be reduced as every sigle instance will always rendered (they are spatially indexed as one, for the whole object).\\
 Since instances may have any  behavior, the AABB used for visibility must be provided by the user, or generated with [[#generate_aabb|generate_aabb]].
##  Member Function Description  
==  set_mesh  ==
  * void [[#set_mesh|set_mesh]]**(** [Mesh](class_mesh) mesh **)**
\\
Set the [[mesh|Mesh]] resource to be drawn in multiple instances.
==  get_mesh  ==
  * [Mesh](class_mesh) [[#get_mesh|get_mesh]]**(****)** const
\\
Return the [[mesh|Mesh]] resource drawn as multiple instances.
==  set_instance_count  ==
  * void [[#set_instance_count|set_instance_count]]**(** [int](class_int) arg0 **)**
\\
Set the amount of instnces that is going to be drawn. Changing this number will erase all the existing instance transform and color data.
==  get_instance_count  ==
  * [int](class_int) [[#get_instance_count|get_instance_count]]**(****)** const
\\
Return the amount of instnces that is going to be drawn.
==  set_instance_transform  ==
  * void [[#set_instance_transform|set_instance_transform]]**(** [int](class_int) arg0, [Transform](class_transform) arg1 **)**
\\
Set the transform for a specific instance.
==  get_instance_transform  ==
  * [Transform](class_transform) [[#get_instance_transform|get_instance_transform]]**(** [int](class_int) arg0 **)** const
\\
Return the transform of a specific instance.
==  set_instance_color  ==
  * void [[#set_instance_color|set_instance_color]]**(** [int](class_int) arg0, [Color](class_color) arg1 **)**
\\
Set the color of a specific instance.
==  get_instance_color  ==
  * [Color](class_color) [[#get_instance_color|get_instance_color]]**(** [int](class_int) arg0 **)** const
\\
Get the color of a specific instance.
==  set_aabb  ==
  * void [[#set_aabb|set_aabb]]**(** [AABB](class_aabb) arg0 **)**
\\
Set the visibility AABB. If not provided, MultiMesh will not be visible.
==  get_aabb  ==
  * [AABB](class_aabb) [[#get_aabb|get_aabb]]**(****)** const
\\
Return the visibility AABB.
==  generate_aabb  ==
  * void [[#generate_aabb|generate_aabb]]**(****)**
\\
Generate a new visibility AABB, using mesh AABB and instance transforms. Since instance information is stored in the [[visualserver|VisualServer]], this function is VERY SLOW and must NOT be used often.