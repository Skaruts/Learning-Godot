# Physics & Collision (2D)

### Introduction

Our world is made of tangible matter. In our world, a piano can't go through a wall when going into a house. It needs to use the door. Video games are often like the the real world and Pac-Man can't go through the walls of his maze (although he can teleport from the left to the right side of the screen and back).

Anyway, moving sprites around is nice but one day they have to collide properly, so let's get to the point.

### Shapes

The base collidable object in Godot's 2D world is a [Shape2D](class_shape2d). There are many types of shapes, all of them inherit this base class:

* [CircleShape2D](class_circleshape2d)
* [RectangleShape2D](class_rectangleshape2d)
* [CapsuleShape2D](class_capsuleshape2d)
* [ConvexPolygonShape2D](class_convexpolygonshape2d)
* [ConcavePolygonShape2D](class_concavepolygonshape2d)
*  etc. (there are others check the class list).

Shapes are of type [Resource](class_resource), but they can be created via code easily. For example:

```python

#create a circle
var c = CircleShape2D.new()
c.set_radius(20)

#create a box
var b = RectangleShape2D.new()
b.set_extents(Vector2(20,10))
```

The main use for shapes is checking collision/intersection and getting resolution information. Shapes are mostly convex, (except the concavepolygon one, which is just a list of segments to check collision against). This collision check is done easily with the built-in functions like:

```python

#check if there is a collision between two shapes, each with a transform
if b.collide(b_xform,a,a_xform):
   print("OMG Collision!")

```

Godot will return correct collision and collision info from the different calls to the Shape2D api. Collision between all shapes and transforms can be done this way, or even obtaining contact information, motion casting, etc.

### Transforming Shapes

As seen before in the collide functions, 2D shapes in godot can be transformed by using a regular [Matrix32](class_matrix32) transform, meaning the can check collision while scaled, moved and rotated. The only limitation to this is that shapes with curved sections (such as circle and capsule) can only be scaled uniformly. This means that circle or capsule shapes scaled in the form of an ellipse **will not work properly**. This is a limitation on the collision algorithm used (SAT), so make sure that your circle and capsule shapes are always scaled uniformly!

<p align="center"><img src="images/shape_rules.png"></p>

### But Problems Begin

Even though this sounds good, reality is that collision detection alone is usually not enough in most scenarios. Many problems start arising as long as the development of the game is in progress:

#### Too Many Combinations!

Games have several dozens, hundreds, thousands! of objects that can collide and be collided. The typical approach is to test everything against everything in two for loops like this:

```python

for i in colliders:
    for j in colliders:
         if (i.collides(j)):
              do_collision_code()
```

But this scales really bad. Let's imagine there are only 100 objects in the game. This means that 100*100=10000 collisions will need to be tested each frame. This is a lot!

#### Visual Aid

Most of the time, creating a shape via code is not enough. We need to visually place it over a sprite, draw a collision polygon, etc. It is obvious that we need nodes to create the proper collision shapes in a scene.

#### Collision Resolution

Imagine we solved the collision issue, we can tell easily and quickly which shapes overlap. If many of them are dynamic objects that move around, or move according to newtonian physics, solving a collision of multiple objects can be really difficult code-wise.

### Introducing.. Godot's Physics Engine!

To solve all these problems, Godot has a physics and collision engine that is well integrated into the scene system, yet it allows different levels and layers of functionality. The built-in physics engine can be used for:

* Simple Collision Detection: See [Shape2D](class_shape2d) API.
* Scene Kinematics: Handle shapes, collisions, broadphase, etc as nodes. See [Area2D](class_area2d),[StaticBody2D](class_staticbody2d),[KinematicBody2D](class_kinematicbody2d).
* Scene Physics: Rigid bodies and constraints as nodes. See [RigidBody2D](class_rigidbody2d), and the joint nodes.

### Units of Measure

It is often a problem when integrating a 2D Physics engine to a game that such engines are optimized to work using meters as unit of measure. Godot uses a built-in custom 2D physics engine that is designed to function properly in pixels, so all units and default values used for stabilization are tuned for this, making development more straightforward.

### CollisionObject2D

[CollisionObject2D](class_collisionobject2d) is the (virtual) base node for everything that can be collided in 2D. Area2D, StaticBody2D, KinematicBody2D and RigidBody2D all inherit from it. This node contains a list of shapes (Shape2D) and a relative transform. This means that all collisionable objects in Godot can use multiple shapes at different transforms (offset/scale/rotation). Just remember that, as mentioned before, **non-uniform scale will not work for circle and capsule shapes**.

