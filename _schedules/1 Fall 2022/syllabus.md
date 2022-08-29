# Data Pipelines

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

### Deadlines

The deadlines for each module can also be found on the module schedule pages
(the first item in the sidebar for each module).

We've found that it can be difficult for students to plan when to work on what
part of the material, especially with two completely new courses, that together
require a full-time time investment. Being unfamiliar with a subject makes it a
lot harder to estimate how long something might take, and structuring your work
can be more difficult, especially when working from home. To help with all of
this, we've made a day-to-day schedule for each module, which indicates what
elements should be completed each day.

### Extension policy

If there are circumstances that require you to have a deadline extension, you
must request this at least 1 hour *before* the deadline expires. The staff will
then determine if extension is permissible and make an alternative schedule
with you. Submissions after the deadline without prior permission will not be
accepted. To avoid late extension requests, it is strongly suggested that you
consult the module's schedule regularly to see if you are on track for the
module, and if not, to contact the staff early. For discussing your module
progress or requesting an extension, you can reach us at <minorai@mprog.nl>.

*Note:* While it is of course possible for circumstances to arise that require
you to need an extension, consecutive extension requests are usually not
granted. If you are given an extension, we will also discuss an alternative
schedule, which is intended to get you back on track for the regular schedule.
If the situation is such that this is not feasible, then an alternative
schedule will be constructed in which you follow fewer courses over a longer
period of time. Due to the content of each module being heavily dependent on
the content of the previous modules, skipping or only partially completing
modules is *not* possible in this curriculum.

### Absences and calling in sick

With COVID, the policy for when you're sick has become a little more
complicated, but also *vital* in minimizing the number of students that has to
work from home, so please do stick to these procedures. The general UvA policy
for the return to campus can be found
[here](https://www.uva.nl/en/current/coronavirus/return-to-campus/return-to-campus.html).
The most important consequence of this policy is that, whenever you're
experiencing coronavirus-related symptoms, you should work from home. You can
return to campus if you get a negative test result or have been symptom-free
for 24 hours.

If you cannot come to campus, due to coronavirus symptoms or otherwise, please
inform us with an email to <minorai@mprog.nl>. If this is due to symptoms, we
will offer online alternatives to every on-campus activity, including lectures
and practical assistance, but can only offer some of these if we are aware you
are working from home. If you are actually sick and not just experiencing
symptoms, then we won't expect you to work from home of course, but you should
still inform us, so we can plan for a possible deadline extension, if needed.
So in either case, please do send us an email and let us know the reason for
your absence, so we can handle it accordingly.

## Asking questions

If you have any questions about the material, there are several ways to get
to ask them and get assistance.

### Practical assistance

Every weekday between 11 and 3, you can ask practical questions to the TA's of
the minor. During these hours you can use the "Request assistance" feature on
the *Introduction to Machine Learning 2* [website](https://ml2.mprog.nl/),
using the question mark symbol at the top of the sidebar there. Please use this
feature instead of raising your hand in class, as it ensures that all questions
get handled in the order that they are asked. Questions can of be about either
the DPL or ML2 courses, just make sure to mention what assignment you're
working on. For your location, please list the room and table you are working
at, so the TA handling your question knows where to find you when it is your
turn.

On some days there will also be a lecture, either from 11 to 1, or from 1 to 3.
During the scheduled lectures there will be *no* practical assistance, but
there will still be assistance the 2 hours before or after lecture, depending
on the time of the lecture. More information on the lectures can be found in
the next section.

If you are working from home, you can also still use the *Request assistance*
to ask for help with your code. The main difference is that you'll need to make
a Zoom link for the TA to join, which you should provide as your "location"
when asking your question. A TA will then join your meeting when it is your
turn in the queue, so you can share your screen and explain your question
there.

### Morning meetings

For those students working from home, we'll offer online morning meetings every
day at **09:00**. Here you can divide yourself into small groups of students,
all working online that day. There you have a cup of coffee and start the day
together. The meeting can be joined at
[Wonder.me](https://www.wonder.me/r?id=c6cdcb4d-7901-44dc-9b9f-fe90898c22a5).

These meetings will also be useful to discuss your progress and what you're
planning to do for the day. If, for example, you find you're stuck on the same
part of an assignment as other students, you can then decide to take a look at
your approach for a problem together. We encourage you to discuss approaches to
problems together, as this is an effective way to learn, but this can only
occur if you know each other and what you are working on. Facilitating this is
the primary purpose of these meetings.

*Note:* This means working together on analysis and approach of a problem, not
directly sharing code with each other! For a complete description of what it
means to do your own work and forms of collaboration are reasonable and
unreasonable, see the end of this document.

### Email the staff

If you have personal matters to discuss or other questions that do not fit any
of the formats above, you can email the course staff at <minorai@mprog.nl>

## Passing the course

Each module will each be graded on a 1 to 10 scale. Your grade will mainly
depend on the style and design of your code.

Design

: This is about adding effective abstractions to your code. Simple examples
might be to use a loop instead of copy-pasting code, or writing a function for
code you want to reuse several times.

Style

: This is about how readable your code is for other people. For example, using
clear variable names, adding comments and adding whitespace to separate blocks
of code can all help to make your code more readable.

Throughout the modules more design and style concepts will be explained. You
are expected to apply these concepts in your code from that point onward.

If you've completed the entire module and your code produces the correct
output, your grade starts at 6. The remainder of your grade is then
determined as follows:

* 0 - Style and design of the code are of insufficient quality. Code does produce correct output and open questions have been answered.

* 1 - Style and design have had some attention, but there are still clear improvements to be made. Answers to most open questions are correct.

* 2 - Style and design are of sufficient quality, answers to open questions are correct.

* 3 - Style and design are very good, answers are correct and show understanding.

* 4 - Exceptional style and design, answers are beyond expectations.

### Exam

The exam will be another *pass/fail* exam. More details on the exam will follow
later.

Once you've passed the exam, your final grade will be computed as the average
of all your grades for all the modules

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
