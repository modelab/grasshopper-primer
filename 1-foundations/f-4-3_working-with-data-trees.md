# F-4-3 Working with Data Trees

#####Grasshopper contains tools for changing the structure of a data tree. Theese tools can help you access specific data within a tree, and change the way it is stored, ordered, and identified.

Let’s look at some data tree manipulations and visualize how they affect the tree.

###F.4.3.0 FLATTEN
Flattening removes all levels of a Data Tree, resulting in a single List. Using the
Flatten component (Sets/Tree/Flatten) on the P output of our Divide Curve
component, we can use the Param Viewer to visualize the new data structure.

(Insert Image)

###F.4.3.1 GRAFT TREE
Grafting creates a new Branch for every Data Item. If we run the data through
the Graft Tree component (Sets/Tree/Graft Tree), each division point now has
its own individual branch, rather than sharing a branch with the other division
points on the same curve.

(Insert Image)

###F.4.3.2 SIMPLIFY TREE
Simplify removes overlapping Branches in a Data Tree. If we run the data
through the Simplify Tree component (Sets/Tree/Simplify Tree), the first branch,
containing no data, has been removed.

(Insert Image)

###F.4.3.3 FLIP MATRIX
The Flip Matrix component (Sets/Tree/Flip Matrix) Swaps the “Rows” and
“Columns” of a Data Tree with two Path Indices.

(Insert Image)

The Flatten, Graft, and Simplify operations can be applied to the component
input or output itself, rather than feeding the data through a separate
component. Just right-click the desired input or output and select Flatten, Graft,
or Simplify from the menu. The component will display an icon to indicate that
the tree is being modified. Keep in mind Grasshopper’s program flow. If you
flatten a component input, the data will be flattened before the component
operation is performed. If you flatten a component output, the data will be
flattened after the component performs its action.

(Insert Image)

###F.4.3.4 THE PATH MAPPER
The Path Mapper component (Sets/Tree/Path Mapper) allows you to perform
lexical operations on data trees. Lexical operations are logical mappings between
data paths and indices which are defined by textual (lexical) masks and patterns.

(Insert Image)

###F.4.3.5 WEAVING DEFINITION
In this example, we will manipulate lists and data trees to weave lists of points,
define a pattern, and create surface geometry.

(Insert Image)

