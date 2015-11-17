# Software Verification and Validation in Pencil2D

## Introduction

Software validation focuses on checking if the product does what was intended, that is, that it follows the specified requirements. When the software client or stakeholder is well defined, a good method of software validation is checking if the product meets the minimum acceptance requirements established by the client. This is usually not the case for open-source software, where the client is pretty mush anybody that may wish to use the software, and there is no contract establishing the acceptance conditions. In this case, the developers may validate their software through user feedback, such as complaints and feature requests, usage statistics integrated in the application and questionaries to target users.

In Pencil2D traditional software validation is minimal since the project has been following the requirements of the original Pencil, which where already implemented when Pencil2D started. Also, these requirements are not rigid, leaving some decisions for later, thus there is some uncertainty about how some specific functionalities should work. On the other end, user feedback seems to be quite useful. Although some of this feedback is in the bug report category, that goes beyond the scope of validation, there are also new feature requests as well as requests for current feature changes. A good example of this is [issue 328](https://github.com/pencil2d/pencil/issues/328), where something that was initially thought of as a bug, ended up being considered as a possible feature.

Software verification is concerned with checking if the product works properly and the functionalities that it implements execute their purpose accurately. That is, it checks if the software is in agreement with its specification. There are two main methods of verification:

- running tests and experiments, which is useful to detect bugs;

- analysis of the code correctness.

In Pencil2D there are some unit tests that the developers use for verification. But perhaps most of testing is done by the end users themselves, with bug reports and issue raising. Since this is an open source project, this bug detection process sometimes leads to users correcting the issues themselves.
 
In the next section, we go further into the degree of testability in Pencil2D, discussing its controllability, observability, isolateability, separation of concerns, understandability and heterogeneity. We also present a section on test statistics for Pencil2D, where we try to evaluate aspects such as code coverage.


##  Degree of Testability

(Isolateability: The degree to which the component under test (CUT) can be tested in isolation.
; Separation of concerns: The degree to which the component under test has a single, well defined responsibility.
; Understandability: The degree to which the component under test is documented or self-explaining.)

### Isolateability, Separation and Understandanbility

Pencil2D has followed a modular implementation. This means that the many utilities that compose the whole software were
developed independently from each other. We take this conclusion from the previously done SoftwareArchitecture.md report. 

That said the task to test the components that constitute Pencil2D is rather easy and simple to do. Which means that the
isolate-ability is achieved because everything is confined in its module. For instance, if the developer wishes to test
something like the BitmapLayer he only has to interact with the module(s) that concerns that specific feature.
 Most modules and the functionalities they provide are self-explanatory and there is a good separation of concerns as we can confirm again in the SoftwareArchitecture.md report.
 Consequently they are easy to understand (in a general way) for anyone that understands the underline concepts that they implement.
 These concepts already have exposed in documentation that was already referenced in previous reports. Therefore it is easy, even for newcomers to the project, to understand the scope of the tests that are currently
 done and even to make new test for other components.
 
### Controllability and Observability
 
The above mentioned tests use functions in the QT Framework library that are responsible for giving the feedback that the test
has either passed or failed. One of those functions is the [QCOMPARE](http://doc.qt.io/qt-5/qtest.html#QCOMPARE). If the test is somewhat large in the way that there are many calls to functions there is no way to give feedback on the test's final result as the framework does not provide anything that can check the intermediate result of the test.d.
Test cases for the modules being currently tested can be easily modified and results easily interpreted.

It is also worth mentioning that some features can't be properly tested using the QT framework alone and need to be checked without unit tests.
 Some functionalities, mainly related to drawing/schetching, can only be tested using system tests. In this regard the modular implementation may help to identefy the root of certain problems however some occurances may be difficult to replicate.

### Heterogeneity

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
 These tests are static and very specific trotyc. The code coverage by them is minimal.

Since this is an opensource project goes without surprise that system tests are done by the Pencil2D community and in some cases even code reviewing and/or feedback related to the usability of the program
 (ex.:[issue 328](https://github.com/pencil2d/pencil/issues/328)).  

## Conclusion

Taking into account that this is not an application that works with a critical system, has a modular implementation and that a lot of features are difficult to verify without an user scope
 (ex.: it is difficult to test if color-fill functionality is working correctly by testing code alone), the coverage of code being tested (referring to the Qt Unit Tests here) by might not be as important as
  system tests and code reviewing. In this regard, Pencil2D appears to have set it's priorities straight. 
  
  As this project isn't yet finished the need for validation tests is relatively inferior to the verification tests furthermore the testability of a project made by a small group of developers and most of them don't have a big impact in the project the code reviewing becomes a task slightly ambiguous in the sense that there is no one else that is able to review the code not excluding the eventual contributors. In that way unit testing has a bigger role in the testing of this project because they give the feedback to the developer(being the reviewer at the same time) with the functionalities' status (if they are either working or buggy). Allowing the developer to focus mainly in the functionality.
  
  
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

5. Robert V Binder, - "Software Testability". [Online].n b
Last access on 18/11/2015 at:
http://robertvbinder.com/software-testability-part-1-what-is-it/
http://robertvbinder.com/software-testability-part-2-controllability-and-observability/
http://robertvbinder.com/testability-part-4-white-box-strategies/

## Authors

[Ângela Cardoso](mailto:angela.cardoso@fc.up.pt)

[Bruno Madeira](mailto:up201306619@fe.up.pt)

[José Teixeira](mailto:up201303930@fe.up.pt)