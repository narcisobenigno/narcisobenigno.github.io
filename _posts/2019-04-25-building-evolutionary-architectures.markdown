---
layout: post
title:  "Learning: Building Evolutionary Architecture"
date:   2019-04-25 22:25:48 +1000
comments: true
categories: learning
---

## Disclaimer

This is not meant to be a fully comprehensive text and I wont review it either.
Even then, I will try to keep it as understandable as possible for later recall.

## About the book

It is the first edition released 2017-09-15

## Annoying things through out the book

The authors keeps saying "the architect can evaluate...", "the architect
defines"... Why not just say "the product team..."?

## I did not understand, visit later on:

Not yet

## Chapter 1: Software Architecture

* Architecture is something to be driven by business requirements

* Meet the balance among all **-ilities**: scalability, testability, resilience, …

## Evolutionary Architecture:
Change software overtime becomes hard despite our best efforts. So, Evolutionary
Architecture has to allow software **evolvability** in face of constant changes
that a software needs to support.

* When we look overtime the only thing that we know is that the things gonna
change.

* The current status quo thinks about architecture as something hard to change.
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

  > an evolutionary architecture supports *guided*, incremental change across
  > multiple dimensions.
  > > -authors definition

  * Fitness function has to do with that *guided* part. So, it guides the
    changes checking if those changed in anyway the important aspects defined
    based upon on business drivers.

  * Systemwide fitness function: The collection of individual fitness functions
    each of them corresponding one of more dimensions of the architecture.
    * Eventually some of those fitness functions make clear that can be
      conflicting with each other, which means that we have to deal with a
      *tradeoff*. For instance, A security fitness function stepping on the
      performance fitness function. Systemwide fitness functions **allow the
      team compare and evaluate the architectural characteristics**.

  * Fitness function **has to pick inflection points**.

### Categories

  * **Atomic Vs Holistic**: Does fitness function checks, respectively, one
    architectural aspect or multiple at same time?
    * Atomic can work, but for some aspects it is not enough, so, you have to
      test combination of multiple aspects.
  * **Triggered Vs Continual**: Does it runs based upon in a event (e.g., like
    commit to repository) or runs in continuous base (e.g., measure a
    **business** transaction time).
  * **Static Vs Dynamic**: Does the fitness function, respectively, has fixed
    results (e.g., unit tests) or does that has a result depending upon the
    context (e.g., performance sling the acceptable value in high load).
  * **Automated vs Manual**: Does it runs in a computer or does it depends of a
    human to run? By default, automate that shit, if you cant, due to
    regulatory or technical reasons, do it manually. Even then, track this
    fitness function in some way. Moreover, try hard to automate that.
  * **Temporal**: remind me if something needs to be checked later on in some
    point like a expected update. It can also be automated, let's say we want
    to check if a **monkey patch** will break in the text release, so, you
    introduce a *break upon upgrade* test to check if a cannot-wait-update
    breaks in the next release when it is supposed to be officially fixed (i.e.
    you are replacing your monkey patch by the official fix).
  * **Intentional over Emergent**: The product team has to try to define as
    most as they can define those fitness function during inception, but we
    know that some of them just emerge during development process.
    Be intentional, also helps teams design what kind of changes we would like
    to design the software to support (saving money, frustration, and
    evolvability).
  * **Domain-Specific**: architectures can have special concerns, such as
    special security or regulatory concerns. Create Fitness Functions for those

### Fitness functions can be...

  * **Key** for make design or technology choices. Put effort to define as soon
    as possible those (e.g., resilience metrics, performance, security, etc).
  * **Relevant** for feature level, but unlikely to impact in
    architectural choices (e.g., code quality metrics).
  * **Not Relevant** for design and technology choices, those can be
    product-wise important, but not for the software architecture. So, does not
    require Fitness function (e.g, cycle time).

### Review fitness functions
  * **Check in a fixed period of time if ...**:
    * They still relevant
    * they needs to be reviewed in scale or magnitude.
    * there are better approaches to measure what the current ones
    * The systems needs new fitness function.

## Chapter 3: Engeneering Incremental Change

  > an evolutionary architecture supports guided, *incremental* change across
  > multiple dimensions.
  > > -authors definition

  * Fitness function has to do with that *incremental* part. So, it put design
    practices in place to make the software evolvable, i.e., evolutionary
    architecture should allow changes to software in small increments.
