<style>
h4{color: #008DB2}
td {background-color:white; vertical-align:top}
td img{
display: block;
margin-left: auto;
margin-right: auto;
}
td:nth-child(3){vertical-align:middle;}
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
