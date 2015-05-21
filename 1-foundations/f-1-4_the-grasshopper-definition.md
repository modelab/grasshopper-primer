## F.1.4 THE GRASSHOPPER DEFINITION

#####Grasshopper Definitions have a Program Flow that represents where to start program execution, what to do in the middle and how to know when program execution is complete.

###F.1.4.0 PROGRAM FLOW
Grasshopper visual programs are executed from left to right. Reading the graph
relative to the wired connections from upstream to downstream provides
understanding about the Program Flow.

(Insert Image)

###F.1.4.1 THE LOGICAL PATH
All of the objects and the wires connecting the objects represent the logical
graph of our program. This graph reveals the flow of data, dependencies of any
input to its wiired output. Any time our graph changes, sometimes referrred to
as being “dirtied,” every downstream connection and object will be updated.

(Insert Image)

(Insert Image)

(Insert Image)

