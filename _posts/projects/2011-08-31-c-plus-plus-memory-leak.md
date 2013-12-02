---
layout: project
title: "Memory leak in C++ (technical report)"
date: 2011-08-31 00:00:00+0800
categories: projects
---

Memory leak is one of the most annoying problems when programming in C++. Although memory leak is hard to detect and may have severe impact on long running program such as Web server, there has been many techniques and paradigms to prevent memory leaks. In this technical report, I investigated potential sources of memory leaks, how to detect them and how to prevent them.

The technical report was divided into 6 sections.
In Section 1, I wrote about the motivation and the goal for this technical report. In Section 2, I briefly summarized possible scenarios of dynamic memory allocation in C++. In Section 3, I presented common situations when memory leak can occur. In Section 4, I introduced some basic techniques to detect potential memory leak, such as `crtdbg.h` in Visual C++. In Section 5, I discussed classic memory leak prevention methods such as smart pointers. I concluded in Section 6.

Smart pointer is a good example of the RAII (Resource Acquisition Is Initialization) principle in C++. A smart pointer is an object capable of managing the lifecycle of some resources such as dynamically allocated memory, file handles, etc. It has interfaces similar to those of raw pointers. The implementation of smart pointers often uses **reference counting** technique, which tracks how many times the resource is being referenced currently. When the reference count drops down to zero, the resource is freed. I analyzed in detail the implementation of `smart_ptr` in the [Boost][] library and `SmartPtr` in the [Loki][] library. In the report, I also showed my experiment results concerning the performance of different smart pointers.

To write the technical report, I had read part of the source code of the Boost and Loki library. I also referred to the following books.

*   [Effective C++](http://book.douban.com/subject/1453373/)
*   [More Effective C++](http://book.douban.com/subject/1457891/‎)
*   [Modern C++ Design: Generic Programming and Design Patterns Applied](http://book.douban.com/subject/1755195/)
    *   [C++设计新思维：泛型编程与设计模式之应用](http://book.douban.com/subject/1119904/)（中译本）
*   [Boost程序库完全开发指南：深入 C++“准”标准库](http://book.douban.com/subject/5276434/)
*   [Beyond the C++ Standard Library: An Introduction to Boost](http://book.douban.com/subject/1461208/)
    *   [超越 C++标准库：Boost库导论](http://book.douban.com/subject/2105720/)（中译本）

This report helped me gain better understanding of the C++ language and some best practices in production code. I also became interested in metaprogramming (generic programing), an powerful aspect of C++.


This technical report was my course project for *C++ Program Design and Training* (Course Number: 34100192) at Tsinghua University in summer 2011.

[Boost]: http://www.boost.org/
[Loki]: http://loki-lib.sourceforge.net/
