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
* Problems with large tests:
    1. **Error localization** - As tests get further, you have to look at the test inputs, look at the failure, and determine where along the path from inputs to outputs the failure occurred.
    2. **Execution time** - Large tests tend to take longer to execute.
    3. **Coverage** - We can have a piece of code exercised by a test, but when we add new code, we might have to do considerable work to create high-level tests that exercise the new code.
* Here are qualities of good unit tests:
    1. They run fast.
    2. They help us localize problems.
* When you have a test that exercises  class along with several of its collaborators, it tends to grow. How easy will it be when you add more code? It never gets easy. People put it off.
* A unit test that takes 1/10th of a second to run is a slow unit test.
* When tests take that long (1/10th of a second), I make sure that I use a subset to work with, but I don't mind running them all every couple of hours.
* A test is not a unit test if:
    1. It talks to a database
    2. It communicates accross a network
    3. It touches the file system
    4. You have to do special things to your environment (such as editing configuration files) to run it.

### Higher level testing

* Higher level tests cover scenarios and interactions in an application.

### Test coverings

* When we cover our code with tests before we change it, we're more likely to catch any mistakes that we make.
* When classes depened directly on things that are hard to use in a test, they are hard to modify and hard to work with.
* Much legacy code work involves breaking dependencies so that change can be easier.
* When we change code, we should have tests in place. To put tests in place, we often have to change code.
* Is this safe to do these refactorings without tests? It can be. When we break dependencies, we can often write tests that make more invasive changes safer. The trick is to do those initial refactorings very conservatively.
* When you break dependencies in legacy code, you often have to suspend your sense of aesthetics a bit. Some dependencies break cleanly; others end up looking less than ideal from a design point of view. They are like the incision points in surgery: There might be a scar left in your code after your work, but anything beneath it can get better.

### The legacy code change algorithm

* When you hoave to make a change in a legacy code base
    1. Identify change points
    2. Find test points
    3. Break dependencies
    4. Write tests
    5. Make changes and refactor

## 3. Sensing and Separation

* We break dependencies to **separate**.
    * Dependencies among classes can make it very difficult to get particular clusters of objects under tests.
* We break dependencies to **sense**.
    * Sometimes the class we want to test has effects on other classes, and out tests need to know about them. We have to impersonate the other class so that we can sense the effects directly.

### Faking Collaborators

#### Fake Objects

* A fake objects is an object that impesonates some collaborator of your class when it is being tested.
* When we write tests, we have to devide and conquer. If we discover a bug, running this test might help us see that the problem isn't in `Sale`. If we can use information like that to help us localize errors, we can save an incredible amount of time.

#### The two sides of a Fake Object

* The `Sale` class will see the `Fake` display as a simple `Display` (abstraction) but in the test, we need to hold on to the object as `FakeDisplay` (implementation). If we don't, we won't be able to call `getLastLine()` to find out what the `Sale` displays.

#### Fakes Distrilled

* In OO languages, fakes are implemented as fake objects. In non-OO languages, we can implement a fake by defining an alternative function - one which records values in some global data structure that we can access in tests.

#### Mock objectss

* Mock objects are fakes that perform assertions internally.
* We can tell mocks what calls to expect, and then we tell them to check and see if they received those calls. After the expectation has been set, we just go ahead and use the object inside the test.

## 4. The Seam Model

* Programming languages don't seem to support testing very well. The only way to end up with an easily testable program is to write tests as you develop it.

### A huge sheet of text

* We are told it is better to write programs that are made of small reusable pieces, but how often are small pieces reused independently? Not very often.

### Seams

* A seam is a place where you can alter behavior in your program without editing in that place.
* We can create a test version of a class that inherits from the original one, but nuls out some of the behavior from the parent class.
* If we can replace behavior at seams, we can selectively exclude dependencies in our tests. We can also run other code where those dependencies were if we want to sense conditions in the code and write tests against those conditions.

### Seam Types

#### Preprocessing Seams

* It's not a good idea to use excessive preprocessing in production code because it tends to decrease code clarity
* The conditional compilation directives (`#ifdef`, `#ifndef`, `#if`, and so on) pretty much force you to maintain several different programs in the same source code.
* Macros can hide terribly obscure bugs.
* Every seam has an enabling poiont: A place where you can make the decision to use one behaviour or another.
* When you ohave a seam, you have a place where behavior can change. We can't go to that place and change the code just to test it. The source code should be the same in both production and test.

#### Link seams

* The compiler produces an intermediate representation of the code, and that representation contains calls to code in other files. Linkers combine these representations. They resolve each of the calls so that you can have a complete program at runtime.
* When a source file contain an import statement, the compiler checks to see if the imported class really has been compiled. If the class hasn't been compiled, it compiles it, if necessary, and then checks to see if all of its calls will really resolve correctly at runtime.
* The only way to verify what the draw code is doing, is looking at the computer screen when figures are redrawn. In complicated code, that is error prone. An alternative is to use link seams. You can create sutb versions that link to the rest of the application. They can be empty functions, or they can return something if you need it.

