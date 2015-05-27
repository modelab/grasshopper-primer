# F.2.1 Working with Attractors

#####Attractors are points that act like virtual magnets - either attracting or repelling other objects. In Grasshopper, any geometry referenced from Rhino or created withinGrasshopper can be used as an attractor. Attractors can influence any number of parameters of surrounding objects including scale, rotation, color, and position. These parameters are changed based on their relationship to the attractor geometry.

![Overview](images/f2-1/f2-1_001-attractor-overview.png)
>1. Attractor point
2. Vectors
3. Circles orient towards attractor based on their normals

In the image above, vectors are drawn between an attractor point and the center
point of each circle. These vectors are used to define the orientation of the
circles so they are always facing the attractor point.
This same attractor could be used to change other parameters of the circles. For
example, circles that are closest to the attractor could be scaled larger by using
the length of each vector to scale the radius of each circle.

![Examples](images/f2-1/f2-1_002-attractor-examples.png)

###F.2.1.0 ATTRACTOR DEFINITION
In this example, we will use an attractor point to orient a grid of circles, based on the vectors between the center points of the circles and the attractor point. Each circle will orient such that it is normal to (facing) the attractor point.
<ol style="background-color:#EEEEEE">
<li>Type Ctrl+N in Grasshopper to start a new definition</li><br>
<li>Vector/Grid/Hexagonal - Drag and drop the Hexagonal Grid component onto the canvas
<br>
![Hexagon Grid Component](images/f2-1/f2-1_003-hex-grid-component)
</li><br>
<li>Params/Input/Slider - Drag and drop two Numeric Sliders on the canvas</li><br>
<li>Double-click on the first slider and set the following:
<ul><br>Name: Cell Radius<br>
Rounding: Floating Point<br>
Lower Limit: 0.000<br>
Upper Limit: 1.000<br>
Value: 0.500</ul></li><br>
<li>Double-click on the second slider and set the following:
<ul><br>Name: # of Cells<br>
Rounding: Integers<br>
Lower Limit: 0<br>
Upper Limit: 10<br>
Value: 10</ul></li><br>
<li>Connect the Number Slider (Cell Radius) to the Size (S) input of the Hexagon Grid component
</li><br>
<li>Connect the Number Slider (# of Cells) to the Extent X (Ex) input and the Extent Y (Ey) input of the Hexagon Grid component
<br>
<br>
![](images/f2-1/f2-1_004-number-sliders.png)
<br>
<br>
![](images/f2-1/f2-1_005-hex-grid.png)
</li><br>
<li>Curve/Primitive/Circle CNR - Drag and drop a Circle CNR component onto the canvas
<br>
![](images/f2-1/f2-1_006-circle-CNR.png)
</li><br>
<li>Connect the Points (P) output of the Hexagon Grid to the Center (C) input of the Circle CNR component</li><br>
<li>Connect the Number Slider (Cell Radius) to the Radius (R) input of the Circle CNR component.
<br>
<br>
![](images/f2-1/f2-1_007-connect-to-circle.png)
</li><br>
<li>Vector/Vector/Vector 2Pt - Drag and Drop the component Vector 2Pt</li><br>
<li>Connect the Points output (P) of the Hexagonal Grid component to the Base Point (A) input of the Vector 2Pt component.</li><br>
<li>Params/Geometry/Point – Drag and Drop the Point component onto the canvas</li><br>
<li>Right-Click the Point component and select set one point. In the model space select where you would like the attractor point to be</li><br>
<li>Connect the Point component to the Tip Point (B) input of the Vector 2Pt component
<br>
<br>
![](images/f2-1/f2-1_008-connect-point-vector.png)
</li><br>
<li>Connect the Vector (V) output of the Vector 2Pt to the Normal (N) input of the Circle CNR component.
<br><br>
![](images/f2-1/f2-1_009-hex-grid-with-attractor-lines.png)
</li><br>
<li>Curve/Util/Offset – Drag and Drop the Offset Component onto the canvas.
<br>
![](images/f2-1/f2-1_010-offset.png)
</li><br>
<li>Params/Input/Slider - Drag and drop a Numeric Slider on the canvas</li><br>
<li>Double-click on the slider and set the following:
<ul><br>Name: Offset Distance<br>
Rounding: Floating Point<br>
Lower Limit: - 0.500<br>
Upper Limit: 0.500<br>
Value: -0.250</ul>
</li><br>
<li>Connect the Number Slider (Offset Distance) to the Distance (D) input of the offset component
<br><br>
![](images/f2-1/f2-1_011-hex-grid-with-offset.png)
</li><br>
<li>Surface/Freeform/Boundary Surfaces – Drag and drop Boundary Surfaces on to the canvas
<br>
![](images/f2-1/f2-1_012-boundary-surface.png)
</li><br>
<li>Connect the Curves (C) output of the offset component to the Edges (E) input of the Boundary Surfaces.</li><br>
<li>Params/Geometry/Surface – Drag and Drop the Surface Component onto the canvas</li><br>
<li>Connect the Surfaces (S) output from the Boundary Surfaces to the Surfaces Parameter
<br>
<br>
![](images/f2-1/f2-1_013-connected-with-boundary.png)
</li>
</ol>

![](images/f2-1/f2-1_014-small-examples.png)

![](images/f2-1/f2-1_015-large-example.png)
