---
layout: post
title:  "Learning: Building Evolutionary Architecture"
date:   2019-04-25 22:25:48 +1000
comments: true
categories: learning
---

## Disclaimer

This is not meant a fully comprehensive text and I neither review it. Although,
I will try to keep it as understandable as possible for later recall.

## About the book

It is the first edition released 2017-09-15

## I did not understand, visit later on:

Not yet

## Chapter 1: Software Architecture

* Architecture is something to be driven by business requirements

* Meet the balance among all **-ilities**: scalability, testability, resilience, …

## Evolutionary Architecture:
Change software overtime becomes hard despite our efforts. So, Evolutionary
Architecture has to allow software **evolvability** in face of constant changes
that a software needs to support.

* When we look overtime the only thing that we know is that the things gonna
change.

* The current status quo think about architecture as something hard to change.
Which becomes a self-fulfilling prophecy.

### Prevents it from Gradually Degrading Over Time:
  * Change it Incrementally: Make few changes per time (CD) and purge when it is not needed anymore
  * Change it guided (Fitness Function): i.e., measure each that mentioned incremental changes.
  * Multiple Architecture Dimensions (Analysis): Changes wont affect only Tech code related. It also affects Data Dimension (DB, Queues, …), Security and Operational.
    * Architectural Scope to keep in mind: Auditability, Performance, Business Requirements, Data, (This and more at page 2), …
    * Protect those using fitness functions (more in chapter 2).

### Conway's Law
  > Organizations which design systems.. are constrained to produce designs which are copies of the communications structures of these organizations.
  > > - Melvin Conway

  * Consequences in how split team: horizontal splits creates **delegation** and **coordination** problems which impacts the final design
  * As well as companies with rigid hierarchy.
  * it is hard to change something if it is owned by someone else.
  * **delegation** requires **coordination**
  * **delegation** requires **coordination**
  * **delegation** requires **coordination**

### Final Summary:

Evolutionary architecture primary aspects: incremental change, fitness functions and appropriate coupling.

## Chapter 2: Fitness Functions

...
