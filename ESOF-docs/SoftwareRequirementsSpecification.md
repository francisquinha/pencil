# Software Requirements Specification in Pencil2D

## Introduction

The software requirements specification should be done at the beginning of any software development. Its goal is to document the purpose of the software and to describe how it will interact with the users, the system and other applications. Thus, even if the requirements are updated throughout the development, which these days is quite common, it is important to have a firm grasp on what they are before progressing to other stages, in order to avoid misunderstandings between clients and developers.

There are two general types of requirements: **functional** and **nonfunctional** requirements. The first are the functions that the software should be able to perform, also known as capabilities. The nonfunctional requirements are the ones that impose restrictions on the solution, such as quality or development requirements.

In order to reach a specification document, one typically progresses along several activities, going from a more general overview to a very detailed description. After a quick analysis aiming to check the feasibility of the software, the first activity is requirement **elicitation**. At this stage, through interviews, joint application design sessions, questionnaires, brainstorming, etc, the requirements are collected from the client. Use cases, which are examples of how the user will interact with the software, should be obtained. At this point, the requirements are very high level.

Once the elicitation process is complete, one should proceed to the **analysis**, where a more precise understanding of the requirements is achieved. At this point the requirements obtained will be on a lower level. The system requirements are derived from the previous information, as well as the software requirements, by breaking down the system requirements into the different software components. One should check the requirements for completeness, correctness, consistency, unambiguity, verifiability, necessity and feasibility. Besides analyses, this is the stage of requirement negotiation. A debate ensues between the stakeholders, in order to arrive at a list of agreed requirements, usually considering mainly the necessity and the feasibility.

The next stage is **specification**, where a detailed document containing all requirements is produced. UML diagrams and other artifacts are typically included in this document. There is a standard template for specification documents that should be followed as closely as possible.

Finally, one can proceed to requirement **validation**, with the goal of guaranteeing that the requirements define the system according to the real objective of the client. This is very important as fixing a requirement error at this stage costs considerably less than doing so after product delivery.

To aid in requirement collection, prototypes are used. These are primitive versions of the system, maybe even done in paper, designed to determine what the system will look like and what it will do, offering some limited capabilities. These prototypes may be done through the whole development, but a first vertical system prototype is usually done in the beginning.

