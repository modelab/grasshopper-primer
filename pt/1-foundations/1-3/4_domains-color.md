<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{font-size: 70%;width: 15%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>
###1.3.4. Domains & Color

{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Example files that accompany this section: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Example files that accompany this section: [Download](../../appendix/A-2/gh-files/1.3.4_domains and color.gh)
{% endif %}

#####The color wheel is a model for organizing colors based on their hue. In Grasshopper, colors can be defined by their hue value in a range of 0.0 to 1.0. Domains are used to define a range of all possible values between a set of numbers between a lower limit(A) and an upper limit (B).

![](images/1-3-4/1-3-4_01-color-wheel.png)
>In the color wheel, hue corresponds to the angle. Grasshopper has taken this 0-360 domainand remapped it between zero and one.

By dividing the Hue domain (0.0 to 1.0) by the number of segments desired, we can assign a hue value to each segment to create a color wheel.

![](images/1-3-4/1-3-4_02-segmented-color-wheels.png)

In this example, we will use Grasshopper’s domain and color components to create a color wheel with a variable amount of segments.

||||
|--|--|--|
|01.| Type Ctrl+N (in Grasshopper) to start a new definition||
|02.| **Curve/Primitive/Polygon** – Drag and drop a **Polygon** component onto the canvas|[![](images/1-3-4/1-3-4_03-polygon.png)](../../appendix/A-1/0_index-of-components.html#CPPolygon)|
|03.| **Params/Geometry/Point** – Drag and drop a **Point** Parameter onto the canvas|[![](images/1-3-4/1-3-4_04-point.png)](../../appendix/A-1/0_index-of-components.html#PGPt)|
|04.| Right-Click on the **Point** Component and select set one point||
|05.| Set a point in the model space.||
|06.| Connect the **Point** Parameter (Base Point) to the Plane (P) input of the **Polygon** component||
|07.| **Params/Input/Number Sliders** – Drag and drop two **Number Sliders** onto the canvas||
|08.| Double-click on the first **Number Sliders** and set the following:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10</ul>||
|09.| Double-click on the second **Number Sliders** and set the following:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 100<br>Value: 37</ul>||
|10.| Connect the **Number Slider** (Radius) to the Radius (R) input of the **Polygon** component <blockquote>When you connect a number slider to a component in will automatically change its name to the name of input that it is connecting to.</blockquote>||
|11.| Connect the **Number Slider** (Segments) to the Segments (S) input of the **Polygon** component|||

![](images/1-3-4/1-3-4_06-connected-sliders.png)

||||
|--|--|--|
|12.| **Curve/Util/Explode** – Drag and drop an **Explode** component onto the canvas.|[![IMAGE](images/1-3-4/1-3-4_07-explode.png)](../../appendix/A-1/0_index-of-components.html#CUExplode)|
|13.| Connect the Polygon (P) output of the **Polygon** component to the Curve (C) input of the **Explode** component||
|14.| **Surface/Freeform/Extrude Point** – Drag and drop the **Extrude Point** component onto the canvas|[![](images/1-3-4/1-3-4_08-extrude.png)](../../appendix/A-1/0_index-of-components.html#SFExtrPt)|
|15.| Connect the Segments (S) output of the **Explode** component to the Base (B) input of the **Extrude Point**||
|16.| Connect the **Point** Parameter (Base Point) to the Extrusion Tip (P) of the **Extrude Point** component||
|17.| **Surface/Analysis/Deconstruct Brep** – Drag and drop the **Deconstruct Brep** component on to the canvas|[![](images/1-3-4/1-3-4_09-deconstruct-brep.png)](../../appendix/A-1/0_index-of-components.html#SADeBrep)|
|18.| Connect the Extrusion (E) output of the **Extrude Point** component to the **Deconstruct Brep** (B) component|||

![IMAGE](images/1-3-4/1-3-4_09b-definition2.png)

||||
|--|--|--|
|19.| **Maths/Domain/Divide Domain** – Drag and drop the **Divide Domain** component<blockquote>The Base Domain (I) is automatically set between 0.0-1.0 which is what we need for this exercise</blockquote>|[![](images/1-3-4/1-3-4_10a-divide-domain.png)](../../appendix/A-1/0_index-of-components.html#MDDivide)|
|20.| Connect the **Number Slider** (Segments) to the Count (C) input of the **Divide Domain** component||
|21.| **Math/Domain/Deconstruct Domain** – Drag and drop the **Deconstruct Domain** component|[![IMAGE](images/1-3-4/1-3-4_10b-deconstruct-domain.png)](../../appendix/A-1/0_index-of-components.html#MDDeDomain)|
|22.| Connect the Segments (S) output of the **Divide Domain** component to the Domain (I) input of the **Deconstruct Domain** component||
|23.| **Display/Colour/Colour HSL** – Drag and drop the **Colour HSL** component|[![IMAGE](images/1-3-4/1-3-4_11-colour-HSL.png)](../../appendix/A-1/0_index-of-components.html#DCHSL)|
|24.| Connect the Start (S) output of the **Deconstruct Domain** component to the Hue (H) input of the **Colour HSL** components||
|25.| **Display/Preview/Custom Preview** – Drag and drop the **Custom Preview** component|[![](images/1-3-4/1-3-4_12-custom-preview.png)](../../appendix/A-1/0_index-of-components.html#DPPreview)|
|26.| Right click on the Geometry (G) input of the **Custom Preview** component and select Flatten<blockquote>See 1-4 Designing with Data Trees for details about flattening</blockquote>||
|27.| Connect the Faces (F) output of the **Deconstruct Brep** component to the Geometry (G) input of the **Custom Preview** component||
|28.| Connect the Colour (C) output of the **Colour HSL** component to the Shade (S) input of the **Custom Preview** component|||

![](images/1-3-4/1-3-4_13-connected-definition.png)

![](images/1-3-4/1-3-4_14-example-result.png)

For different color effects, try connecting the Deconstruct Domain component to the saturation (S) or Luminance (L) inputs of the Colour HSL component.

![](images/1-3-4/1-3-4_15-saturation.png)

![](images/1-3-4/1-3-4_16-large-example.png)
