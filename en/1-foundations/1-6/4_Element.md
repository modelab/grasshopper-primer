### 1.6.4 Element* 

#####Element\* is a mesh geometry plugin for Grasshopper, enabling mesh creation, analysis, transformation, subdivision, and smoothing. Element* provides access to mesh topology data using the Plankton half-edge data structure for polygon meshes.

####1.6.4.1 Half Edge Data

In the beginning of this chapter, we looked at how Grasshopper defines a mesh using a Face-Vertex data structure. This is a relatively simple data structure, and is widely used in.

####1.6.4.2 Analyse

**Element Mesh Closest Point**

Unlike Grasshopper's **Mesh Closest Point** component, this component also calculates the normal and color at the outputed point, eliminating the need for a  **Mesh Eval** component and simplfying the canvas workspace.

**Element Mesh Evaluate**
The built in Grasshopper **Mesh Eval** component requires a mesh parameter as an input, which can be extracted from a **Mesh Closest Point** component, but which can be difficult to construct manually. Element's closest point component allows direct input of the index of a mesh face and the barycentric coordinates. 

Note - barycentric coordinates are defined such that they always add to 1. If the input values of U,V, and M do not add to 1, this component will maintain the ratio of the three values, while normalizing them to add to 1. For example, if you had the input values of 2,2, and 4, the mesh parameter would be calculated as {0.25;0.25;0.5}

**Element Mesh Sample Plus**

This component is used to quickly extract color information from a mesh. It returns the Alpha, Red, Green, Blue, Hue, Saturation, and Luminosity values of the inputed points. If the given points are not on the mesh, this component will calculate the closest point.

####1.6.4.3 Data

####1.6.4.4 Primitives

####1.6.4.5 Smooth

####1.6.4.6 Subdivide

####1.6.4.7 Transform

####1.6.4.8 Utility

####1.6.4.9 Exercise

