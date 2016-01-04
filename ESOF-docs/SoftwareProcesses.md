# Software Processes in Pencil2D

## Introduction

### Software Processes

A software process is a set of activities that result in a software product. Some of these activities involve programming in one or more languages, but that is not the whole software process or even the most crucial part. Aside from coding and even designing or testing, a true software process should guarantee that the final product will satisfy the needs of the client, will be done in the time frame established and will be cost effective.

The equilibrium between scope, schedule and cost is very difficult to obtain. The client will typically pull for a large scope, within a reduced schedule and with a small cost. While the development team will probably need to partly compromise at least one of these three aspects. But once an agreement as been reached to what point of this triangle one is aiming, this contract needs to be respected and that must never come at the cost of quality.

<div align="center">
	<img src=pyramid.jpg height=200>
</div>

It is the job of the development team not only to deliver the product, but to ensure that it is done in a timely and cost effective fashion, while not dropping the quality. This is why having an adequate software process is crucial, it establishes rules and organizes the different parts of software creation, in order to guarantee that there are no delays or budget derails.

While in some ways the process of creating software is similar to that of creating a building, in others it is very much different. Typically, once a decision has been made regarding the specification of the building, that will not change. But software requirements, especially today, are always evolving. And even if that causes some difficulties in the development, it also ensures that software products do not become obsolete and that one does not need to reinvent the software wheel, only to modify it.

This constant evolution in software specification is why some older software models, like the Waterfall Model, illustrated by the image below, are very ill suited for current software development. The idea that one can simply do each activity a single time and in a specific order is not at all conductive of the ever changing software requirements.

<div align="center">
	<img src=waterfall.jpg height=400>
</div>

Due to the failing of the Waterfall Model, with delays becoming a constant in software development, more adaptive software process models have emerged. One of these models is Incremental Delivery, in which the activities are interleaved, in order to develop each successive version of the software. In this approach, each increment adds some functionalities to the software, usually the more urgent ones, making these features available throughout the development, instead of doing it in bulk near the end of the development process.

A kind of Incremental Delivery software process that is mainly oriented at risk management is the Spiral Model proposed by Boehm in 1988, which is illustrated in the following image.

<div align="center">
	<img src=spiral.jpg height=500>
</div>

In what follows we analyze Pencil2D and some of the aspects of its development, trying to identify the software processes it might be using. 

### About Pencil2D

Pencil2D is a kind of resurrected software. It was born around 2013 when the development of Pencil halted. According to its creators (Pascal Naidon and Patrick Corrieri), Pencil was meant to be an open source animation tool, using bitmap and vector graphics. The idea was to create an aid to the slow painful process of traditional animation, that consists of having successive slightly different images.

