## Player controls

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 200px; flex-grow: 1; margin-right: 15px;">
The player needs to be able to control your character so that they can move around your world. 
</div>
<div>
![The Game view showing the Cat player character moving around on the plane with the camera following.](images/camera-movements.gif){:width="300px"}
</div>
</div>

--- task ---

**Choose:** How will your player move?
+ If you have chosen the Cat or Raccoon model, then you can reuse your PlayerController movement script and IdleWalk animator. 
+ If you have chosen the Car01 or Car02 model, you can reuse your PlayerController movement script and use the matching Car1 or Car2 animators.
+ If you have created your own Player, then you can create your own simple movement script without animation. 

![An animated gif showing the Raccoon character moving around on the plane.](images/animated-char.gif)

--- collapse ---

---
title: Add the PlayerController script for a Cat, Raccoon, or Rat
---

Select your **Player GameObject** and then click **Add Component** in the Inspector and choose **Character Controller**.

![The Character Controller component in the Inspector window with default settings.](images/character-controller.png)

Find your **IdleWalk Animator** in the Animation folder in the Project window, select the **Player GameObject** and drag the **Animator** to the Inspector. 

![The Animator component in the Inspector window with 'IdleWalk' populated.](images/animator-component.png)

If you started from a project containing the PlayerController script, then you can add it to a new character GameObject. Find the **PlayerController** script in the Project window, select the **Player GameObject** and drag the Script to the Inspector. 

![The Script component in the Inspector window with 'Player Controller' script populated.](images/script-component.png)

**Tip:** You can also drag the Script and Animator from the Project window to the Player GameObject in the Hierarchy. Just be careful to drag it to the correct GameObject. 

If you don't have the PlayerController script, then select your **character GameObject** and click **Add Component** and create a script called `PlayerController` with this script:

--- code ---
---
language: csharp
filename: PlayerController.cs
line_numbers: false
line_number_start: 
line_highlights: 
---
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float speed = 3.0f;
    public float rotateSpeed = 1.0f;
    Animator anim;

    void Start()
    {
        anim = gameObject.GetComponent<Animator>();
    }

    void Update()
    {
        float moveSpeed = speed;

        if (Input.GetAxis("Vertical") > 0)
        {
            anim.SetBool("forward", true);
        }
        else if (Input.GetAxis("Vertical") < 0)
        {
            anim.SetBool("forward", false);
            moveSpeed *= 0.5f;
        }
        else
        {
            anim.SetBool("forward", false);
        }

        CharacterController controller = GetComponent<CharacterController>();
        transform.Rotate(0, Input.GetAxis("Horizontal") * rotateSpeed, 0);
        Vector3 forward = transform.TransformDirection(Vector3.forward);
        float curSpeed = moveSpeed * Input.GetAxis("Vertical");
        controller.SimpleMove(forward * curSpeed);
    }
}

--- /code ---

--- /collapse ---

[[[unity-player-character-controller]]]

[[[unity-animation]]]

--- /task ---

--- task ---

**Test:** Try moving around in Play mode and make sure your character can move around. 

Adjust the speed settings to get the right effect for your character. 

![An animated gif showing the Car01 model moving around on the plane with animation.](images/animated-car.gif)

**Tip:** If you change the speed properties in the Inspector, then those values will be used instead of the defaults. Default values are useful if you want to reuse the script in other scenes or projects. 

[[[unity-console-error]]]

--- collapse ---

---
title: My character isn't moving
---

+ Check that you are in Play mode with the colour tint and you have the mouse cursor over the Game view. 
+ Check for any errors in the Console. If there are errors in GameObjects you are not using, such as NPCs, then you could delete the NPCs (you can copy them from another scene if you want them later).
+ Make sure that the SimpleController script is attached to the Player GameObject (and not a different GameObject).
+ Make sure the parameter name used for the Animator is the same as the parameter name in your script. In the above example `isRunning` is used as the parameter name.

--- /collapse ---

--- /task ---

--- task ---

You don't have to make the camera follow the Player, but it often makes sense. 

[[[unity-camera-follow-player]]]

--- /task ---

--- task ---

**Test:** Play your scene and make sure the camera follows the Player. 

![An animated gif showing the camera following the player from a slightly elevated position.](images/camera-follow-player.gif)

You may want to adjust the camera settings later when you have your scenery in place. 


--- /task ---

--- task ---

**Debug:**

Useful debugging tips:
- Turn on the Play mode tint so that you can tell when you are in Game mode.
- Click on **Gizmos** in Play mode and then click on a GameObject in the Inspector to view its colliders.
- Look at the values of public variables in the Inspector in Play mode to see how they are changing. 
- Use `Debug.Log()` to print messages to the Console to understand what's happening. 
- Check the Console for errors. Script errors also appear in the bar at the bottom of the editor. 

[[[unity-camera-error]]]

[[[unity-changes-gone]]]

[[[unity-method-absent]]]

[[[unity-show-variables]]]

--- /task ---

--- save ---