Remitting to the first document created under the ESOF scope, 'Software Processes', this topic has already been briefly touched. An [important reference](http://www.pencil2d.org/2010/06/the-vision-for-pencil-by-pascal-naidon/) to the project specification for Pencil2D was also given then. The present document aims to dive further into the details on this subject.

##Requirements in Pencil2D

One of the main figures of the original Pencil project states that this is a personal non-profit oriented project that is open for other people to develop and use. This creates a sort of  duality in the analysis because we can access the Pencil2D requirements from different perspectives. It is possible to think of Pencil2D, referring to the overall software ramifications such as forks like bluePencil and not to the actual project, as a software whose specification arises from the intersections between public demand and developers self set goals. It is also possible to think of Pencil2D in the context of its origins or individually or in context of the public demand for such an application. We will try to approach the 'main branch perspective' where we can consider the initial stated requirements (original Pencil) and it's new iteration (current Pencil2D) requirements according to the public contribution.
 
Pencil2D, the project, started from one of these intersections by picking up a existing project, Pencil, and giving it continuity. After that, specifications may have been refined and slightly changed by the public contribution and feedback. It is possible that some requirements are only specified in some branch/fork and, after a merge, the main project assimilates the result without having to make aditional specifications.
 
 
###Original Pencil Requirements

There is some [documentation](http://www.pencil2d.org/2010/06/the-vision-for-pencil-by-pascal-naidon/) on requirements that dates from the original Pencil project on the Pencil2D website. This documentation clarifies the motives and aspirations behind Pencil and tries to establish future directions to the project, according to the creator belief "that an application like Pencil should be designed with some personal vision and goal to remain effective". It appears that there was no entity besides main developers working on Pencil at the time that act as stakeholder, and, since the project is being continued by new developers, we can take this documentation as being the first requirement elicitation of the current Pencil2D, that establishes initial goals for the project.

The exposed requirements are mainly user and system related. The project already presumes the use of C++ in the development, since it is using the Qt framework, and software requirements are not the main focus although they are briefly touched. Being done by the main developers some 'technical' requirements related to the application functionality may have been easier to assert due too the understanding of the topics and the already established project vision. The clarity of these specifications seems to confirm this, it establishes a well-defined set of features for the main application. 

In regards to non-functional requirements, internal quality and software requirements, modular design is referred in 'future development' of Pencil (this 'future' at the time of the documentation), to allow the implementation of secondary usages, but it does not expand much beyond that. There are some 'paper' prototypes of these modules and how they should appear to the user, as well as some considerations about their integration (or not) into a main application, but nothing stays explicitly defined or planned. 

The following image is one example of the mentioned 'paper' prototypes.
 
 <div align="center">
	<img src= pascal-vision-d-008.jpg height=200>
</div>
  
###Pencil2D Requirements
 
In its primordial development there were already some tools and features implemented, although after the rebirth of Pencil being now known as Pencil2D its particular focus was to produce working versions for OS X, Windows and Linux, the bug fixing and handling the codebase (simplify it). There was no clear idea if it was supposed to add new features to the pre-existing ones. One can only get hints from the [TODO list] (https://github.com/pencil2d/pencil/blob/master/TODO.md) and the [Issues tracker] (https://github.com/pencil2d/pencil/issues).

This is an open-source project, even though its creator did not want to shape it in the vision of another person it does not exclude the fact that it is open for new ideas that might come up. From the time this report is being written, there have been requests for new features so the requirement elicitation tends to be a bit chaotic, in the way that in the middle of its development there might appear some pertinent opinions whether a particular feature should be added. The process of requirement identification and analysis/negotiation is handled at the same time via GitHub's issue tracker when diverse entities (mostly individual users) submit a report on whether new feature would be feasible to be added.

We take the example from a [request issued in the 19th of February of 2015] (https://github.com/pencil2d/pencil/issues/288):
>Hey there. I've enjoyed using Pencil on my Linux systems and am elated to know that development is continuing on a fork of it.

>https://www.youtube.com/watch?v=xU4nQuRw-e4

>I'd like to know if there could be an option to export our creations to the WebM format, for its slim form and relative lack of patent encumbrance.
>It'll make for easy uploading to sites like Youtube.
>Alternatively, if it'd be possible to upload our cartoons directly to Youtube, that'd be just as good.

This is a good example when an user wants the developers to add a new important feature to increase the versatility of Pencil2D. Nevertheless there are still plenty of bugs from the date that this request has been issued, it is a very good example of the software requirement life-cycle.
 
##Use Cases Diagram

The following image presents a possible use cases diagram that could have been done as specification for the current Pencil2D.

<div align="center">
	<img src= PossivelDiagramaDeCasosDeUtilizacaoParaOestadoActualPrint.png height=500>
</div>

The presented diagram is somewhat detailed and due to some more specific features like the "onion skin" for example (which is a display option more relevant than others because of the practical utility) we could still branch the presented graph a little more. Overall, it displays a very accurate representation of the use cases without being over detailed. 

Looking at the original specifications there are some minor details that could appear differently in the diagram. The original specification suggest using 4 sub layers per layer or allowing to define hierarchies and groups of layers. This, in a detailed view, changes the diagram by allowing extra actions that would need to be specified later in an Activity Diagram when addressing the Software Architecture.

There are also some additional details regarding sound and media resources. The project may still incorporate some of these features in the future, but since we cannot know for sure if there are plans for them in the project we do not present these features in the diagram. 

Overall, the presented diagram, remains faithful to the original requirements which means that Pencil2D has not strayed from the original vision and goals of Pencil.

## Conclusion

It appears that the requirements in Pencil2D were treated in a very informal manner. Clearly there is no software specification document, not in the usual sense at least. User feedback and forum discussions can work as social observation for the need of particular features. They may also help to form a light requirement analysis and/or validation but no formal or consistent procedure seems to exist for these usual steps.

Considering the nature of the project it probably would not benefit of a more formal approach. Being a relatively small project, presently developed mainly by one contributor, a formal or strict procedure could waste time needlessly and work against the flexibility that the current methodology has, by forcing the incremental approach to use wider development intervals and consequently reducing the productivity of development.

From another perspective, the recent phases of development of the project, which consisted mainly in sleuthing bug fixes, may have been avoided or reduced with a more formal approach and by establishing well defined quality and/or non-functional requirements in the early days of the project.

The requirements in Pencil seem to address only the software architecture, not the feasibility and quality. So topics like the testability of the software are of relevance, specially so when it is an open-source project that can have a long development time. It is plausible that the current Pencil2D works as a solution to the lack of these requirements since it mentions improving the code as one of the goals. Since the initial Pencil the requirements evolved to focus on making the current Pencil2D more stable and complete. Not forsaking the plans for the original Pencil, they have changed the work scope but not the main goals established for the final application.

## Bibliography

1. Github, "Pencil2d/Pencil". [Online].
Last access on 18/10/2015 at: https://github.com/pencil2d/Pencil.

2. Pencil2D, "Pencil2D - opensource animation software". [Online].
Last access on 18/10/2015 at:  http://www.pencil2d.org/.

3. FEUP - MIEIC - Engenharia de Software - 2015/2016, "REQUIREMENTS ENGINEERING & PROTOTYPING". [Online]. Last access on 3/10/2015 at: http://moodle.up.pt/pluginfile.php/68505/mod_resource/content/2/ESOF-Requirements%20Engineering.pdf.

4. Ian Sommerville, Software Engineering, 9th Edition, Pearson, 2011.


## Authors

[Ângela Cardoso](mailto:angela.cardoso@fc.up.pt)

[Bruno Madeira](mailto:up201306619@fe.up.pt)

[José Teixeira](mailto:up201303930@fe.up.pt)