Although at the time of its demise (version 0.4.4b) Pencil already had a quite rich [set of features](http://www.pencil2d.org/2010/06/the-vision-for-pencil-by-pascal-naidon/), it was still in a beta release, thus having many bugs, as well as opportunities for further developments. At the impossibility from the creators of continuing their project, [Matt Chang](https://github.com/chchwy) stepped forward and started a fork called [Pencil2D](http://www.pencil2d.org).

<div align="center">
	<img src=pencil.jpg height=500>
</div>

After several beta releases, Pencil2D is now in version 0.5.4b and Matt Change is attempting to reach 0.5.5b, one of the milestones. The application is still plagued by several bugs, some of which are related to its initial objective of being a cross-platform application. A list of issues is maintained, with feature requests and enhancements in addition to bugs, and it is this list that guides the increments being developed at each stage.

## Software Process Roles

In any software development process there are different roles performed by the people involved. If the team is not very strictly organized, these roles may be somewhat merged and performed by a same person. This seems to be the case with Pencil2D, as we discuss below, where we present the main roles that can be found in the project. Although in general there may be other roles, we present here the ones we have found in Pencil2D.

### Client

In general, the role of client is performed by a representative of the organization that requested the software. Sometimes, the person performing this role is not from the client company, but from the development company. In any case, its the job of this person to guarantee that the software requirements are met, as well as generally speak for the client company.

Pencil2D does not have a client company. Not in the strict sense at least. The software is simply being developed for anyone who might have an interest in its features. Although "random" people on the internet do make feature requests, these people do not have a representative that coordinates their efforts. Also, since they are not paying for anything, there is a clear limit to how much pressure they can place on the development team. Thus, in a way, the role of the client is performed by whomever decides to use the application and comment on it, but with many restrictions in their power to really influence the development process.

### Project Manager

The project manager is, in a sense, the leader of the development team. It is their responsibility to supervise the planning, execution and, eventually, conclusion of the project. Also, most of the decisions may fall on the project manager.

Currently, the project manager of Pencil2D seems to be the main developer: Matt Chang. This is the person in charge of driving the project forward, either by personally contributing with increments, or by coordinating the efforts of others and ensuring that their contributions are successfully merged.

### Developer

The developers of a software project are responsible for both the design and the programming. In ancient software development methods, these roles where performed by different people. While some would theoretically conceive the whole application, like the architects who create the plans for a building; others would actually code these ideas, thus being the constructors of the building. This is not the case anymore, not in any current software development process. The main reason for this is the fact that, these days, software is so complex and has so many lines of code, it would be virtually impossible for any person to simply conceive the whole design, while not getting involved in the actual programming.

As stated above, Pencil2D has a main developer, who contributes most of the design and code. The other developers, making a current total of 14, vary a lot productivity. Some have only made on or two short commits, while others have contributed some thousand lines of code. In any case, they all seem to be free agents, instead of belonging to a cohesive team. 

The following image illustrates the contribution of some of the project members.

<div align="center">
	<img src= contributors.bmp height=800>
</div>

### Tester

Every piece of software needs to be tested. Many times, this is done together with development and often by the same people. This seems to be the case in part with Pencil2D, since there is no team or person whose single job is to test what others have developed. Actually, there is a set of software tests that has been created precisely by the developers.

This does not mean however that the only testers in Pencil2D are developers. Anybody can be a tester and many people have done so, by installing the application and reporting bugs. These testers are precisely the same people playing the role of client, both benefiting from the software and helping its development with their real use test cases.

## Software Process Activities

All software processes are characterized by similar activities, although the way they are organized depends on each specific process. In this section we describe the four main activities and the way they are addressed in Pencil2D. 

### Specification

The objective of software specification is to determine the requirements of the software. The client should let the development team know how the software will be used, by whom, to which effect and under what circumstances. It is very important to decide what the software is supposed to do with precision, because everything else will follow from this stage. 

A part from the user requirements, system requirements, which are more detailed and oriented for the software developers, also should be determined in this phase. This whole part of the process can be split in four activities:

1. Feasibility Study - A quick analysis to decide whether the project is possible and cost-effective, whose result should inform if further analysis should be mande;  
2. Requirement Elicitation - The system requirements are obtained from the discussion with potential users and the observation of other systems;
3. Requirements Specification - The information from the previous stage is written in a document;
4. Requirements Validation - The requirements are checked for consistency, realism and completeness.

These activities may not be performed strictly in this order. Also, the software requirements may be updated throughout the development, depending on the software process used.

It is not completely clear how the software specification was initially performed in Pencil2D. The idea was to develop "a tool for creating traditional animation, using both bitmap and vector graphics; which was intuitive, cool, light, open source, cross-platform...". However, we could not find a detailed list of early system requirements, from the time of Pencil. 

In any case, there is a task list, dating from the time when Pencil was forked into Pencil2D, whose contents are features to be added to the software. Since there is no proper client for the application, that part of their role was performed by the Project Manager.

### Design and Implementation

This is the stage where the software is actually built in order to match the system requirements. In order to accomplish that, there are processes of design and programming.

The design is a description of the structure of the software, its interfaces and sometimes the algorithms that will be used. The different components of the software should be identified and described, as well as their organization as a whole. The interfaces between different components and between the software and the user also need to be detailed.

The image below contains a diagram for the implementation of Pencil2D gives some indication of its design process. Accompanying it there is a description of the ideas the main developer has regarding the organization and the role of the several components of the software as he wishes them to be. Although these designes could be better organize, they do show some concern with this stage of the development process.

<div align="center">
	<img src= roadmap.jpeg height=400>
</div>

From the software design, the implementation should come naturally. Along with programming the software, some programmers also perform some tests on it, in order to check that their code is doing what is intended. Has in a previous chapter, in Pencil2D the development is mainly done by a single person. But there are other programmers who occasionally contribute, some more than others.

The implementation that is being done in Pencil2D is one of the main evidences to the use of a sort of Incremental Delivery software process. There are nightly builds and beta releases and the software requirements are updated throughout the development. There is also some mild evidence of agile methods, with some circular software processes. However, this is not very well accomplished, because there are hardly any established timeframes. For example, currently there are two open and no closed milestones. But the open milestones have no due date. We will discuss this in further detail in a following chapter.

### Validation

This is the part of the process where the software is tested, in order to ensure that it conformes with the specification. In medium or large programs, this verification should be modular, in the sense that each component of the software should be tested individually, instead of only testing the full finished application. This modular approach reduces the time needed for validation and makes error correction easier and faster.

Software testing can be done in three main stages:

1. Development testing - the developers debug the code as they write it, as mentioned in the previous section;
2. System testing - the different components of the software are integrated and the result is tested, finding errors that where not visible in any single module;
3. Acceptance testing - the system is tested with real data, instead of simulated test data.

Pencil2D has at least two distinct evidences of software testing. The first is a set of tests in the Qt framework. Up to this point, we could not determine weather these tests were developed before or after the code that they aim to test. Therefore, we can not confirm if some part of the development process was test-driven. In any case, it seems to concern the application as a whole.

Another set of tests are being performed by the end users. These tests are clearly using real data and therefore are a part of acceptance testing. They also provide evidence to a circular process: requirements, development, testing, more requirements, more developing, etc.

Of course there must also be some development testing, otherwise the application would not even compile and run, with all the bugs that would certainly plague it.

### Evolution

This stage of the software process aims to better deal with the fact that these days, most software is a kind of living organism. One no longer develops an application and considers it finished. With the use, new features will be requested, new bugs will be discovered and all this will lead to further development. 

In a way, it was a kind of software evolution that led to Pencil2D. Since the creators of Pencil where no longer able to continue developing it and there was a feeling that some important features where still missing, Matt Chang felt that he should provide the necessary continuity. 

There is also some clear evolutionary contribution made by the end users. In addition to reporting bugs, they also request new features, some of which may be considered for future developments. All of this is quite clear in the list of issues maintained in the repository of the project. While most of these issues are bugs, some are suggestions of application enhancements and others are requests, as the following image shows.

<div align="center">
	<img src= issues.bmp height=300>
</div>

## Factors to consider

Putting our critical thinking on matters of development processes we tried to identify project characteristics that could be relevant in terms of deciding the general methodology process philosophy in this type of projects. The picture below contains the synthesizes of our analysis.

<div align="center">
	<img src= thought_bubble.png height=600>
</div>

## Incremental Delivery

In an Incremental Delivery software development process, as the name suggests, successive versions (or increments) of the software are delivered to the customer and used in their final environment. In order to achieve this, the requirements are divided into categories according to their urgency. This way, in each new delivery stage the prioritized specifications are implemented and deployed for use. The following image illustrates this development process, that after some initial stages becomes circular.

<div align="center">
	<img src= incremental.png height=260>
</div>

As we have already seen above, Pencil2D shows several signs of this kind of approach. The main one being the preoccupation with releasing successive versions of the software for public use. This goes even further than each beta increment, with nightly builds also available for the more adventurous user to tinker with the new features or obtain faster bug fixes.

Also, as evidenced by the image below, whether the coding is done by the main developer or by someone else, there seems to be a concern to isolate each small increment in its own development fork. This shows a well organized programming process, that is specially helpful if several people are working together or if a single developer wants to dedicate himself to different parts of the software simultaneously.

<div align="center">
	<img src= merges.bmp height=540>
</div>

In addition to this, there are clear objectives for each increment, both in terms of bug fixes and of new features or enhancements. There is a large list of all that needs to be done and the most needed tasks are isolated to be included in each successive release.

If there was a larger development team, or simply if each developer could spend more time with the project, instead of it being a kind of pass time activity, perhaps some Agile Methods could work really well. They would provide the much needed schedule to the project, with each increment being released faster. As it is, the project seems to evolve very slowly with virtually no concerns for time or cost effectiveness. Which is more so true in a situation where any cost evaluation is somewhat subjective, since nobody seems to be paid for their work and all the technology is free to use.

In any case, even though one can assume there are no cost and time pressures, a software process is still useful in ensuring that the scope is achieved with quality and with minimal wastes. For this particular project, Incremental Delivery seems to be a very good choice, because it allows the use of the application as it is being developed, thus maintaining user interest.

## Conclusion

We contacted Matt Chang, the main contributor of this project, but unfortunately, up to this point, he did not reply to our email (it might have fallen on his spam pit). So we don’t have his own overview on his project. That said, we will never know anything else besides our own opinion on this topic, so it’s up to us to give our final thoughts in all of this. 

The information related to the project is quite scattered, some of it is on GitHub and some in the projects webpage, whose organization is not entirely clear to us. Thus, we do not know all the specifics about the original pencil project state. Also, we have a limited understanding of the current version, so our opinion may be a bit blunt. Before asserting our conclusion, we expose a summarized state of the current project.

1. This project is the salvaged remains of an older project named Pencil.
2. Its developing team is not diverse neither numerous, just a few contributors and most of them don’t even add features, but just code restructuring.
3. Although many features were already implemented in the beginning of Pencil2D, there have been some improvements to the previous features and new features have been added.
4. There was a peek on its developing around the end of July and beginning of August of 2013, with various branches from different contributors.
6. There are no milestones fulfilled, and most of the requirements are bug fixes.

From our analysis it is not entirely clear whether this project has truly adopted a software process model. One thing we are completely sure of is that it does not follow the Waterfall Model, because there is a constant roll back between design, testing and features being added. 

There is some planning in what seems to be a modular design approach, which should make the development more accessible. So it is clear that the process is flexible. While there is a kind of circular development model, with numerous bug fixes and quality of life checks as more features were being added, there seems to be no particular concern with risk management, thus it is probably not following Boehm’s Spiral Model.

That said, there are successive software versions being released and tested, sometimes leading to redefined objectives, others simply enabling the developers to advance to the issues they wish to tackle next. All of this corresponds to an Incremental Delivery approach, which is why that is our main bet for the software process chosen for Pencil2D.


## Overview of the chosen software process

Revisiting this chapter, we have now a more complex and insightful idea on the whole project, due to our analysis of most of its aspects.

Considering that the developing team is small, it will come to a point where most tasks will have to be dealt with by a single person. What we mean with this is the features that are missing most likely will be implemented by the same person that was working on many others. 

We are still convinced that the software process adopted by the developing team is incremental delivery. What works the best with the choice of this software process is undoubtedly the possilibty for the developers to launch stable versions of their product in its development state. By doing this, they already have a program that is useable (to some extent) while the development team can continue working in the next features. Also, they get user feedback which plays a very import roll in the software verification and validation, while also having an influence in the future developments.

As there are no real deadlines defined the features are added at the rate they are created, which we think adds a lot more flexibilty to a project like this. Of course it also has an obvious downside, because the project does not really have a stable flow progress, with many months going by between successive increments. This is also due to the fact that the development team is so small.

We could also admit that the XP (extreme programming) software process could be used as it is a lightweight process that emphasizes on an agile approach. It meets some of incremental delivery principles such as the delivery of software to the customer (in this case to the users) in short and often iterations. It also emphasizes plenty on feedback as seen on the issue tracker for pencil2D's github repository. But it also follows a TDD (test-driven development), which obviously Pencil2D does not use, since it has very few unit tests. Of course this lack of tests in Pencil2D is not good, and so, the use of the XP process would benefit this project in two very important aspects, the speed of development and the quality of the product obtained, as fewer errors would reach the end users. On the other hand, many of Pencil2D's features are not suitable for unit testing. Prioritize other means to test the software might be a better option in this type of project. 

It is our opinion that with a larger team, Pencil2D could have a better organized development, with faster and better delivery. As it is, there seems to be only a slight concern with the software process use, without much regard for the bennefits that would surely come from a stricter following of a software process like XP.

## Bibliography

1. Github, "pencil2d/pencil". [Online].
Last access on 4/10/2015 at: https://github.com/pencil2d/pencil.

2. Pencil2D, "Pencil2D – opensource animation software". [Online].
Last access on 4/10/2015 at:  http://www.pencil2d.org/.

3. Wikipedia, “Software development process”  10:05, 30 September 2015. [Online].
Last access on 3/10/2015 at: https://en.wikipedia.org/wiki/Software_development_process.

4. FEUP - MIEIC - Engenharia de Software – 2015/2016, "Software Processes". [Online].
Last access on 3/10/2015 at: http://moodle.up.pt/pluginfile.php/61587/mod_resource/content/3/Software%20Processes.pdf.

5. Ian Sommerville, Software Engineering, 9th Edition, Pearson, 2011.

## Authors

[Ângela Cardoso](mailto:angela.cardoso@fc.up.pt)

[Bruno Madeira](mailto:up201306619@fe.up.pt)

[José Teixeira](mailto:up201303930@fe.up.pt)
