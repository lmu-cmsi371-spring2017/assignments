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
The focus of this assignment is the creation of a library for specifying 3D scenes. There is an explicit design element here, so rather than providing sample or starter code, you are instead given _just_ the requested functionality. Design decisions are yours to make. You may use sample code from the [bazaar](https://github.com/dondi/bazaar) as models or starting points, but are not obligated to follow their structure. [three.js](https://threejs.org) can be viewed as an example of what a full-featured version of such a library could look like. For this course, we are aiming for a subset of what [three.js](https://threejs.org) can do.

### Envision a Scene
It’s a good idea to have _some_ notion of what you want to render by the end of the semester. Create a stub web page that will eventually hold the final version; for now, you can use it to demonstrate and test the work listed below.

### Define a 3D Object Class
Design and implement a bona fide JavaScript class for representing a 3D object. You may use the ad hoc objects from the sample code as a basis for your class, but as mentioned we are leaving the design specifics up to you.

Your class will need a constructor function, at the very least. You may discover that certain prototype functions will also be useful. These design choices are up to you.

Like the 2D sprites from earlier this semester, note that your 3D objects will have a local origin. When rotation and scaling are implemented later, these operations will take place in relation to this origin. This idea of a local origin pervades all of the code that you are writing for this assignment, so don’t forget that.

### Modify the Drawing Code Accordingly
Implement a new version of the scene drawing code that works with your 3D shape objects. Remember to take into account the preprocessing that is needed before they can be sent to WebGL.

_Protip:_ As mentioned earlier, keep an eye out for activities that would work well as prototype functions. Candidates for such conversion can be found both in the sample 3D drawing code and in the current _shapes.js_ utility object (*cough* conversion to WebGL-ready array buffers *cough*).

### Define a Polygon Mesh Class
Design and implement a JavaScript class for representing a _polygon mesh_. As covered in class, a polygon mesh is a level up from a base 3D object, capturing a polyhedron’s geometry in a more compact way that lends itself for conversion into vertex arrays for different modes (particularly `GL_LINES` and `GL_TRIANGLES`). Again, you may use the ad hoc polygon mesh from the sample code as a basis for your class, but the design specifics are up to you.

As with the 3D object, you will likely need a constructor function at the very least. You will also want to implement one or more functions that then convert this polygon mesh into the lower-level 3D object. This allows the same polygon mesh to be displayed as solid vs. wireframe, or both, for example.

### Define a “Mesh Maker” Library
As a top-level layer for your 3D framework, build a library of “mesh maker” functions: i.e., functions that create polygon mesh instances of a certain kind. Once more, design choices are flexible—for instance, you may use the JavaScript prototype mechanism to create “subclasses.” Alternatively, you may prefer to take a factory approach (i.e., similar to what the sample code currently does in _shapes.js_). Either way, the specifications for this library are:

- A function that creates a _sphere_ polygon mesh...because this is such a satisfying, iconic polyhedron to code up from first principles. The Angel textbook has an example but it isn’t too hard to come up with one on your own, either.
- At least two (2) more mesh-building functions, based on what your envisioned scene will need. Feel free to implement simpler building blocks then use the composition/grouping functionality to build more sophisticated objects.

When building your mesh’s triangles, remember to adhere to the convention that the triangle’s vertices should be listed in _counterclockwise_ order when viewed from their “outside.” This will affect lighting when that gets implemented later on.

### Supply Unit Tests
Note that we are now back to writing code that can be feasibly unit-tested. Thus, the three major units to be implemented here (3D object, polygon mesh, mesh maker) should each come with a suite of unit tests. The [Istanbul](http://gotwarlost.github.io/istanbul/) tool will be used to measure the coverage of your test suites.

## Summary of Deliverables

- A 3D object class
  * Vertices must be relative to a local origin
  * Unit test suite
- A polygon mesh class
  * Function(s) that “convert” a polygon mesh into the lower-level 3D object
  * Unit test suite
- A “shape maker” library
  * A function that creates a sphere
  * Two additional shape-creating functions
  * _Extra credit:_ Functions that create shapes based on _extrusion_ and/or _lathing/rotating_
  * Unit test suite
- A drawing pipeline that is tailored to your shape class
