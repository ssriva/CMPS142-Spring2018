---
title: CMPS 142 - Machine Learning and Data Mining
layout: default
img: HAL.png
img_link: https://en.wikipedia.org/wiki/HAL_9000
#caption: I am putting myself to the fullest possible use, which is all I think that any conscious entity can ever hope to do. 
active_tab: main_page 
---

<!-- Display an alert about upcoming homework assignments -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% for page in site.pages %}
{% if page.release_date and page.due_date %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%s'}}{% endcapture %}
{% if release_date < now and due_date >= now %}
<div class="alert alert-info">
<a href="{{page.url}}">{{ page.title }}</a> has been released.  
{% if page.deliverables %}
The assignment has multiple deliverables.
{% for deliverable in page.deliverables %}
The {{deliverable.description}} is due before {{ deliverable.due_date | date: "%I:%M%p" }} on {{ deliverable.due_date | date: "%A, %B %-d, %Y" }}.  
{% endfor %}
{% else %}
It is due before {{ page.due_date | date: "%I:%M%p" }} on {{ page.due_date | date: "%A, %B %-d, %Y" }}.
{% endif %}
</div>
{% endif %}
{% endif %}
{% endfor %}
<!-- End alert for upcoming homework assignments -->



Course number
: CMPS 142 - Machine Learning and Data Mining 

Instructor
: [Snigdha Chaturvedi](https://sites.google.com/site/snigdhac/)

Discussion Forum
: [Piazza]()

Lectures
: Spring 2018, TuTh 1:30-3:05 in  	N. Sci Annex 101 

Sections
: 2 discussion sections W 12-01:05 PM and F 01:20-02:25 PM in PhysSciences 140 
: <font color="blue"> Enrollment in discussion sections is strongly recommened </font>


Office hours
: Instructor: Tuesdays 3:15-4:15 (tentative). 
: TA: TBA

Prerequisites
:	* CMPS  101  (advanced  data  structures  and  algorithms)
	* Math  23a  (post-calculus linear algebra), and 
	* either AMS 131 or CE 107 (probability)

<div class="alert alert-info"> While exceptions can be made on a case-to-case basis, they are at the student's own risk. Exceptions will not be made before end of March, 2018. Also, there won't be wailist until start of second pass of enrollment. </div>
 

Other notes (likely to change in the first few weeks):
: * Evaluation will be based on regular homework assignments, including a multi-week project towards the end of the course, and the final exam.  Exam and homework will be weighted about equally, although I reserve the right to not pass students with very poor performance on the final regardless of their other scores.
* Students  are  responsible  for  their  own  understanding.   If  anything  is  unclear,  ask questions in lecture, sections, office hours, or the class forum.
* Students should check the forum regularly (daily or at least every other day) for announcements and clarifications.
* Both  lectures  and  the  reading  are  important.   It  is  important  to  keep  up  with  the reading, and reading ahead is often helpful.  Lectures are mandatory, and students are responsible for the material covered there.
* Due dates are firm, and it is each student’s responsibility to manage their time and complete the assignments on time.  Students should read and think about the assignments the day they are assigned so they can ask questions and get the help they need well before the due date.
* All help from outside the group (from the web, books other than those recommended above, or people other than the TA or instructor) must be clearly acknowledged. Presenting other’s work as your own is dishonest and is called plagiarism
* Academic Honesty violations, such as submitting the un-attributed work of others, are
serious issues and will result in a zero on the assignment, a lowered grade in the course,
and a report to the department, and Dean of Graduate Studies.  Improperly borrowed
work can be as large as an entire solution or as small as a single sentence, figure, or
idea.  [See also](http://www.ucsc.edu/academics/academic_integrity/undergraduate_students)
* If  you  qualify  for  classroom  accommodations  because  of  a  disability,  please  get  an accommodation Authorization from the Disability Resource Center (DRC) and submit it to me in person during my office hours or by appointment within the first two weeks of the quarter.  Contact DRC by phone at 831-459-2089, or by email at drc@ucsc.edu for more information.
* If you need accommodation due to conflicts, family emergencies, illness/injury, or other difficulties, inform the instructor as soon as possible.  An “incomplete” is only given by request when there is a medical, family, or similar emergency that prevents a student who has been doing clearly passing work from finishing the course.


