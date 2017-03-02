**CMSI 371** Computer Graphics, Spring 2017

# Assignment 0407a
Alright, time to go 3D and stay there. As mentioned in class, the overall spirit of the 3D assignments is to give you a taste of what it’s like to build your very own 3D graphics library. Design decisions are yours to make, as long as you implement the requested functionality.

## Background Reading
If you have access to the Angel textbook, the following readings will add depth and detail:
- (already mentioned) _3D graphics overview and pipeline:_ Sections 1.1–1.10 (pages 1–36)
- _Graphics programming:_ Section 2 (pages 39–94)

## Automated Feedback Setup
In order to connect your repository to our automated code review and feedback system, once you are up and running please send your repository’s URL to Ed Seim. You can either find him in person in the lab, tweet him at [https://twitter.com/SirSeim](https://twitter.com/SirSeim), or create a GitHub issue on your repository and mention him in it (`@SirSeim`). Once he has you hooked up, the system will provide feedback on code formatting and quality whenever you commit a new version to GitHub. _Points will be deducted if issues here linger in the final submission._

For this assignment, we are back to writing code that can be feasibly unit-tested. A sample module and test suite are provided, and usage of the test framework (Karma + Jasmine) will be covered in class.

## Library for Building 3D Scenes
The focus of this assignment is the creation of a library for specifying 3D scenes. There is an explicit design element here, so rather than providing sample or starter code, you are instead given _just_ the requested functionality. Design decisions are yours to make. You may use sample code from the [bazaar](https://github.com/dondi/bazaar) as models or starting points, but are not obligated to follow their structure.

## Summary of Deliverables
Deliverables in bold will need Assignment 0407b.

- A 3D shape class
  * Vertices must be relative to a local origin
  * Support for composite shapes (i.e., allow shape objects to “contain” other shape objects)
  * **Support for an instance transformation**
  * **Instance transformation on a parent shape must also affect its children** (i.e., child transformations are performed _relative to_ the parent transformation)
  * Unit test suite
- A “shape maker” library
  * A function that creates a sphere
  * Two additional shape-creating functions
  * _Extra credit:_ Functions that create shapes based on _extrusion_ and/or _lathing/rotating_
  * Unit test suite
- A drawing pipeline that is tailored to your shape class
- **A static 3D scene built from your shape class and shape maker library**
  * Use instance transformations to position, rotate, and resize your shapes
  * _Extra credit:_ Separate the scene from the code and allow it to be loaded from a JSON URL
