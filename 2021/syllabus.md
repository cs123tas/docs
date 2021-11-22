# CSCI 1230 Course Syllabus

Welcome to CSCI 1230, the longest-running computer graphics course in the known universe! This document will get you started with the course.

## Table of Contents

* [Course Missive](#course-missive): The essential information about the course, its content, workload, and policies.
  * [Course Staff & Essential Info](#course-staff--essential-info)
  * [Prerequisites](#prerequisites)
  * [Learning Goals](#learning-goals)
  * [Work Expectations](#work-expectations)
  * [Grading](#grading)
  * [Materials](#materials)
  * [Collaboration Policy](#collaboration-policy)
  * [Late Policy](#late-policy)
  * [Diversity and Inclusion](#diversity-and-inclusion)
  * [Accommodations](#accommodations)
  * [Mental Health](#mental-health)
  * [Incomplete Policy](#incomplete-policy)
* [Half-Credit Missive](#half-credit-missive): Information for those interested in taking CSCI 1234 for an additional half credit.
* [Student Guide](#student-guide): More in-depth details about course contents, policies, computing infrastructure, and advice.
  * [Lectures](#lectures)
  * [Help Sessions](#help-sessions)
  * [Programming](#programming)
  * [Assignments](#assignments)
  * [Support Code Tips](#support-code-tips)
  * [Grading](#grading-1)
  * [Getting Your Questions Answered](#getting-your-questions-answered)
  * [Welcome!](#finally-welcome)

---

## Course Missive

### Course Staff & Essential Info
* Professor: Daniel Ritchie (dritchi1)
* Head TAs: Alex Mina (jmina), Caleb Trotz (ctrotz)
* UTAs: Aalia Habib (ahabib3), Aparna Natarajan (anatara7), Adam Pikielny (apikieln), Alana White (apikieln), Breese Sherman (bsherma3), Junewoo Park (jpark49), Yuna Hiraide (yhiraide)
* Lectures: Tues & Thurs 10:30am -- 11:50am, location TBD. Lectures will be recorded and promptly available online for students who have chosen remote asynchronous participation this semester.
* Course website: https://csci1230.graphics
* TA mailing list: cs1230tas@cs.brown.edu
* Ed discussion board: https://edstem.org/us/courses/12828
* Labs/Help Sessions/Gear Ups: See the [course calendar](https://csci1230.graphics) for times and locations

### Prerequisites

The official prerequisite **courses** for CSCI 1230 are CSCI 0150/0160, CSCI 0170/0180, or CSCI 0190.

CSCI 0330, because it uses C, can be helpful but not strictly required. CSCI 0320, for its software design, is additionally helpful but not required. Some familiarity with C++ will be helpful, but help sessions, gear ups, and extra support will be offered to students who don't have any prior C++ experience. Most students take the class without any prior C++ experience. Some knowledge of basic linear algebra (i.e., vector and matrix multiplication, dot and cross products) may also be helpful, but none is required or assumed.

There are some **software and infrastructure prerequisites** as well:
* You need to be able to access Github, esp. Github classroom.
* You need to be able to compile and run the course projects on your own computer, or have a *very*
fast internet connection to the department machines. Most laptop computers post-2015 should have no problem with compiling and running projects. More specifically, we use OpenGL 4.0 for many of our projects, which is supported on Intel, AMD, and NVIDIA graphics hardware that most common computers have newer than 2012.
* You need at least 3GB of space on your machine to dedicate to CSCI 1230.

### Learning Goals

Students who complete this course will:
* Be familiar with different ways 3D shapes can be represented in graphics applications.
* Understand mathematical models for calculating the amount of light reflected from an object in a scene.
* Be able to implement the ray tracing rendering algorithm, which produces pseudo-realistic images with reflections, refractions, and other effects.
* Be comfortable writing real-time graphics programs using OpenGL and the GLSL shading language.
* Know how to create and control virtual cameras which can convert 3D scenes to 2D images using linear algebra.
* Know how to process images by applying filters and transformations while minimizing artifacts such as aliasing (a.k.a. “jaggies”).
* Understand the fundamentals of human color perception, the abilities of displays to reproduce colors, and the impact of color choice on viewer experience.

The full list of CSCI 1230 topics can be found on the "class" page of the website (https://csci1230.graphics/lectures.html).

### Work Expectations

Over 13 weeks, students will spend 3 hours per week in class (39 hours total), and approximately 2 hours per week in labs (20 hours total). Homeworks, which consists of 1-2 week projects and the accompanying algorithm assignments, usually take 15-20 hours per week, though they can also require somewhat more or less time depending on how much extra credit a student chooses to implement. In any case, students will spend a minimum of 8.5 hours per week and 120 hours total on homework by the end of the semester.

### Grading

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

### Materials

The primary text for this course is the most recent edition of *Computer Graphics: Principles and Practice, by John Hughes, Andy van Dam, Morgan McGuire, David Sklar, Jim Foley, Steve Feiner, and Kurt Akeley*. The book is currently available at Amazon.com for $80.

The book is not required, as the lecture slides for CS1230 are nearly comprehensive. These slides do not replace the textbook, but they are the best source of information that is directly relevant to the assignments.

The course website has a wealth of information that will be useful to you throughout the semester:
* Instructions and stencil code for each project: https://csci1230.graphics/asgns.shtml
* Instructions and stencil code for each lab: https://csci1230.graphics/labs.shtml
* Links to PDF and PowerPoint versions of each class and accompanying videos and/or demos: https://csci1230.graphics/lectures.shtml
* Documentation for the support code, help session slides, and links to external sources for help
with OpenGL: https://csci1230.graphics/docs.shtml
* TA hours schedule and contact information: https://csci1230.graphics/staff.shtml

### Collaboration Policy

CSCI 1230 has a strictly enforced [collaboration policy](https://github.com/cs123tas/docs/blob/master/2021/2021%20Collaboration%20Policy.pdf) in line with [Brown's Academic Code](https://www.brown.edu/academics/college/degree/sites/brown.edu.academics.college.degree/files/uploads/Academic-Code.pdf) which emphasizes that all written work must be the student's own except for certain limited forms of collaboration that are explicitly permitted. Our collaboration policy in particular prohibits collaboration on the design and implementation of programs.

### Late Policy
A late algo or lab checkoff will receive **no credit**. Each day a project is turned in late will be penalized 10% of the possible total points. (If you are 25 hours late in handing in that’s a 20% even though you hand in during the first hour of that ‘extra day’).

Every student has five late passes that can each be used to waive a day that a project was turned in late (and the opportunity to earn an extra late pass by filling out the mid-semester and final survey). A maximum of 3 late days can be applied per project (except for Filter and the Final project). These late passes will automatically be applied optimally (to maximize your grade) at the end of the semester. The Filter project is due on the Wednesday before Thanksgiving, and you may use a *single* late day to extend this due-date to Sunday of Thanksgiving break. You may **not** use **any** late days at all on the Final project.

Late days are expected to cover clustering of due dates and job interviews. For sickness and other issues of wellbeing, please obtain a note from health services or a dean and communicate with Daniel; the TAs will not be involved in handling these.

Lastly, all labs (11 out of 12) and projects must be handed in with at least minimal functionality by the end of the semester in order to receive your course grade (these handins are **not** exceptions to late penalties). As projects build upon each other, it is important to start early and quickly recover from late handins.

### Diversity and Inclusion

Our intent is that this course provide a welcoming environment for all students who satisfy the prerequisites. Our TAs have undergone training in diversity and inclusion, and all members of the CS community, including faculty and staff, are expected to treat one another in a professional manner. If you feel you have not been treated in a professional manner by any of the course staff, please contact either the instructor, [Ugur Cetintemel](mailto:ugur@cs.brown.edu) (Dept. Chair), [Tom Doeppner](mailto:twd@cs.brown.edu) (Vice Chair) or [Laura Dobler](mailto:laura_dobler@brown.edu) (diversity & inclusion staff member). We will take all complaints about unprofessional behavior seriously. Prof. Krishnamurthi has [good notes](http://cs.brown.edu/courses/cs019/2016/professionalism.html) on this area. To access student support services and resources, and to learn more about diversity and inclusion in CS, please visit [this webpage](http://cs.brown.edu/about/diversity/resources/).

Brown welcomes students from all around the country and the world, and their unique perspectives enrich our learning community. To empower students whose first language is not English, an array of support is available on campus, including language and culture workshops and individual appointments. For more information, contact the English Language Learning Specialists at [ellwriting@brown.edu](ellwriting@brown.edu).

### Accommodations

Brown University is committed to full inclusion of all students. Please inform Daniel if you have a disability or other condition that might require accommodations or modification of any of these course procedures. You may email Daniel, come to office hours, or speak with him after class, and your confidentiality is respected. We will do whatever we can to support accommodations recommended by SEAS. For more information contact Student and Employee Accessibility Services ([SEAS](https://www.brown.edu/campus-life/support/accessibility-services/)) at 401-863-9588 or SEAS@brown.edu. Students in need of short-term academic advice or support can contact one of the deans in the Dean of the College office.

### Mental Health

Being a student can be very stressful. If you feel you are under too much pressure or there are psychological issues that are keeping you from performing well at Brown, we encourage you to contact Brown’s Counseling and Psychological Services [CAPS](https://www.brown.edu/campus-life/support/counseling-and-psychological-services/). They provide confidential counseling and can provide notes supporting extensions on assignments for health reasons.

### Incomplete Policy

We expect everyone to complete the course on time. However, we certainly understand that there may be factors beyond your control, such as health problems and family crises, that prevent you from finishing the course on time. If you feel you cannot complete the course on time, please discuss with the instructor the possibility of being given a grade of Incomplete for the course and setting a schedule for completing the course in the upcoming year.

*Thanks to Tom Doeppner and Laura Dobler for the text on accommodation, mental health, and incomplete policy.*

---

## Half-Credit Missive

Here, we provide more detailed information to students who are attempting to earn an additional half-credit while taking CSCI 1230. CSCI 1234 is **not** a separate course and cannot be taken alone. If you are a graduate student and wish to earn 2000 level grad credit, you will also need to follow these guidelines.

### Registration

You must register for CSCI 1230 **and** CSCI 1234 to earn the half-credit or grad credit (graduate students may sign up with the HTA as to not incurr additional fees). If you are uncertain about attempting this, we strongly encourage you to register for both anyway. You can always drop the lab course later in the semester if you decide the workload becomes untenable. If you have any questions, feel free to email cs1230tas@lists.brown.edu.

### Assignment Enhancements

For each of the 6 projects, you will be expected to complete additional features in order to pass the lab course. We've worked hard to ensure that these enhancements are not just more work, but that they also will increase your understanding of graphics programming. This does not mean they are easy and/or quick to do.  In a couple of cases you will be able to use your creativity to implement something of your own choosing. Do not assume what you implement will count towards the half credit requirement! Check with a TA during hours or email them before handing in. As a group, they have all implemented the enhancements and should be able to help answer any questions. 

### Time Management

We tell everyone this, but for meeting these requirements, you will really need to start each project as soon as it is released. We aren't joking or exagerating in the slightest. If you find the assignments easy, we hope you will apply to be a CSCI 1230 TA next year!

### Further Questions?

As always please, email the TAs if you have any questions on half credit requirements.

---

## Student Guide

This section provides more in-depth information on the contents of the course and our expectations for the work that students will produce. The Course Missive section above covers the most critical info, but if you've made up your mind that you want to take CSCI 1230 (and we hope you have!), then read on for more details.

### Lectures

A strong correlation has been shown between those who do well in CSCI 1230 and those who come to class. Lectures are enriched by class discussion, live demos and other content beyond the slides themselves. We strongly encourage class attendance.

We don’t have nearly enough lecture time to teach everything we wish we could. The lecture topics have been carefully selected by Daniel and the TAs, taking into account the feedback we receive from former CSCI 1230 students. If you feel like you aren’t getting enough out of the lectures, we encourage you to talk to Daniel or the TAs rather than abandoning them altogether. We are constantly revising CSCI 1230, and we take all feedback under serious consideration during our weekly staff meetings.

Sick? Please do not come to lecture or use public computer labs if you have a communicable illness (like the flu). Ask a friend to fill you in on details from class, and review the lecture slides online. We would like to keep everyone in good health.

### Help Sessions

There will be several CS1230 help sessions throughout the year. There are two on C++, another on linear algebra, and a third on the shader programming language GLSL. Dates and times will be on the course calendar. If you feel that a particular help session would be useful to clarify a topic, you may contact the Head TA (at cs1230headtas@lists.brown.edu) to discuss your proposal.

### Programming

Because graphics work can be computationally intensive, CSCI 1230 is one of the few remaining courses at Brown to use C++, and the only remaining course to teach it. In computer graphics, the performance implications of managed language features such as garbage collection and memory bounds-checking can be unacceptably high. We promote object oriented coding practices to ensure maintainability and extensibility as your graphics system grows. One of the key techniques you’ll take away from CSCI 1230 is the ability to carefully balance raw performance with excellent code maintainability and style.

#### Toolkit 

Creating GUIs in C++ is often a hassle. We use Qt to achieve cross-platform UI functionality.
Because Qt depends on special preprocessors and compilers, we recommend that you use Qt Creator to author your C++ code. Qt Creator features automatic code completion, integrated debugging, and automatic Makefile management. Both Qt and Qt Creator are free (under the LGPL license) and cross-platform.

**Where is Qt Creator installed?**

For your convenience, Qt Creator is installed in several locations throughout the CIT.
* All department Linux machines
* All department Windows machines
* All CIS cluster Windows machines on the second floor of the CIT

You may also install the Qt SDK on your personal computer to work from home. Regardless of your choice of development platform, you must ensure that your code compiles and runs properly on the Linux machines in the Sun Lab.

#### Software Engineering

We expect that you have all had a thorough grounding in the principles of good software design by now. Most of the assignments are relatively small, and shouldn't require hours of design work. We care mostly about the functionality, stability, and speed of your implementation; however, we will also grade partially on code quality. Good engineering practices early on will greatly help you on future assignments.

Basic engineering principles by which you should abide:
* Avoid repeated code by thinking about good class design in advance.
* Don't do anything grossly inefficient. For example, factor repeated computation out of loops.
* Always remember to free your memory.

#### Don't know C++?

Students are able to take the course without knowing C++. However, these students will need to spend extra time at the beginning of the course learning C++. The Intro to C++, Intermediate C++, and Advanced C++ help session slides are available on the CSCI 1230 documents page. These help sessions will be run by the TAs at the start of the semester. See section 3 above. TAs are also ready and willing to help students with C++ questions at office hours. Aside from the help sessions and TA help, the course has no special provisions for students learning C++. Programs will be due at the same time for everyone and will be graded on the same scale. 

### Assignments

#### Projects

##### Brush
The first assignment is designed to get your feet wet in the world of graphics programming. In this assignment, you will be implementing various different airbrushes, similar to ones found in many commercial painting programs such as Adobe Photoshop. This assignment should give you a good introduction to the kind of C++ programming you will be doing in this course, as well as gently familiarize you with Qt user interfaces.

##### Shapes
This assignment covers one of the earliest steps in the 3D rendering pipeline: object tessellation. For this assignment you will be constructing simple 3D objects (e.g., spheres and cylinders) out of triangles and then displaying them on the screen. All you need to do for this assignment is compute the necessary triangles; our stencil code handles the task of drawing them for you.

##### Intersect
In this assignment, you will begin to explore an algorithm for drawing (or 'rendering') the shapes you tessellated in the Shapes assignment. Specifically, you will compute intersections between these objects and rays (of light). You will then use this code to create somewhat photorealistic images of scenes.

##### Ray
Ray tracing is a method for rendering realistic pictures of geometric objects. It uses available information about lighting and optical effects like light reflection and refraction. It may sound complicated, but it is a relatively simple technique, and the cool pictures you get are well worth it! You will essentially be taking your code from Intersect, adding in the ability to illuminate the objects, and applying textures from 2D images.

##### Sceneview
In this assignment, you will dive into real-time graphics programming with OpenGL and create an interactive viewer for the 3D scenes you rendered in the Intersect and Ray assignments. This assignment builds upon the code from Shapes, Intersect, Ray, and from the Camtrans lab.

##### Filter
Ever wonder how programs like Photoshop generate all those cool special effects? This assignment represents a subset of the functionality that photo editing programs have. It is designed to teach you the basics of image processing and anti-aliasing. You will implement various image manipulation operations like edge detection, blurring, and image scaling.

##### Final Project
Lastly, you will be creating a final project. The final project can be anything you want that includes one or more of the concepts we covered during the semester, plus a technique you research on your own. Examples include a short game, a cool OpenGL shader program, a demo scene, an implementation of an advanced rendering system, or some combination of the above! Note you're not restricted to these ideas alone. We’ll cover the final project in greater detail in late November.

#### Labs
In addition to homework assignments, a series of labs will provide hands-on experience with various graphics programming topics and tools. The concepts you learn in lab will prove quite useful for implementing your final project (see section above).

#### Algos

##### Algorithm worksheets

Each programming assignment will be accompanied by a written algorithm (“algo”) assignment to get you started thinking about how to approach the assignment mathematically and algorithmically. These hand-ins will contribute 10% of the final grade. There is also an algorithm assignment for the Camtrans lab. See the assignment handouts for more details and exceptions. Algorithm worksheets are returned the same day as the deadline so you can begin coding with confidence right away!

Algorithm answers should be clear and succinct. Don't just start writing. Think first, and then write up the clearest answer you can. If we ask you to describe a section of the project’s algorithm, you should probably go with a description, or pseudo code, rather than actual C++. That said, some incredibly simple parts, such as loops, may be easier to read in actual code.

##### Tips for Algorithm worksheets

When you think you’re done with the algorithm worksheet, begin coding immediately while it’s still fresh in your mind. Don’t wait for the solutions to begin coding. The solutions to the algorithm worksheets are designed to help you to debug your program, not to help you write the code for the first time.

Take it seriously! Expect to spend between 1 to 2 hours on each algorithm worksheet. Late algorithm worksheets aren’t accepted, so be sure to turn them in on time.

#### Optimization

While we don’t expect you to go overboard with optimization, we do expect your programs to perform well. Be sure to factor repeated computation out of loops, but don’t feel compelled to write assembly code or special SSE instructions.

**Memory Management**: Rather than repeatedly allocating bits of memory, allocate a large chunk all at once. Use smart pointers and STL or Qt data structures that automatically manage your memory when approrpiate.

**Orders of Magnitude**: Be aware of the differences (especially with regard to O(n) performance and memory overhead) between different data structures. We’ll dock points for big memory leaks and things you obviously should have factored out of your loops.

**Accuracy**: Above all, don’t sacrifice accuracy for performance! You will not lose points for an efficient, yet accurate, program. If you ever have a question about optimization, ask a TA on hours.

#### Workload

This set of assignments probably looks like a burden, but in fact, if approached sensibly (i.e., working steadily), you will have sufficient time for each and every one. The normal load is about 15 hours per week. By the time you take CSCI 1230 you are expected to be a competent programmer, with good design and debugging habits, and able to turn assignments in on time. Good time management will make this course much more enjoyable!


### Support Code Tips

#### Vectors and Matrices

The support code uses a library called glm for vector and matrix operations. Glm contains vector types called glm::vec2, glm::vec3, and glm::vec4, as well as matrix types such as glm::mat4. Examples:
```cpp
glm::vec2 pos; // Default constructor initializes x and y to 0
pos.x = 1;
glm::value_ptr(pos)[1] = 3;
std::cout << glm::to_string(pos) << std::endl; // Outputs [ 1 3 ]

glm::vec3 v = glm::vec3(1, 2, 3);
glm::vec3 n = glm::vec3(5, 2, 0);
float dotProduct = glm::dot(v, n); // dotProduct == 9
for (int i = 0; i < 3; ++i)
   glm::value_ptr(n)[i] = 2 * i;
glm::vec3 piecewiseProduct = v * n; // piecewiseProduct == [0, 4, 12]
```

#### Qt Creator

Qt Creator has lots of shortcuts and tricks that can make your life a lot easier. Here are some of the most helpful shortcuts:
* F2: Go to the definitions of the symbol under the cursor.
* F4: Switches between the header and cpp file.
* Ctrl+Shift+R: Rename and refactor the symbol under the cursor.
* Ctrl+Shift+U: Find all usages of the symbol under the cursor.
* Ctrl+L: Go to a specific line number.
* Ctrl+K: Godmode - Search for **anything**. If you learn one new shortcut, this should be it. Examples:
   * Type Ctrl+K followed by “m paintGL” to see a list of all methods named paintGL. Hit Enter to go to the implementation of the selected method.
   * Type Ctrl+K followed by “c Canvas2D” to see a list of all classes named Canvas2D. Hit Enter to go to the Canvas2D class definition.
   * Type Ctrl+K followed by “? QList” then hit Enter to view the Qt Help on the QList class.
   * (For more information, hit Ctrl+K and read what each letter prefix does)

#### Floating Point Calculations

Keep in mind that floating point numbers have limited precision, so floating point calculations may lead to rounding errors. To compare two floating point numbers x and y for equality, use abs(x-y) < EPSILON. You can define an EPSILON that works well for your program (usually 1e-4 to 1e-8).

#### Settings

The support code defines a global object named settings to hold values entered through the GUI. This object is automatically updated when things are changed in the GUI, though the GUI is not updated when the settings object is changed programmatically.


### Grading

Your final grade will be determined based on the programming assignments, algorithm hand-ins, and labs.

You must complete all the assignments (including 11 out of 12 labs) to pass the course. As in all other computer science courses at Brown, you must hand in a working solution for all programming assignments in order to be eligible for a passing grade. Please note the adjective working: if you receive a grade of NC (no credit) on any of the assignments (before late penalties are deducted), you will be expected to revise your program and hand in an acceptable version if you want to pass the course. Also note that the reverse implication is not intended: handing in all assignments does not guarantee that you will pass the course; your accumulated points will determine that.

Daniel doesn't use a curve, and would be delighted to hand out As to the entire class. Indeed, the majority of students traditionally have worked hard and gotten As. In borderline cases (e.g. 89-91), Daniel will take attendance and class participation into account, as well as your perceived effort and dedication. We all love to both give and receive good grades, but do understand that merely working hard doesn’t guarantee you an A. Your grade will reflect primarily upon the quality, correctness, and timeliness of your hand-ins.

#### Extra Credit

There is ample room for bells, whistles, and other credit-garnering efforts on the part of ambitious programmers. You are invited to get creative, as long as it does not make you late. Rewarding bells and whistles with extra credit is left to the discretion of the TAs, so we strongly encourage you to discuss your creative plans with a TA before you forge ahead to make sure that they are considered appropriate for credit. Also, keep in mind that bells and whistles should only be done after the standard assignment is fully working since they won't count in lieu of missing or buggy features! CSCI 1230 offers many opportunities for extra credit: if you finish a program a little early, seek appropriate inspiration and add something fancy.

#### Regrade Requests

Sometimes you may feel that you have been graded unfairly. If you ever feel this way, please request a regrade on Gradescope. Once your request is evaluated, you will be provided with an explanation and possibly points back. If you are not satisfied with the regrade decision please talk to the Head TA. If there is still a problem, Daniel is the final word in grading and will be happy to hear what you have to say.

If you decide to challenge a grade, you must do so within two weeks of its receipt. In the past, students have tried to get points back on all of their assignments in the last week of classes. Our first priority is fairness, both to us and to you! You may ask questions about your grades at any time. You can’t change the contents of your hand-in after your grade is returned. If you discover that you handed in the wrong work after you get your grade back, or if you fix your program after getting its grade back, we are unable to take that “external” content into account for grading purposes.


### Getting Your Questions Answered

For most course-related questions, you should ask a TA during TA hours.

You may not ask TAs course-related questions when they are not on hours. All TAs are prohibited by department and university policy from answering course-related questions when not on official TA hours. TAs may answer general administrative questions when not on TA hours.

Thank you for helping us comply with departmental and university regulations (which reflect applicable labor laws). If you have any questions about this policy, please contact mta@cs.brown.edu.

#### TA Hours

The TA hour listing is available from the CS1230 home page. We will make every effort to maintain these hours without exception. On rare occasion, we might need to cancel or reschedule a TA hour session. When TA hours are rescheduled or exceptions are made, these will be announced on the CS1230 web page.

TA hours are often very busy, and many times there will be a waiting list on the board. You may sign up on the waiting list when TA hours are in progress, but not before TA hours start. The TA will erase the waiting list at the start of TA hours each day. If the waiting list is very long and the end of TA hours is approaching, the TA may close the waiting list so that all people on the waiting list can be helped before TA hours are over. You can help alleviate this problem of crowded hours by simply starting early. While there is no bonus for doing this, starting early often means finishing in less time, since you won't have to wait as long to get your questions answered.

Before asking a TA for help, please check the lecture slides to see if your question is answered there. If you still do not understand something, you are welcome to ask questions and clarifications about the lecture slides.

Please note that taking any source code (or a TA’s modifications to your source code) away from TA hours is a violation of the CS1230 collaboration policy. The TAs are not here to debug your code, but rather to clarify your understanding of the concepts taught in class and used in the assignments.

#### Sending mail to the TAs

If there is a problem with an assignment that affects the entire class (such as a bug in the support code), you may e-mail the TAs at cs1230tas@lists.brown.edu. TAs will respond to course-related e-mail during their office hours. For administrative questions or if there is a problem with a TA, you can e-mail the head TA at cs1230headtas@lists.brown.edu.

Questions related to coding the projects or concepts explained in class should be asked at TA hours and TA help sessions. We are not able to respond to these types of questions via e-mail.

#### Course webpage

The CS1230 web page, which you are responsible for checking and reading daily, is located at https://csci1230.graphics. It is a useful source of online course material. A wide variety of things like lectures, handouts, the syllabus, TA hours, and software guides can be found on this site.

You are responsible for checking the web site frequently, as we will be updating it with important information as the semester progresses. Most updates to the website will be accompanied by an announcement to the course mailing list and Piazza.

### Finally, welcome!

As we mentioned before, CSCI 1230 is a continually evolving course. As such, we are bound to have our own 'bugs' hiding in the corners. Please read everything we hand out very carefully. If there is something which you do not understand, or which is not stated very clearly, please let us know so we can fix it right away.
This applies to the material discussed in lecture as well. Give us constructive criticism on all aspects of the course. The more feedback there is, the better we can make this course for you as the semester progresses, and the better we can make it for the next twenty-five years of Brown computer graphics students!

We just went through a lot of heavy talk. Please take all of it seriously, but also remember that we're not trying to scare you. We are here to help you! We're just clearing preliminaries and establishing the ground rules. With that done, we hope you'll have as much fun as we did in CSCI 1230.
