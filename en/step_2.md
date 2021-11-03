## Theme your world

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
Add an introductory sentence. What will learners achieve by the end of this step?
</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
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

You can either create a new empty scene in the project, or save a copy of your Non-player character scene with a new name. 

Name the new scene with the name of your world. 

--- task ---

**Choose:**

--- collapse ---

---
title: Create a new scene
---

Select 'File' (or 'Unity') then 'New Scene'. 

--- /collapse ---

--- collapse ---

---
title: Save a copy of an existing scene
---

Right-click on your NPC scene and choose 'Save As'. 

You can delete any GameObjects that you don't want in your new world. If you think you might want to use a GameObject later, you can deactivate it by unchecking the box next to its name in the Inspector. 

![The inspector window for the NPC Dog GameObject with the active box unchecked.](images/path)

--- /collapse ---

--- /task ---

Your world or map will need a floor or ground for the player to walk on.

--- task ---
If you're starting from a new scene, add a plane for the floor. If you're working on an existing scene you can just change the material or size.

--- collapse ---

---
title: Add a plane
---

Right-click on your scene in the Hierarchy and select 'GameObject' then '3D Object' then 'Plane'. 

The default size for the plane is 10m x 10m. Unity uses metres as the unit of measurement.

You can change the X and Z Scale properties for the Plane's Transform in the Scene view or in the Inspector. 

--- /collapse ---

Add or change the material for the plane to fit with the world you are designing. 

--- collapse ---

---
title: Create a material with a texture
---

The material of a GameObject controls how it looks. A material can have a colour and a texture and there are lots of properties that you can adjust to get different effects. 

In the Model view, navigate to 'My Assets' then right-click and choose 'Create' -> 'Material'. Give the material a descriptive name. 

Click on the colour next to 'Base Map' in the Inspector and choose a colour for your material. 

You can optionally add a texture by clicking on the circle to the left of 'Base Map' and selecting a texture. Note that textures are usually designed for a specific shape of object so the texture will need to be suitable for the shape you will be using it with. The 'Stone Wall' and 'Brick Wall' textures can be used on cube GameObjects. 

The **Tiling** property controls how the texture repeats. Bigger numbers will make the pattern smaller. 

There are lots of other settings that you can experiment with to control how metallic the surface will be and how it reflects light. 

--- /collapse ---

--- collapse ---

---
title: Add a material to a GameObject
---

To add a material to a GameObject, navigate to the material in the Model window and drag the material over the GameObject in the scene view. The new material will be applied immediately. 


--- /collapse ---

You can adjust the **Tiling** and other properties in the Inspector for the Material, or in the Inspector for each GameObject that uses the texture. Experiment to get a result you like!

--- /task ---

What kind of character will the Player be in your world? We have included some animal and car mdoel objects that you can choose from. Alternatively you can make a character from a 3D GameObject with child objects that move together. 

--- task ---

If you made a copy of an existing scene but want a different player character:
+ Drag the Main Camera from the existing Player to the top level in the Hierarchy, then
+ Delete the Player GameObject. 

**Choose:**

--- collapse ---

---
title: Create a GameObject from a model
---

Navigate to the Model you want to use in the Project window. 

Drag the model to your scene. 

Name the new GameObject 'Player' and add the 'Player' tag.  

Adjust the start position of the Player's transform. 

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

**Choose:** If you have chosen the Cat or Raccoon model then you can reuse your PlayerController movement script and IdleWalk animator. If you have chosen a Car or made your own Player then you can create your own simple movement script without animation. 

--- collapse ---

---
title: Reuse your PlayerController script for a Cat or Raccoon
---

Character controller
Script
Animator

--- /collapse ---

--- collapse ---

---
title: Add player movement with a Character Controller
---

Select your player GameObject and choose 'Add Cmponent' in the Inspector and add a 'Character Controller'.

Adjust the collider settings so that the collider is same height as the player and Y center is half that height. Adjust the radius so that the collider covers your player. 

The 'Character Controller' component add the `SimpleMove` method which you will need to call from `Update` on a script attached to the Player. 

Click 'Add Component' then 'New script'. Name the script 'SimpleController' (or use a name specific to your character such as 'SnowmanController'.)

Click on the Script in the Inspector to find it in the Project window then open the script in your Code Editor. 

Add code to move your character based on keyboard input. 

```
public class SimpleController : MonoBehaviour
{
    public float moveSpeed = 3.0F; // default move speed
    public float rotateSpeed = 3.0F; // default rotate speed

    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        CharacterController controller = GetComponent<CharacterController>();
        transform.Rotate(0, Input.GetAxis("Horizontal") * rotateSpeed, 0);
        Vector3 forward = transform.TransformDirection(Vector3.forward);
        float speed = moveSpeed * Input.GetAxis("Vertical");
        controller.SimpleMove(forward * speed);
    }
}
```

--- /collapse ---

--- /task ---

--- task ---
**Test:** Try moving around in Playmode and make sure your character can move around. 

Adjust the speed settings to get the right effect for your character. 

**Tip:** If you change the speed properties in the Inspector then those values will be used instead of the defaults. Default values are useful if you want to reuse the script in other scenes or projects. 

--- collapse ---

---
title: My character isn't moving
---

+ Check that you are in Playmode with the green tint and you have the mouse cursor over the Game view. 
+ Check for any errors in the Console. If there are errors in GameObjects you are not using, such as NPCs, then you could delete the NPCs (you can copy them from another scene if you want them later.)
+ Make sure that the SimpleController script is attached to the correct GameObject - your Player. 

--- /collapse ---

--- collapse ---

---
title: The material texture is too big or small
---

You can change the **Tiling** properties for the Material, or for a material used in a GameObject. Choose bigger tiling numbers to create a smaller pattern.

--- /collapse ---
--- /task ---

--- save ---
