# Software Requirements Specification in Pencil2D

## Introduction

The software requirements specification should be done at the beginning of any software development. Its goal is to document the purpose of the software and to describe how it will interact with the users, the system and other applications. Thus, even if the requirements are updated throughout the development, which these days is quite common, it is important to have a firm grasp on what they are before progressing to other stages, in order to avoid misunderstandings between clients and developers.

There are two general types of requirements: functional and nonfunctional requirements. The first are the functions that the software should be able to perform, also known as capabilities. The nonfunctional requirements are the ones that impose restrictions on the solution, such as quality or development requirements.

In order to reach a specification document, one typically progresses along several activities, going from a more general overview to a very detailed description. After a quick analysis aiming to check the feasibility of the software, the first activity is requirement **elicitation**. At this stage, through interviews, joint application design sessions, questionnaires, brainstorming, etc, the requirements are collected from the client. Use cases, which are examples of how the user will interact with the software, should be obtained. At this point, the requirements are very high level.

Once the elicitation process is complete, one should proceed to the **analysis**, where a more precise understanding of the requirements is achieved. At this point the requirements obtained will be on a lower level. The system requirements are derived from the previous information, as well as the software requirements, by breaking down the system requirements into the different software components. One should check the requirements for completeness, correctness, consistency, unambiguity, verifiability, necessity and feasibility. Besides analyses, this is the stage of requirement negotiation. A debate ensues between the stakeholders, in order to arrive at a list of agreed requirements, usually considering mainly the necessity and the feasibility.

The next stage is **specification**, where a detailed document containing all requirements is produced. UML diagrams and other artifacts are typically included in this document. There is a standard template for specification documents that should be followed as closely as possible.

Finally, one can proceed to requirement **validation**, with the goal of guaranteeing that the requirements define the system according to the real objective of the client. This is very important as fixing a requirement error at this stage costs considerably less than doing so after product delivery.

To aid in requirement collection, prototypes are used. These are primitive versions of the system, maybe even done in paper, designed to determine what the system will look like and what it will do, offering some limited capabilities. These prototypes may be done through the whole development, but a first vertical system prototype is usually done in the beginning.

