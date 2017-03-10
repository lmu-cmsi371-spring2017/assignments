**CMSI 371** Computer Graphics, Spring 2017

# Assignment 0502a
This assignment seeks to wrap up the visual aspect of your 3D scene.

## Background Reading
If you have been following along with the Angel textbook, at this point, we have pretty much covered *Chapters 1, 2, 4, and 5*, with the exception of Sections 4.14, 5.10, and 5.11. Non-graphics-specific interaction material in *Chapter 3* was studied in CMSI 370; the computer graphics content shouldn’t be too hard to assimilate if you understand the rest of the material.

The lighting model that we are using, plus a few more details, can be seen in greater detail in *Angel Chapter 6* and the *orange book Chapter 9*. And of course, the C or C++ code in the orange book must be superseded by or adapted into JavaScript and WebGL.

## Automated Feedback Setup
In order to connect your repository to our automated code review and feedback system, once you are up and running please send your repository’s URL to Ed Seim. You can either find him in person in the lab, tweet him at [https://twitter.com/SirSeim](https://twitter.com/SirSeim), or create a GitHub issue on your repository and mention him in it (`@SirSeim`). Once he has you hooked up, the system will provide feedback on code formatting and quality whenever you commit a new version to GitHub. _Points will be deducted if issues here linger in the final submission._

We are back to an aspect of the 3D scene code that is difficult to test automatically in a straightforward way, so this is de-emphasized for these last units of work.

## The New Normal
Add support for normal vectors to your shape objects. You may use any technique for generating them, including (correctly) using the functions given to you, writing code of your own, and manually specifying them. You want to do this because you will then set up...

## Lights!
Implement a lighting model for your 3D framework, using it in your scene-in-progress and enhancing your shaders accordingly. At a minimum, you should use the model shown in class and detailed in the reading (a.k.a., the _fixed function_ model). You can go beyond that if you wish (e.g., the UberLight model described in Chapter 12 of the orange book).

## Camera!
Implement the camera transformation matrix and integrate it into your 3D framework (most likely your matrix library). Model and use a camera in your 3D scene. Note that, at this point, you should have full scene layout and navigation capabilities.

## Action...Almost
Ultimately it may be too restrictive to strictly partition the remaining 3D scene work to just lighting and camera or just animation and interaction. However, acknowledging the amount of work involved, we separate animation/interaction work into the next assignment. Chances are that you will want to work on both concurrently—after all, what fun will it be to have a camera but not be able to fly around like a superhero? 😎
