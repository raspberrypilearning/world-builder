## Build scenery

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Now you can build out the map of your world with scenery and particle systems. 
</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
</div>
</div>

--- task ---
Use 3D shapes to add steps or hills to your world to create different levels for your player to explore. 
--- /task ---

--- task ---
The 'Character Controller' component has properties that allow the character to walk up slopes and steps. 

--- collapse ---

---
title: Steps and slopes with the Character Controller
---



--- /collapse ---

--- /task ---

--- task ---
**Test:** Play your scene and try walking up the slopes or steps you created. 

Adjust the Character Controller settings or your scenery to get the effect you want. 

--- /task ---

--- task ---
Now add some scenery to your world.

You can use the models we have provided, 3D Objects or a combination. 

[unity-3d-objects]

--- collapse ---

---
title: Add 3D Objects to a scene
---

You can add spheres, cubes, cylinders and other 3D shapes to a scene. 

Right-click in the Hierarchy and choose '3D Object' and then the shape of your choice. 

You can also right-click on a shape in the Hierarchy and add more shapes as child objects. You can position child objects relative to the parent so that they will move with the parent if you reposition it. 

--- /collapse ---

[unity-add-material]

We have included Car, Tree and other models that could be used as scenery in your world. 

--- collapse ---

---
title: Add model objects to a scene
---

Navigate to a model in the Project window then drag it to the Scene view to add it to your scene. 

Adjust the Transform to position, rotate or scale the GameObject. 

--- /collapse ---

You can adjust the Transform of the GameObjects you create to change their position, rotation and scale (size).

--- collapse ---

---
title: View your world in top-down perspective
---



--- /collapse ---

--- collapse ---

---
title: Navigate your world in Scene view
---



--- /collapse ---

--- /task ---

--- task ---
**Test:** Play your scene and walk around. You might want to adjust the camera angle to work well with the scenery you've chosen. 

--- /task ---

Particle Systems are a great way to make your world come to life. 

--- task ---
Consider whether particle effects could make your world more interesting. They can be used to make objects sparkle, to create weather effects, to make a volcano errupt. 

--- collapse ---

---
title: Add a Particle System
---

Particle Systems use lots of small images to create graphical effects that make a 3D world come alive. 

Click in the Inspector and choose 'Effects' -> 'Particle System' to add a particle effect to your world. You can also add a Particle System as a child of another GameObject if that makes sense. 

There are lots of settings you can experiment with to get different particle effects. 

Try adjusting these settings:
+ **Start Color** - Click on the colour to choose the colour for your particles. 
+ **Start Speed** - Control how fast your particles move. 
+ **Start Size** - Control the size of each particle. 
+ **Gravity Modifier** - Set to a positive number if you want your particles to fall to the ground. 
+ **Shape** - Controls the shape that particles appear from. The default is a Cone shape but it might make more sense for your particles to appear in a Sphere or a Cube area. 
+ **Max Particles** - The maximum number of particles that will be active at the same time. 

<mark>It would be good if we could include some specific examples such as snow, smoke, volcano erupting.</mark>

--- /collapse ---

--- /task ---

Background music is another way to add atmosphere to a world. 

--- task ---

The DeathLoop and MenuTheme sounds are suitable for background music. 

<mark>Update if we add more or rename these.</mark>

--- collapse ---

---
title: Add looping background music
---

Background music can be attached to any GameObject, you could choose the floor plane, or the Player. 

Select a GameObject and choose 'Add Component' and then 'Audio Source'. Click on the circle next to AudioClip and choose your music. 

Make sure 'Play on Awake' is selected to automatically play the music and check the 'Loop' box to play the music repeatedly in a loop.

--- /collapse ---

<mark>Would be better if we had a choice of music.</mark>

--- /task ---

<mark>Could also add skybox ingredient</mark>

--- save ---