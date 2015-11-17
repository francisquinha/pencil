# Software Verification and Validation in Pencil2D

## Introduction

Software validation focuses on verifying if the product does what was intended, that is, that it follows the specified requirements. In Pencil2D Software validation is minimal since the project has been following the specification of the original Pencil, which was already implemented when Pencil2D started. Also, this specification is not rigid, leaving some decisions for later, thus there is some uncertainty about how very specific functionalities should work. This way, validation goes along the software requirements revision. A good example of this is the [issue 328](https://github.com/pencil2d/pencil/issues/328), where something that was initially thought of as a bug, ended up being considered a feature.

Software verification is concerned with checking if the product works properly and the functionalities that it implements execute their purpose accurately. In Pencil2D this means having a program that runs smoothly, without crashes or bugs, and in which the developed modules map well the underline core concepts regarding the creation of animations.
 
In the next section, we go further into the degree of testability in Pencil2D, discussing its controllability, observability, isolateability, separation of concerns, understandability and heterogeneity. We also present a section on test statistics for Pencil2D, where we try to evaluate aspects such as code coverage.

##  Degree of Testability

(Isolateability: The degree to which the component under test (CUT) can be tested in isolation.
; Separation of concerns: The degree to which the component under test has a single, well defined responsibility.
; Understandability: The degree to which the component under test is documented or self-explaining.)

Pencil2D has followed a modular implementation. This means that the many utilities that compose the whole software were
developed independently from each other. We take this conclusion from the previously done SoftwareArchitecture.md report. 

That said the task to test the components that constitute Pencil2D is rather easy and simple to do. Which means that the
isolate-ability is achieved because everything is confined in its module. For instance, if the developer wishes to test
something like the BitmapLayer he only has to interact with the module(s) that concerns that specific feature.
 Most modules and the functionalities they provide are self-explanatory and there is a good separation of concerns as we can confirm again in the SoftwareArchitecture.md report.
 Consequently they are easy to understand (in a general way) for anyone that understands the underline concepts that they implement.
 These concepts already have exposed in documentation that was already referenced in previous reports. Therefore it is easy, even for newcomers to the project, to understand the scope of the tests that are currently
 done and even to make new test for other components.

(Isolateability: The degree to which the component under test (CUT) can be tested in isolation.
; Controllability: The degree to which it is possible to control the state of the component under test (CUT) as required for testing.
; Observability: The degree to which it is possible to observe (intermediate and final) test results.)
??? (apparently not  much controllability) 
...TODO...

(Heterogeneity: The degree to which the use of diverse technologies requires to use diverse test methods and tools in parallel)

The Qt IDE and framework can be used for multi platform development.
 The Qt framework already provides tools for test cases and benchmarking (performance tests). It also allows for dynamic verification using additional tools in conjunction that can check
 functions call, existence of memory leaks and some other useful behaviours/properties of the application. 
 This makes testing easier since most tests can be done inside the Qt IDE.
 Code coverage can be done using an external tool such as LCOV but there is no indication that it has been used so far.
 Since Pencil2d is only being developed for Windows, MAC and Linux PCs it does not need any other specific tools in parallel.

## Test Statistics

There are no integration or performance tests that we are aware of in Pencil2D, only unit tests.
Excluding "unit tests" that are made to test the Qt testing framework and initialize/free objects there is a total of 12 unit tests that focus on 2 critical components.
 There are 8 unit tests regarding the Layer components, with the exception of one that only checks the type of a Layer when it is created, all of them only
 focus on the BitmapLayer and test the basic functions regarding the insertion, deletion and queries of KeyFrames.
 The remaining 4 test the loading of .pcl files.
 These tests are static and very specific. The code coverage by them is minimal.

Since this is an opensource project goes without surprise that system tests are done by the Pencil2D community and in some cases even code reviewing and/or feedback related to the usability of the program
 (ex.:[issue 328](https://github.com/pencil2d/pencil/issues/328)).  
 
 
Since this is a opensource project many tests could have been done manually. It's difficult to account precisely how code verification goes but we an 
 
     Number of tests (# tests unitários; # tests de sistema, # tests de desempenho, ...)
     % coverage (given by tools like EclEmma)
     Code coverage: is it any good? (see http://avandeursen.com/2013/11/19/test-coverage-not-for-managers/)

## Conclusion

Taking into account that this is not an application that works with a critical system, has a modular implementation and that a lot of features are difficult to verify without an user scope
 (ex.: it is difficult to test if color-fill functionality is working correctly by testing code alone), the coverage of code being tested (referring to the Qt Unit Tests here) by might not be as important as
  system tests and code reviewing. In this regard, Pencil2D appears to have set it's priorities straight. 
  
  As this project isn't yet finished the need for validation tests is relatively inferior to the verification tests furthermore the testability of a project made by a small group of developers and most of them don't have a big impact in the project the code reviewing becomes a task slightly ambiguous in the sense that there is no one else that is able to review the code not excluding the eventual contributors. In that way unit testing have a bigger role in the testing of this project because they give the feedback to the developer(being the reviewer at the same time) with the functionalities' status (if they are either working or buggy). Allowing the developer to focus mainly in the functionality.
  
  ...TODO...

## Bibliography

1. Github, "Pencil2d/Pencil". [Online].
Last access on 18/10/2015 at: https://github.com/pencil2d/Pencil.

2. Pencil2D, "Pencil2D - opensource animation software". [Online].
Last access on 18/10/2015 at:  http://www.pencil2d.org/.

3. FEUP - MIEIC - Engenharia de Software – 2015/2016, "Software Verification and Validation PART I". [Online].
Last access on /11/2015 at: http://moodle.up.pt/pluginfile.php/74998/mod_resource/content/2/ESOF-VV%20-%20Part%20I.pdf.

4. FEUP - MIEIC - Engenharia de Software – 2015/2016, "Software Verification and Validation PART II". [Online].
Last access on /11/2015 at: http://moodle.up.pt/pluginfile.php/74999/mod_resource/content/2/ESOF-VV%20-%20Part%20II.pdf.

## Authors

[Ângela Cardoso](mailto:angela.cardoso@fc.up.pt)

[Bruno Madeira](mailto:up201306619@fe.up.pt)

[José Teixeira](mailto:up201303930@fe.up.pt)
