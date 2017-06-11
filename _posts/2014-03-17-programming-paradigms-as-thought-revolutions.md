---
layout: post
title: Programming Paradigms as Thought Revolutions
modified:
categories: 
excerpt:
tags: []
image:
  feature:
date: 2014-03-17-05:00
---

> “A language that doesn’t affect the way you think about programming, is not worth knowing” [Alan Perlis](http://pu.inf.uni-tuebingen.de/users/klaeren/epigrams.html)

Last quarter I read Thomas Kuhn’s [*The Structure of Scientific Revolutions*](http://en.wikipedia.org/wiki/The_Structure_of_Scientific_Revolutions). I’m not sure how closely I believe it, but it got me thinking and of course I related it to to software.

Kuhn convincingly argues for the importance of paradigm for the progress of “normal science”. That is, most work is incremental progress within a similar framework of evaluation working towards a single, or several related, research questions. Kuhn argues that this tight focus is the feature of scientific work that allows it to progress so rapidly.

In programming, we also talk about paradigms such as object-oriented, functional, logical, array-based, etc. There is a similar connotation, where learning and embracing the paradigm and its conventions will improve the coherancy of the system you are building. While plenty of time has been spent arguing about the value of one paradigm versus the other, I think it is pretty universally considered a good thing to have one in mind when designing a programming language (although I didn’t take Programming Languages this quarter). And for the majority of us who are not language designers, understanding the paradigm of the language you are working in is critical for producing “idiomatic” code (an issue I hope to write more about at a later date).

All this leads me to wonder about “paradigm shifting” in programming. For Kuhn, this occurs when the evidence gathered from experimentation starts to contradict the dominant paradigm. Scientists begin to have less and less elegant formulations of their work to match their results to the paradigm they are working within. Eventually someone comes up with a competing theory that explains the data in an elegent way, and a scientific revolution happens. What follows is a sort of scientific gold rush, as new research can make huge strides towards this newly reframed research question. (I’m grossly over simplifying Kuhn’s book-length arguments, which themselves simplify the immensely complex topic of scientific progress).

Kuhn characterizes these revolutions as changes of world view (p 128). Scientists in the new paradigm perceive the same objective data differently than scientists working in the old paradigm would. Anecdotally, I think programming paradigms are also changes of world view: i.e. learning a new paradigm changes the way you view programming and the world. Looking at a problem that could potentially be solved with software, the ways you attempt to solve it are completely shaped by the paradigms you are familiar with.

As always, I have more questions than answers. What is the effect of different paradigms on: pedagogy, maintainability, stability, extensibility? What changes depending on which language you learn first? What changes when you rewrite the same system in a different paradigm? Do architectural styles or design patterns count as paradigms?
