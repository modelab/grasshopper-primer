<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{font-size: 70%;width: 15%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>
### 1.4.7. WORKING WITH LISTS
{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Example files that accompany this section: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)

{% else %}
>Example files that accompany this section: [Download](../../appendix/A-2/gh-files/1.4.7_working with lists.gh)

{% endif %}

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
|05.| **Params/Geometry/Geometry** – Drag and drop two **Geometry** parameters onto the canvas.| [![IMAGE](images/1-4-7/1-4-7_003-geometry.png)](../../appendix/A-1/0_index-of-components.html#PGGeo)|
|06.| Right-Click the first **Geometry** Parameter and select set one Geometry. Set the first Geometry that you are referencing. ||
|07.| Right-Click the second **Geometry** Parameter and select set one Geometry. Set the second Geometry that you are referencing. <br><blockquote>It is possible to reference multiple geometries in a single parameter, but for simplicity were are using two separate parameter components.</blockquote>||
|08.| **Params/Geometry/Curve** – Drag and drop two **Curve** parameters onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_004-curve.png)](../../appendix/A-1/0_index-of-components.html#PGCrv)|
|09.| Right-Click the first **Curve** Parameter and select set one Curve. Set the first square that you are referencing.||
|10.| Right-Click the second **Curve** Parameter and select set one Curve. Set the second square that you are referencing. <br><blockquote>Be sure that the geometry and the square that you are referencing correspond.</blockquote>||
|11.| **Vector/Grid/Rectangular** – Drag and drop a **Rectangular Grid** component onto the canvas. |[![IMAGE](images/1-4-7/1-4-7_005-rectangular-grid.png)](../../appendix/A-1/0_index-of-components.html#VGRecGrid)|
|12.| **Params/Input/Slider** - Drag and drop three **Number Sliders** on the canvas. ||
|13.| Double-click on the first **Number Slider** and set the following:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|14.| Double-click on the second **Number Slider** and set the following:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|15.| Double-click on the third **Number Slider** and set the following:<ul>Name: Extents X & Y<br>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|16.| Connect the first **Number Slider** to the Size X (Sx) input of the **Rectangular Grid** component.||
|17.| Connect the second **Number Slider** to the Size Y (Sy) input of the **Rectangular Grid** component.||
|18.| Connect the third **Number Slider** to the Extent X (Ex) input and the Extent Y (Ey) input of the **Rectangular Grid** component.|||

![IMAGE](images/1-4-7/1-4-7_006-definition-1.png)

||||
|--|--|--|
|19.| **Sets/Tree/Merge** – Drag and drop two **Merge** components onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_007-merge.png)](../../appendix/A-1/0_index-of-components.html#STMerge)|
|20.| Connect the first **Geometry** parameter to Data Stream 1 (D1) input of the first **Merge** component. ||
|21.| Connect the second **Geometry** parameter to Data Stream 2 (D2) input of the first **Merge** component. ||
|22.| Connect the first **Curve** parameter to Data Stream 1 (D1) input of the second **Merge** component. ||
|23.| Connect the second **Curve** parameter to Data Stream 1 (D2) input of the second **Merge** component. ||
|24.| Right-click the Cells (C) output of the **Rectangular Grid** component and select Flatten. |||

![IMAGE](images/1-4-7/1-4-7_008-definition-2.png)

||||
|--|--|--|
|25.| **Sets/List/List Length** – Drag and drop a **List Length** component onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_009-list-length.png)](../../appendix/A-1/0_index-of-components.html#SLLng)|
|26.| Connect the Cells (C) output of the **Rectangular Grid** component to the List (L) input of the **List Length** component. ||
|27.| **Sets/Sequence/Repeat Data** – Drag and drop a **Repeat Data** component onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_010-repeat-data.png)](../../appendix/A-1/0_index-of-components.html#SSRepeat)|
|28.| Connect the Length (L) output of the **List Length** component to the Length (L) input of the **Repeat Data** component. ||
|29.| **Params/Input/Panel** – Drag and drop a **Panel** onto the canvas.||
|30.| Double-click the **Panel**. Deselect multiline data, wrap items, and special codes. Enter the following:<ul>1<br>0<br>0</ul><br><blockquote>This is the pattern in which the geometries are being distributed. 0 is calling out the first referenced Geometry and 1 is calling out the second referenced Geometry. Changing the number sequence will change the pattern, as will changing the extents of the grid.</blockquote>|[![IMAGE](images/1-4-7/1-4-7_011-panel.png)](../../appendix/A-1/0_index-of-components.html#PIPanel)|
|31.| Connect the **Panel** to the Data (D) input of the **Repeat Data** component.|||

![IMAGE](images/1-4-7/1-4-7_012-definition-3.png)

||||
|--|--|--|
|32.| **Sets/List/List Item** – Drag and drop two **List Item** components.|[![IMAGE](images/1-4-7/1-4-7_013-list-item.png)](../../appendix/A-1/0_index-of-components.html#SLItem)|
|33.| Connect the Result (R) output of the first **Merge** component to the List (L) input of the first **List Item**component.||
|34.| Connect the Result (R) output of the second **Merge** component to the List (L) input of the second **List Item** component.||
|35.| Connect the Data (D) output of the **Repeat Data** component to the Index (i) input of the first and second **List Item** components.||
|36.| **Transform/Affine/Rectangle Mapping** – Drag and Drop the **Rectangle Mapping** component onto the canvas.|[![IMAGE](images/1-4-7/1-4-7_014-rectangle-mapping.png)](../../appendix/A-1/0_index-of-components.html#TARecMap)|
|37.| Connect the Cells (C) output of the **Rectangular Grid** component to the Target (T) input of the **Rectangular Mapping** component.||
|38.| Connect the items (I) output of the first **List Item** component to the Geometry (G) input of the **Rectangular Mapping** component.||
|39.| Connect the items (I) output of the second **List Item** component to the Source (S) input of the **Rectangular Mapping** component.|||

![IMAGE](images/1-4-7/1-4-7_015-definition-4.png)

Changing the input geometry and the pattern will change the final tile pattern.

![IMAGE](images/1-4-7/1-4-7_016-example-results.png)

![IMAGE](images/1-4-7/1-4-7_017-large-example.png)
