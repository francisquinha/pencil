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

The nearest thing we could find related to the Logical View in Pencil2d was the roadmap diagram.

<div align="center">
	<img src= roadmap.jpeg height=200>
</div>

The roadmap suggests how key components of the Editor, from a user standpoint, should be connected without being too specific.

By using Enterprise Architect reverse engineering capabilities we made a simplified class diagram with the classes that seemed to establish the project "core". This diagram does not convey tools/functionalities that Pencil2D offers, but rather the base skeleton that supports/manages them. After this diagram we present a close up on some of its  classes to present concise functionalities.

>Legend:
<br>Orange - "core classes"
<br>Green - "core classes" that are Qt related
<br>Full Arrow - a subclass of pointed class
<br>Other Arrows - class has a field of pointed class
<br>plus sign - public field
<br>minus sig - private field
<br>sharp sign - protected field


<div align="center">
	<img src= class_diagram.png  height=420>
</div>
<div align="center">
	<img src= class_diagram_base_tool_closeup.png height=300>
	<img src= class_diagram_BitmalNobjectNlayer_closeup.png height=300>
	<img src= class_diagram_MainWindow2AndScribbleArea_closeup.png height=300>
</div>

## Process View in Pencil2D

## Physical View in Pencil2D

## Development View in Pencil2D

### Component Diagram

This project uses external libraries whose main focus is to read from and write to ZIP archives. It is provided by the component QuaZIP, QuaZIP allows the access to files inside ZIP archives using QIODevice API (contained from the Qt Framework).
The Qt framework provides the graphical interface that is going to support the visualization of the canvas. Basically it is the interface between the user and the software.

<div align="center">
	<img src= Component.png height=500>
</div>

## Use Case View

## Conclusion

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
