### 1.4.7. WORKING WITH LISTS

Lets take a look at an example using the components from the previous section. In this example, we are creating a tile pattern by mapping geometry to a rectangular grid. The pattern is created by using the List Item component to retrieve the desired tile from a list of geometry.

![IMAGE](images/1-4-7/1-4-7_001-working-with-lists.png)
>1. Geometry corresponding to index 1
2. Geometry corresponding to index 0
3. Rectangular grid

![IMAGE](images/1-4-7/1-4-7_002-mapping.png)
>1. Mapping pattern
2. Mapped geometry

<ol style="background-color:#F9F9F9">
<li> Start a Rhinoceros File. </li>
<li> Create two equally sized squares. </li>
<li> Create different geometries in each square.<br>
<i>In the example shown above, we created a simple surface with a tab. The tab is filleted to demonstrate the orientation and the base is filleted to distinguish the two geometries.</i></li>
<li> Start a new definition, type Ctrl+N (in Grasshopper). </li>
<li> <b>Params/Geometry/Geometry</b> – Drag and drop two <b>Geometry</b> parameters onto the canvas. </li>
<li> Right-Click the first <b>Geometry</b> Parameter and select set one Geometry. Set the first Geometry that you are referencing. </li>
<li> Right-Click the second <b>Geometry</b> Parameter and select set one Geometry. Set the second Geometry that you are referencing. </li>
<li> <b>Params/Geometry/Curve</b> – Drag and drop two <b>Curve</b> parameters onto the canvas. </li>
<li> Right-Click the first <b>Curve</b> Parameter and select set one Curve. Set the first square that you are referencing. </li>
<li> Right-Click the second <b>Curve</b> Parameter and select set one Curve. Set the second square that you are referencing. <br>
<i>Be sure that the geometry and the square that you are referencing correspond.</i></li>
<li> Vector/Grid/Rectangular – Drag and drop a <b>Rectangular Grid</b> component onto the canvas. </li>
<li> Params/Input/Slider - Drag and drop three <b>Number Sliders</b> on the canvas. </li>
<li> Double-click on the first <b>Number Slider</b> and set the following:
<ul>Rounding: Integers<br>
Lower Limit: 0<br>
Upper Limit: 10<br>
Value: 10 </ul></li>
<li> Double-click on the second <b>Number Slider</b> and set the following:
<ul>Rounding: Integers<br>
Lower Limit: 0<br>
Upper Limit: 10<br>
Value: 10 </ul></li>
<li> Double-click on the third <b>Number Slider</b> and set the following:
<ul>Name: Extents X & Y<br>
Rounding: Integers<br>
Lower Limit: 0<br>
Upper Limit: 10<br>
Value: 10 </ul></li>
<li> Connect the first <b>Number Slider</b> to the Size X (Sx) input of the <b>Rectangular Grid</b> component. </li>
<li> Connect the second <b>Number Slider</b> to the Size Y (Sy) input of the <b>Rectangular Grid</b> component. </li>
<li> Connect the third <b>Number Slider</b> to the Extent X (Ex) input and the Extent Y (Ey) input of the <b>Rectangular Grid</b> component. <br>
<img src="images/1-4-7/1-4-7_003-example-1.png" alt="IMAGE">
</li>
<br>
<li> <b>Sets/Tree/Merge</b> – Drag and drop two <b>Merge</b> components onto the canvas. </li>
<li> Connect the first <b>Geometry</b> parameter to Data Stream 1 (D1) input of the first <b>Merge</b> component. </li>
<li> Connect the second <b>Geometry</b> parameter to Data Stream 2 (D2) input of the first <b>Merge</b> component. </li>
<li> Connect the first <b>Curve</b> parameter to Data Stream 1 (D1) input of the second <b>Merge</b> component. </li>
<li> Connect the second <b>Curve</b> parameter to Data Stream 1 (D2) input of the second <b>Merge</b> component. </li>
<li> Right-click the Cells (C) output of the <b>Rectangular Grid</b> component and select Flatten. <br>
<img src="images/1-4-7/1-4-7_004-example-2.png" alt="IMAGE"> </li>
<br>
<li> <b>Sets/List/List Length</b> – Drag and drop a <b>List Length</b> component onto the canvas. </li>
<li> Connect the Cells (C) output of the <b>Rectangular Grid</b> component to the List (L) input of the <b>List Length</b> component. </li>
<li> <b>Sets/Sequence/Repeat Data</b> – Drag and drop a <b>Repeat Data</b> component onto the canvas. </li>
<li> Connect the Length (L) output of the <b>List Length</b> component to the Length (L) input of the <b>Repeat Data</b> component. </li>
<li> <b>Params/Input/Panel</b> – Drag and drop a <b>Panel</b> onto the canvas. </li>
<li> Double-click the <b>Panel</b>. Deselect multiline data, wrap items, and special codes. Enter the following:
<ul>1<br>
0<br>
0</ul></li>
<i>This is the pattern in which the geometries are being distributed. 0 is calling out the first referenced Geometry and 1 is calling out the second referenced Geometry. Changing the number sequence will change the pattern, as will changing the extents of the grid.</i></ul>
<li> Connect the <b>Panel</b> to the Data (D) input of the <b>Repeat Data</b> component. <br>
<img src="images/1-4-7/1-4-7_005-example-3.png" alt="IMAGE"></li>
<br>
<li> <b>Sets/List/List Item</b> – Drag and drop two <b>List Item</b> components. </li>
<li> Connect the Result (R) output of the first <b>Merge</b> component to the List (L) input of the first <b>List Item</b>component. </li>
<li> Connect the Result (R) output of the second <b>Merge</b> component to the List (L) input of the second <b>List Item</b> component. </li>
<li> Connect the Data (D) output of the <b>Repeat Data</b> component to the Index (i) input of the first and second <b>List Item</b> components. </li>
<li> <b>Transform/Affine/Rectangle Mapping</b> – Drag and Drop the <b>Rectangle Mapping</b> component onto the canvas. </li>
<li> Connect the Cells (C) output of the <b>Rectangular Grid</b> component to the Target (T) input of the <b>Rectangular Mapping</b> component. </li>
<li> Connect the items (I) output of the first <b>List Item</b> component to the Geometry (G) input of the <b>Rectangular Mapping</b> component. </li>
<li> Connect the items (I) output of the second <b>List Item</b> component to the Source (S) input of the <b>Rectangular Mapping</b> component. <br>
<br>
<img src="images/1-4-7/1-4-7_006-example-4.png" alt="IMAGE"> </li>
</ol>

Changing the input geometry and the pattern will change the final tile pattern.

![IMAGE](images/1-4-7/1-4-7_007-example-results.png)

![IMAGE](images/1-4-7/1-4-7_008-large-example.png)
