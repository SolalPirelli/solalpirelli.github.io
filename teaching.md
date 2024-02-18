---
title: Teaching
layout: default
courses:
  - name: Software Engineering
    url: https://github.com/sweng-epfl/public
    description: |-
      In this course, students learn the basics of software engineering, enabling students to go from _writing code_ to _developing software_.  
      This includes the entire product lifecycle, from requirements to maintenance, including designing, testing, and debugging code.
      _(Co-taught with Prof. George Candea)_

  - name: Software Development Project
    url: https://github.com/sweng-epfl/public/tree/main/project
    description: |-
      In this companion course taught after Software Engineering,
      students build an Android app in a team following a Scrum-like process.  
      The course is divided into two-week Scrum sprints,
      during which students work on their assigned tasks, review each other's code, and have intermediate "standup" meetings to coordinate.
      _(Co-taught with Prof. George Candea)_
---

# Teaching

I have taught the following courses at EPFL.

{% for course in page.courses %}
## [{{ course.name }}]({{ course.url }})
{{ course.description }}
{% endfor %}
