# F.2.3 Domains & Color

#####The color wheel is a model for organizing colors based on their hue. In Grasshopper, colors can be defined by their hue value in a range of 0.0 to 1.0. Domains are used to define a range of all possible values between a set of numbers between a lower limit(A) and an upper limit (B).

![](images/f2-3/f2-3_001-color-wheel.png)
>In the color wheel, hue corresponds to the angle. Grasshopper has taken this 0-360 domainand remapped it between zero and one.

By dividing the Hue domain (0.0 to 1.0) by the number of segments desired, we
can assign a hue value to each segment to create a color wheel.

![](images/f2-3/f2-3_002-segmented-color-wheels.png)

In this example, we will use Grasshopper’s domain and color components to
create a color wheel with a variable amount of segments.

<ol style="background-color:#EEEEEE">
<li>Type Ctrl+N (in Grasshopper) to start a new definition</li><br>
<li>Curve/Primitive/Polygon – Drag and drop a polygon component onto the
canvas
<br>
![](images/f2-3/f2-3_003-polygon.png)
</li><br>
<li>Params/Geometry/Point – Drag and drop a Point Parameter onto the
canvas
<br>
![](images/f2-3/f2-3_004-point.png)
</li><br>
<li>Right-Click on the Point Component and select set one point</li><br>
<li>Set a point in the model space.</li><br>
<li>Connect the Point Parameter (Base Point) to the Plane (P) input of the
polygon component
<br><br>
![](images/f2-3/f2-3_005-connected-point-polygon.png)
</li><br>
<li>Params/Input/Number Sliders – Drag and drop two number sliders onto
the canvas</li><br>
<li>Double-click on the first slider and set the following:
<ul><br>Rounding: Integers<br>
Lower Limit: 0<br>
Upper Limit: 10<br>
Value: 10</ul></li><br>
<li>Double-click on the second slider and set the following:
<ul><br>Rounding: Integers<br>
Lower Limit: 0<br>
Upper Limit: 100<br>
Value: 37</ul></li><br>
<li>Connect the Number Slider (Radius) to the Radius (R) input of the
Polygon component
<br><br>
![](images/f2-3/f2-3_006-connected-sliders.png)
<ul>*Note: When you connect a number slider to a component in will automatically change its name to the name of input that it is connecting to.*</ul>
</li><br>
<li>Connect the Number Slider (Segments) to the Segments (S) input of the
Polygon component</li><br>
<li>Curve/Util/Explode – Drag and drop an Explode component onto the
canvas.</li><br>
<li>Connect the Polygon (P) output of the Polygon component to the Curve
(C) input of the Explode component
<br>
![](images/f2-3/f2-3_007-explode.png)
</li><br>
<li>Surface/Freeform/Extrude Point – Drag and drop the Extrude Point
component onto the canvas</li><br>
<li>Connect the Segments (S) output of the Explode component to the Base
(B) input of the Extrude Point
<br>
![](images/f2-3/f2-3_008-extrude.png)
<li>Connect the Point Parameter (Base Point) to the Extrusion Tip (P)</li><br>
<li>Surface/Analysis/Deconstruct Brep – Drag and drop the Deconstruct
Brep component on to the canvas</li><br>
<li>Connect the Extrusion (E) output of the Extrude Point component to the
Deconstruct Brep (B) component
<br>
![](images/f2-3/f2-3_009-deconstruct-brep.png)
</li><br>
<li>Maths/Domain/Divide Domain – Drag and drop the Divide Domain
component</li><br>
<li>Connect the Number Slider (Segments) to the Count (C) input of the
Divide Domain component
<br>
![](images/f2-3/f2-3_010-divide-domain.png)
</li><br>
<li>Math/Domain/Deconstruct Domain – Drag and drop the Deconstruct
Domain component</li><br>
<li>Connect the Segments (S) output of the Divide Domain component to the Domain (I) input of the Deconstruct Domain component</li><br>
<li>Display/Colour/Colour HSL – Drag and drop the Colour HSL component</li><br>
<li>Connect the Start (S) output of the Deconstruct Domain component to the Hue (H) input of the Colour HSL components
<br><br>
![](images/f2-3/f2-3_011-color-HSL.png)
<ul>*Note:The Base Domain (I) is automatically set between 0.0-1.0 which is what we need for this exercise.*</ul>
</li><br>
<li>Display/Preview/Custom Preview – Drag and drop the Custom Preview component</li><br>
<li>Right click on the Geometry (G) input of the Custom Preview component and select Flatten
<br>
![](images/f2-3/f2-3_012-flatten-custom-preview.png)
</li><br>
<li>Connect the Faces (F) output of the Deconstruct Brep component to the Geometry (G) input of the Custom Preview</li><br>
<li>Connect the Colour (C) output of the Colour HSL component to the Shade (S) input of the Custom Preview Components
<br><br>
![](images/f2-3/f2-3_013-connected-definition.png)
</li>
</ol>

![](images/f2-3/f2-3_014-example-result.png)

For different color effects, try connecting the Deconstruct Domain component to the saturation (S) or Luminance (L) inputs of the Colour HSL component.

![](images/f2-3/f2-3_015-saturation.png)

![](images/f2-3/f2-3_016-large-example.png)