#### Object seams

* If we can change which method is called in a line of code without changing the code around it, that call is a seam.
* Not all mehotd calls are seams. If the choice depend on the implementation, rather than on the abstraction, there is no enabling point. The class is decided when the object is created, and we can't change it without modifying the method.
* By injecting dependencies, the enabling point is the argument list of a method.
* not all the object seams are straighforward. Sometimes a method invokes another method of the same class. In that case, we can subclass and override the invoked method during tests.

## 5. Tools

### Automated Refactoring Tools

* Refactoring: A change made to the internal structure of software to make it easier to understand and cheaper to modify without changing its existing behavior.
* A change is a refactoring only if it doesn't change behavior.

### Mock Objects

* If we remove the other code, we need to have something in its place that supplies the right values when we are testing, so that we can exercise our piece of code thoroughly. These are often called mocked objects.

### Unit Testing Harnesses

* xUnit testing framework:
    * It lets programmers write tests in the language that they are developing in.
    * All tests run in isolation.
    * Tests can be grouped into suites so that they can be run and rerun on demand.

#### JUnit

* You write tesets by subclassing a class named TestCase.
* Each method in a test class defines a test if it has a signature of this form: `void testXXX()`, where `XXX` is the name you want to give the test. Each test method can contain code and assertions.
* JUnit test runner loads a test class, and then it uses reflection to find all the methods. Then, it created a complete separate object of each on of those test methods. There is no way that they can affect each other.
* The method `setup` is defined in `TestCase` and is run in each test object before the method is run. The setup method allows us to create a set of objects that we'll use in a test.
* If you need to do anything special after a test finishes executing, you can override another method named `tearDown`, defined in `TestCase`. It runs after the test method for each object.

### General Test Harness

* xUnit frameworks were designed to be used for unit testing. To test several classes at a time, it is more appropriate to use FIT and Fitnesse.

#### Framework for Integrated Tests (FIT)

* You can write documents about your system and embed tables within them that describe inputs and outputs for your system.
* The only thing you have to do to make this work is to customize some table-handling code so that it knows how to run chunks of your code and retrieve results from them.
* FIT is capable to foster communication between people who write software and people who need to specify what it should do.

#### Fitnesse

* Fitnesse is essentially FIT hosted in a wiki.

## 6. I don't have much time and I have to change it

* The work that you do to break dependencies and write tests for your changes is going to take sometime, but in most cases, you are going to end up saving time - and a lot of frustration.

### Sprout Method

* When you need to add a feature to a system and it can be formulated completely as new code, write the code in a new method. Call it from the places where the new functionality need to be. you might not be able to get those call points under test easily, but at the very least you can write tests for the new code.
* When we need to add some functionality, we might be tempted to modify the current behavior. This is not correct, since there will be no separation between the new code we've added and the old code. We can create a new method to encapsulate the new functionality, using TDD. When we have the method, we can go back to the original code and add the call. If we need to add more code, we can make a method for that code also and call it from here.
* Steps to apply sprout method:
    1. Identify where you need to make your code change.
    2. Write down a call for a new method that will do the work, and them comment it out.
    3. Determne what local variables are needed from the source method, and make them arguments to the call.
    4. Determine whether the sprouted method will need to return values to source method. If so, assign the returned value to a variable.
    5. Develop the sprout method using TDD.
    6. Remove the comment in the source method to enable the call.

#### Advantages and Disadvantages

* When you use it, you are saying that you are giving up on the source method. You aren't going to get it under test - you are just going to add some new functionality in a method.
* You have a clean interface between the new code and the old code.

### Sprout Class

* Maybe you have a large set of creational dependencies, things that make it hard to instantiate your class. In that case, you can create another class to hold your changes and use it from the source class.
* The way that you look at a sprouted class when you first create it and the way that you look at it after a few months are often significantly different. When youo need to make a change close to the new odd class, you start to think about whether the change is part of a new concept of whether the concept need to change a little.
* Two cases lead us to sprout classes:
    1. You have to add an entire new responsibility to one of your classes.
    2. We have a small bit of functionality that we could place into an existing class, but we can't get the class into test harness.

### Wrap method

* Chances are, you are adding behavior to a method because it has to execute at the same time as the code you are adding it to. This was named "temporal coupling".
* Steps:
    1. Identify the method you need to change
    2. Rename the method and then create a new method with the same name and signature as the old method.
    3. Place a call to the old method in the new method.
    4. Develop a method for the new feature using TDD, and call it from the new feature.
* If we don't care to use the same name as the old method:
    1. Identify the method you need to change
    2. Develop a new method using TDD
    3. Create another method that calls the new method and the old method.

#### Advantages and Disadvantages

* Wrap method makes the new functionality independent of existing functionality
* The primary disadvantage of wrap method is that it can lead to poor names.



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