<p align="center"><img src="images/collision_inheritance.png"></p>

### StaticBody2D

The simplest node in the physics engine is the StaticBody2D, which provides a static collision. This means that other objects can collide against it, but StaticBody2D will not move by itself or generate any kind of interaction when colliding other bodies. It's just there to be collided.

Creating one of those bodies is not enough, because it lacks collision:

<p align="center"><img src="images/collision_inheritance.png"></p>

From the previous point, we know that CollisionObject2D derived nodes have an internal lists of shapes and transforms for collisions, but how to edit them? There are two special nodes for that.

### CollisionShape2D

This node is a helper node. It must be created as a direct children of a CollisionObject2D derived node ([Area2D](class_area2d),[StaticBody2D](class_staticbody2d),[KinematicBody2D](class_kinematicbody2d),[RigidBody2D](class_rigidbody2d)). 

By itself it does nothing, but when created as a child of the above mentioned nodes, it adds collision shapes to them. Any amount of CollisionShape2D children can be created, meaning the parent object will simply have mroe collision shapes. When added/deleted/moved/edited, it updates the list of shapes in the parent node.

At run time, though, this node does not exist (can't be accessed with get_node() ), since it's only meant to be an editor helper. To access the shapes created at runtime, use the CollisionObject2D API directly.

As an example, here's the scene from the platformer, containing an Area2D with child CollisionObject2D and coin sprite:

<p align="center"><img src="images/area2dcoin.png"></p>

#####Triggers

A CollisionShape2D or CollisionPolygon2D can be set as a trigger. When used in a RigidBody2D or KinematicBody2D, "trigger" shapes become non-collidable (objects can't collide against it). They just move around with the object as ghosts. This makes them useful in two situations:

*  Disabling collision in a specific shape.
*  Get an Area2D to trigger a body_enter / body_exit signals with non collidable objects (useful in several situations).

### CollisionPolygon2D

This one is similar to CollisionShape2D, except that instead of assigning a shape, a polygon can be edited (drawn by the user) to determine the shape. The polygon can be convex or concave, it doesn't matter.

Going back, here's the scene with the StaticBody2D, the static body is the child of a sprite (meaning if the sprite moves, the collision does too). In turn, the CollisionPolygon is a child of staticbody, meaning it adds collision shapes to it.

<p align="center"><img src="images/spritewithcollision.png"></p>

In fact, what CollisionPolygon does is to decompose the polygon in convex shapes (shapes can only be convex, remember?) and adds them to the CollisionObject2D:

<p align="center"><img src="images/decomposed.png"></p>

### KinematicBody2D

[Kinematic](class_kinematicbody2d) bodies are special types of bodies that are meant to be user-controlled. They are not affected by the physics at all (to other types of bodies, such a character or a rigidbody, these are the same as a staticbody). They have however, two main uses:

* **Simulated Motion**: When these bodies are moved manually, either from code or from an [AnimationPlayer](class_animationplayer) (with process mode set to fixed!), the physics will automatically compute an estimate of their linear and angular velocity. This makes them very useful for moving platforms or other AnimationPlayer-controlled objects (like a door, a bridge that opens, etc). As an example, the 2d/platformer demo uses them for moving platforms.
* **Kinematic Characters**: KinematicBody2D also has an api for moving objects (the move() function) while performing collision tests. This makes them really useful to implement characters that collide against a world, but that don't require advanced physics. A special [tutorial for this exists](tutorial_kinematic_char).

### RigidBody2D

This type of body simulates newtonian physics. It has mass, friction, bounce, and the 0,0 coordinates simulates the center of mass. When real physics are needed, [RigidBody2D](class_rigidbody2d) is the node to use. The motion of this body is affected by gravity and/or other bodies.

Rigid bodies are usually active all the time, but when they end up in resting position and don't move for a while, they are put to sleep until something else wakes them up. This saves an enormous amount of CPU.

RigidBody2D nodes update their transform constantly, as it is generated by the simulation from a position, linear velocity and angular velocity. As a result, **this node can't be scaled**. Scaling the children nodes should work fine though.

As a plus, as this is very common in games, it is possible to change a RigidBody2D node to behave like a Character (no rotation), StaticBody or KinematicBody according to different situations (example, an enemy frozen by an ice beam becomes a StaticBody)

The best way to interact with a RigidBody2D is during the force integration callback. In this very moment, the physics engine synchronizes state with the scene and allows full modification of the internal parameters (otherwise, as it may be running in a thread, changes will not take place until next frame). To do this, the following function must be overridden:

```python
func _integrate_forcres(state):
   [use state to change the object]
```

The `state` parameter is of type [Physics2DDirectBodyState](class_physics2ddirectbodystate). Please do not use this object (state) outside the callback as it will result in an error.

##### Contact Reporting

In general, RigidBody2D will not keep track of the contacts, because this can require a huge amount of memory if thousands of rigid bodies are in the scene. To get contacts reported, simply increase the amount of the "contacts reported" property from zero to a meaningful value (depending on how many you are expecting to get). The contacts can be later obtained via the [Physics2DDirectBodyState.get_contact_count](class_physics2ddirectbodystate#get_contact_count)() and related functions.

Contact monitoring via signals is also available (signals similar to the ones in Area2D, described below) via a boolean property.

### Area2D

Areas in Godot physics have two main roles:

1. Override the space parameters for objects entering them (ie. gravity, gravity direction, gravity type, density, etc).
2. Monitor when rigid or kinematic bodies enter or exit the area.

The second function is the most common. For it to work, the "monitoring" property must be enabled (it is by default). There are two types of signals emitted by this node:

```python
#Simple, high level notification
body_enter(body:PhysicsBody2D)
body_exit(body:PhysicsBody2D)

#Low level shape-based notification
#notifies which shape specifically in both the body and area are in contact
body_enter_shape(body_id:int,body:PhysicsBody2D,body_shape_index:int,area_shape_index:idx)
body_exit_shape(body_id:int,body:PhysicsBody2D,body_shape_index:int,area_shape_index:idx)
```

### Physics Global Variables

A few global variables can be tweaked in the project settings for adjusting how 2D physics works:

<p align="center"><img src="images/physics2d_options.png"></p>

Leaving them alone is best (except for the gravity, that needs to be adjusted in most games), but there is one specific parameter that might need tweaking which is the "cell_size". Godot 2D physics engine used by default a space hashing algorithm that divides space in cells to compute close collision pairs more efficiently.

If a game uses several colliders that are really small and occupy a small portion of the screen, it might be necessary to shrink that value (always to a power of 2) to improve efficiency. Likewise if a game uses few large colliders that span a huge map (of several screens of size), increasing that value a bit might help save resources. 

### Fixed Process Callback

The physics engine may spawn multiple threads to improve performance, so it can use up to a full frame to process physics. Because of this, when accessing physics variables such as position, linear velocity, etc. they might not be representative of what is going on in the current frame.

To solve this, Godot has a fixed process callback, which is like process but it's called once per physics frame (by default 60 times per second). During this time, the physics engine is in _synchronization_ state and can be accessed directly and without delays. 

To enable a fixed process callback, use the set_fixed_process() function, example:

```python
extends KinematicBody2D

func _fixed_process(delta):
   move( direction * delta )

func _ready():
   set_fixed_process(true)
```

### Casting Rays and Motion Queries

It is very often desired to "explore" the world around from our code. Throwing rays is the most common way to do it. The simplest way to do this is by using the RayCast2D node, which will throw a ray every frame and record the intersection.

At the moment there isn't a high level API for this, so the physics server must be used directly. For this, the [Physics2DDirectspaceState](class_physics2ddirectspacestate) class must be used. To obtain it, the following steps must be taken:

1. It must be used inside the _fixed_process() callback, or at _integrate_forces()
2. The 2D RIDs for the space and physics server must be obtained.

The following code should work:

```python:
func _fixed_process(delta):
    var space = get_world_2d().get_space()
    var space_state = Physics2DServer.space_get_direct_state( space )
```

Enjoy doing space queries!

### Contact Reporting

Remember that not every combination of two bodies can "report" contacts. Static bodies are passive and will not report contacts when hit. Kinematic Bodies will report contacts but only against Rigid/Character bodies. Area2D is also passive and will not report against another Area2D. The following table should make it more visual:

#### In case of overlap, who receives contacts?

| Type      | RigidBody | CharacterBody | KinematicBody | StaticBody | Area |
|-----------|-----------|---------------|---------------|------------|------|
| **RigidBody** |    Both   |     Both      |    Both       |  Rigidbody | Area |  
| **CharacterBody** |    Both   |     Both      |    Both   |  CharacterBody | Area |  
| **KinematicBody** |    Both   |     Both      |    None   |  None | Area |  
| **StaticBody** |    RigidBody   |    CharacterBody  |    None   |  None | None |  
| **Area** |    Area   |    Area  |    Area   |  None | None |  