01. Start a new definition, type Ctrl+N (in Grasshopper)
02. Curve/Primitive/Line SDL – Drag and drop the Line SDL component onto
the canvas
(Border Image)
03. Vector/Point/Construct Point – Drag and drop the Construct Point
component onto the canvas
(Border Image)
04. Connect the Point (Pt) output of the Construct Point component to the
Start (S) Input of the Line SDL component
05. Vector/Vector/Unit Y – Drag and drop the vector Unit Y component onto
the canvas
(Border Image)
06. Connect the Unit Y component to the Direction (D) input of the Line SDL
component
07. Params/Input/Number Slider – Drag and drop the Number Slider
component onto the canvas
08. Double-click on the Number slider and set the following:
Name: Length
Rounding: Integer
Lower Limit: 0
Upper Limit: 96
Value: 96
(Border Image)
09. Connect the Number slider to the Length (L) input of the Line SDL
component
10. Transform/Array/Linear Array – Drag and drop the Linear Array
component onto the canvas
(Border Image)
11. Connect the Line (L) output of the Line SDL component to the Geometry
(G) input of the Linear Array component
12. Vector/Vector/Unit X – Drag and drop the Vector Unit X component onto
the canvas
(Border Image)
13. Params/Input/Number Slider – Drag and drop two Number Slider
components onto the canvas
14. Double-click on the first slider and set the following:
Name: Offset Distance
Rounding: Integer
Lower Limit: 1
Upper Limit: 10
Value: 4
15. Double-click on the second slider and set the following:
Name: # of Offsets
Rounding: Even
Lower Limit: 2
Upper Limit: 20
Value: 20
16. Connect the Number Slider (Offset Distance) to the Factor (F) input of
the Unit X component
17. Connect the Vector (V) output of the Unit X component to the Direction
(D) input of the Linear Array component
18. Connect the Number Slider (# of Offsets) to the Count (N) input of the
Linear Array component

(Insert Image)

19. Sets/Lists/Dispatch – Drag and drop the component onto the canvas
(Border Image)
20. Connect the Geometry (G) output of the Linear Array component to the
List (L) input of the Dispatch component
21. Params/Input/Panel – Drag and drop the component onto the canvas
(Border Image)
22. Double-click the panel and enter the following:
true
false
23. Connect the Panel to the Pattern (P) input of the Dispatch component
24. Curve/Division/Divide Curve – Drag and drop two Divide Curve
components onto the canvas
(Border Image)
25. Connect the List A (A) output of the Dispatch component to the Curve (C)
input of the First Divide Curve component
26. Connect the List B (B) output of the Dispatch component to the Curve (C)
input of the Second Divide Curve component
27. Params/Input/Number Slider – Drag and drop the Number Slider
component onto the canvas
28. Double-click on the Number slider and set the following:
Name: Divisions
Rounding: Integer
Lower Limit: 0
Upper Limit: 20
Value: 20
29. Connect the Number Slider (Divisions) to the Count (N) input of both
Divide Curve components.

(Insert Image)

30. Sets/Sequence/Cull Pattern – Drag and drop two Cull Pattern
components onto the canvas
(Border Image)
31. Connect the Points (P) output of the First Divide Curve component to the
List (L) input of the First Cull Pattern component
32. Connect the Points (P) output of the Second Divide Curve component to
the List (L) input of the Second Cull Pattern component
33. Params/Input/Panel – Drag and drop a Second Panel component onto the
canvas
34. Double-click the Scond panel and deselect: Multiline Data, Wrap Items,
and Special Codes. Then enter the following:
1
1
0
0
(Border Image)
35. Connect the Second Panel to the Pattern (P) input of the First Cull
Pattern component
36. Connect the Second Panel to the Pattern (P) input of the Second Cull
Pattern component
37. Right-click on the Pattern (P) input of the Second Cull Pattern component
and select Invert
38. Sets/List/Weave – Drag and drop the Weave component onto the canvas
(Border Image)
39. Connect the Second Panel to the Pattern (P) input of the Weave
component
40. Right-click the Pattern (P) input of the Weave component and select
reverse
41. Connect the List (L) output of the First Cull Pattern component to the
Stream 0 (0) input of the Weave component
42. Connect the List (L) output of the Second Cull Pattern component to the
Stream 0 (0) input of the Weave component
43. Curve/Spline/Nurbs Curve – Drag and drop the Nurbs Curve component
onto the canvas 
(Border Image)
44. Connect the Weave (W) output of the Weave component to the Vertices
(V) input of the Nurbs Curve component.

(Insert Image)

(Insert Image)

45. Surface/Freeform/Revolution – Drag and drop two Revolution
components onto the canvas
(Border Image)
46. Connect the Curve output of the Nurbs Curve component to the Profile
Curve (P) input of both Revolution components.
47. Right Click on Axis (A) input of both Revolution components and select
Graft.
48. Connect the List A (A) output of the Dispatch component to the Axis (A)
input of the First Revolution component
49. Connect the List B (B) output of the Dispatch component to the Axis (A)
input of the Second Revolution component

(Border Text)

(Insert Image)

(Insert Image)

###F.4.3.6 RAIL INTERSECTION DEFINITION
In this example, we will use some of Grasshopper’s tools for manipulating data
trees to retreive, reorganize, and interpolate the desired points contained in a
data tree and create a lattice of intersecting fins.

(Insert Image)

01. Start a new definition, type Ctrl+N (in Grasshopper)
02. Params/Geometry/Curve – Drag and drop three curve parameters onto
the canvas
03. Surface/Freeform/Sweep2 – Drag a Sweep2 component onto the canvas
04. Right-click the first curve parameter and select “Set one curve.” Select the
first rail curve in the Rhino viewport
05. Right-click the second curve parameter and select “Set one curve.” Select
the second rail curve in the Rhino viewport
06. Right-click the third curve parameter and select “Set one curve.” Select
the section curve in the Rhino viewport
07. Connect the outputs of the curve parameters to the Rail 1 (R1), Rail 2
(R2), and Sections (S) inputs respectively
(Border Image)
08. Params/Geometry/Surface – drag a surface parameter to the canvas
09. Connect the Brep (S) output of the Sweep2 component to the input of the
surface parameter

10. Right-click the surface parameter and select “Reparameterize”
(Border Image)
11. Maths/Domain/Divide Domain2 – drag and drop a Divide Domain2
component onto the canvas
(Border Text)(Border Image)
12. Params/Input/Number Slider – drag two number sliders onto the canvas
13. Double click the first slider and set the following:
Rounding: Integer
Lower Limit: 1
Upper Limit: 40
Value: 20
14. Set the same values on the second slider
15. Connect the output of the reparameterized surface parameter to the
Domain (I) input of the Divide Domain2 component
16. Connect the first number slider to the U Count (U) input of the Divide
Domain2 component
17. Connect the second number slider to the V Count (V) input of the Divide
Domain2 component
18. Surface/Util/Isotrim – Drag and drop the Isotrim component onto the
canvas
(Border Image)
19. Connect the Segments (S) output of the Divide Domain2 component to
the Domain (D) input of the Isotrim component
20. Connect the output of the surface parameter to the Surface (S) input of
the Isotrim component

(Insert Image)

21. Maths/Domain/Deconstruct Domain2 – Drag a Deconstruct Domain2
component onto the canvas
(Border Image)
22. Maths/Domain/Construct Domain2 – Drag a Construct Domain2
component to the canvas
(Border Image)
23. Params/Input/Graph Mapper – Drag a Graph Mapper to the canvas
(Border Image)
24. Sets/List/List Length – Drag a List Length component to the canvas
(Border Image)
25. Sets/Tree/Merge – Drag a Merge component to the canvas
(Border Image)
26. Sets/List/Split List – Drag a Split List component to the canvas
27. Connect the U min (U0) and U max (U1) outputs of the Deconstruct
Domain2 component to the Data 1 (D1) and Data 2 (D2) inputs of the
Merge component
28. Connect the Result (R) output of the Merge component to the input of
the Graph Mapper
29. Right-click the Graph Mapper and select “Bezier” under “Graph Types”
30. Connect a second wire from the U max (U1) output of the Deconstruct
Domain2 component to the List (L) input of the List Length component
31. Connect the Graph Mapper output to the List (L) input of the Split List
(Border Text)
32. Connect the Length (L) output of the List Length component to the Index
(i) input of the Split List component
33. Connect the List A (A) output of the Split List component to the U min
(U0) input of the Construct Domain2 component
34. Connect the List B (B) output of the Split List component to the U max
(U1) input of the Construct Domain2 component
35. Connect the V min (V0) output of the Deconstruct Domain2 component
to the V min (V1) input of the Construct Domain2 component
36. Connect the V max (V1) output of the Deconstruct Domain2 component
to the V max (V1) input of the Construct Domain2 component
(Border Text)

(Insert Image)

37. Connect the 2D Domain (I2) output of the Construct Domain2
component to the Domain (D) input of the Isotrim component, replacing
the existing connection
38. Surface/Analysis/Deconstruct Brep – Drag the deconstruct Brep
component onto the canvas
(Border Image)
39. Sets/Tree/Flip Matrix – Drag the Flip Matrix Component to the canvas
(Border Image)
40. Sets/Tree/Explode Tree – Drag the Explode Tree component to the
canvas
(Border Image)
41. Connect the Surface (S) output of the Isotrim component to the Brep (B)
input of the Deconstruct Brep component
(Border Text)
42. Connect the Vertices (V) output of the Deconstruct Brep component to
the Data (D) input of the Flip Matrix component
(Border Text)
43. Connect the Data (D) output of the Flip Matrix component to the Data
(D) input of the Explode Tree component
44. Right-click the Explode Tree component and select “Match Outputs”
45. Right-click the Data (D) input of the Explode Tree component and select

(Insert Image)

simplify
46. Curve/Primitive/Line – Drag and drop two line components onto the
canvas
47. Connect the Branch 0 {0} output of the Explode Tree component to the
Start Point (A) input of the first Line component
48. Connect the Branch 1 {1} output of the Explode Tree component to the
Start Point (A) input of the Second Line component
49. Connect the Branch 2 {2} output of the Explode Tree component to the
End Point (B) input of the first Line component
50. Connect the Branch 3 {3} output of the Explode Tree component to the
End Point (B) input of the Second Line component

(Insert Image)

51. Curve/Until/Join Curves – Drag and drop the Join Curves component to
the canvas
(Border Image)
52. Curve/Analysis/Control Points – Drag a Control Points component onto
the canvas
(Border Image)
53. Curve/Spline/Interpolate – Drag and drop the Interpolate component
onto the canvas
(Border Image)
54. Connect the Line (L) outputs of each Line component to the Curves (C)
input of the Join Curves component
(Border Text)
55. Connect the Curves (C) output of the Join Curves component to the
Curve (C) input of the Control Points component
56. Connect the Points (P) output of the Control Points component to the Vertices (V) input of the Interpolate component
57. Sets/Tree/Prune Tree – Drag and drop the Prune Tree component onto
the canvas
(Border Image)
58. Params/Input/Panel – Drag a Panel onto the canvas
59. Connect the Points (P) output of the Control Points component to the
Tree (T) input of the Prune Tree component
60. Double click the Panel and enter 4.
(Border Text)
61. Connect the output of the Panel to the Minimum (N0) input of the Prune
Tree component
62. Connect the Tree (T) output of the Prune Tree
63. Surface/Freeform/Extrude – Drag and drop the Extrude component onto
the canvas
64. Vector/Vector/Unit Y – Drag a Unit Y component onto the canvas
(Border Text)
65. Params/Input/Number Slider – Drag a number slider onto the canvas
66. Double click the Number Slider and set the following:
Rounding: Integer
Lower Limit: 1
Upper Limit: 5
Value: 3
67. Connect the Curve (C) output of the Interpolate component to the Base
(B) input of the Extrude component
68. Connect the Number Slider output to the Factor (F) input of the Unit Y
component
69. Connect the Unit Vector (V) output of the Unit Y component to the
Direction (D) input of the Extrude component 
(Border Text)

(Insert Image)

(Insert Image)
