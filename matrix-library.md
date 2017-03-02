**CMSI 371** Computer Graphics, Spring 2017

# Assignment 0407b
This aspect of your 3D framework adds major flexibility to your 3D objects through the power of vectors and matrices.

## Background Reading
If you have access to the Angel textbook, read/scan Sections 4.1–4.13 (pages 135–205) for additional depth and detail.

The code you will write for this assignment can be patterned after the [vector](https://github.com/dondi/bazaar/tree/master/vector) bazaar sample. Make sure that you are clear on what that does before going all Morpheus (or Neo?) on your code.

## Automated Feedback Setup
In order to connect your repository to our automated code review and feedback system, once you are up and running please send your repository’s URL to Ed Seim. You can either find him in person in the lab, tweet him at [https://twitter.com/SirSeim](https://twitter.com/SirSeim), or create a GitHub issue on your repository and mention him in it (`@SirSeim`). Once he has you hooked up, the system will provide feedback on code formatting and quality whenever you commit a new version to GitHub. _Points will be deducted if issues here linger in the final submission._

This assignment, perhaps more than any other unit of code in the course, benefits from a robust test suite.

## Enter the Matrix
Design and implement a computer graphics matrix library with an accompanying suite of unit tests. As with the 3D object framework, no specific design is mandated. However, the following capabilities should be provided:
- A basic matrix object that initializes, by default, to the identity matrix
- Matrix multiplication
- Creation of 3D translation matrices
- Creation of 3D scale matrices
- Creation of 3D rotation matrices based on an arbitrary axis (i.e., refactor the sample code to fit your matrix object implementation)
- Creation of orthographic projection matrices
- Creation of perspective (frustum) projection matrices
- Conversion/convenience functions to prepare the matrix data for direct consumption by WebGL and GLSL

## Test the Matrix
This item is sufficiently important to deserve its own section:
- A unit test suite based on Karma/Jasmine
The reason for the test suite’s importance is the reality that the aforementioned matrix functionality is fairly cut-and-dried; it will not be hard to find implementations on the web and in the textbook. Thus, what makes _your_ implementation different are the specific design choices that you will make for your library _and its test suite_. Use the test suite’s coverage to demonstrate your understanding of matrix and transformations.

## Apply the Matrix
Armed with your newly-minted matrix library, enhance your 3D framework from Assignment 0407a in the following ways:
- Give your 3D objects an _instance transformation_: A composition of rotate, scale, and translate and extend your scene drawing code to apply those transforms. Yes, you will need to touch the vertex shader.
- You might also need something similar to the 2D `canvas`’s _save_ and _restore_ functions.
- Implement _composite_ or _group_ objects: A natural consequence of having an instance transformation is the ability to _composite_ or _group_ objects: that is, allow your 3D objects to have children, each of which is also a 3D object and _whose own instance transformation builds on the parent’s_. Your implementation should allow for arbitrary depth, and of course the drawing code should be able to handle this without a problem. Yes, you are implementing a tree. And now you know why the data structures course is a prerequisite to this one.

The key idea here is to have, after this portion is done, a complete “construction set” of sorts for creating, composing, and now transforming your scene objects in a manner that is limited solely by your imagination.

## Project the Matrix
The second major capability afforded by your matrix library will now be the ability to break out of that 2×2×2 cube thanks to the availability of projection matrices. Do take advantage of them now, in your main scene drawing code.

## Use the Matrix
Once you reach this point, you now have all of the pieces needed to create a _complete static 3D scene_ from your 3D object and matrix framework. Use instance transformations to position, rotate, and resize the objects in your scene. Use the composite/group ability to build more complex objects that transform as a unit.

### Extra Credit (+10)
Separate your 3D scene from the code by allowing it to be loaded from a JSON URL. Find a way to express and process the scene such that one or more of these capabilities is present:

- Objects at different levels of abstraction (3D object, polygon mesh, mesh maker) are supported
  * Mesh maker functions can be called in order to create an object programmatically
- Properties that define a current instance transformation are available
- Environment settings such as a viewing volume and projection type can be specified
