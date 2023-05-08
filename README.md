Download Link: https://assignmentchef.com/product/solved-shape-maker
<br>
<a id="user-content-overview" class="anchor" href="https://github.com/Grimlek/Course-Work/tree/master/Shape%20Maker#overview" aria-hidden="true"></a>Overview

In this project you will create a simple shape drawing application with a graphical user interface. The user will be able to choose a shape, determine its color, and allow it to be filled or unfilled using components in a control panel. A shape is drawn by the user with the mouse using a rubberbanding technique. Buttons on the control panel will allow the user to erase (undo) the last shape drawn and to clear the drawing area completely. The sketch of the user interface shown below will give you a rough idea of the interface components and layout.

<a href="https://i0.wp.com/github.com/Grimlek/Course-Work/blob/master/Shape%20Maker/shape-maker.png?ssl=1" target="_blank" rel="noopener"><img decoding="async" alt="Shape Maker GUI" data-recalc-dims="1" data-src="https://i0.wp.com/github.com/Grimlek/Course-Work/raw/master/Shape%20Maker/shape-maker.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

  <noscript>

   <img decoding="async" src="https://i0.wp.com/github.com/Grimlek/Course-Work/raw/master/Shape%20Maker/shape-maker.png?w=980&amp;ssl=1" alt="Shape Maker GUI" data-recalc-dims="1">

  </noscript></a>

The current settings in the control panel determine the characteristic of the shape drawn. After dragging a shape into existence and releasing the mouse button, the user can then change the settings and draw another shape. Once drawn, a shape cannot be changed in any way except to delete it using the undo or clear buttons. While drawing the shape, the user should be able to move in any direction relative to the starting point.

<h3><a id="user-content-design" class="anchor" href="https://github.com/Grimlek/Course-Work/tree/master/Shape%20Maker#design" aria-hidden="true"></a>Design</h3>

Create a class called ShapeMakerPanel that represents the panel on which the shapes will be drawn. In its constructor, create a JPanel to serve as the control panel, and give it the name “controls” (use setName() to give components names). Add the appropriate components to the control panel and then add the control panel to ShapeMakerPanel. Create all listeners as inner classes within ShapeMakerPanel.

Create a corresponding ShapeMaker class to hold your main() method, which should be as simple as those in recent assignments. Your main() should simply create a frame and place a new instance of your panel in it, and be structured like this:

Use a JComboBox named “shapeChoice” to allow the user to choose the shape. Use a small JPanel named “currentColor” to show the current drawing color. Initially, the drawing color should be black until it is changed. When the user clicks the panel, display a JColorChooser dialog box to allow the user to change the color (which is then shown in the “currentColor” panel). Use a single JCheckBox named “filled” to determine if the shape is filled. Use two JButton objects named “undo” and “clear” for the undo and clear buttons.

All shapes are added by clicking the mouse at a starting point, dragging (which should appropriately animate a dynamically stretching shape) to indicate the intended size, and then releasing the mouse at an ending point.

The shapes should be represented as separate objects based on the following class hierarchy:

<a href="https://i0.wp.com/github.com/Grimlek/Course-Work/blob/master/Shape%20Maker/shapes-class-diagram.jpg?ssl=1" target="_blank" rel="noopener"><img decoding="async" alt="Shapes Class Diagram" data-recalc-dims="1" data-src="https://i0.wp.com/github.com/Grimlek/Course-Work/raw/master/Shape%20Maker/shapes-class-diagram.jpg?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

  <noscript>

   <img decoding="async" src="https://i0.wp.com/github.com/Grimlek/Course-Work/raw/master/Shape%20Maker/shapes-class-diagram.jpg?w=980&amp;ssl=1" alt="Shapes Class Diagram" data-recalc-dims="1">

  </noscript></a>

You will need to write all of these classes yourself. Be sure to use the class names shown here.

The Shape class you write should be abstract. It must support the following methods at a minimum:

<ul>

 <li>public void draw(Graphics context): This abstract method draws the shape on the given graphics context.</li>

 <li>public Color getColor(): Returns the color of the shape as a java.awt.Color object.</li>

</ul>

The BoundedShape class you write should be abstract also. It must support the following methods at a minimum:

<ul>

 <li>public boolean isFilled(): Returns a boolean value indicating whether the shape is filled.</li>

</ul>

Include fields in the hierarchy as appropriate to indicate the shape’s color, filled status, and other data needed to represent the position and size of the shape. Rectangles and ovals can only be drawn parallel to the axes.

Finally, your ShapeMakerPanel must maintain a List internally to keep track of the shapes that are currently on screen. It must also provide a method called getShapes() that returns this list.

For this assignment, pay particular attention to the OO design aspects of your code. While this section outlines the class hierarchy for shapes and specifies some minimum required methods, there is still room for you to make substantive choices about where you place fields and methods, and how you design the internals of these classes. Consider your choices carefully, and aim to allocate responsibilities (and corresponding code) where they best fit in the hierarchy. Re-read the Program Grading Rubric to make sure your class design follows the expectations described there, and ask questions if you are unclear.

Similarly, there is a large range of design variability possible in creating the panels and drawing code in the remaining classes for your solution. Again, carefully consider object-oriented design principles, and strive to create a clean, easily understandable set of classes that highlights your ability to create an object-oriented design. Consider how you separate the user interface aspects of your code (controls, event handlers for controls, etc.) from the data being manipulated (the shapes and the current state of the drawing and drawing settings) to avoid unnecessary coupling and to maintain clarity in your code.

<h3><a id="user-content-core-features" class="anchor" href="https://github.com/Grimlek/Course-Work/tree/master/Shape%20Maker#core-features" aria-hidden="true"></a>Core Features</h3>

The required features include providing the two required panels with the following features:

<ul>

 <li>The “controls” panel must be contained in the ShapeMakerPanel.</li>

 <li>The “controls” panel must include the combo box for shape selection.</li>

 <li>The “controls” panel must include the clear button.</li>

 <li>The “controls” panel must include the check box control for indicating filled shapes.</li>

 <li>Shape, BoundedShape, Rectangle, and Oval must be implemented with full features.</li>

 <li>Your solution must support drawing filled and unfilled rectangles and ovals in the initial drawing color (black).</li>

 <li>Support for the Line subclass and its use in drawings.</li>

 <li>Support for the Square subclass and its use in drawings.</li>

 <li>Support for the Circle subclass and its use in drawings.</li>

 <li>Support for clicking on the “currentColor” and using a JColorChooser to select drawing colors.</li>

 <li>Support for the “undo” button and its behavior.</li>

</ul>

<span class="kksr-muted">Rate this product</span>