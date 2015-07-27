## 1.6.3 Working With Meshes

#####In the last section, we looked at the basic structure of meshes. In this section, we will look at ways to create and manipulate meshes, as well as methods to extract data and information.

####1.6.3.1 Creating

There are three fundamental ways of creating meshes in Grasshopper:
1. Starting with a mesh primitive
2. Manually constructing a mesh from faces and vertices
3. Converting NURBS geometry into a mesh

**Primitives** - Grasshopper comes with a few simple mesh primitive components:
1. **Mesh Box** - This primitve requires a Box object as an input which provides the size and location, as well as X,Y, and Z values that determine how many faces to divide the box into.
2. **Mesh Plane** - This primitive requires a Rectangle input to determine the size and location of the plane, as well as W and H values to determine the number of faces.
3. **Mesh Sphere** - This primitive requires a base plane to determine the center of the sphere, a radius for the size, and U and V values to determine the number of faces.
4. **Mesh Sphere Ex** - Also known as a Quadball, this primitive creates a sphere composed of six patches, which are subdivided according to the C input

![IMAGE]()
>Mesh primitives

**Construct Mesh** 

We have already seen this component in the last section. The **Construct Mesh** component can be used to directly create a mesh from a list of vertices and a list of faces (and an optional list of vertex colors). Constructing an entire mesh manually can be extremely tedious, so this component is more often used with an existing list of faces and vertices which have been extracted using a **Deconstruct Mesh** component on an existing mesh.

**NURBS to mesh**

Perhaps the most common method of creating a complex mesh is to generate one based off of NURBS geometry. This can be done with the **Mesh Brep** component. This component also has an optional Settings input, which can be set by using one of the built in *Speed*, *Quality*, or *Custom* Settings components, or by right-clicking the S input and selecting "Set Mesh Options". For efficient use of meshes, it is often necessary to refine this mesh by using various strategies such as rebuilding, smoothing, or subdividing. Some of these techniques will be discussed later in this Primer.

![IMAGE]()
>Example of NURBS to mesh

NOTE: it is generally much easier to convert from a NURBS geometry to a mesh object rather than the other way around. While the UV coordinates of a NURBS surface are straightforward to convert to quad faces of a mesh, the opposite is not necessarily true, since a mesh might contain a combination of triangles and quads in a way that is not simple to extract a UV coordinate system out of. 


####1.6.3.2 Mesh Operations

**Cull Faces**

FOR ARMON TO WRITE

**Smooth**

Smoother meshes can sometimes be achieved by simply increases the number of faces, but this can often lead to extremely large datasets which take a long time to calculate. In these situations, the **Smooth** component can be used as an alternative to make meshes less jagged or faceted.  The *strength*, *number of iterations*, and displacement *limit* can all be to adjust how much smoothing occurs.

![IMAGE]()
>Image showing smoothing

**Blur**

The **Blur** component acts in a similar way as smooth, except it only affect the vertex colors. It can also be used to reduce the jagged appearance of colored meshes, although to a lesser extent since it does not change any geometry.

![IMAGE]()
>Image showing blur

**Triangulate**

In order to ensure each face is planar, or to export a mesh to a different software that might not allow quad faces, it is sometimes necessary to triangulate a mesh. Using the **Triangulate** component, each quad face is replaced with two triangle faces. 

![IMAGE]()
>Image showing triangluated mesh

**Weld**

In the last section, we noticed that a single vertex can be shared by adjacent faces and the normal for that vertex is calculated as the average of the two faces, allowing a smoother visualization. However, it is sometimes desireable to have a sharp crease or seam, where one face does not smoothly transition to the next by way of the vertex normals. For this situation, it is necessary for each face to have its own vertex with its own normal. The list of vertices would contain at least two point that have the same coordinates, but different indices.

![IMAGE]()
>Faces with shared vertex and list of vertices
>Faces with coincident vertex and list of vertices

The process of taking two vertices that are in the same position and combining them into a single vertex is called *welding*, while *unwelding* takes a single vertex and splits it into two.

The **Weld** component uses an input angle A. Any two adjacent faces with an angle less than the input angle will be welded together, resulting in common vertices with a normal that is the average of the adjacent faces. 

![IMAGE]()
>1. The default Box Mesh has 726 vertices. The mesh is creased at the corners of the box, where vertices are doubled up.
2. If the mesh is welded with an angle greater than 90 degrees, the resulting mesh faces are welded together, and the number of vertices has decreased to 602 while the number of faces has remained the same.
3. Looking at the previewed geometry, you can also notice that the rendered welded mesh has smoothed corners. 
4. Unlike the Smooth component which changes the mesh geometry, this mesh only appears smoother due to the vertex normal's role in rendering and shading. The edges and faces remain unaffected.


####1.6.3.3 Interactions with Other Objects

**Intersect**

**Mesh Boolean**

**Mesh Eval**

**Closest Point/Inclusion**

####1.6.3.4 Exercise
