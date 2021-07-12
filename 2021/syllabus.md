# CSCI 1230 Course Syllabus

Welcome to CSCI 1230, the longest-running computer graphics course in the known universe! This document will get you started with the course.

## Table of Contents

Links to different subsections go here

## Course Missive

### Course Staff & Essential Info
* Professor: Daniel Ritchie (dritchi1)
* Head TAs: Alex Mina (jmina), Caleb Trotz (ctrotz)
* UTAs: Aalia Habib (ahabib3), Aparna Natarajan (anatara7), Adam Pikielny (apikieln), Alana White (apikieln), Breese Sherman (bsherma3), Junewoo Park (jpark49), Yuna Hiraide (yhiraide)
* Lectures: Tues & Thurs 10:30am -- 11:50am, location TBD. Lectures will be recorded and promptly available online for students who have chosen remote asynchronous participation this semester.
* Course website: https://csci1230.graphics
* TA mailing list: cs1230tas@cs.brown.edu
* Ed discussion board: (link forthcoming)
* Labs/Help Sessions/Gear Ups: See the [course calendar](https://csci1230.graphics) for times and locations

### Prerequisites

The official prerequisite **courses** for CSCI 1230 are CSCI 0150/0160, CSCI 0170/0180, or CSCI 0190.

CSCI 0330, because it uses C, can be helpful but not strictly required. CSCI 0320, for its software design, is additionally helpful but not required. Some familiarity with C++ will be helpful, but help sessions, gear ups, and extra support will be offered to students who don't have any prior C++ experience. Most students take the class without any prior C++ experience. Some knowledge of basic linear algebra (i.e., vector and matrix multiplication, dot and cross products) may also be helpful, but none is required or assumed.

There are some **software and infrastructure prerequisites** as well:
* You need to be able to access Github, esp. Github classroom.
* You need to be able to compile and run the course projects on your own computer, or have a *very*
fast internet connection to the department machines. Most laptop computers post-2015 should have no problem with compiling and running projects. More specifically, we use OpenGL 4.0 for many of our projects, which is supported on Intel, AMD, and NVIDIA graphics hardware that most common computers have newer than 2012.
* You need at least 3GB of space on your machine to dedicate to CSCI 1230.

### Topics

The full list of CSCI 1230 topics can be found on the "class" page of the website (https://csci1230.graphics/lectures.html). These topics include:
* **OpenGL**: Industry standard graphics library used to produce real-time 2D and 3D graphics.
* **3D geometry**: Different ways 3D shapes can be represented in graphics applications.
* **Image processing**: How to process images by applying filters and transformations while minimizing artifacts like aliasing (a.k.a. “jaggies”).
* **Viewing 3D scenes**: How to create a virtual camera that converts a 3D scene to a 2D image using linear algebra.
* **Illumination**: Mathematical models that can be used to calculate the amount of light reflected from an object in a scene.
* **Ray tracing**: A rendering method that is used to produce pseudo-realistic images with reflections, refraction, and other effects.
* **Color theory**: Various ways to think about and represent colors.
* **Input & output devices**: Different devices used to interact with and view (or otherwise "sense") computer graphics.
* **Virtual and Augmented Reality**: An introduction to creating fully immersive computer-generated experiences.

### Course-Related Work Expectations ###

Over 13 weeks, students will spend 3 hours per week in class (39 hours total), and approximately 2 hours per week in labs (20 hours total). Homeworks, which consists of 1-2 week projects and the accompanying algorithm assignments, usually take 15-20 hours per week, though they can also require somewhat more or less time depending on how much extra credit a student chooses to implement. In any case, students will spend a minimum of 8.5 hours per week and 120 hours total on homework by the end of the semester.

### Assignment Structure ###

Your CSCI 1230 grade consists of 1 tiny written homework, 7 rigorously graded projects, 12 labs that are given completion grades (one of the three final labs is optional), and a final project that is graded according to your presentation to the class during finals period, together with a small "citizenship/participation" score. There are no exams or quizzes, and final grades are not curved; if the work meets specification, it deserves an A, and that is the most common grade. HW0 (which is about the collaboration policy) is critical: you must do it correctly or fail the course.
* **HW0** (Out 9/9) ***(must be done correctly to pass course)***
* **Projects**:
  * **Brush** (Out 9/9, Due 9/21, weight 7%)
  * **Shapes** (Out 9/21, Due 10/5, weight 12%)
  * **Intersect** (Out 10/5, Due 10/19, weight 13%)
  * **Ray** (Out 10/19, Due 11/2, weight 11%)
  * **Sceneview** (Out 11/2, Due 11/11, weight 8%)
  * **Filter** (Out 11/11, Due 11/24, weight 11%)
* **"Algo" assignments for projects**: 10%
* **Final Project** (Out 11/16, Due 12/9, Presentation date 12/10, weight 15%)
* **11 out of 12 Labs** (Due by Monday of next lab, total weight 10%)
* **Citizenship/Participation** (weight 3%)

Furthermore, students will have the option to log their attendance at TA hours. This helps us track participation at TA hours, which may be taken into account when calculating final grades for some students. A student’s grade will not be harmed by lack of attendance.

### Materials ###

The primary text for this course is the most recent edition of *Computer Graphics: Principles and Practice, by John Hughes, Andy van Dam, Morgan McGuire, David Sklar, Jim Foley, Steve Feiner, and Kurt Akeley*. The book is currently available at Amazon.com for $80.

The book is not required, as the lecture slides for CS1230 are nearly comprehensive. These slides do not replace the textbook, but they are the best source of information that is directly relevant to the assignments.

The course website has a wealth of information that will be useful to you throughout the semester:
* Instructions and stencil code for each project: https://csci1230.graphics/asgns.shtml
* Instructions and stencil code for each lab: https://csci1230.graphics/labs.shtml
* Links to PDF and PowerPoint versions of each class and accompanying videos and/or demos: https://csci1230.graphics/lectures.shtml
* Documentation for the support code, help session slides, and links to external sources for help
with OpenGL: https://csci1230.graphics/docs.shtml
* TA hours schedule and contact information: https://csci1230.graphics/staff.shtml

### Collaboration Policy ###

CSCI 1230 has a strictly enforced [collaboration policy](https://github.com/cs123tas/docs/blob/master/2021/2021%20Collaboration%20Policy.pdf) in line with [Brown's Academic Code](https://www.brown.edu/academics/college/degree/sites/brown.edu.academics.college.degree/files/uploads/Academic-Code.pdf) which emphasizes that all written work must be the student's own except for certain limited forms of collaboration that are explicitly permitted. Our collaboration policy in particular prohibits collaboration on the design and implementation of programs.

### Half-Credit Course ###

Students can also register for CSCI 1234 and complete specific additional assignments for each project to earn an extra half-credit. This course can be used to get grad credit, and it can also count as a capstone course. See the Half-Credit Missive section of this document for more information.

### Late Policy ###
A late algo or lab checkoff will receive **no credit**. Each day a project is turned in late will be penalized 10% of the possible total points. (If you are 25 hours late in handing in that’s a 20% even though you hand in during the first hour of that ‘extra day’).

Every student has five late passes that can each be used to waive a day that a project was turned in late (and the opportunity to earn an extra late pass by filling out the mid-semester and final survey). A maximum of 3 late days can be applied per project (except for Ray and the Final project). These late passes will automatically be applied optimally (to maximize your grade) at the end of the semester. The Filter project is due on the Wednesday before Thanksgiving, and you may use a *single* late day to extend this due-date to Sunday of Thanksgiving break. You may not use any more late days on Filter. You may **not** use **any** late days at all on the Final project.

Late days are expected to cover clustering of due dates and job interviews. For sickness and other issues of wellbeing, please obtain a note from health services or a dean and communicate with Daniel; the TAs will not be involved in handling these.

Lastly, all labs (11 out of 12) and projects must be handed in with at least minimal functionality by the end of the semester in order to receive your course grade (these handins are **not** exceptions to late penalties). As projects build upon each other, it is important to start early and quickly recover from late handins.
