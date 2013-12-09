---
layout: project
title: "CodeChoir"
date: 2013-06-07 00:00:00+0800
categories: projects
---

CodeChoir is an online collaborative programming platform. The name **CodeChoir** comes from our goal: helping programmers code together in harmony, like a choir.

Here are some key features of CodeChoir:

*   A powerful browser-based development environment (based on ACE Editor)
    *   Syntax highlighting
    *   Project file explorer
    *   Online build system
    *   Interactive shell (in sandboxes based on Linux Container)
    *   Voice messages
*   Collaborative editing
*   Project management
*   User account management

![CodeChoir]({{ site.baseurl }}/images/projects/codechoir.png)

Our front end was based on HTML5 and jQuery, and we used the Bootstrap framework to ease the design of our site. The back end was written in Python, based on Tornado Web Server. We used MongoDB as the storage engine. The communication between the browser and the server was enabled by AJAX and WebSocket, and messages were exchanged in JSON.

Our collaborative editing algorithm would merge editing history of different users in real time and resolve potential conflicts. It was based on the Operational Transformation (OT) algorithm described in the following resources:

*   Nichols, D. A., Curtis, P., Dixon, M., & Lamping, J. (1995, December). High-latency, low-bandwidth windowing in the Jupiter collaboration system. In Proceedings of the 8th annual ACM symposium on User interface and software technology (pp. 111-120). ACM.
*   <http://en.wikipedia.org/wiki/Operational_transformation>

Our team followed agile software development methodologies. We divided the development process into several iterations. We combined the following practices from Extreme Programming (XP) and the Scrum framework.

*   Stand-up meetings
*   Pair programming
*   Code review

CodeChoir was a course project for *Software Engineering* (Course Number: 44100203) at Tsinghua University in spring 2013. The team members are: Heran Lin, Wei Liao, Yue Cao, Yongbo Xiao and Yuqi Wang.