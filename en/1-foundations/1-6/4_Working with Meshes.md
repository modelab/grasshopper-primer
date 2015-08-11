## 1.6.4 Working With Meshes

#####In the last section, we looked at the basic structure of meshes. In this section, we will look at ways to manipulate meshes, as well as methods to extract data and information.


####1.6.4.1 Mesh Operations

**Smooth**

Smoother meshes can sometimes be achieved by simply increasing the number of faces, but this can often lead to extremely large datasets which take a long time to calculate. In these situations, the **Smooth** component can be used as an alternative to make meshes less jagged or faceted, without increasing vertex and face count.  The *strength*, *number of iterations*, and displacement *limit* can all be used to adjust how much smoothing occurs.

Attaching a boolean value to the input N provides option to skip naked vertices. A vertex is naked if it is connected to a naked edge, meaning the vertex is on the boundary of an open mesh. By toggling this option, you maintain the exterior boundary of a mesh while smoothing the interior edges.

![IMAGE](images/1-6-4/03_smooth.png)
>1. Initial box mesh with 3 faces removed
2. Smoothing after 2 iterations
3. 6 iterations
4. 25 iterations
5. 50 iterations

**Blur**

The **Blur** component acts in a similar way as smooth, except it only affect the vertex colors. It can also be used to reduce the jagged appearance of colored meshes, although to a lesser extent since it does not change any geometry.

![IMAGE](images/1-6-4/04_blur.png)
>1. Initial mesh
2. Blur after 1 iterations
3. 6 iterations
4. 12 iterations
5. 20 iterations

**Triangulate**

In order to ensure each face is planar, or to export a mesh to a different software that might not allow quad faces, it is sometimes necessary to triangulate a mesh. Using the **Triangulate** component, each quad face is replaced with two triangle faces by creating a new edge along the shortest diagonal of the face.

![IMAGE](images/1-6-4/05_triangulate.png)
>1. Original quad mesh
2. Added edges according to shortest distance across quads
3. Triangulated resultant mesh

**Weld**

In the last section, we noticed that a single vertex can be shared by adjacent faces and the normal for that vertex is calculated as the average of the adjacent faces, allowing a smoother visualization. However, it is sometimes desireable to have a sharp crease or seam, where one face does not smoothly transition to the next by way of the vertex normals. For this situation, it is necessary for each face to have its own vertex with its own normal. The list of vertices would contain at least two point that have the same coordinates, but different indices.

![IMAGE](images/1-6-4/06_simple-weld.png)
>1. Welded Faces - Both faces share vertices 1 and 2. The vertex normals at these vertices are the average of the face vertices.
2. Unwelded Faces - Duplicate vertices are added to the list. The faces do not share any vertex indices. Vertex 1 and vertex 6 each have the same coordinates, but different indices. They each have their own vertex normal

The process of taking two vertices that are in the same position and combining them into a single vertex is called *welding*, while *unwelding* takes a single vertex and splits it into two.

The **Weld** component uses a threshold angle as input. Any two adjacent faces with an angle less than the threshold angle will be welded together, resulting in common vertices with a normal that is the average of the adjacent faces. **Unweld** works in the opposite manner, where adjancent faces with an angle greater than the given threshold will be unwelded, and their shared vertices will be duplicated.

![IMAGE](images/1-6-4/07_box-weld.png)
>1. The default Box Mesh has 726 vertices. The mesh is creased at the corners of the box, where vertices are doubled up.
2. If the mesh is welded with an angle greater than 90 degrees, the resulting mesh faces are welded together, and the number of vertices has decreased to 602 while the number of faces has remained the same.
3. Looking at the previewed geometry, you can also notice that the rendered welded mesh has smoothed corners. 
4. Unlike the Smooth component which changes the mesh geometry, this mesh only appears smoother due to the vertex normal's role in rendering and shading. The edges and faces remain unaffected.


####1.6.4.2 Interactions with Other Objects

**Mesh Inclusion**

![IMAGE](images/1-6-4/inclusion.png)

This component tests to determine whether a given point is inside a mesh solid or not. This only works with closed meshes.

**Mesh Closest Point**

![IMAGE](images/1-6-4/mesh-closest-point.png)

This component will calculate the position on a mesh that is closest to a given point. This component outputs three pieces of data: the coordinates of the calculated point on the mesh, the index of the face which contains that point, and the mesh parameter. This parameter is extremely useful in conjunction with the **Mesh Eval** component discussed below.

![IMAGE](images/1-6-4/08_mesh-closest-point.png)
>1. Given a point in space, We want to find the closet point on the mesh
2. The face that contains the closest point is identified
3. The parameters of the closest point on the face are calculated

For those users interested in a little more detail about how a mesh is parameterized, we can take a closer look at how a mesh parameter is structured. In the image below, we have attached a panel to the parameter output of a **Mesh Closest Point** component. The mesh parameter is N[A,B,C,D]. The first number, N, is the index of the face which contains the calculated point. The following four numbers define the *barycentric* coordinates of the point within that face. The coordinates of the referenced point can be found by multiplying each vertex of the face by these numbers in order and then add the results together. (Of course, this is already done for us, and is given in the Point output). Also note that barycentric coordinates are only unique for triangular faces, meaning that on a quad face the same point could have multiple different parameterizations. Grasshopper avoids this problem by internally triangulating a quad face when calculating a parameter, the result of which is that of the four numbers in a mesh parameter, at least one of them will always be zero.

![IMAGE](images/1-6-4/09_barycentric.png)
>Barycentric Coordinates

**Mesh Eval**

![IMAGE](images/1-6-4/mesh-eval.png)

