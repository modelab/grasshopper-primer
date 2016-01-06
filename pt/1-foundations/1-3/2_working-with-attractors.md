<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{font-size: 70%;width: 15%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>
### 1.3.2. Working with Attractors

#####Attractors are points that act like virtual magnets - either attracting or repelling other objects. In Grasshopper, any geometry referenced from Rhino or created withinGrasshopper can be used as an attractor. Attractors can influence any number of parameters of surrounding objects including scale, rotation, color, and position. These parameters are changed based on their relationship to the attractor geometry.

![Overview](images/1-3-2/1-3-2_001-attractor-overview.png)
>1. Attractor point
2. Vectors
3. Circles orient towards attractor based on their normals

In the image above, vectors are drawn between an attractor point and the center
point of each circle. These vectors are used to define the orientation of the
circles so they are always facing the attractor point.
This same attractor could be used to change other parameters of the circles. For
example, circles that are closest to the attractor could be scaled larger by using
the length of each vector to scale the radius of each circle.

![Examples](images/1-3-2/1-3-2_002-attractor-examples.png)

####1.3.2.1. ATTRACTOR DEFINITION
{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Example files that accompany this section: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Example files that accompany this section: [Download](../../appendix/A-2/gh-files/1.3.2.1_attractor definition.gh)
{% endif %}

In this example, we will use an attractor point to orient a grid of circles, based on the vectors between the center points of the circles and the attractor point. Each circle will orient such that it is normal to (facing) the attractor point.

||||
|--|--|--|
|01.| Type Ctrl+N in Grasshopper to start a new definition||
|02.| **Vector/Grid/Hexagonal** - Drag and drop the **Hexagonal Grid** component onto the canvas|[![IMAGE](images/1-3-2/1-3-2_003-hex-grid-component.png)](../../appendix/A-1/0_index-of-components.html#VGHexGrid)|
|03.| **Params/Input/Slider** - Drag and drop two **Numeric Sliders** on the canvas||
|04.| Double-click on the first **Numeric Sliders** and set the following:<ul>Name: Cell Radius<br>Rounding: Floating Point<br>Lower Limit: 0.000<br>Upper Limit: 1.000<br>Value: 0.500</ul>||
|05.| Double-click on the second **Numeric Sliders** and set the following:<ul>Name: # of Cells<br>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10</ul>||
|06.| Connect the **Number Slider** (Cell Radius) to the Size (S) input of the Hexagon Grid component||
|07.| Connect the **Number Slider** (# of Cells) to the Extent X (Ex) input and the Extent Y (Ey) input of the Hexagon Grid component|||

![](images/1-3-2/1-3-2_004-definition1.png)

||||
|--|--|--|
|08.| **Curve/Primitive/Circle CNR** - Drag and drop a **Circle CNR** component onto the canvas|[![](images/1-3-2/1-3-2_005-circle-CNR.png)](../../appendix/A-1/0_index-of-components.html#CPCirCNR)|
|09.| Connect the Points (P) output of the **Hexagon Grid** to the Center (C) input of the **Circle CNR** component||
|10.| Connect the **Number Slider** (Cell Radius) to the Radius (R) input of the **Circle CNR** component.||
|11.| **Vector/Vector/Vector 2Pt** - Drag and Drop the **Vector 2Pt** component onto the canvas|[![IMAGE](images/1-3-2/1-3-2_006-vector-2pt.png)](../../appendix/A-1/0_index-of-components.html#VVVec2Pt)|
|12.| Connect the Points output (P) of the **Hexagonal Grid** component to the Base Point (A) input of the **Vector 2Pt** component.||
|13.| **Params/Geometry/Point** – Drag and Drop the **Point** component onto the canvas|[![IMAGE](images/1-3-2/1-3-2_007-point.png)](../../appendix/A-1/0_index-of-components.html#PGPt)|
|14.| Right-Click the **Point** component and select set one point. In the model space select where you would like the attractor point to be||
|15.| Connect the **Point** component to the Tip Point (B) input of the **Vector 2Pt** component||
|16.| Connect the Vector (V) output of the **Vector 2Pt** to the Normal (N) input of the **Circle CNR** component.|||

![IMAGE](images/1-3-2/1-3-2_008-definition2.png)

||||
|--|--|--|
|17.| **Curve/Util/Offset** – Drag and Drop the **Offset Component** onto the canvas.|[![IMAGE](images/1-3-2/1-3-2_009-offset.png)](../../appendix/A-1/0_index-of-components.html#CUOffset)|
|18.| **Params/Input/Slider** - Drag and drop a **Numeric Slider** on the canvas||
|19.| Double-click on the Number Slider and set the following:<ul>Name: Offset Distance<br>Rounding: Floating Point<br>Lower Limit: - 0.500<br>Upper Limit: 0.500<br>Value: -0.250</ul>||
|20.| Connect the **Number Slider** (Offset Distance) to the Distance (D) input of the **Offset** component|||

![IMAGE](images/1-3-2/1-3-2_010-definition3.png)

![IMAGE](images/1-3-2/1-3-2_011-output3.png)

||||
|--|--|--|
|21.| **Surface/Freeform/Boundary Surfaces** – Drag and drop **Boundary Surfaces** on to the canvas|[![IMAGE](images/1-3-2/1-3-2_012-boundary-surface.png)](../../appendix/A-1/0_index-of-components.html#SFBoundary)|
|22.| Connect the Curves (C) output of the **Offset** component to the Edges (E) input of the **Boundary Surfaces**|||

![IMAGE](images/1-3-2/1-3-2_013-definition4.png)


![](images/1-3-2/1-3-2_014-small-examples.png)

![](images/1-3-2/1-3-2_015-large-example.png)
