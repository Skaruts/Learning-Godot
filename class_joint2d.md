##  Joint2D  
**Inherits:** [[node2d|Node2D]]\\
**Category:** Core\\
##  Brief Description  
Base node for all joint constraints in 2D phyisics.
##  Member Functions 
  * void [[#set_node_a|set_node_a]]**(** [NodePath](class_nodepath) node **)**
  * [NodePath](class_nodepath) [[#get_node_a|get_node_a]]**(****)** const
  * void [[#set_node_b|set_node_b]]**(** [NodePath](class_nodepath) node **)**
  * [NodePath](class_nodepath) [[#get_node_b|get_node_b]]**(****)** const
  * void [[#set_bias|set_bias]]**(** [real](class_real) bias **)**
  * [real](class_real) [[#get_bias|get_bias]]**(****)** const
##  Description  
Base node for all joint constraints in 2D phyisics. Joints take 2 bodies and apply a custom constraint.
##  Member Function Description  
==  set_node_a  ==
  * void [[#set_node_a|set_node_a]]**(** [NodePath](class_nodepath) node **)**
\\
Set the path to the A node for the joint. Must be of type PhysicsBody2D.
==  get_node_a  ==
  * [NodePath](class_nodepath) [[#get_node_a|get_node_a]]**(****)** const
\\
Return the path to the A node for the joint.
==  set_node_b  ==
  * void [[#set_node_b|set_node_b]]**(** [NodePath](class_nodepath) node **)**
\\
Set the path to the B node for the joint. Must be of type PhysicsBody2D.
==  get_node_b  ==
  * [NodePath](class_nodepath) [[#get_node_b|get_node_b]]**(****)** const
\\
Return the path to the B node for the joint.