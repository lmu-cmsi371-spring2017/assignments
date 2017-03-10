**CMSI 371** Computer Graphics, Spring 2017

# Assignment 0502b
As advertised, this assignment (your last!) focuses on interaction and dynamic behavior. Specifics can’t really be stipulated here because this will be very dependent on your scene. But just have something that isn’t trivial. Definitely do more than the sample code! 

## Background Reading
The previously mentioned readings from the Angel textbook, if you have that, remain relevant to this assignment (and may actually be more meaningful now that you have a bigger picture of things). A closer focus on Chapter 3, in particular, may be helpful here, depending on the specific interaction that you are planning to do.

## Take the Red Pill
Build on a variety of sources to add animated, interactive, or dynamic elements to your scene. For animation, do _at least one_ of the following:

* Adapt the keyframe tweener library from [Assignment 0222](https://github.com/lmu-cmsi371-spring2017/assignments/blob/master/animated-tweened-scene.md) so that it can be used with your scene. _Hints:_ The easing functions don’t change; you will want a keyframes data structure that references your 3D framework objects; and finally the biggest changes you’ll make code-wise will be in your periodically-called scene-updating function.
* Implement physics-based behavior like gravity, acceleration, or anything else. You may integrate a physics engine or roll your own simple one. _Hints:_ The assignment repository already has a full-blown vector library—use it! Some of this work harkens back to assignments from CMSI 186 and CMSI 370, only now in 3D and displayed visually.

For interaction, do this:
* Set up JavaScript event handlers to enable interactive navigation, viewing, or any other user-driven manipulation of your scene. If this is not familiar to you, talk to me and/or read Chapter 6 of the JavaScript text and Chapter 3 in the Angel textbook. There are many ways to do this; Angel Sections 3.13 (page 180) and 4.9.3 (page 247) offer some ideas, but you don’t have to restrict yourself to those. In the GitHub bazaar, the _sierpinski-webgl_ sample illustrates how you might do interactive mouse rotation.

Remember that these approaches are largely orthogonal and therefore can be mixed and matched. Note also that although some changes to your model and view code may be necessary, they should be quite distinct and separate from the actual dynamic behavior. In fact, these changes may have no effect at all on the view code, with the model affected mainly through additional properties or data.
