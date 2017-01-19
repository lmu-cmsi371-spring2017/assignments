**CMSI 371** Computer Graphics, Spring 2017

# Assignment 0222
This assignment is the actual big 2D scene, implemented from scratch with our homebrew keyframe/tweening library. Let your imagination run wild **:)**

## Background Reading
Read [Robert Penner’s book chapter on motion, tweening, and easing](http://robertpenner.com/easing/penner_chapter7_tweening.pdf). His [overall website](http://robertpenner.com/easing/) holds additional useful resources as well.

## Automated Feedback Setup
Like the previous assignment, please send your repository’s URL to Ed Seim. Also like the previous assignment, automated feedback only covers code presentation and formatting.

## For Submission
Modify the starter _scene.json_ so that it features a 2D animated scene that is written and directed (and implemented!) by _you_ and starring the “sprites” (actually parameterized drawing functions) from the preceding assignment. Ideally, your scene will work as a very brief animated short, with a quick and engaging little store and characters.

To support your new and improved animated scene, enhance the _keyframe-tweener.js_ animation module in the following ways. Of course, you should demonstrate these enhancements by using them in your own animated short (a.k.a. “eating your own dog food”).

### Overlapping/Skipping Keyframe Ranges
_Limitation:_ The current version of `KeyframeTweener` requires that all tweened properties appear in _every keyframe_ of a sprite. That is, if a translation is specified in one keyframe, the destination translation _must_ be specified in the next one, or else the sprite gets tweened back to some default value.

_Improvement to Make:_ Modify the animation code so that properties can skip keyframes, allowing properties to start and end tweening at any time. That way, a sprite can move from one location to another in, say, 100 frames, but within those 100 frames it might perform multiple rotations.

### Arbitrary Tweenable Properties
_Limitation:_ In its current form, `KeyframeTweener` can only tween whole-sprite translation, rotation, and scaling. In addition, that code is quite repetitive.

_Improvement to Make:_ Extend `KeyframeTweener` so that it can handle _arbitrary tweenable property values_ in the keyframe objects that it processes. This feature is intended precisely to support the ability to animate your parameterized sprites in addition to just whole-sprite translation, rotation, and scaling. Design the data structure and write the needed code to process (tween) these properties then relay them into your sprite’s object parameter. Ideally, this work will also reduce the repetitive transform-tweening code that is in the current `KeyframeTweener`.

### New Tweening Functions
_Limitation:_ The current `KeyframeTweener` implements only four tweening functions.

_Improvement to Make:_ Adapt at least two (2) _non-monotonic tweening functions_ from either [Dan Rogers’s library](https://github.com/danro/jquery-easing/blob/master/jquery.easing.js) or [Tim Groleau’s Easing Function Generator](http://www.timotheegroleau.com/Flash/experiments/easing_function_generator.htm) (Flash required) into `KeyframeTweener`  and use them in your animated scene. The more visually distinct, the better.