Remitting to the first document created under the ESOF scope, 'Software Processes', this topic has already been briefly touched. An [important reference](http://www.pencil2d.org/2010/06/the-vision-for-pencil-by-pascal-naidon/) to the project specification for Pencil2D was also given then. The present document aims to dive further into the details on this subject.

##Requirements in Pencil2d

One of the main figures of the original pencil project states that this is a personal non-profit oriented project that is open for other people to develop and use. This creates a sort of  duality in the analysis because we can access the pencil2d requirements from different perspectives. It's possible to think of "pencil2d", referring to the overall software ramifications like forks like bluepencil and not to the actual project, as a software which specification arises from the intersections between public demands and developers self set goals. It is also possible to think of "pencil2d" in the context of it's origins or individually or in context of the public demand for such an application. We will try to approach the "main branch perspective" where we can consider the initial stated requirements (original pencil) and it's new iteration (current pencil2d) requirements according to the public contribution.
 
 ...maybe some image
 
Pencil2D, the project, started from one of these intersections by picking up a existing project, pencil, and giving it continuity.
 After that, specifications may have been refined and slightly changed by the public contribution and feedback. It's possible 
 that some requirements are only specified in some branch/fork and after a merge the main
 project assimilates the result without having to make "side" specifications.
 
 
###Original Pencil Requirements/Specifications

There is some documentation on [requirements that dates from the original pencil project on the pencil2d website](http://www.pencil2d.org/2010/06/the-vision-for-pencil-by-pascal-naidon/).
<br>The documentation clarifies the motives and aspirations behind Pencil and tries to establish future direction to the project, according to the original developer believe "that 
an application like Pencil should be designed with some personal vision and goal to remain effective".
<br>From it we see that there was no entity besides main developers working on pencil at the time that functions as stakeholder, and since the project is being continued
 by new developers we can take this documentation as being the current Pencil2d's first requirement elicitation that establishes initial goals for the project.

The exposed requirements are mainly user and system related. The project already presumes the use of c++ in the development since it is using the Qt framework
 and software requirements are not the main focus although they are briefly touched.
<br>Being done by the main developers some "technical" requirements related to the application functionality may have been easier to assert due too the understanding of the topics
 and the already established project vision. The clarity of these specifications seems to confirm this, it establishes a well-defined set of features for the main application. 
<br>In regards to non-functional requirements,internal quality and software requirements it's referred modular design in "future development" of
 Pencil ("future" at the time of the documentation) to allow the implementation of secondary usages but it doesn't expand much beyond that. There are presented some "paper" prototypes of 
 these modules and how they should appear to the user and then some considerations about their integration (or not) into a main application but nothing stays explicitly defined or planned. 

... add image of prototype and rearrange text a bit
  
###Pencil2d Requirements/Specifications
 
 In its primordial development there were already some tools and features implemented,
although after the rebirth of Pencil being now known as Pencil2D its particular
focus was to produce working versions for OSX, Windows and Linux, the
bug fixing and handling the codebase(simplify it). There wasn't a clear idea if it was
supposed to add new features to the pre-existing ones.

So from the day (19th January of 2013) the article we 
are building our opinion we, can clarify some of this project
requirements:

1. Being able to distribute Pencil2D for all operative systems.
2. Bug fixes and general code improvement.

As it was already mentioned before there isn't a clear neither concrete
idea on what particular feature it's being planned to be added.

This is an open-source project even though its creator didn't want to shape it in another person's vision,
it does not exclude the fact that it's not open for new ideas that might come up.
<br>From the time this report is being written, there has been requests for new features so the requirement elicitation
tends to be a bit chaotic, in the way that in the middle of its development there might appear some pertinent opinions
whether a particular feature should be added. The process of requirement identification and analysis/negotiation is handled
at the same time via github's issue tracker when diverse entities(mostly individual users) submit a report on whether
new feature would be feasible to be added.

We take the example from a [request issued in the 19th of February of 2015] (https://github.com/pencil2d/pencil/issues/288):
>Hey there. I've enjoyed using Pencil on my Linux systems and am elated to know that development is continuing on a fork of it.

>https://www.youtube.com/watch?v=xU4nQuRw-e4

>I'd like to know if there could be an option to export our creations to the WebM format, for its slim form and relative lack of patent encumbrance.
>It'll make for easy uploading to sites like Youtube.
>Alternatively, if it'd be possible to upload our cartoons directly to Youtube, that'd be just as good.

This is a good example when an user wants the developers to add a new important feature to increase Pencil2D's versatility, nevertheless
there are still plenty of bugs from the date that this request has been issued it is a very good example of the software requirement life-cycle.
 
##Use Cases Diagram

The following image presents a possible use cases diagram that could have been done as specification for the current Pencil2D.

<div align="center">
	<img src= PossivelDiagramaDeCasosDeUtilizacaoParaOestadoActualPrint.png height=500>
</div>

The presented diagram is somewhat detailed. Because of details, like "onion skin" which is a display option more relevant than others
 because of it's practical utility, we could still branch the presented graph a little more but overall
 it displays a very accurate representation of the use cases. 
<br>Looking at the original specifications there are some minor details that could appear differently in the diagram. The original
 specification suggest using 4 sub layers per layer or allowing to define hierarchies and groups of Layers. This, in a detailed view,
 changes the diagram by allowing extra actions that would need to be specified later in an Activity Diagram when addressing the Software Architecture.
 There are also some additional details regarding sound and media resources. 
<br>The project may still incorporate some of these features in the future, but since we don't know the current plans for the project
 we don't present these features in he diagram. Overall, the presented diagram, remains faithful to the original requirements which means
 that Pencil2D has not strayed from the original Pencil's vision and goals.
 
 
## some rand thoughts and links

(??? need a 2nd opinion on these)

The dynamic nature of the development, like the change of main developers in the transition from Pencil to Pencil2d  or the already mentioned in "Software Development.md" incremental development process,
 may introduce a volatility problem . In the context of a long term development of an open-source project it's more questionable whether this just part of the project's nature and
 not necessarily a problem since public feedback from users or other developers is usually present and technology evolves over time.
 
 The more recent requirements seem more related to fix bugs or "clean" code than changing the original requirements
 (so they appear to be fixing
 something that failed in the development or in the initial requirements.
 conjecture quality requirements


## Conclusion


...

## Bibliography

1. Github, "pencil2d/pencil". [Online].
Last access on X/10/2015 at: https://github.com/pencil2d/pencil.

2. Pencil2D, "Pencil2D - opensource animation software". [Online].
Last access on X/10/2015 at:  http://www.pencil2d.org/.

3. FEUP - MIEIC - Engenharia de Software - 2015/2016, "REQUIREMENTS ENGINEERING & PROTOTYPING". [Online]. Last access on 3/10/2015 at: http://moodle.up.pt/pluginfile.php/68505/mod_resource/content/2/ESOF-Requirements%20Engineering.pdf.

...

## Authors

[Ângela Cardoso](mailto:angela.cardoso@fc.up.pt)

[Bruno Madeira](mailto:up201306619@fe.up.pt)

[José Teixeira](mailto:up201303930@fe.up.pt)
