### 1.4.2. What is a List?

#####It’s helpful to think of Grasshopper in terms of flow, since the graphical interface is designed to have data flow into and out of specific types of components. However, it is the data that define the information flowing in and out of the components. Understanding how to manipulate list data is critical to understanding the Grasshopper plug-in.

Grasshopper generally has two types of data: persistent and volatile. Even though the data types have different characteristics, typically Grasshopper stores this data in an array, a list of variables.

When storing data in a list, it’s helpful to know the position of each item in that list so that we can begin to access or manipulate certain items. The position of an item in the list is called its index number.

![IMAGE](images/1-4-2/1-4-2_001-list-index.png)
>1. List Item
2. Index

The only thing that might seem odd at first is that the first index number of a list is always 0; not 1. So, when we talk about the first item of a list, we actually mean the item that corresponds to index number 0.

For example, if we were to count the number of fingers we have on our right hand, chances are that you would have counted from 1 to 5. However, if this list has been stored in an array, then our list would have counted from 0 to 4. Note, that we still have 5 items in the list; it’s just that the array is using a zero-based counting system. The items being stored in the list don’t just have to be numbers. They can be any data type that Grasshopper supports, such as points, curves, surfaces, meshes, etc.

Often times the easiest way to take a look at the type of data stored in a list is to connect a Text Panel (Params/Input/Panel) to the output of a particular component. By default, the Text Panel automatically shows all index numbers to the left side of the panel and displays the data items on the right side of the panel. The index numbers will become a crucial element when we begin working with our lists. You can turn the index numbers on and off by right-clicking on the Text Panel and clicking on the “Draw Indices” item in the sub-menu. For now, let’s leave the entry numbers turned on for all of our text panels.

![IMAGE](images/1-4-2/1-4-2_002-list-menu.png)
