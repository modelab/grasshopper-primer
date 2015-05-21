# F-2-1 Working with Attractors

#####Attractors are points that act like virtual magnets - either attracting or repelling other objects. In Grasshopper, any geometry referenced from Rhino or created withinGrasshopper can be used as an attractor. Attractors can influence any number of parameters of surrounding objects including scale, rotation, color, and position. These parameters are changed based on their relationship to the attractor geometry.

(Insert Image)

In the image above, vectors are drawn between an attractor point and the center
point of each circle. These vectors are used to define the orientation of the
circles so they are always facing the attractor point.
This same attractor could be used to change other parameters of the circles. For
example, circles that are closest to the attractor could be scaled larger by using
the length of each vector to scale the radius of each circle.

(Insert Image)

###F.2.1.0 ATTRACTOR DEFINITION
In this example, we will use an attractor point to orient a grid of circles, based on the vectors between the center points of the circles and the attractor point. Each circle will orient such that it is normal to (facing) the attractor point.

01. Type Ctrl+N in Grasshopper to start a new definition
02. Vector/Grid/Hexagonal - Drag and drop the Hexagonal Grid component onto the 	   		canvas
03. Params/Input/Slider - Drag and drop two Numeric Sliders on the canvas
04. Double-click on the first slider and set the following:
05. Name: Cell Radius
06. Rounding: Floating Point
07. Lower Limit: 0.000
08. Upper Limit: 1.000
09. Value: 0.500
10. Double-click on the second slider and set the following:
11. Name: # of Cells
12. Rounding: Integers
13. Lower Limit: 0
14. Upper Limit: 10
15. Value: 10
16. Connect the Number Slider (Cell Radius) to the Size (S) input of the Hexagon Grid component
17. Connect the Number Slider (# of Cells) to the Extent X (Ex) input and the Extent Y (Ey) input of the Hexagon Grid component
18. Curve/Primitive/Circle CNR - Drag and drop a Circle CNR component onto the canvas
19. Connect the Points (P) output of the Hexagon Grid to the Center (C) input of the Circle CNR component
20. Connect the Number Slider (Cell Radius) to the Radius (R) input of the Circle CNR component.
21. Vector/Vector/Vector 2Pt - Drag and Drop the component Vector 2Pt
22. Connect the Points output (P) of the Hexagonal Grid component to the Base Point (A) input of the Vector 2Pt component.
23. Params/Geometry/Point – Drag and Drop the Point component onto the canvas
24. Right-Click the Point component and select set one point. In the model space select where you would like the attractor point to be
25. Connect the Point component to the Tip Point (B) input of the Vector 2Pt component
26. Connect the Vector (V) output of the Vector 2Pt to the Normal (N) input of the Circle CNR component.
27. Curve/Util/Offset – Drag and Drop the Offset Component onto the canvas.
28. Params/Input/Slider - Drag and drop a Numeric Slider on the canvas
29. Double-click on the slider and set the following:
30. Name: Offset Distance
31. Rounding: Floating Point

(Border Image)
(Border Image)
(Border Image)
(Border Image)
(Border Image)
(Border Image)
(Border Image)

32. Lower Limit: - 0.500
33. Upper Limit: 0.500
34. Value: -0.250
35. Connect the Number Slider (Offset Distance) to the Distance (D) input of the offset component
36. Surface/Freeform/Boundary Surfaces – Drag and drop Boundary Surfaces on to the canvas
37. Connect the Curves (C) output of the offset component to the Edges (E) input of the Boundary Surfaces.
38. Params/Geometry/Surface – Drag and Drop the Surface Component onto the canvas
39. Connect the Surfaces (S) output from the Boundary Surfaces to the Surfaces Parameter

(Border Image)
(Border Image)

(Insert Image)
(Insert Image)

(Insert Image)

