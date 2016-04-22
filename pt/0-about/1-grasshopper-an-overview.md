## Grasshopper - an Overview

#####Grasshopper is a visual programming editor developed by David Rutten at Robert McNeel & Associates. As a plug-in for Rhino3D, Grasshopper is integrated with the robust and versatile modeling environment used by creative professionals across a diverse range of fields, including architecture, engineering, product design, and more. In tandem, Grasshopper and Rhino offer us the opportunity to define precise parametric control over models, the capability to explore generative design workflows, and a platform to develop higher-level programming logic – all within an intuitive, graphical interface.

The origins of Grasshopper can be traced to the functionality of Rhino3d
Version 4’s “Record History” button. This built-in feature enabled users to
store modeling procedures implicitly in the background as you go. If you lofted
four curves with the recording on and then edited the control points of one of
these curves, the surface geometry would update. Back in 2008, David posed
the question: “what if you could have more explicit control over this history?”
and the precursor to Grasshopper, Explicit History, was born. This exposed
the history tree to editing in detail and empowered the user to develop logical
sequences beyond the existing capabilities of Rhino3D’s built in features. Six
years later, Grasshopper is now a robust visual programming editor that can
be extended by suites of externally developed add-ons. Furthermore, it has
fundamentally altered the workflows of professionals across multiple industries
and fostered an active global community of users.

This primer focuses on Foundations, offering the core knowledge you need
to dive into regular use of Grasshopper and several on-ramps to how you
might go further within your own creative practice. Before diving into the
descriptions, diagrams, and examples supplied hereafter, let’s discuss what visual
programming is, the basics of the Grasshopper interface and terminology, as well
as the “live” characteristics of the viewport feedback and user experience.

Visual Programming is a paradigm of computer programming within which
the user manipulates logic elements graphically instead of textually. Some of
the most well-known textual programming languages such as C#, Visual Basic,
Processing – and more close to home for Rhino – Python and Rhinoscript require
us to write code that is bound by language-specific syntax. In contrast, visual
programming allows us to connect functional blocks into a sequence of actions
where the only “syntax” required is that the inputs of the blocks receive the data
of the appropriate type, and ideally, that is organized according to the desired
result – see the sections on Data Stream Matching and Designing with Data
Trees. This characteristic of visual programming avoids the barrier to entry
commonly found in trying to learn a new language, even a spoken one, as well as
foregrounds the interface, which for designers locates Grasshopper within more
familiar territory.

![IMAGE](images/python-and-gh-sine.png)
>This image show the process for drawing a sine curve in python and in Grashopper.

To access Grasshopper and its visual programming capabilities, we need to
download and install the program from the Grasshopper3D.com website.
Once installed, we can open the plug-in by typing “Grasshopper” into the Rhino
Command Line. The first time we do so in a new session of Rhino, we will be
presented with the Grasshopper loading prompt followed by the Grasshopper
editor window. We can now add functional blocks called “components” to the
“canvas,” connect them with “wires,” and save the entire “definition” in the .ghx
file format.

![IMAGE](images/gh-definition.png)
>A Grasshopper definition, made up of components connected with wires on the canvas

Once we’ve started to develop a Grasshopper definition and created “slider”
objects within our canvas to control geometry, we may naturally intuit the
connection we’ve made between this input object to what we see in Rhino’s
viewports. This connection is essentially live – if we adjust the grip on the slider,
we will see the consequences in that, within our definition an input somewhere
has changed and the program must be solved again to recompute a solution and
display the update. To our benefit when getting started with using Grasshopper,
the geometry preview we see is a lightweight representation of the solution
and it automatically updates. It is important to take note this connection now
as when your definitions become more complex, adeptly managing the flow of
data, the status of the “solver,” and what is previewed in the Rhino viewport will
prevent many unwanted headaches.

![IMAGE](images/flow.png)
>Program flow from left to right

####THINGS TO REMEMBER
* Grasshopper is a graphical algorithm editor that is integrated with
Rhino3D’s modeling tools.
* Algorithms are step by step procedures designed to perform an operation.
* You use Grasshopper to design algorithms that then automate tasks in
Rhino3D.
* An easy way to get started if you are unclear how to perform a specific
operation in Grasshopper would be to try manually and incrementally
creating an algorithm using Rhino commands.

As you begin first exploring Grasshopper or further building your skills, you have
joined the global Grasshopper community, one that is full of active members
from many fields, with diverse experience levels. The forum at Grasshopper3D.
com is a useful resource for posing questions, sharing findings, and gaining
knowledge. This is a community that we have held dear as we’ve written this
primer and watched Grasshopper develop over the years. Welcome!