---
title: "Scalable Teaching of Software Engineering Theory and Practice: An Experience Report"
excerpt: My takeaways from teaching software engineering to CS undergrads
date: 2024-04-19
venue: ICSE '24 SEET
authors: S. Pirelli
artifact: https://github.com/sweng-epfl/public
video: https://youtu.be/EzWTVLK_lNY
doi: https://doi.org/10.1145/3639474.3640053
---

Starting in the final years of my undergrad, and during my entire PhD, I went from being a teaching assistant in the pair of theory + practice courses
to being the head TA, giving a couple of lectures, and finally re-designing the entire course.

The result is a course that scales to a couple hundred students quite easily, with only the equivalent of one full-time staff spread over many people.
I believe the theory course could scale much further without much more effort, though the project course needs a little more work.

The course materials are available [here]({{ page.artifact }}), including documentation about the more "meta" aspects, and scripts to manage exams.


## Problem

How do we teach the basics of software engineering to computer science undergrads, given tight time constraints, and in a way that scales to 200 students with little staff?


## Results

Overall, _strongly_ enforcing _lightweight_ mechanisms is the key.
Students inherit bad habits from other contexts, such as expecting to learn about an entire topic all at once by reading the documentation cover-to-cover.
We cannot use heavy mechanisms that would require lots of time, such as grading students by having them write long essays.
Instead, we must instill good software engineering practices both by making the course itself a good example, such as by teaching in short segments followed by interactive exercises,
and by picking specific lightweight mechanisms that students are forced to comply with so they can experience their benefits.


## Limitations

The courses were given to ~200 students for the theory and ~120 students for the project.
How do we scale to, say, 1000 students?

My intuition is that the current state of the theory course could scale reasonably well, as there are no obvious bottlenecks,
but the project course needs more work to scale further, especially in terms of organizing the staff.


## Lessons Learned

That's what the paper is mainly about, thus I encourage you to read it!
