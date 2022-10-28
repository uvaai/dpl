# Data Processing and Representations

University of Amsterdam / Programming Lab / 5082DAPI6Y

## Syllabus<br><small>Fall 2021</small>

This course is the continuation of Python for Data Processing. A data pipeline
is a sequence of steps that transforms raw data into something more useable.
The course will taught in slightly modified form this semester, and we'll focus
on two aspects in particular. For the first half we'll learn about classes and
using them to represent data in your program. The second half of the course
will be about other types of representations of data and the transformations you
can apply to them.

## Staff

Tim Doolan (coordinator)

Wouter Vrielink (teacher)

You can reach us at <minorai@mprog.nl> for any practical matters or other
questions.

## Schedule

The core schedule for this course, combined with Introduction to Machine Learning 2, is
built around working with the material each weekday from 9 to 5.  For this we
have one room on the Science Park campus permanently reserved for minor AI
students, namely **L0.11**, which provides enough space for all of you to work
on campus full-time.

Most on-campus activities, including practical assistance, will generally be
held in this room. There are some exceptions with activities that do not fit
in the room, like the group seminars and the exam. The schedule for these
group seminars can be found on Datanose [here](https://datanose.nl/#course[111919])

The schedule for the practical assistance hours and lectures that will be held
in L0.11 can be found in the "Asking Questions" section below.

### Deadlines and daily schedules

The deadlines for each module can be found on the module schedule pages
(the first item in the sidebar for each module).

We've found that it can be difficult for students to plan when to work on what
part of the material, especially with two completely new courses, that together
require a full-time time investment. Being unfamiliar with a subject makes it a
lot harder to estimate how long something might take, and structuring your work
can be more difficult. To help with all of this, we've made a day-to-day schedule
for each module, which indicates what elements should be completed each day.

If you're finding it hard to keep on track with the daily schedule, you can
contact the staff at <minorai@mprog.nl>. We can discuss possible approaches or
even offer extra help or resources, if needed. In general, it is a good idea to
already contact us if are more than 1 day behind on the schedule, so we can
look at possible solutions early.

### Absences and calling in sick

If you are sick or are otherwise unable to come to campus, you should inform
your group TA by sending them a message on Slack. When you are feeling better,
inform your TA again, so a new planning for that module can be made. Any exceptions
or extensions required for this will need to be discussed with course staff (so not
your TA). See the extension policy below for more details.

If you are experiencing coronavirus-related symptoms, but are feeling fit enough
otherwise, you should do a self-test. If the self-test is negative, you can and
should still come to campus. If the self-test is positive, you should report in sick,
like described above, but work from home instead. When contacting your group TA, do
also mention that you are absent because of a positive self-test, so we know you are
working from home.

### Extension policy and late days

There are two types of extension; staff extensions and late days.

Staff extensions usually require meeting with staff and will generally also
include making an alternative planning for the module. If any circumstances
arise that would make it hard for you to make the deadline, send us an
email at <minorai@mprog.nl> so we can discuss your situation. Please do this as
soon as the problem arises, rather than on the day of deadline, so we can
schedule a meeting and still have room in the module for an alternative planning.
Note that a meeting does not always guarantee an extension, as this might still
depend on the details of your circumstances.

In addition, for this course and Introduction to Machine Learning 2, you have a combined
total of 2 late days, each of which you can use to get a single 24 hour extension
for the module deadline. To request a late-day extension, you should write to
your TA on Slack *before* the deadline expires and indicate you intend to
use a late day. Any submissions received after the deadline without a requested
late day will not be graded, meaning your grade will default to a 1.

You can use only 1 late day per module to get a 24 hour extension on the deadline.
This extension is for the whole module, so applies to both courses. If the deadline
is on a Friday, using  a single late day will instead grant a 48 hour extension
over the weekend, meaning your deadline will move to Sunday. If you have used both
late-days, or require more than 24 hours of extension, you may still try and
request a staff extension.

Any staff extension request needs to be agreed upon before the deadline expires,
which means your request must be sent at least 2 hours before the actual deadline.
If you do not receive a reply in time, you should *always* still submit your
current version of the assignment before the deadline, so this part can still be
graded. Staff extension requests should be emailed to <minorai@mprog.nl>

## Asking questions

If you have any questions about the material, there are several ways to ask them
and get assistance.

### Practical assistance

There are 3 hours scheduled every day where you can ask practical
questions to the TA's of the minor. During these hours you can use the
"Request assistance" feature on the *Introduction to Machine Learning 2* [website](https://ml2.proglab.nl/),
using the question mark symbol at the top of the sidebar. Please use this feature instead of raising your hand
in class, as it ensures that all questions get handled in the order that they
are asked. Questions can of be about either the DPR or ML2 courses, just make
sure to mention what assignment you're working on. For your location, please
list the  table you are working at, so the TA handling your question knows
where to find you when it is your turn.

The hours are scheduled as follows:

* In general, assistance hours are from 10 to 13
* If there is a Q&A lecture listed in the daily schedule, the assistance will start after the Q&A, generally from 11 to 14

### Q & A Lectures

Every module there will be at least one Q & A lecture, where you can ask
questions about the theoretical parts of the course. The schedule for these
lectures can be found as part of the daily schedule for the module. The lectures
will always be in the main room L0.11 at 10:00 on the scheduled day.

These Q & A sessions will generally be scheduled the day after you should watch
the theory videos of the module. While watching the videos, you can write
down any questions you might have. There will be a question form linked
in the schedule, where you can submit your questions beforehand. Based on
the submitted questions, we'll discuss any part of the theory the might
need more clarification or context.

### Email the staff

If you have personal matters to discuss or other questions that do not fit any
of the formats above, you can email the course staff at <minorai@mprog.nl>

## Passing the course

This course consists of 3 larger assignments, that have been divided over 6
modules. For each first module of an assignment, you'll only receive feedback
on your code, which you can use the to improve your work. Then, for the second
module, you'll hand in the full assignment, which will be graded on a 1 to
10 scale. Your grade will mainly depend on the style and design of your code.

Design

: This is about adding effective abstractions to your code. Simple examples
might be to use a loop instead of copy-pasting code, or writing a function for
code you want to reuse several times.

Style

: This is about how readable your code is for other people. For example, using
clear variable names, adding comments and adding whitespace to separate blocks
of code can all help to make your code more readable.

If you've completed the entire assignment and your code produces the correct
output, your grade starts at 6. The remainder of your grade is then
determined as follows:

* 0 - Style and design of the code are of insufficient quality. Code does produce correct output and open questions have been answered.

* 1 - Style and design have had some attention, but there are still clear improvements to be made. Answers to most open questions are correct.

* 2 - Style and design are of sufficient quality, answers to open questions are correct.

* 3 - Style and design are very good, answers are correct and show understanding.

* 4 - Exceptional style and design, answers are beyond expectations.

### Attendance

We expect you to be present and working on campus every weekday from 9 to 5.
The material of these course covers a lot of practical skills, which cannot
just be learned from reading a book or watching a video. This means we expect
you'll need to ask plenty questions while working on assignments, as you try and
master these different skills. This is why we offer a lot practical assistance,
so there is a chance for you to ask the questions you have about the
scheduled material *every day*.

In spite of this, we maintain a soft attendance requirement. This means that
there is no hard rule stating that if you miss a certain percentage of days,
you will fail the course, i.e. attendance does not directly affect your final
grade.

However, indirectly attendance definitely will affect your grade. The material
requires you to work regularly on the assignments and ask questions along the
way so you don't get stuck. This means if you are not on campus, you are much
more likely to get stuck longer and thus end up with too little time before the
deadline.

In addition, we will still take attendence samples regularly in the room. This
does not affect whether you pass or fail the course, but is used as metric to
give us an indication of the effort you are putting into following the courses
as intended. If you request an extension or exception, or ask for extra
help or resources for the material, we'll always take your attendance into
account when considering your request. Requests from students who miss attendance
are generally much less likely to be granted.

If you are done with all the material for the module before the day of the deadline,
you should show your assignments to a TA by asking a question *during practical assistance*. The TA
will check if they agree every element has been properly completed, and if so
 you'll be granted exemption from the attendance checks for the rest of the module.

### Exam

The exam will be another *pass/fail* exam. More details on the exam will follow
later.

Once you've passed the exam, your final grade will be computed as the average
of the 3 graded assignments in the course.

## Academic honesty

This course's philosophy on academic honesty is best stated as "be reasonable." The course recognizes that interactions with classmates and others can facilitate mastery of the course's material. However, there remains a line between enlisting the help of another and submitting the work of another. This policy characterizes both sides of that line.

The essence of all work that you submit to this course must be your own. Collaboration on problem sets is not permitted except to the extent that you may ask classmates and others for help so long as that help does not reduce to another doing your work for you. Generally speaking, when asking for help, you may show your code to others, but you may not view theirs, so long as you and they respect this policy's other constraints. Collaboration on the course's test and quiz is not permitted at all.

Below are rules of thumb that (inexhaustively) characterize acts that the course considers reasonable and not reasonable. If in doubt as to whether some act is reasonable, do not commit it until you solicit and receive approval in writing from the course's heads. Acts considered not reasonable by the course are handled harshly.

### Reasonable

- Communicating with classmates about problem sets' problems in English (or some other spoken language).

- Discussing the course's material with others in order to understand it better.

- Helping a classmate identify a bug in his or her code at office hours, elsewhere, or even online, as by viewing, compiling, or running his or her code, even on your own computer.

- Incorporating a few lines of code that you find online or elsewhere into your own code, provided that those lines are not themselves solutions to assigned problems and that you cite the lines' origins.

- Reviewing past semesters' quizzes and solutions thereto.

- Sending or showing code that you've written to someone, possibly a classmate, so that he or she might help you identify and fix a bug.

- Sharing a few lines of your own code online so that others might help you identify and fix a bug.

- Turning to the course's heads for help or receiving help from the course's heads during the quiz or test.

- Turning to the web or elsewhere for instruction beyond the course's own, for references, and for solutions to technical difficulties, but not for outright solutions to assignment problems or your own final project.

- Whiteboarding solutions to problem sets with others using diagrams or pseudocode but not actual code.

- Working with (and even paying) a tutor to help you with the course, provided the tutor does not do your work for you.

### Not Reasonable

- Accessing a solution to some problem prior to (re-)submitting your own.

- Asking a classmate to see his or her solution to a problem set's problem before (re-)submitting your own.

- Decompiling, deobfuscating, or disassembling the staff's solutions to problem sets.

- Failing to cite (as with comments) the origins of code or techniques that you discover outside of the course's own lessons and integrate into your own work, even while respecting this policy's other constraints.

- Giving or showing to a classmate a solution to a problem set's problem when it is he or she, and not you, who is struggling to solve it.

- Looking at another individual's work during the test or quiz.

- Paying or offering to pay an individual for work that you may submit as (part of) your own.

- Providing or making available solutions to problem sets to individuals who might take this course in the future.

- Searching for or soliciting outright solutions to problem sets online or elsewhere.

- Splitting a problem set's workload with another individual and combining your work.

- Submitting (after possibly modifying) the work of another individual beyond the few lines allowed herein.

- Submitting the same or similar work to this course that you have submitted or will submit to another.

- Submitting work to this course that you intend to use outside of the course (e.g., for a job) without prior approval from the course's heads.

- Turning to humans (besides the course's heads) for help or receiving help from humans (besides the course's heads) during the quiz or test.

- Viewing another's solution to a problem set's problem and basing your own solution on it.

In all cases we follow the directives regarding fraud and plagiarism of the
University of Amsterdam and of the Computer Science
BSc programme. Find them here in [English] and [Dutch].

[Dutch]: http://uva.nl/plagiaat
[English]: https://student.uva.nl/en/content/az/plagiarism-and-fraud/plagiarism-and-fraud.html