The **Mesh Eval** component uses a mesh parameter as an input and returns the referenced point, as well as the normal and color at that point. The color and normal are calculated as interpolations of the vertex colors and vertex normals, using the same barycentric coordinates as the mesh parameter.

**Mesh Join**

![IMAGE](images/1-6-4/mesh-join.png)

Unlike joining curves or NURBS surfaces, which require adjacency, any meshes can be joined into a single mesh, even meshes that are not touching. Recall that a mesh is simply a list of vertices, and a list of faces. There is no actual requirement for those faces to be connected. 

**Mesh Boolean**

Meshes in Grasshopper have a set of boolean operations similar to boolean operations for NURBS solids. Boolean operations are order specific, meaning that  switching the order of the input meshes A and B will result in different outputs.

![IMAGE](images/1-6-4/10_boolean.png)
>1. Mesh Difference
2. Mesh Intersection
3. Mesh Split
4. Mesh Union

**Intersect**

Intersections can be calculated between meshes and other objects: rays, planes, curves, and other meshes

![IMAGE](images/1-6-4/11_mesh-intersection.png)
>1. Mesh | Ray
2. Mesh | Plane
3. Mesh | Curve
4. Mesh | Mesh

**Occlusion**

As we have seen, one of the many uses of mesh geometry is for visualizations and creating shaded rendering based on face normals. When rendering, it also necessary to know when an object is in shadow behind another object. The **Occlusion** component in Grasshopper allows us to enter a set of sample points, along with occluding mesh geometry that will 'cast shadows', and a *view ray*, or vector, to indicate the direction that 'light' is coming from.

Such a process can be used to create shadows in rendering, or determine whether objects are hidden from a certain camera view.

![IMAGE](images/1-6-4/12_mesh-occlusion.png)
>1. View Ray to test for occlusion
2. Occluding mesh geometry
3. 'Hit' sample points
4. 'Occluded' sample points


####1.6.4.3 Exercise

{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Example files that accompany this section: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Example files that accompany this section: [Download](../../appendix/A-2/gh-files/1.6.4_working with meshes.gh)
{% endif %}

<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{width: 10%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>


||||
|--|--|--|
|01.| Start a new definition, type Ctrl-N (in Grasshopper)||
|02.| **Mesh/Primitive/Mesh Box** - Drag and drop a **Mesh Box** component onto the canvas|![IMAGE](images/1-6-4/mesh-box.png)|
|03.| **Params/Input/Number Slider** - Drag and drop a **Number Slider** component onto the canvas and set the following values: <ul>Rounding: Integer<br>Lower Limit: 1<br>Upper Limit: 10</ul>||
|04.| Connect the **Number Slider** to the X,Y, and Z inputs of the **Mesh Box**||
|05.| **Mesh/Util/Weld Mesh** - Drag and drop a **Weld Mesh** component onto the canvas|![IMAGE](images/1-6-4/weld-mesh.png)|
|06.| Connect the Mesh (M) output of the **Mesh Box** component to the Mesh (M) input of the **Weld Mesh** Component||
|07.| **Mesh/Util/Smooth Mesh** - Drag and drop a **Smooth Mesh** component onto the canvas|![IMAGE](images/1-6-4/smooth-mesh.png)|
|08.| Connect the Result (R) output of the **Weld Mesh** component to the Mesh (M) input of the **Smooth Mesh** component.||
|09.| **Params/Input/Number Slider** - Drag and drop a **Number Slider** component onto the canvas and set the following values: <ul>Rounding: Integer<br>Lower Limit: 1<br>Upper Limit:100</ul>|| 
|10.| Connect the Number Slider to the Iterations (I) input of the **Smooth Mesh** component|||

![IMAGE](images/1-6-4/exercise-01.png)
>Adjust the Iterations number slider and watch the smoothing of the cube mesh

||||
|--|--|--|
|11.| **Vector/Sets/Populate 3D** - Drag and drop a **Populate 3D** component onto the canvas|![IMAGE](images/1-6-4/populate-3d.png)
|12.| **Params/Input/Number Slider** - Drag and drop a **Number Slider component onto the canvas and set the following values: <ul>Rounding: Integer<br>Lower Limit: 1<br>Upper Limit: 10<br>Value: 4</ul>||
|13.| Connect the **Number Slider** to the Count (N) input of the **Populate 3D** component||
|14.| Connect the Result (R) output of the **Weld Mesh** component to the Region (R) input of the **Populate 3D** component||
|15.| **Mesh/Analysis/Mesh Closest Point** - Drag and drop a **Mesh Closest Point** component onto the canvas|![IMAGE](images/1-6-4/mesh-closest-point.png)|
|16.| Connect the Points (P) output of the **Populate 3D** component to the Point (P) input of the **Mesh Closest Point** component.||
|17.| Connect the Result (R) output of the **Weld Mesh** component to the Mesh (M) input of the **Mesh Closest Point** component.||
|18.| **Mesh/Util/Delete Faces** - Drag and drop a **Delete Faces** component onto the canvas|![IMAGE](images/1-6-4/delete-faces.png)|
|19.| Connect the Result (R) output of the **Weld Mesh** component to the Mesh (M) input of the **Delete Faces** component||
|20.| Connect the Indices (I) output of the **Mesh Closest Point** component to the Index (I) input of the **Delete Faces** component||
|21.| Connect the Mesh (M) output of the **Delete Faces** component to the Mesh (M) input of the the **Smooth Mesh** component|||

![IMAGE](images/1-6-4/exercise-02.png)
![IMAGE](images/1-6-4/exercise-03.png)
>By default, the **Smooth Mesh** component skips naked edges when smoothing a mesh.

||||
|--|--|--|
|22.|