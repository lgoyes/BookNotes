# Working Effectively with Legacy Code

**Author**: Michael Feathers

**Language**: English

**Start date**: Mar 8th, 2021.

**End date**: Apr 26th, 2021.

## Index

1. [Changing Software](#1-changing-software)
2. [Working with Feedback](#2-working-with-feedback)
3. [Sensing and Separation](#3-sensing-and-separation)
4. [The Seam Model](#4-the-seam-model)
5. [Tools](#5-tools)
6. [I don't have much time and I have to change it](#6-i-dont-have-much-time-and-i-have-to-change-it)
7. [It takes forever to make a change](#7-it-takes-forever-to-make-a-change)
8. [How do I add a feature?](#8-how-do-i-add-a-feature)
9. [I can't get this class into a test harness](#9-i-cant-get-this-class-into-a-test-harness)
10. [I can't run this method in a test harness](#10-i-cant-run-this-method-in-a-test-harness)
11. [I need to make a change. What methods should I test?](#11-i-need-to-make-a-change-what-methods-should-I-test)
12. [I need to make many changes in one area](#12-i-need-to-make-many-changes-in-one-area)
13. [I need to make a change, but I don't know what tests to write](#13-i-need-to-make-a-change-but-i-dont-know-what-tests-to-write)
14. [Dependencies on libraries are killing me](#14-dependencies-on-libraries-are-killing-me)
15. [My application is all api calls](#15-my-application-is-all-api-calls)
16. [I don't understand the code well enough to change it](#16-i-dont-understand-the-code-well-enough-to-change-it)
17. [My application has no structure](#17-my-application-has-no-structure)
18. [My test code is in the way](#18-my-test-code-is-in-the-way)
19. [My project is not object oriented. How do I make safe changes?](#19-my-project-is-not-object-oriented-how-do-i-make-safe-changes)
20. [This class is too big and I don't want it to get any bigger](#20-this-class-is-too-big-and-i-dont-want-it-to-get-any-bigger)
21. [I'm changing the same code all over the place](#im-changing-the-same-code-all-over-the-place)
22. [I need to change a monster method and I can't write tests for it](#22-i-need-to-change-a-monster-method-and-i-cant-write-tests-for-it)
23. [How do I know that I'm not breaking anything?](#23-how-do-i-know-that-im-not-breaking-anything)
24. [We feel overwhelmed. It isn't going to get any better](#24-we-feel-overwhelmed-it-isnt-going-to-get-any-better)
25. [Dependency-breaking techniques](#25-dependency-breaking-techniques)

## 1. Changing Software

### Four reasons to change software

* Reasons to change software
    1. Adding a feature
    2. Fixing a bug
    3. Improving a design
    4. Optimizing resouce usage

#### Adding Features and Fixing Bugs

* Behaviour is the most important thing about software. Iit is what users depend on. Users like it when we add behavior, but if we change or remove behavior they depened on, they stop trusting us.
* If we have to modify code, we could be changing behavior. If we are adding code and colling, we are adding behavior.
* It seems nearly impossible to add behavior without chaging it to some degree.

#### Improving Design

* When we want to alter software's structure to make it more maintainable, generally we want to keep its behaviour intact also. When we drop hebaior in that process, we often call that a bug.
* We can write tests to make sure that existing behavior doesn't change and take small steps to verify that all along the process.

#### Optimization

* Optimization is like refactoring. We want to keep functionality exactly the same when we make changes, but we change some resources used by the program, usually time or memory.

#### Putting it all together

* In general, three things can change when we do work in a system: structure, functionality and resouce usage.
* We have to know that the behavior isn't changing. The amount of behavior that we have to preserve is usually very large, and we don't know how much of that behavior is at risk when we make our changes. If we knew, we could concentrate on that behavior and not care about the rest.
* In good systems, you feel pretty calm after you've dont that learning, and you are confident in the change you are about to make. In poorly structured code, the move from figuring things out to make changes feels like jumping off a cliff to avoid a tiger.
* Many teams live with fear of change.

## 2. Working with Feedback

* Ways to make changes in a system: **edit and pray** and **cover and modify**.
    1. **Edit and pray:** You carefully plan the change you are going to make, you make sure that you understand the code you are going to modify, then you make the changes. When you are done, you run the system to see if the change was enabled, and then you poke around further to make sure that youo odidn't break anything.
    2. **Cover and modify:** When we have a good set of tests around a piece of code, we can make changes and find out very quickly whether the effects were good or bad.
* Testing done after development is really "testing to attempt to show correctness".
* Testing to detect change is called regression testing. Periodically running tests that check for known good behavior to find out whether our software still works the way it did in the past.
* The problem with regression testing is that people do it at the application interface. The feedback is very useful and we could use it at a finer-grained level.
* System-level regression tests are great, but small, localized tests are invaluable.

### What is unit testing?

* In unit testing, we are concerned with the most atomic behavioural units of a sytem. In procedural code, the units are functions, in object-oriented code, the units are classes.
* Testing in isolation is an important part of a unit test. We have to test one only class, and one only function.

## 3. Sensing and Separation
## 4. The Seam Model
## 5. Tools
## 6. I don't have much time and I have to change it
## 7. It takes forever to make a change
## 8. How do I add a feature?
## 9. I can't get this class into a test harness
## 10. I can't run this method in a test harness
## 11. I need to make a change. What methods should I test?
## 12. I need to make many changes in one area
## 13. I need to make a change, but I don't know what tests to write
## 14. Dependencies on libraries are killing me
## 15. My application is all api calls
## 16. I don't understand the code well enough to change it
## 17. My application has no structure
## 18. My test code is in the way
## 19. My project is not object oriented. How do I make safe changes?
## 20. This class is too big and I don't want it to get any bigger
## 21. I'm changing the same code all over the place
## 22. I need to change a monster method and I can't write tests for it
## 23. How do I know that I'm not breaking anything?
## 24. We feel overwhelmed. It isn't going to get any better
## 25. Dependency-breaking techniques