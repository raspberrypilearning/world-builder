## Theme your world

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
What will your world be like? The material you choose for the ground will set the scene and you will choose or create a player character. 

</div>
<div>
![The Scene view showing a character made from 3D GameObjects with coloured materials. The Characher is standing on a plane.](images/character-plane.png){:width="300px"}
</div>
</div>

--- task ---
Think about the kind of world you want to make: 

+ What kind of biome, habitat, geography or weather system will it have?
+ Will it be based on somewhere in the real world, an imagined planet, or based on a book or movie you enjoy?

Think of a **name** for your world. 

--- /task ---

--- task ---
Open your Introduction to Unity project containing the scenes you created in the three Explore projects in this path. 

--- /task ---

--- task ---

**Choose:**

You can either create a new empty scene in the project, or save a copy of your Non-player character scene with a new name. 

Name the new scene with the name of your world. 


--- collapse ---

---
title: Create a new scene
---

Select 'File' then 'New Scene'. 

![The expanded file menu showing the 'New Scene' option](images/new-scene.png)

--- /collapse ---

--- collapse ---

---
title: Save a copy of an existing scene
---

Right-click on your NPC scene and choose 'Save As'. 

Delete any GameObjects that you don't want in your new world. If you think you might want to use a GameObject later, you can deactivate it by unchecking the box next to its name in the Inspector. 

![The inspector window for the NPC Dog GameObject with the active box unchecked.](images/dog-inactive.png)

--- /collapse ---

--- /task ---

Your world or map will need a floor or ground for the player to walk on.

--- task ---
If you're starting from a new scene, add a plane for the floor. If you're working on an existing scene you can just change the material or size.

![The Scene view showing a large plane.](images/new-plane.png)

--- collapse ---

---
title: Add a plane
---

Right-click on your scene in the Hierarchy and select 'GameObject' then '3D Object' then 'Plane'. 

![The 3D object menu with 'plane' highlihted.](images/3D-plane.png)

The default size for the plane is 10m x 10m. Unity uses metres as the unit of measurement.

You can change the X and Z Scale properties for the Plane's Transform in the Scene view or in the Inspector. 

![The transform component showing X and Z scale properies with value '4'.](images/plane-transform.png)

--- /collapse ---

Add or change the material for the plane to fit with the world you are designing.

![The Scene view showing a large plane with 'Yellow Stone' material.](images/yellow-stone-plane.png)

--- collapse ---

---
title: Create a material with a texture
---

The material of a GameObject controls how it looks. A material can have a colour and a texture and there are lots of properties that you can adjust to get different effects. 

In the Model view, navigate to 'My Assets' then right-click and choose 'Create' -> 'Material'. Give the material a descriptive name. 

Click on the colour next to 'Base Map' in the Inspector and choose a colour for your material. 

![In the Material component, the box to the right of 'Base Map' is filled with the colour green.](images/base-green.png)

You can optionally add a texture by clicking on the circle to the left of 'Base Map' and selecting a texture. Note that textures are usually designed for a specific shape of object so the texture will need to be suitable for the shape you will be using it with. The 'Stone Wall' and 'Brick Wall' textures can be used on cube GameObjects. 

![In the Material component, the circle to the left of 'Base Map' is annotated. A popup window shows the Brick Wall texture. ](images/add-texture.png)

**Tip:** Adding both a colour and a texture will apply both the colour and texture to the material.

![Green, blue and purple brick materials.](images/coloured-brick.png)

The **Tiling** property controls how the texture repeats. Bigger numbers will make the pattern smaller. 

There are lots of other settings that you can experiment with to control how metallic the surface will be and how it reflects light. 

--- /collapse ---

[unity-add-material]

--- collapse ---

---
title: Add a material to a GameObject
---

To add a material to a GameObject, navigate to the material in the Model window and drag the material over the GameObject in the scene view. The new material will be applied immediately. 

--- /collapse ---

You can adjust the **Tiling** and other properties in the Inspector for the Material, or in the Inspector for each GameObject that uses the texture. Experiment to get a result you like!

--- /task ---

What kind of character will the Player be in your world? We have included some animal and car mdoel objects that you can choose from. Alternatively you can make a character from a 3D GameObject with child objects that move together. 

![A strip of images showing different characters. There are charaters built from 3D GameObjects, and characters from models such as the cat, raccoon and cars.](images/player-examples.png)

--- task ---

If you made a copy of an existing scene but want a different player character:
+ Drag the Main Camera from the existing Player to the top level in the Hierarchy, then
+ Delete the Player GameObject. 

Models can be created in 3D modelling tools such as Blender. You can also reuse existing Models if you have permission. To save time, we recommend that you use one of the models we have provided, or design your own GameObject using 3D shapes in Unity.

**Choose:**

--- collapse ---

---
title: Create a GameObject from a model
---

Navigate to the Model you want to use in the Project window. 

Drag the model to your scene. 

![The Scene view with the raccoon model added.](images/raccoon-character.png)

Name the new GameObject 'Player' and add the 'Player' tag. 

![The Inspector window for the Player character. The model has been remnamed 'Player' and the tag has been updated to show 'Player'.](images/player-tag.png)

Adjust the start position of the Player's transform. 

If you use the Cat or Raccoon then decide which accessories you will enable and disable the others by unchecking the box next to their name in the Inspector.

![The Player with 'ConstructionGearMesh' and 'PartHatandBowtie' disabled.](images/child-disabled.png)

--- /collapse ---

--- collapse ---

---
title: Create a GameObject from 3D shapes
---

Add a '3D Object' to your scene to represent the player. 

Name the new GameObject 'Player' and add the 'Player' tag.  

Right-click on the Player and add other 3D shapes from 'Create' -> '3D Object' as child game objects. The child objects will move with the Player GameObject. 

--- /collapse ---

--- /task ---

--- task ---

**Debug:**

--- collapse ---

---
title: The material texture is too big or small
---

You can change the **Tiling** properties for the Material, or for a material used in a GameObject. Choose bigger tiling numbers to create a smaller pattern.

--- /collapse ---

--- collapse ---

---
title: I deleted the Camera!
---

If your camera is a child of the Player and you delete the Player then you will also delete the Camera.

To add a new Camera, right-click in the Hierarchy and choose Camera. 

You can drag this Camera to be a child of your Player and adjust the settings. 

--- /collapse ---

--- /task ---

--- save ---
