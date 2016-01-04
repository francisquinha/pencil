# Software Architecture in Pencil2D

## Introduction

Software Architecture is the process of creating and documenting high level structures for a software system. Theses structures detail the software elements, the relations among these elements and the properties of both the elements and the relations. The major objective of this architectural design is to satisfy all software requirements, whether they are functional or non functional.

In order to represent the architecture of a given piece of software, one uses a set of views or perspectives. Each view is directed at a specific set of concerns and follows certain conventions, namely the type of UML diagrams used to describe the software. Although there are many different view models, that are commonly used, we focus our attention in the **4 + 1 View Model** described in the next section.


### The 4 + 1 View Model

This view model was presented by Philippe Kruchten in his 1995 paper entitled *Architectural Blueprints—The “4+1” View Model of Software 
Architecture*.

<div align="center">
	<img src= 4+1.gif height=400>
</div>

As the name implies, it is compromised of 4 main views, as well as another view whose objective is to unify and relate the others. The four views are:

- **Logical View** - which contains the object model, often represented by a class diagram.
- **Process View** - which is concerned with the different processes of the system and how they communicate, often represented by a sequence diagram.
- **Physical View** - which represents the software components on the physical layer and the physical connections between them; the diagram used is the deployment diagram.
- **Development View** - which shows the system from the point of view of a programmer, making use of a component diagram.

Finally, relating these 4 views, there is a **Scenarios** diagram, also known as use cases diagram, illustrating the different roles of each view.


## Logical View in Pencil2D

The nearest thing we could find related to the Logical View in Pencil2d was the following roadmap diagram:

<div align="center">
	<img src= roadmap.jpeg height=400>
</div>

It suggests how key components of the Editor, from a user standpoint, should be connected without being too specific.

Using the reverse engineering capabilities of Enterprise Architect we made a simplified class diagram with the classes that seemed to establish the "core" of the project. This diagram does not convey tools/functionalities that Pencil2D offers, but rather the base skeleton that supports/manages them.

<div align="center">
	<img src= class_diagram.png  width=700>
</div>

>Caption:
<br>orange - "core classes"
<br>green - "core classes" that are Qt related
<br>full arrow - a subclass of pointed class
<br>other arrows - class has a field of pointed class
<br>plus sign - public field
<br>minus sig - private field
<br>sharp sign - protected field

We also have diagrams with a close up view on some classes, in order to present concise functionalities. The first of these diagrams details the base tool. We can see how each tool was built as a subclass of this base tool.

<div align="center">
	<img src= class_diagram_base_tool_closeup.png width=700>
</div>

The next class diagram presents a greater detail on layers, key frames and the bitmap image.

<div align="center">
	<img src= class_diagram_BitmalNobjectNlayer_closeup.png width=700>
</div>

Finally, we have a better understanding of the several widgets and preferences that have a main window field, as well as the color widgets and their relation with the scribble area. 

<div align="center">
	<img src= class_diagram_MainWindow2AndScribbleArea_closeup.png width=700>
</div>

## Process View in Pencil2D

Regarding the Process View we thought that most Activity Diagrams would be too similar to the use cases unless they were very detailed. With that said, there are some important features in Pencil2D that can't be inferred by the UseCases Diagram like the blending of a bitmap layer keyframes or how the autosave system works.

To avoid redundant and/or over detailed exposition we present a simple activity diagram that presents the start of the application. The diagram exposes subtle features like translation and options loading. 

<div align ="center">
	<img src= pencilstart_activitydiagram.png height=50% width=50%>
</div>

## Physical View in Pencil2D

### Deployment Diagram

Although this project has not seen the green light for its full release, there is the opportunity for the anyone who wishes to make use of Pencil2D  without having to get the source code and compile it so they can run it on their machines. The Beta Version is available for Mac and Windows on BitBucket and Linux on TuxFamily. Was also released at least a nightly build to the public and more could be released at any storage website.

<div align ="center">
	<img src= Deployment.png height=100% width=100%>
</div>

## Development View in Pencil2D

### Component Diagram

This project uses external libraries whose main focus is to read from and write to ZIP archives. It is provided by the component QuaZIP, QuaZIP allows the access to files inside ZIP archives using QIODevice API (contained from the Qt Framework).
The Qt framework provides the graphical interface that is going to support the visualization of the canvas. Basically it is the interface between the user and the software.

<div align="center">
	<img src= Component.png height=500 >
</div>

## Scenarios View

###Use Cases Diagram

A use cases diagram was already presented in [SoftwareRequirementsSpecification.md](https://github.com/francisquinha/pencil/blob/master/ESOF-docs/SoftwareRequirementsSpecification.md). We reproduce it here again, as the final diagram of the 4 + 1 View Model.

<div align="center">
	<img src= PossivelDiagramaDeCasosDeUtilizacaoParaOestadoActualPrint.png height=600>
</div>

## Conclusion

As we saw, each section of the 4 + 1 View Model presents a different perspective on the same software architecture. Sometimes, it is not easy to clearly delimit what belongs in each perspective. Indeed, the same diagram type (like the class diagram), albeit with different details, can be used in several views. Also, depending on the specific software, there may not be a lot to say or show in some of these views. For example, a server-client architecture certainly has a lot more detail on the deployment diagram than a simple client application.

Given the nature of our research, which picks up an ongoing software project and tries to understand the Software Engineering that may have been behind that project, it is easier to feel that our observations may be somewhat off. This was certainly the case regarding the Software Architecture behind Pencil2D.

## Bibliography

1. Github, "Pencil2d/Pencil". [Online].
Last access on 18/10/2015 at: https://github.com/pencil2d/Pencil.

2. Pencil2D, "Pencil2D - opensource animation software". [Online].
Last access on 18/10/2015 at:  http://www.pencil2d.org/.

3. FEUP - MIEIC - Engenharia de Software - 2015/2016, "ARCHITECTURAL DESIGN- PART I". [Online]. Last access on 29/10/2015 at: http://moodle.up.pt/pluginfile.php/71055/mod_resource/content/2/ArchitecturalDesign%20-%20Part1.pdf.

4. FEUP - MIEIC - Engenharia de Software - 2015/2016, "ARCHITECTURAL DESIGN PART II - ARCHITECTURE MODELING WITH UML". [Online]. Last access on 29/10/2015 at: http://moodle.up.pt/pluginfile.php/71062/mod_resource/content/3/ArchitecturalDesign%20-%20Part2.pdf.

4. Ian Sommerville, Software Engineering, 9th Edition, Pearson, 2011.

5. Architectural Blueprints — The “4+1” View Model of Software Architecture, Philippe Kruchten, IEEE Software 12 (6), pp. 42-50, 1995. 


## Authors

[Ângela Cardoso](mailto:angela.cardoso@fc.up.pt)

[Bruno Madeira](mailto:up201306619@fe.up.pt)

[José Teixeira](mailto:up201303930@fe.up.pt)
