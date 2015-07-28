## 1.6.2 What is a Mesh?

#####A Mesh is a collection of quadrilaterals and triangles that represents a surface or solid geometry. This section discusses the structure of a mesh object, which includes vertices, edges, and faces, as well as additional characterstics such as colors and normals that can be used to refine a mesh.

####1.6.2.1 Basic Anatomy of a Mesh

At their most basic, meshes are simply a collection of points that are grouped into polygons. The points of a mesh are called *vertices*, while the polygons are called *faces*. To create a mesh, then, we need a minimum of two parts:

1. A list of vertices
2. A system of grouping those vertices into faces

**Vertices**

The vertices of a mesh are simply a list of points. Recall that in Grasshopper, a *list* is a collection of objects and each object in the list has an *index* which describes that objects position in a list. The index of the vertices is very important when constructing a mesh, or getting information about the structure of a mesh.

![IMAGE]()
>1. A collection of points are labeled with their index.
2. In Grasshopper, these points are stored as a list. Each vertex has an Index that gives its location within the list.

**Faces**

A face is created by specifying an ordered list of either three or four vertices. We already have the list of vertices that make up the mesh, so instead of providing individual points to define a face, we instead simply use the index of the vertices. This also allows us to use the same vertex in more than one face.

![IMAGE]()
>1. A Triangle Face made with indices 0,1, and 2
2. A Quad Face made with indices 1,2,3, and 4

In Grasshopper, we can create faces with either three or four vertices. These can be created with the **Mesh Triangle** and **Mesh Quad** components. The input for these components are integers that correspond to the index of the vertices we want to use for a face. By connecting a **Panel** to the output of these components, we can see that a triangular face is represented as T{A;B;C}, and a quad face as Q{A;B;C;D}. 

![IMAGE]()
>1. A triangular face with indices 0,1, and 2
2. A quad face with indicies 0,1,2, and 3

You may have been wondering about the fact that these two components so far do not have any connection to the actual list of vertices. If you right click on these components, you will also see that there is no option to 'Preview' them. This is because in Grasshopper a face is only a list of numbers, and only defines a specfic geometry when combined with a list of vertices to make a mesh. In addition to using these two components to construct mesh faces, we can also create faces manually by editing a **Panel** component and entering the appropriate format for either triangular or quad faces.

![IMAGE]()
>1. A face created using a **Mesh Triangle** component
2. A face created using a **Panel**

It is extremely important to pay attention to the order of the indices when constructing a mesh face. The face will be constructed by connecting the vertices listed in order, so the quad face Q{0,1,2,3} and Q{1,0,2,3} are very different, despite using the same four vertices.

![IMAGE]()
>1. A quad face with indices 0,1,2,3
2. A quade with indicies 1,0,2,3

To create an actual Mesh, we can use the **Construct Mesh** component. We can connect our list of vertices to the V input, and a face (or a list of faces) to the F input. (The component also has room for a Colour input, which is discussed below.) Connect a panel to the output of a **Construct Mesh** and notice that we get information about the number of faces and number of indices.

####1.6.2.2 Mesh Attributes

While the vertices and faces make up the basic structure of a mesh, there are other attributes that are associated with the mesh as well. Some of these attributes are determined by the Vertex and Face structure of the mesh, such as edges and normals. Another attribute, vertex colour, can be modified and adjusted.

**Edges**

The Edges of a Mesh are lines connecting any two consecutive vertices in a face. Notice that some edges are shared between multiple faces, while other edges are only adjacent to one face. The number of faces an edge is adjacent to is called the *Valence* of that edge.

![IMAGE]()
>1. Edge with valence of 1
2. Edge with valence of 2

We can use the **Mesh Edges** component to get the edges of a mesh. Notice that the mesh edges are split into three categories:

1. E1 - 'Naked Edges' have a valence of 1. They make up the external boundary of a mesh.
2. E2 - 'Interior Edges' have a valence of 2. 
3. E3 - 'Non-Manifold Edges' have a valence of 3 or greater. Meshes that contain such structure are called "Non-Manifold", and are discussed in more detail below.

Sometimes it is more useful to have the full boundary of each face. For this, we can use the **Face Boundaries** component. This will return a list of polylines.

![IMAGE]()
>1. **Mesh Edges** Component
2. **Face Boundaries** Component

**Face Normals**

The **Face Normals** component will return a list of center points and normals for each face. In the case of triangular faces, we know that any three points must be planar, so the normal will be perpendicular to that plane, but how do we know which direction ('up' or 'down') the normal will be pointing? Once again, the *order* of the indicies is crucial here. Mesh faces in Grasshopper are defined counter-clockwise, so a face with indices {0,1,2} will be 'flipped' as compared to the indicies {1,0,2}. Another way to visualize this is to use the *Right-Hand-Rule*. 

![IMAGE]()
>1. Normal in one direction 
2. Normal in other direction
3. Right hand rule???

Grasshopper also allows quad faces, in which case the 4 points will not always be planar. For these faces, it is slightly more complicated to determine the normal and center point. The center point of such a face will be simply the average of the coordinates of the 4 vertices. To calculate the normal of a quad face, we need to first trianglulate the quad by splitting it into two planar triangles. The normal of the overall face is then the average of the two normals, weighted according to the area of the two triangles.

**Vertex Normals**

In addition to the face normals, it is also possible to calculate normals for each vertex of a mesh. For a vertex that is only used in a single face, the normal at the vertex will be equal to the normal of the face. If a vertex has multiple adjacent faces, the vertex normal is calculated by taking the average of the faces. While less intuitive than face normals, vertex normals are important for smooth visualization of meshes. You might notice that even though a triangulated mesh is composed of planar facets, such a mesh can still appear smooth and rounded when shaded in Rhino. Using the vertex normals allows this smooth visualization.

![IMAGE]()
>

**Colour**

As an additional attribute, each vertex can also be assigned a color. These colors are used for visualitizations, with each face rendered as an interpolation of the vertex colous. For example, the image below shows triangle face with vertex colors of Red, Green, and Blue.

![IMAGE]()
>COLORS!


####1.6.2.3 Mesh Characteristics

**Open vs Closed**

It is often necessary to know whether a mesh is a *closed* mesh which represents a volumetric solid, or an *open* mesh that is just represents a 2-dimensional surface. We can use the **Mesh Edges** component to help determine this. If none of the edges of a mesh have a valence of 1 (if the E1 output is *null*), then we know that all the edges are 'Interior Edges' and the mesh does not have an external boundary edge, and is therefore a closed mesh.

On the other hand, if there exist 'Naked Edges', then those edges must be on a boundary of the mesh, and the mesh is not closed.

![IMAGE]()
>Images showing closed and open meshes

**Manifold vs Non-Manifold**

An edge with a valence greater than 2 would mean that at least three faces meet along a single edge. A mesh can also be considered Non-Manifold if there are any vertices which are shared by multiple faces, but do not share any edges. This situtation occurs when two faces meet at a single point rather than along an edge. Non-Manifold meshes are much more complicated to work with, and should generally be avoided.

![IMAGE]()
>Examples of non-manifold meshes


####1.6.2.4 Exercise

In this exercise, we use a basic Mesh primitive, perform a transformation on the vertices, and then assign a color based on the normal vectors to approximate the rendering process.

EXERCISE