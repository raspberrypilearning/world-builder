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
+ If you have chosen the Cat or Raccoon model then you can reuse your 'PlayerController' movement script and 'IdleWalk' animator. 
+ If you have chosen the Car01 or Car02 model you can reuse your 'PlayerController' movement script and use the matching Car1 or Car2 animators.
+ If you have created your own Player then you can create your own simple movement script without animation. 

![An animated gif showing the Raccoon character moving around on the plane](images/animated-char.gif)

--- collapse ---

---
title: Reuse your PlayerController script for a Cat or Raccoon
---

Select your Player GameObject and then click 'Add Component' in the Inspector and choose 'Character controller'.

![The Character controller component in the Inspector window with default settings.](images/character-controller.png)

Find your IdleWalk Animator in the Project window, select the Player GameObject and drag the Animator to the Inspector. 

![The Animator component in the Inspector window with 'IdleWalk' populated.](images/animator-component.png)

Find your PlayerController script in the Project window, select the Player GameObject and drag the script to the Inspector. 

![The Script component in the Inspector window with 'Player Controller' script populated.](images/script-component.png)

**Tip:** You can also drag the Script and Animator from the Project window to the Player GameObject in the Hierarchy. Just be careful to drag it to the correct GameObject. 

<mark>Mention the specific folder location of these Assets when we finalise it.</mark>

--- /collapse ---

[[[unity-player-character-controller]]]

--- collapse ---

---
title: Add animation to a GameObject
---

### Choosing or creating an Animator
The Unity starter asset pack includes animations that can be used with the models. It also includes some Animators including 'IdleWalk' and others in the 'Animation/More/Animators' folder including Animators for the Car models. 

![Car model animator and game view showing a red car moving with animation.](images/car-anim.gif)

To create your own animation, select the 'Animation' folder in the Project window and right-click then create a new Animation Controller. 

Click on the GameObject that will use the Animator and go to the Inspector window. Drag the Animator controller to the 'Controller' property in the 'Animator' component:

![The animator component with 'FollowMove' in the Controller property.](images/animator-follow.png)

Double-click on the Animator to open it in the Animation window. Drag in the animations you want to use. Right-click on animations to add transitions for all the animation changes that you character can make. 

![The animator window with new 'Dog_Run' grey box and arrows going between the idle and run boxes in both directions.](images/idle-run-animator.png)

Go to the 'Parameters' tab.  Bool parameters allow you to change between animations by setting them to 'true' or 'false' in your code. Parameter examples include 'forward', 'crashed', 'isRunning'. To add a parameter, click on the dropdown arrow next to the '+'. Choose 'bool' and add a new Parameter.

![The Animator window with Parameters tab selected in the top left. The '+' button is extended with optin 'bool' selected.](images/animator-parameters.png)

![The Animator window with Parameters tab selected and new parameter called 'isRunning' appears in the list.](images/isRunning-param.png)

**Tip:** Unselect 'Exit Time' on transitions to make the animation change immediately without completing. 

### Adding code to your GameObject to control the animation

Add code to a script on your GameObject to set the Parameter(s) to change the animation:

```
    Animator anim;

    // Start is called before the first frame update
    void Start()
    {
        anim = gameObject.GetComponent<Animator>();
        anim.SetBool("isRunning", false);
    }

    void Update()
    {
        if (Input.GetAxis("Vertical") > 0) // forwards
        {
            anim.SetBool("isRunning", true);
        }
        else // idle
        {
            anim.SetBool("isRunning", false);
        }

        // Code to move
    }
```
--- /collapse ---

--- /task ---

--- task ---
**Test:** Try moving around in Playmode and make sure your character can move around. 

Adjust the speed settings to get the right effect for your character. 

![An animated gif showing the Car01 model moving with animation around on the plane](images/animated-car.gif)

**Tip:** If you change the speed properties in the Inspector then those values will be used instead of the defaults. Default values are useful if you want to reuse the script in other scenes or projects. 

--- collapse ---

---
title: My character isn't moving
---

+ Check that you are in Playmode with the green tint and you have the mouse cursor over the Game view. 
+ Check for any errors in the Console. If there are errors in GameObjects you are not using, such as NPCs, then you could delete the NPCs (you can copy them from another scene if you want them later.)
+ Make sure that the SimpleController script is attached to the Player GameObject (and not a different GameObject). 

--- /collapse ---

--- /task ---


--- task ---

You don't have to make the camera follow the player, but it often makes sense. 

[[[unity-camera-follow-player]]]

--- /task ---

--- task ---
**Test:** Play your scene and make sure the camera follows the Player. 

![An animated gif showing the camera following the player from a slightly elevated position.](images/camera-follow-player.gif)

You may want to adjust the camera settings later when you have your scenery in place. 

--- /task ---

--- task ---
**Debug:**

--- collapse ---

---
title: The camera is not following the player
---

Make sure the Main Camera is a child object of the Player Game Object. 

![The Hierarchy window showing the Main Camera indented under the Player as a child GameObject.](images/camera-child.png)

--- /collapse ---

--- /task ---

--- save ---