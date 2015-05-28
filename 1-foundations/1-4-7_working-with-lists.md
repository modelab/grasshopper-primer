<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{font-size: 70%;width: 15%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>
### 1.4.7. WORKING WITH LISTS

Lets take a look at an example using the components from the previous section. In this example, we are creating a tile pattern by mapping geometry to a rectangular grid. The pattern is created by using the List Item component to retrieve the desired tile from a list of geometry.

![IMAGE](images/1-4-7/1-4-7_001-working-with-lists.png)
>1. Geometry corresponding to index 1
2. Geometry corresponding to index 0
3. Rectangular grid

![IMAGE](images/1-4-7/1-4-7_002-mapping.png)
>1. Mapping pattern
2. Mapped geometry




||||
|--|--|--|
|01.| Start a Rhinoceros File. ||
|02.| Create two equally sized squares.||
|03.| Create different geometries in each square.<br><blockquote>In the example shown above, we created a simple surface with a tab. The tab is filleted to demonstrate the orientation and the base is filleted to distinguish the two geometries.</blockquote>||
|04.| Start a new definition, type Ctrl+N (in Grasshopper).||
|05.| </b>Params/Geometry/Geometry</b> – Drag and drop two <b>Geometry</b> parameters onto the canvas.| [![IMAGE](images/1-4-7/1-4-7_003-geometry.png)](/appendix/index.html#index)|
|06.| Right-Click the first <b>Geometry</b> Parameter and select set one Geometry. Set the first Geometry that you are referencing. ||
|07.| Right-Click the second <b>Geometry</b> Parameter and select set one Geometry. Set the second Geometry that you are referencing. <br><blockquote>It is possible to reference multiple geometries in a single parameter, but for simplicity were are using two separate parameter components.</blockquote>||
|08.| <b>Params/Geometry/Curve</b> – Drag and drop two <b>Curve</b> parameters onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_004-curve.png)](/appendix/index.html#index)|
|09.| Right-Click the first <b>Curve</b> Parameter and select set one Curve. Set the first square that you are referencing.||
|10.| Right-Click the second <b>Curve</b> Parameter and select set one Curve. Set the second square that you are referencing. <br><blockquote>Be sure that the geometry and the square that you are referencing correspond.</blockquote>||
|11.| **Vector/Grid/Rectangular** – Drag and drop a <b>Rectangular Grid</b> component onto the canvas. |[![IMAGE](images/1-4-7/1-4-7_005-rectangular-grid.png)](/appendix/index.html#index)|
|12.| **Params/Input/Slider** - Drag and drop three <b>Number Sliders</b> on the canvas. ||
|13.| Double-click on the first <b>Number Slider</b> and set the following:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|14.| Double-click on the second <b>Number Slider</b> and set the following:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|15.| Double-click on the third <b>Number Slider</b> and set the following:<ul>Name: Extents X & Y<br>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|16.| Connect the first <b>Number Slider</b> to the Size X (Sx) input of the <b>Rectangular Grid</b> component.||
|17.| Connect the second <b>Number Slider</b> to the Size Y (Sy) input of the <b>Rectangular Grid</b> component.||
|18.| Connect the third <b>Number Slider</b> to the Extent X (Ex) input and the Extent Y (Ey) input of the <b>Rectangular Grid</b> component.|||

![IMAGE](images/1-4-7/1-4-7_006-definition-1.png)

||||
|--|--|--|
|19.| <b>Sets/Tree/Merge</b> – Drag and drop two <b>Merge</b> components onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_007-merge.png)](/appendix/index.html#index)|
|20.| Connect the first <b>Geometry</b> parameter to Data Stream 1 (D1) input of the first <b>Merge</b> component. ||
|21.| Connect the second <b>Geometry</b> parameter to Data Stream 2 (D2) input of the first <b>Merge</b> component. ||
|22.| Connect the first <b>Curve</b> parameter to Data Stream 1 (D1) input of the second <b>Merge</b> component. ||
|23.| Connect the second <b>Curve</b> parameter to Data Stream 1 (D2) input of the second <b>Merge</b> component. ||
|24.| Right-click the Cells (C) output of the <b>Rectangular Grid</b> component and select Flatten. |||

![IMAGE](images/1-4-7/1-4-7_008-definition-2.png)

||||
|--|--|--|
|25.| <b>Sets/List/List Length</b> – Drag and drop a <b>List Length</b> component onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_009-list-length.png)](/appendix/index.html#index)|
|26.| Connect the Cells (C) output of the <b>Rectangular Grid</b> component to the List (L) input of the <b>List Length</b> component. ||
|27.| <b>Sets/Sequence/Repeat Data</b> – Drag and drop a <b>Repeat Data</b> component onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_010-repeat-data.png)](/appendix/index.html#index)|
|28.| Connect the Length (L) output of the <b>List Length</b> component to the Length (L) input of the <b>Repeat Data</b> component. ||
|29.| <b>Params/Input/Panel</b> – Drag and drop a <b>Panel</b> onto the canvas.||
|30.| Double-click the <b>Panel</b>. Deselect multiline data, wrap items, and special codes. Enter the following:<ul>1<br>0<br>0</ul><br><blockquote>This is the pattern in which the geometries are being distributed. 0 is calling out the first referenced Geometry and 1 is calling out the second referenced Geometry. Changing the number sequence will change the pattern, as will changing the extents of the grid.</blockquote>|[![IMAGE](images/1-4-7/1-4-7_011-panel.png)](/appendix/index.html#index)|
|31.| Connect the <b>Panel</b> to the Data (D) input of the <b>Repeat Data</b> component.|||

![IMAGE](images/1-4-7/1-4-7_012-definition-3.png)

||||
|--|--|--|
|32.| <b>Sets/List/List Item</b> – Drag and drop two <b>List Item</b> components.|[![IMAGE](images/1-4-7/1-4-7_013-list-item.png)](/appendix/index.html#index)|
|33.| Connect the Result (R) output of the first <b>Merge</b> component to the List (L) input of the first <b>List Item</b>component.||
|34.| Connect the Result (R) output of the second <b>Merge</b> component to the List (L) input of the second <b>List Item</b> component.||
|35.| Connect the Data (D) output of the <b>Repeat Data</b> component to the Index (i) input of the first and second <b>List Item</b> components.||
|36.| <b>Transform/Affine/Rectangle Mapping</b> – Drag and Drop the <b>Rectangle Mapping</b> component onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_014-rectangle-mapping.png)](/appendix/index.html#index)|
|37.| Connect the Cells (C) output of the <b>Rectangular Grid</b> component to the Target (T) input of the <b>Rectangular Mapping</b> component.||
|38.| Connect the items (I) output of the first <b>List Item</b> component to the Geometry (G) input of the <b>Rectangular Mapping</b> component.||
|39.| Connect the items (I) output of the second <b>List Item</b> component to the Source (S) input of the <b>Rectangular Mapping</b> component.|||

![IMAGE](images/1-4-7/1-4-7_015-definition-4.png)

Changing the input geometry and the pattern will change the final tile pattern.

![IMAGE](images/1-4-7/1-4-7_016-example-results.png)

![IMAGE](images/1-4-7/1-4-7_017-large-example.png)
