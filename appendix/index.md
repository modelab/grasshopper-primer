<style>
h4{color: #008DB2}
td {background-color:white; vertical-align:top}
td img{
display: block;
width: 100%;
max-width: 150px;
margin-left: auto;
margin-right: auto;
}
td:nth-child(1){width:150px;}
td:nth-child(2){width:500px;}
td:nth-child(3){
vertical-align:middle;
width:150px;
}
thead {display: none}
</style>

## 2.1. Index
<a name="index"></a>

#####This index provides additional information on all the components used in this primer, as well as other components you might find useful. This is just an introduction to over 500 components in the Grasshopper plugin.

Parameters
--

####Geometry
||||
|--|--|--|
|<a name="PGCrv"></a>P.G.Crv|Curve Parameter<br>Represents a collection of Curve geometry. Curve geometry is the common denominator of all curve types in Grasshopper.|![IMAGE](images/PGCrv.png)|
|<a name="PGCircle"></a>P.G.Circle|Circle Parameter<br>Represents a collection of Circle primitives.|![IMAGE](images/PGCircle.png)|
|<a name="PGGeo"></a>P.G.Geo|Geometry Parameter<br>Represents a collection of 3D Geometry.|![IMAGE](images/PGGeo.png)|
|<a name="PGPipeline"></a>P.G.Pipeline|Geometry Pipeline<br>Defines a geometry pipeline from Rhino to Grasshopper.|![IMAGE](images/PGPipeline.png)|
|<a name="PGPt"></a>P.G.Pt|Point Parameter<br>Point parameters are capable of storing persistent data. You can set the persistent records through the parameter menu.|![IMAGE](images/PGPt.png)|
|<a name="PGSrf"></a>P.G.Srf|Surface Parameter<br>Represents a collection of Surface geometry. Surface geometry is the common denominator of all surface types in Grasshopper.|![IMAGE](images/PGSrf.png)|

####Primitive
||||
|--|--|--|
|<a name="PPBool"></a>P.P.Bool|Boolean Parameter<br>Represents a collection of Boolean (True/False) values.|![IMAGE](images/PPBool.png)|
|<a name="PPD"></a>P.P.D|Domain Parameter<br>Represents a collection of one-dimensional Domains. Domains are typically used to represent curve fragments and continuous numeric ranges. A domain consists of two numbers that indicate the limits of the domain, everything in between these numbers is part of the domain.|![IMAGE](images/PPD.png)|
|<a name="PPD2"></a>P.P.D2|Domain<sup>2</sup> Parameter<br>Contains a collection of two-dimensional domains. 2D Domains are typically used to represent surface fragments. A two-dimensional domain consists of two one-dimensional domains.|![IMAGE](images/PPD2.png)|
|<a name="PPID"></a>P.P.ID|Guid Parameter<br>Represents a collection of Globally Unique Identifiers. Guid parameters are capable of storing persistent data. You can set the persistent records through the parameter menu.|![IMAGE](images/PPID.png)|
|<a name="PPInt"></a>P.P.Int|Integer Parameter<br>Represents a collection of Integer numeric values. Integer parameters are capable of storing persistent data. You can set the persistent records through the parameter menu.|![IMAGE](images/PPInt.png)|
|<a name="PPNum"></a>P.P.Num|Number Parameter<br>Represents a collection of floating point values. Number parameters are capable of storing persistent data. You can set the persistent records through the parameter menu.|![IMAGE](images/PPNum.png)|
|<a name="PPPath"></a>P.P.Path|File Path<br>Contains a collection of file paths.|![IMAGE](images/PPPath.png)|

####Input
||||
|--|--|--|
|<a name="PIToggle"></a>P.I.Toggle|Boolean Toggle<br>Boolean (true/false) toggle.|![IMAGE](images/PIToggle.png)|
|<a name="PIButton"></a>P.I.Button|Button<br>Button object with two values. When pressed, the button object returns a true value and then resets to false.|![IMAGE](images/PIButton.png)|
|<a name="PISwatch"></a>P.I.Swatch|Color Swatch<br>A swatch is a special interface object that allows for quick setting of individual color values. You can change the color of a swatch through the context menu.|![IMAGE](images/PISwatch.png)|
|<a name="PIGrad"></a>P.I.Grad|Gradient Control<br>Gradient controls allow you to define a color gradient within a numeric domain. By default the unit domain (0.0 ~ 1.0) is used, but this can be adjusted via the L0 and L1 input parameters. You can add color grips to the gradient object by dragging from the color wheel at the upper left and set color grips by right clicking them.|![IMAGE](images/PIGrad.png)|
|<a name="PIGraph"></a>P.I.Graph|Graph Mapper<br>Graph mapper objects allow you to remap a set of numbers. By default the {x} and {y} domains of a graph function are unit domains (0.0 ~ 1.0), but these can be adjusted via the Graph Editor. Graph mappers can contain a single mapping function, which can be picked through the context menu. Graphs typically have grips (little circles), which can be used to modify the variables that define the graph equation. By default, a graph mapper objects contains no graph and performs a 1:1 mapping of values.|![IMAGE](images/PIGraph.png)|
|<a name="PISlider"></a>P.I.Slider|Number Slider<br>A slider is a special interface object that allows for quick setting of individual numeric values. You can change the values and properties through the menu, or by double-clicking a slider object. Sliders can be made longer or shorter by dragging the rightmost edge left or right. Note that sliders only have an output (ie. no input).|![IMAGE](images/PISlider.png)|
|<a name="PIPanel"></a>P.I.Panel|Panel<br>A panel for custom notes and text values. It is typically an inactive object that allows you to add remarks or explanations to a Document. Panels can also receive their information from elsewhere. If you plug an output parameter into a Panel, you can see the contents of that parameter in real-time. All data in Grasshopper can be viewed in this way. Panels can also stream their content to a text file.|![IMAGE](images/PIPanel.png)|
|<a name="PIList"></a>P.I.List|Value List<br>Provides a list of preset values from which to choose.|![IMAGE](images/PIList.png)|

####Utilities
||||
|--|--|--|
|<a name="P.U.Cin"></a>P.U.Cin|Cluster Input<br>Represents a cluster input parameter.|![IMAGE](images/PUCin.png)|
|<a name="P.U.COut"></a>P.U.COut|Cluster Output<br>Represents a cluster input parameter.|![IMAGE](images/PUCOut.png)|
|<a name="P.U.Dam"></a>P.U.Dam|Data Dam<br>Delay data on its way through the document.|![IMAGE](images/PUDam.png)|
|<a name="P.U.Jump"></a>P.U.Jump|Jump<br>Jump between different locations.|![IMAGE](images/PUJump.png)|
|<a name="P.U.Viewer"></a>P.U.Viewer|Param Viewer<br>A viewer for data structures.|![IMAGE](images/PUViewer.png)|
|<a name="P.U.Scribble"></a>P.U.Scribble|Scribble<br>A quick note.|![IMAGE](images/PUScribble.png)|

Maths
--

####Domain
||||
|--|--|--|
|<a name="M.D.Bnd"></a>M.D.Bnd|Bounds<br>Create a numeric domain which encompasses a list of numbers.|![IMAGE](images/MDBnd.png)|
|<a name="M.D.Consec"></a>M.D.Consec|Consecutive Domains<br>Create consecutive domains from a list of numbers.|![IMAGE](images/MDConsec.png)|
|<a name="MDDom"></a>M.D.Dom|Construct Domain<br>Create a numeric domain from two numeric extremes.|![IMAGE](images/MDDom.png)|
|<a name="MDDom2Num"></a>M.D.Dom2Num|Construct Domain²<br>Create a two-dimensional domain from four numbers.|![IMAGE](images/MDDom2Num.png)|
|<a name="MDDeDomain"></a>M.D.DeDomain|Deconstruct Domain<br>Deconstruct a numeric domain into its component parts.|![IMAGE](images/MDDeDomain.png)|
|<a name="MDDeDom2Num"></a>M.D.DeDom2Num|Deconstruct Domain²<br>Deconstruct a two-dimensional domain into four numbers.|![IMAGE](images/MDDeDom2Num.png)|
|<a name="MDDivide"></a>M.D.Divide|Divide Domain²<br>Divides a two-dimensional domain into equal segments.|![IMAGE](images/MDDivide.png)|
|<a name="MDInc"></a>M.D.Inc|Includes<br>Test a numeric value to see if it is included in the domain.|![IMAGE](images/MDInc.png)|
|<a name="MDReMap"></a>M.D.ReMap|Remap Numbers<br>Remap numbers into a new numeric domain.|![IMAGE](images/MDReMap.png)|


####Operators
||||
|--|--|--|
|<a name="MOAdd"></a>M.O.Add|Addition<br>Mathematical addition.|![IMAGE](images/MOAdd.png)|
|<a name="MODiv"></a>M.O.Div|Division<br>Mathematical division.|![IMAGE](images/MODiv.png)|
|<a name="MOEquals"></a>M.O.Equals|Equality<br>Test for (in)equality of two numbers.|![IMAGE](images/MOEquals.png)|
|<a name="MOAnd"></a>M.O.And|Gate And<br>Perform boolean conjunction (AND gate). Both inputs need to be True for the result to be True.|![IMAGE](images/MOAnd.png)|
|<a name="MONot"></a>M.O.Not|Gate Not<br>Perform boolean negation (NOT gate).|![IMAGE](images/MONot.png)|
|<a name="MOOr"></a>M.O.Or|Gate Or<br>Perform boolean disjunction (OR gate). Only a single input has to be True for the result to be True.|![IMAGE](images/MOOr.png)|
|<a name="MOLarger"></a>M.O.Larger|Larger Than<br>Larger than (or equal to).|![IMAGE](images/MOLarger.png)|
|<a name="MOMultiply"></a>M.O.Multiply|Multiplication<br>Mathematical multiplication.|![IMAGE](images/MOMultiply.png)|
|<a name="MOSmaller"></a>M.O.Smaller|Smaller Than<br>Larger than (or equal to).|![IMAGE](images/MOSmaller.png)|
|<a name="MOSimilar"></a>M.O.Similar|Similarity<br>Test for similarity of two numbers.|![IMAGE](images/MOSimilar.png)|
|<a name="MOSub"></a>M.O.Sub|Subtraction<br>Mathematical subtraction.|![IMAGE](images/MOSub.png)|

####Script
||||
|--|--|--|
|<a name="MSEval"></a>M.S.Eval|Evaluate<br>Evaluate an expression with a flexible number of variables.|![IMAGE](images/MSEval.png)|
|<a name="MSExpression"></a>M.S.Expression|Expression<br>Evaluate an expression.|![IMAGE](images/MSExpression.png)|

####Trig
||||
|--|--|--|
|<a name="MTCos"></a>M.T.Cos|Cosine<br>Compute the cosine of a value.|![IMAGE](images/MTCos.png)|
|<a name="MTDeg"></a>M.T.Deg|Degrees<br>Convert an angle specified in radians to degrees.|![IMAGE](images/MTDeg.png)|
|<a name="MTRad"></a>M.T.Rad|Radians<br>Convert an angle specified in degrees to radians.|![IMAGE](images/MTRad.png)|
|<a name="MTSin"></a>M.T.Sin|Sine<br>Compute the sine of a value.|![IMAGE](images/MTSin.png)|

####Utilities
||||
|--|--|--|
|<a name="MUAvr"></a>M.U.Avr|Average<br>Solve the arithmetic average for a set of items.|![IMAGE](images/MUAvr.png)|
|<a name="MUPhi"></a>M.U.Phi|Golden Ratio<br>Returns a multiple of the golden ratio (Phi).|![IMAGE](images/MUPhi.png)|
|<a name="MUPi"></a>M.U.Pi|Pi<br>Returns a multiple of Pi.|![IMAGE](images/MUPi.png)|

Sets
--

####List
||||
|--|--|--|
|<a name="SLCombine"></a>S.L.Combine|Combine Data<br>Combine non-null items out of several inputs.|![IMAGE](images/SLCombine.png)|
|<a name="SLCrossRef"></a>S.L.CrossRef|Cross Reference<br>Cross Reference data from multiple lists.|![IMAGE](images/SLCrossRef.png)|
|<a name="SLDispatch"></a>S.L.Dispatch|Dispatch<br>Dispatch the items in a list into two target lists. List dispatching is very similar to the [Cull Pattern] component, with the exception that both lists are provided as outputs.|![IMAGE](images/SLDispatch.png)|
|<a name="SLIns"></a>S.L.Ins|Insert Items<br>Insert a collection of items into a list.|![IMAGE](images/SLIns.png)|
|<a name="SLItem"></a>S.L.Item|List Item<br>Retrieve a specific item from a list.|![IMAGE](images/SLItem.png)|
|<a name="SLLng"></a>S.L.Lng|List Length<br>Measure the length of a list. Elements in a list are identified by their index. The first element is stored at index zero, the second element is stored at index one and so on and so forth. The highest possible index in a list equals the length of the list minus one.|![IMAGE](images/SLLng.png)|
|<a name="SLLong"></a>S.L.Long|Longest List<br>Grow a collection of lists to the longest length amongst them.|![IMAGE](images/SLLong.png)|
|<a name="SLSplit"></a>S.L.Split|Split List<br>Split a list into separate parts.|![IMAGE](images/SLSplit.png)|
|<a name="SLReplace"></a>S.L.Replace|Replace Items<br>Replace certain items in a list.|![IMAGE](images/SLReplace.png)|
|<a name="SLRev"></a>S.L.Rev|Reverse List<br>Reverse the order of a list. The new index of each element will be N-i where N is the highest index in the list and i is the old index of the element.|![IMAGE](images/SLRev.png)|
|<a name="SLShift"></a>S.L.Shift|Shift List<br>Offset all items in a list. Items in the list are offset (moved) towards the end of the list if the shift offset is positive. If Wrap equals True, then items that fall off the ends are re-appended.|![IMAGE](images/SLShift.png)|
|<a name="SLShort"></a>S.L.Short|Shortest List<br>Shrink a collection of lists to the shortest length amongst them.|![IMAGE](images/SLShort.png)|
|<a name="SLSift"></a>S.L.Sift|Sift Pattern<br>Sift elements in a list using a repeating index pattern.|![IMAGE](images/SLSift.png)|
|<a name="SLSort"></a>S.L.Sort|Sort List<br>Sort a list of numeric keys. In order for something to be sorted, it must first be comparable. Most types of data are not comparable, Numbers and Strings being basically the sole exceptions. If you want to sort other types of data, such as curves, you’ll need to create a list of keys first.|![IMAGE](images/SLSort.png)|
|<a name="SLWeave"></a>S.L.Weave|Weave<br>Weave a set of input data using a custom pattern. The pattern is specified as a list of index values (integers) that define the order in which input data is collected.|![IMAGE](images/SLWeave.png)|

####Sets
||||
|--|--|--|
|<a name="SSCulli"></a>S.S.Culli|Cull Index<br>Cull (remove) indexed elements from a list.|![IMAGE](images/SSCulli.png)|
|<a name="SSCull"></a>S.S.Cull|Cull Pattern<br>Cull (remove) elements in a list using a repeating bit mask. The bit mask is defined as a list of Boolean values. The bit mask is repeated until all elements in the data list have been evaluated.|![IMAGE](images/SSCull.png)|
|<a name="SSDup"></a>S.S.Dup|Duplicate Data<br>Duplicate data a predefined number of times. Data can be duplicated in two ways, either copies of the list are appended at the end until the number of copies has been reached, or each item is duplicated a number of times before moving on to the next item.|![IMAGE](images/SSDup.png)|
|<a name="SSJitter"></a>S.S.Jitter|Jitter<br>Randomly shuffles a list of values. The input list is reordered based on random noise. Jittering is a good way to get a random set with a good distribution. The jitter parameter sets radius of the random noise. If jitter equals 0.5, then each item is allowed to reposition itself randomly to within half the span of the entire set.|![IMAGE](images/SSJitter.png)|
|<a name="SSRandom"></a>S.S.Random|Random<br>Generate a list of pseudo random numbers. The number sequence is unique but stable for each seed value. If you do not like a random distribution, try different seed values.|![IMAGE](images/SSRandom.png)|
|<a name="SSRange"></a>S.S.Range|Range<br>Create a range of numbers. The numbers are spaced equally inside a numeric domain. Use this component if you need to create numbers between extremes. If you need control over the interval between successive numbers, you should be using the [Series] component.|![IMAGE](images/SSRange.png)|
|<a name="SSRepeat"></a>S.S.Repeat|Repeat Data<br>Repeat a pattern until it reaches a certain length.|![IMAGE](images/SSRepeat.png)|
|<a name="SSSeries"></a>S.S.Series|Series<br>Create a series of numbers. The numbers are spaced according to the {Step} value. If you need to distribute numbers inside a fixed numeric range, consider using the [Range] component instead.|![IMAGE](images/SSSeries.png)|

####Tree
||||
|--|--|--|
|<a name="STExplode"></a>S.T.Explode|Explode Tree<br>Extract all the branches from a tree.|![IMAGE](images/STExplode.png)|
|<a name="STFlatten"></a>S.T.Flatten|Flatten Tree<br>Flatten a data tree by removing all branching information.|![IMAGE](images/STFlatten.png)|
|<a name="STFlip"></a>S.T.Flip|Flip Matrix<br>Flip a matrix–like data tree by swapping rows and columns.|![IMAGE](images/STFlip.png)|
|<a name="STGraft"></a>S.T.Graft|Graft Tree<br>Typically, data items are stored in branches at specific index values (0 for the first item, 1 for the second item, and so on and so forth) and branches are stored in trees at specific branch paths, for example: {0;1}, which indicates the second sub-branch of the first main branch. Grafting creates a new branch for every single data item.|![IMAGE](images/STGraft.png)|
|<a name="STMerge"></a>S.T.Merge|Merge<br>Merge a bunch of data streams.|![IMAGE](images/STMerge.png)|
|<a name="STPath"></a>S.T.Path|Path Mapper<br>Perform lexical operations on data trees. Lexical operations are logical mappings between data paths and indices which are defined by textual (lexical) masks and patterns.|![IMAGE](images/STPath.png)|
|<a name="STPrune"></a>S.T.Prune|Prune Tree<br>Removes all branches from a Tree that carry a special number of Data items. You can supply both a lower and an upper limit for branch pruning.|![IMAGE](images/STPrune.png)|
|<a name="STSimplify"></a>S.T.Simplify|Simplify Tree<br>Simplify a tree by removing the overlap shared amongst all branches.|![IMAGE](images/STSimplify.png)|
|<a name="STTStat"></a>S.T.TStat|Tree Statistics<br>Get some statistics regarding a data tree.|![IMAGE](images/STTStat.png)|
|<a name="STUnflatten"></a>S.T.Unflatten|Unflatten Tree<br>Unflatten a data tree by moving items back into branches.|![IMAGE](images/STUnflatten.png)|

Vector
--

####Grid
||||
|--|--|--|
|<a name="VGHexGrid"></a>V.G.HexGrid|Hexagonal<br>2D grid with hexagonal cells.|![IMAGE](images/VGHexGrid.png)|
|<a name="VGRecGrid"></a>V.G.RecGrid|Rectangular<br>2D grid with rectangular cells.|![IMAGE](images/VGRecGrid.png)|
|<a name="VGSqGrid"></a>V.G.SqGrid|Square<br>2D grid with square cells|![IMAGE](images/VGSqGrid.png)|

####Point
||||
|--|--|--|
|<a name="VPPt"></a>V.P.Pt|Construct Point<br>Construct a point from {xyz} coordinates.|![IMAGE](images/VPPt.png)|
|<a name="VPpDecon"></a>V.P.pDecon|Deconstruct<br>Deconstruct a point into its component parts.|![IMAGE](images/VPpDecon.png)|
|<a name="VPDist"></a>V.P.Dist|Distance<br>Compute Euclidean distance between two point coordinates.|![IMAGE](images/VPDist.png)|

####Vector
||||
|--|--|--|
|<a name="VVX"></a>V.V.X|Unit X<br>Unit vector parallel to the world {x} axis.|![IMAGE](images/VVX.png)|
|<a name="VVY"></a>V.V.Y|Unit Y<br>Unit vector parallel to the world {y} axis.|![IMAGE](images/VVY.png)|
|<a name="VVVec2Pt"></a>V.V.Vec2Pt|Vector 2Pt<br>Create a vector between two points.|![IMAGE](images/VVVec2Pt.png)|

Curve
--

####Analysis
||||
|--|--|--|
|<a name="CACP"></a>C.A.CP|Control Points<br>Extract the nurbs control points and knots of a curve.|![IMAGE](images/CACP.png)|

####Division
||||
|--|--|--|
|<a name="CDDivide"></a>C.D.Divide|Divide Curve<br>Divide a curve into equal length segments.|![IMAGE](images/CDDivide.png)|

####Primitive
||||
|--|--|--|
|<a name="CPCir"></a>C.P.Cir|Circle<br>Create a circle defined by base plane and radius.|![IMAGE](images/CPCir.png)|
|<a name="CPCir3Pt"></a>C.P.Cir3Pt|Circle 3Pt<br>Create a circle defined by three points.|![IMAGE](images/CPCir3Pt.png)|
|<a name="CPCirCNR"></a>C.P.CirCNR|Circle CNR<br>Create a circle defined by center, normal and radius.|![IMAGE](images/CPCirCNR.png)|
|<a name="CPLine"></a>C.P.Line|Line SDL<br>Create a line segment defined by start point, tangent and length.|![IMAGE](images/CPLine.png)|
|<a name="CPPolygon"></a>C.P.Polygon|Polygon<br>Create a polygon with optional round edges.|![IMAGE](images/CPPolygon.png)|

####Spline
||||
|--|--|--|
|<a name="CSIntCrv"></a>C.S.IntCrv|Interpolate<br>Create an interpolated curve through a set of points.|![IMAGE](images/CSIntCrv.png)|
|<a name="CSKinkCrv"></a>C.S.KinkCrv|Kinky Curve<br>Construct an interpolated curve through a set of points with a kink angle threshold.|![IMAGE](images/CSKinkCrv.png)|
|<a name="CSNurbs"></a>C.S.Nurbs|Nurbs Curve<br>Construct a nurbs curve from control points.|![IMAGE](images/CSNurbs.png)|
|<a name="CSPLine"></a>C.S.PLine|PolyLine<br>Create a polyline connecting a number of points.|![IMAGE](images/CSPLine.png)|

####Util
||||
|--|--|--|
|<a name="CUExplode"></a>C.U.Explode|Explode<br>Explode a curve into smaller segments.|![IMAGE](images/CUExplode.png)|
|<a name="CUJoin"></a><C.U.Join|Join Curves<br>Join as many curves as possible.|![IMAGE](images/CUJoin.png)|
|<a name="CUOffset"></a>C.U.Offset|Offset<br>Offset a curve with a specified distance.|![IMAGE](images/CUOffset.png)|

Surface
--

####Analysis
||||
|--|--|--|
|<a name="SADeBrep"></a>S.A.DeBrep|Deconstruct Brep<br>Deconstruct a brep into its constituent parts.|![IMAGE](images/SADeBrep.png)|

####Freeform
||||
|--|--|--|
|<a name="SFBoundary"></a>S.F.Boundary|Boundary Surfaces<br>Create planar surfaces from a collection of boundary edge curves.|![IMAGE](images/SFBoundary.png)|
|<a name="SFExtr"></a>S.F.Extr|Extrude<br>Extrude curves and surfaces along a vector.|![IMAGE](images/SFExtr.png)|
|<a name="SFExtrPt"></a>S.F.ExtrPt|Extrude Point<br>Extrude curves and surfaces to a point.|![IMAGE](images/SFExtrPt.png)|
|<a name="SFLoft"></a>S.F.Loft|Loft<br>Create a lofted surface through a set of section curves.|![IMAGE](images/SFLoft.png)|
|<a name="SFRevSrf"></a>S.F.RevSrf|Revolution<br>Create a surface of revolution.|![IMAGE](images/SFRevSrf.png)|
|<a name="SFSwp2"></a>S.F.Swp2|Sweep2<br>Create a sweep surface with two rail curves.|![IMAGE](images/SFSwp2.png)|

####Primitive
||||
|--|--|--|
|<a name="SPBBox"></a>S.P.BBox|Bounding Box<br>Solve oriented geometry bounding boxes.|![IMAGE](images/SPBBox.png)|

####Util
||||
|--|--|--|
|<a name="SUSDivide"></a>S.U.SDivide|Divide Surface<br>Generate a grid of {uv} points on a surface.|![IMAGE](images/SUSDivide.png)|
|<a name="SUSubSrf"></a>S.U.SubSrf|Isotrim<br>Extract an isoparametric subset of a surface.|![IMAGE](images/SUSubSrf.png)|

Mesh
--

####Triangulation
||||
|--|--|--|
|<a name="MTVoronoi"></a>M.T.Voronoi|Voronoi<br>Planar voronoi diagram for a collection of points.|![IMAGE](images/MTVoronoi.png)|

Transform
--

####Affine
||||
|--|--|--|
|<a name="TARecMap"></a>T.A.RecMap|Rectangle Mapping<br>Transform geometry from one rectangle into another.|![IMAGE](images/TARecMap.png)|

####Array
||||
|--|--|--|
|<a name="TAArrLinear"></a>T.A.ArrLinear|Linear Array<br>Create a linear array of geometry.|![IMAGE](images/TAArrLinear.png)|

####Morph
||||
|--|--|--|
|<a name="TMMorph"></a>T.M.Morph|Box Morph<br>Morph an object into a twisted box.|![IMAGE](images/TMMorph.png)|
|<a name="TMSBox"></a>T.M.SBox|Surface Box<br>Create a twisted box on a surface patch.|![IMAGE](images/TMSBox.png)|

Display
--

####Color
||||
|--|--|--|
|<a name="DCHSL"></a>D.C.HSL|Colour HSL<br>Create a colour from floating point {HSL} channels.|![IMAGE](images/DCHSL.png)|

####Dimensions
||||
|--|--|--|
|<a name="DDTag"></a>D.D.Tag|Text tags<br>A text tag component allows you to draw little Strings in the viewport as feedback items. Text and location are specified as input parameters. When text tags are baked they turn into Text Dots.|![IMAGE](images/DDTag.png)|
|<a name="DDTag3D"></a>D.D.Tag3D|Text Tag 3D<br>Represents a list of 3D text tags in a Rhino viewport|![IMAGE](images/DDTag3D.png)|

####Preview
||||
|--|--|--|
|<a name="DPPreview"></a>D.P.Preview|Custom Preview<br>Allows for customized geometry previews.|![IMAGE](images/DPPreview.png)|

####Vector
||||
|--|--|--|
|<a name="DVPoints"></a>D.V.Points|Point List<br>Displays details about lists of points.|![IMAGE](images/DVPoints.png)|


