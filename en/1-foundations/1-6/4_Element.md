### 1.6.4 Element* 

#####Element\* is a mesh geometry plugin for Grasshopper, enabling mesh creation, analysis, transformation, subdivision, and smoothing. Element* provides access to mesh topology data using the Plankton half-edge data structure for polygon meshes.

####1.6.4.1 Half Edge Data

In the beginning of this chapter, we looked at how Grasshopper defines a mesh using a Face-Vertex data structure. This is a relatively simple data structure and is widely used in applications that use meshes, but can be computationally inefficient for more advanced algorithms. The Element\* add-on restructures the mesh using Half-Edge data in order to allow for efficient queries of adjacent vertices, faces, and edges, which can vastly improve on algorithm speed and performance.

The half-edge data structure is a representation for a mesh in which each edge is split up into two half-edges with opposite directions. This allows explicit and implicit access to data from one mesh element to adjacent elements.

![IMAGE](images/1-6-4/01_half-edge.png)
>1. Half-Edge
2. Face
3. Vertex
4. Next
5. Half-Edge Face

####1.6.4.2 Analyse

![IMAGE](images/1-6-4/02_analyse-components.png)
>1. Mesh Closest Point
2. Mesh Evaluate
3. Mesh Sample Plus

**Element\* Mesh Closest Point**

Unlike Grasshopper's **Mesh Closest Point** component, this component also calculates the normal and color at the outputed point, eliminating the need for a  **Mesh Eval** component and simplfying the canvas workspace.

**Element\* Mesh Evaluate**

The built in Grasshopper **Mesh Eval** component requires a mesh parameter as an input, which can be extracted from a **Mesh Closest Point** component, but which can be difficult to construct manually. Element's closest point component allows direct input of the index of a mesh face and the barycentric coordinates. 

Note - barycentric coordinates are defined such that they always add to 1. If the input values of U,V, and W do not add to 1, this component will maintain the ratio of the three values while normalizing them. For example, if you had the input values of 2, 2, and 4 the mesh parameter would be calculated as {0.25;0.25;0.5}

**Element\* Mesh Sample Plus**

This component is used to quickly extract color information from a mesh. It returns the Alpha, Red, Green, Blue, Hue, Saturation, and Luminosity values of the inputed points. If the given points are not on the mesh, this component will calculate the closest point.



####1.6.4.3 Data

![IMAGE](images/1-6-4/03_data-components.png)
>1. Data Visualizer
2. Edge Neighbors
3. Face Neighbors
4. Vertex Neighbors


**Element\* Data Visualizer**

This component is used to help visualize the half-edge data of the faces of an input mesh. 

**Element\* Edge Neighbors**

This component provides access to the adjacency data structured according to the edges of the input mesh. The output data is provided as a tree with one branch for each edge in the mesh. It provides the end points, center ponts of adjacent faces, neighboring edges as line objects, and the center points of the neighboring faces.

**Element\* Face Neighbors**

This component is similar to the others in this section, but the data is organized in a tree according to the faces of the mesh, with one branch per face. The outputs are the vertices of each face, the adjacent edges, and the centers of neighboring faces.

Note - This component only allows triangulated meshes.

**Element\* Vertex Neighbors**

This component outputs neighboring vertices, edges, and face centers structured in a tree according to the vertices of the mesh.

![IMAGE](images/1-6-4/04_neighbors-diagram.png)
>1. **Edge Neighbors** - End vertices, adjacent faces, neighboring edges, and neighboring faces
2. **Face Neighbors** - Adjacent vertices, adjacent edges, and neighboring faces
3. **Vertex Neighbors** - Adjacent Edges, adjactent faces, and neighboring vertices

####1.6.4.4 Primitives

Element\* provides four additional mesh primitives: the Icosohedron, Dodecahedron, Octahedron, and Tetrahedron. These components take a single number as input for the radius, and produce meshes centered at the origin, and composed of one face per side. With the addition of the Cube, which is already availible through Grasshopper's built-in primitives, these make up the five Platonic solids. 

![IMAGE](images/1-6-4/05_primitives.png)
>1. Dodecahedron
2. Icosohedron
3. Octahedron
4. Tetrahedron
5. EDIT - THE COMPONENTS ARE OUT OF ORDER IN THE IMAGE

####1.6.4.5 Smooth

**Element\* Smooth** provides an optimized smoothing algorithm that is more efficient than Grasshopper's **Smooth Mesh** for large datasets. It makes use of the Lapacian Smoothing algorithm for Half-Edge structured meshes. It does not change the topology or vertex count of welded meshes, but will weld together any unwelded meshes.

![IMAGE](images/1-6-4/06_smooth.png)

####1.6.4.6 Subdivide

**Element\* Catmull Clark Subdivision** 

This is a recursive subdivision defined by the Catmull Clark algorithm. We can specify the number of iterations as well as how to handle naked edge conditions.


**Element\* Constant Quad**

This subdivison component will create an all quad mesh by adding a face for each edge of the mesh.

![IMAGE](images/1-6-4/07_subdivide.png)
>1. Catmull Clark subdivision
2. Constant Quad subdivision

####1.6.4.7 Transform

![IMAGE](images/1-6-4/08_transform-components.png)
>1. Mesh Windown
2. Mesh Frame
3. Mesh Thicken
4. Mesh Offset

These components provide a number of different transformations described below. Each component has the additional capability of accepting per-vertex distance data to allow for variations of the transformation magnitudes across the mesh.

**Element\* Mesh Window**

Reconstructs a new mesh on the inside of a face based on an offset value.

**Element\* Mesh Frame**

Outputs a frame around mesh faces. Each resultant face will have a new hole in the center.

**Element\* Mesh Thicken**

This component will thicken an input mesh along the vertex normals, and according to provided distance values.

**Element\* Mesh Offset**

This component creats an offset of the input mesh based on the vertex normals.

![IMAGE](images/1-6-4/09_transform-examples.png)
>1. Mesh Window
2. Mesh Frame
3. Icosohedron transformed with mesh frame, then thickend and subdivided

####1.6.4.8 Utility

The **Element\* Mesh Combine and Clean** component will combine multiple meshes together and weld the vertices and vertex normals according to an input threshold angle.

####1.6.4.9 Exercise

