# Cutout Animation

### What is it?

Cut-out is a technique of animating in 2D where pieces of paper (or similar material) are cut in special shapes and laid one over the other. The papers are animated and photographed, frame by frame using a stop motion technique (more info [here](http://en.wikipedia.org/wiki/Cutout_animation).

With the advent of the digital age, this technique became possible using computers, which resulted in an increased amount of animation TV shows using digital Cut-out. Notable examples are [South Park](http://en.wikipedia.org/wiki/South_Park) or [Jake and the Never Land Pirates](http://en.wikipedia.org/wiki/Jake_and_the_Never_Land_Pirates).

In video games, this technique also become very popular. Examples of this are [Paper Mario](http://en.wikipedia.org/wiki/Super_Paper_Mario) or [Rayman Origins](http://en.wikipedia.org/wiki/Rayman_Origins).

### Cutout in Godot

Godot provides a few tools for working with these kind of assets, but it's overall design makes it ideal for the workflow. The reason is that, unlike other tools meant for this, Godot has the following advantages:

* **The animation system is fully integrated with the engine**: This means, animations can control much more than just motion of objects, such as textures, sprite sizes, pivots, opacity, color modulation, etc. Everything can be animated and blended.
* **Mix with Traditional**: AnimatedSprite allows traditional animation to be mixed, very useful for complex objects, such as shape of hands and foot, changing face expression, etc.
* **Custom Shaped Elements**: Can be created with [Polygon2D](class_polygon2d) allowing the mixing of UV animation, deformations, etc.
* **Particle Systems**: Can also be mixed with the traditional animation hierarchy, useful for magic effecs, jetpacks, etc.
* **Custom Colliders**: Set colliders and influence areas in different parts of the skeletons, great for bosses, fighting games, etc.
* **Animation Tree**: Allows complex combinations and blendings of several animations, the same way it works in 3D. 

And much more!

### Making of GBot!

For this tutorial, we will use as demo content the pieces of the [GBot](https://www.youtube.com/watch?v=S13FrWuBMx4&list=UUckpus81gNin1aV8WSffRKw) character, created by Andreas Esau. 

<p align="center"><img src="images/tuto_cutout_walk.gif"></p>

Get your assets [here](media/gbot_resources.zip).

### Setting up the Rig

Create an empty Node2D as root of the scene, weĺl work under it:

<p align="center"><img src="images/tuto_cutout1.png"></p>

OK, the first node of the model that we will create will be the hip. Generally, both in 2D and 3D, the hip is the root of the skeleton. This makes it easier to animate:

<p align="center"><img src="images/tuto_cutout2.png"></p>

Next will be the torso. The torso needs to be a child of the hip, so create a child sprite and load the torso, later accommodate it properly:

<p align="center"><img src="images/tuto_cutout3.png"></p>

This looks good. Let's try if our hierarchy works as a skeleton by rotating the torso:

<p align="center"><img src="images/tutovec_torso1.gif"></p>

Ouch, that doesn't look good! The rotation pivot is wrong, this means it needs to be adjusted.
This small little cross in the middle of the [Sprite](class_sprite) is the rotation pivot:

<p align="center"><img src="images/tuto_cutout4.png"></p>

#### Adjusting the Pivot

The Pivot can be adjusted by changing the _offset_ property in the Sprite:

<p align="center"><img src="images/tuto_cutout5.png"></p>

However, there is a way to do it more _visually_. Pick the object and move it normally. After the motion has begun and while the left mouse button is being held, press the "v" key **without releasing** the mouse button. Further motion will move the object around the pivot. This small tool allows adjusting the pivot easily. Finally, move the pivot to the right place:

<p align="center"><img src="images/tutovec_torso2.gif"></p>

Now it looks good! Let's continue adding body pieces, starting by the right arm. Make sure to put the sprites in hierarchy, so their rotations and translations are relative to the parent:

<p align="center"><img src="images/tuto_cutout6.png"></p>

This seems easy, so continue with the right arm. The rest should be simple! Or maybe not:

<p align="center"><img src="images/tuto_cutout7.png"></p>

Right. Remember your tutorials, Luke. In 2D, parent nodes appear below children nodes. Well, this sucks. It seems Godot does not support cutout rigs after all. Come back next year, maybe for 1.2.. no wait. Just Kidding! It works just fine.

But how can this problem be solved? We want the whole to appear behind the hip and the torso. For this, we can move the nodes behind the hip:

<p align="center"><img src="images/tuto_cutout8.png"></p>

But then, we lose the hierarchy layout, which allows to control the skeleton like.. a skeleton. Is there any hope?.. Of Course!

#### RemoteTransform2D Node

Godot provides a special node, [RemoteTransform2D](class_remotetransform2d). This node will transform nodes that are sitting somewhere else in the hierarchy, by copying it's transform to the remote node.
This enables to have a visibility order independent from the hierarchy. 

Simply create two more nodes as children from torso, remote_arm_l and remote_hand_l and link them to the actual sprites:

<p align="center"><img src="images/tuto_cutout9.png"></p>

Moving the remote transform nodes will move the sprites, allowing to easily animate and pose the character:

<p align="center"><img src="images/tutovec_torso4.gif"></p>







