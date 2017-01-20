**CMSI 371** Computer Graphics, Spring 2017

# Assignment 0201
This initial assignment is meant to get you into a development groove with 2D canvas graphics, as well as mark your first step toward an animated 2D scene.

## Background Reading
Don’t limit your canvas exposure solely to the functions/properties that you specifically use in your drawings—spend some “big picture” time with the [MDN `canvas` tutorial](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial) and [reference](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API#Reference) pages. You might be pleasantly surprised by how much you can do.

## Automated Feedback Setup
In order to connect your repository to our automated code review and feedback system, once you are up and running please send your repository’s URL to Ed Seim. You can either find him in person in the lab, tweet him at [https://twitter.com/SirSeim](https://twitter.com/SirSeim), or mention him in a GitHub comment (`SirSeim`). Once he has you hooked up, the system will provide feedback on code formatting and quality whenever you commit a new version to GitHub. _Points will be deducted if issues here linger in the final submission._

For this assignment, a unit test suite is not practical to do: the “demo pages” pretty much comprise a visual test suite. Thus, automated feedback only covers code presentation and formatting.

## For Submission
First, envision an animated 2D scene that you’d like to render. Storyboard or script it so that you can get a concrete idea of what you’d like to see.

Then, write at least three (3) `canvas` functions that draw three distinct objects in your scene. Known as _sprites_, they can be things, characters, vehicles, buildings, whatever you like. We say “at least” because, really, the more you do, the better you’ll get, and we don’t want to artificially limit your practice time (or your creativity). Give your sprites some internally movable characteristics like limbs or facial expressions (see the next section).

Use standard control structures like loops and conditionals as needed; don’t feel limited to just `canvas` functions and properties. We are assuming that you can figure these out in JavaScript on your own, but if you’re really stuck then ask me.

Consult the [MDN `canvas` website](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) extensively so that you don’t miss out on its full feature set.

### Parameterize the Sprites
Your functions’ drawing commands should be _parameterized by a separate model object_. That is, your functions should accept an object parameter whose properties affect how something gets drawn. For example, if you decide to draw a cartoon character, you can supply an object with a property that states how open or closed its eyes are. Or, you might draw a box with a hinged lid, and its object might state how open, in degrees, the lid should be.

### Draw Around the Origin, Transform to Test
One set of characteristics that you _shouldn’t_ parameterize is whole-object movement, rotation, or scaling. These can be done independently by using the `translate`, `scale`, and `rotate` functions, as seen in class.

Also as mentioned in class, center your drawing code around the origin. You can invoke `translate` before calling your sprite function to draw it at the desired location. Similarly, `scale` and `rotate` will resize and turn your entire sprite, respectively. You may play with these in your demonstration pages (described next).

### Deliverable: Naive Animation Sprite Demo
Define your sprite functions in separate JavaScript files (e.g., _lion.js_, _clown.js_, and _circus.js_). Because these functions are intended for reuse, yes, this time you are allowed to define them within a top-level-scope container object, following the pattern in the provided sample code. For encapsulation, it remains recommended that you define the functions inside an anonymous function that is called immediately.

Test/demonstrate your functions by using your sprites in a “naive animation” program, as shown in the sample code. In case you’re keeping score, this all means that, if you define _n_ sprites, you should end up with _n + 1_ JavaScript files and a single HTML file that loads all of them.
