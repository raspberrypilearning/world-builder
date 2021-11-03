## Player controls

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
The player needs to be able to control your character so that they can move around your world. 
</div>
<div>
Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png){:width="300px"}
</div>
</div>

--- task ---

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

--- /task ---


--- task ---

You don't have to make the camera follow the player, but it often makes sense. 

--- collapse ---

---
title: Make the camera follow the player
---

Drag the Main Camera to the Player in the Hierarchy so that it becomes a child. 

Adjust the Tranform position and rotation of the camera to get the camera view that you want. 

--- /collapse ---

--- /task ---

--- task ---
**Test:** Play your scene and make sure the camera follows the Player. 

You may want to adjust the camera settings later when you have your scenery in place. 

--- /task ---

--- task ---
**Debug:**

--- collapse ---

---
title: The camera is not following the player
---

Make sure the Main Camera is a child object of the Player Game Object. 

--- /collapse ---

--- /task ---

--- save ---