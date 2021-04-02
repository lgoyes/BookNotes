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
12. [I need to make many changes in one area](#12-i-need-to-make-many-changes-in-one-area-do-i-have-to-break-dependencies-for-all-the-classes-involved)
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

### Wrap Class

* We can add new behavior to a class, which calls the existing functionality.
* Decorator pattern: We create objects of a class that wraps another class and pass them around. The class that wraps should have the same interface as the class it is wrapping, so that clients don't know that they are working with a wrapper.
* When you are using the decorator patter, you need to have at least one of these "basic" classes that you wrap around.
* Decorator is a nice pattern, but it is good to it sparingly.
* When you use the decorator pattern, you can transparently add new behavior to a set of existing calls, all at one. On the other hand, if the new behavior only has to happen in a couple of places, creating a wrapper that isn't decorator-ish can be very useful.
* There are two cases to use _WrapClass_:
    1. The new behavior is completely independent, and I don't want to pullute the existing class with unrelated behavior.
    2. The class has grown so large that I can't stand to make it worse.
* The biggest obstacle to improvement in large code bases is the existing code. When you see ugly code, it's easy to believe that it will always be ugly and that any little thing that you do to make it better is simply not worth it.

## 7. It takes forever to make a change.

### Understanding

* In a well-maintained system, it might take a while to figure out how to make a change, but once you do, the change is usually easy and you feel much more comfortable with the system. In a legacy system, it can take a long time to figure out what to do, and the change is difficult also.

#### Lag Time

* _Lag Time_: time that passes between a change that you make and the moment that you oget real feedback about the change.
* You should be able to compile every class or module in your system separately from the others and in its own test harness. When you have that, you can get very rapid feedback and that just helps developement go faster.

### Breaking Dependencies

* People working in legacy code are stopped dead in their tracks by the first step: attempting to get a class into a test harness.
* Some classes are very huge; others have so many dependencies that they seem to overwhelm the functionality that you want to work on entirely. In cases like these, it pays to see if you can cut out a larger chunk of the code and put it under test.

#### Build Dependencies

* Nearly every problem that you run into will be the result of some dependency that you should break.
* The way to handle this is to extract interfaces for the classes in your cluster that are used by classes outside the cluster.
* Moving classes into new packages, grows the overall cost of a rebuild of the entire system, but the average time for a build can decrease dramatically.
> Depedency Inversion Principle: When your code depends on an interface, that dependency is usually very minor and unobtrusive. Your code doesn't have to change unless the interface changes, and interfaces typically change far less often than the code behind them.
* At times, it can take a little longer to find things when you have more packages and interfaces, but when you do, you can work with them very easiily.

## 8. How do I add a feature?

* In legacy code, one of the most important considerations is that we don't have tests around much of our code.
* Possible hazzards of using sprout or wrap:
    1. When we sprout or wrap, we don't significantly modify the existing code, so it isn't going to get any getter for a while.
    2. **Duplication:** The code that we add might duplicate code that exist in untested areas.
    3. **Fear:** We can't change a particular piece of code.
    4. **Resignation:** A whole area of the code just isn't getting any better.
* Once we have tests in place we have a solid foundation.

### Test Driven Development (TDD)

* If we can write a test for a mehotd that doesn't exist yet, we've solidified our understanding of what the code we are about to write should do.
* One of the most valuable things about TDD is that it lets us concentrate on one thing at a time. We are either writing code or refactoring.
* After we have written some new code, we can refactor to removoe any duplication between it and the old code.
* TDD algorithm for legacy code:
    0. Get the class you want to change under test.
    1. Write a failing test case.
    2. Get it to compile.
    3. Make it pass (try not to change existing code as you do this).
    4. Remove duplication.
    5. Repeat.

### Programming by Difference

* In OO, we have another option. We can use inheritance to introduce features without modifying a class directly. After we've added the feature, we can figure out exactly how we really want the feature integrated.
* We can create a new class `B` by inheriting class `A`. Then, make the test pass on `B` by overriding any behavior. If we can comment the overriden behavior on `B`, and the tests still pass, then we have finished the refactor.
* We can have multiple behaviors in a class by temporarily checking the value of a configuration property. Then, we could refactor this configuration checking (which is a passive behavior) by moving it to another class.
* Programming by difference allows us to make changes quickly, but we have to take care not to violate the Liskov Substitution Principle.
* According to the Liskov Substitution Principle (LSP), objects of subclasses should be substitutable for objects of their superclasses throughout or code. If they aren't, we could have silent errors in our code. Take as an example, the scenario where `Square` inherits from `Rectagle`, and you want to get the area from the square using the rectangle's interface.
* LSP implies that clients of a class should be able to use objects of a subclass without having to know that they are objects of a subclass.
* Rules of thumb:
    1. Whenever possible, avoid overriding concrete methods.
    2. If you do, see if you can call the method you are overriding in the the overriding method.
* When we override concrete methods, we could be changing the behavior of some of the code that uses the `super` class. People who are using the super class would think it's like the super class without knowing they are using a child class, instead.
* In general, code gets confusing when we override concrete methods too often.
* In a normalized hierarchy, we can make the super class abstract, and let the subclasses provide concrete bodies. None of the subclasses has a method that override a concrete method it inherit from a superclass.
* A few concrete overrides every once in a while don't hurt, as long as it doesn't cause a Liskov Substitution Principle violation. However, it's good to think about how far classes are from normalized form, every once in a while.

## 9. I can't get this class into a test harness

* Most common problems:
    1. Objects of the class can't be created easily.
    2. The test harness won't easily build with the class in it.
    3. The constructor we need to use has bad side effects.
    4. Significant work happens in the constructor, and we need to sense it.

### The case of the irritating parameter

* In a construction test, we just attempt to create an object in it. Later, when we are finally able to construct the object in the test harness, we can get rid of the test.
* Establishing a connection to the server in a test is not a good idea. It takes a long time, and the server isn't always up. The connection to the server is an irritating parameter. We have to create some sort of a fake server-connection object and make the test class believe it's talking to a real one.
* We can extract the interface from the server connection class, and then create a fake class using that same interface.
* The rules are edifferent for classes that we use to make testing possible. The code in `FakeConnection` isn't production code. It won't ever run in our full working application.
* Test code doesn't have to live up to the same standards as production code. In general, I don't mind breaking encapsulation by making variables public, if it make it easier to write tests. However, test code should be clean.
* When you are writing tests and an object requires a parameter that is hard to construct, consider just passing null instead. If the parameter is used in the course of your test execution, the code will throw an exception and the test harness will catch the exception.
* Don't pass null in production code unless you have no other choice. If you are tempted to use null in production code, consider using the `Null Object Pattern` instead.
* `Null Object` can shield clients from explicit error checking. They just do nothing. Be careful when you use them. For instance, imagine that you count objects, and one of them is the null object - The count will be wrong. `Null objects` are useful when a client doesn't have to care whether an operation is successful.
* `Pass null` and `Extract Interface` are two ways of approaching to irritating parameters. We can also subclass and override method to get rid of the dependency. You have to make sure, you aren't altering the behavior you want to test when you use it.

### The case of the hidden dependency.

* The constructor uses some resource that we just can't access nicely in our test harness.
* Some times, there are some dependencies created in the constructor. We can externalize a dependency that we have in a constructor by passing it into the constructor (`Parameterize Constructor`).
* We can go back to the original implementation by first creating another method to initialize the object by preserving signatures as we do it. Now, we can supply a constructor that has the original signature. Tests can call the constructor parameterized, and clients can call the constructor with the original signature.

### The case of the constructor blob

* SOmetimes, a constructor creates a few objects and then uses them to create other objects. If we cannot parameerize constructor, we can use another option: `Supersede instance variable`. We write a setter on the class that allows us to swap in another instance after we construct the object.
* In C++ we have to be very careful with this refactoring. When we replace an object, we have to get rid of the old one. Often, that means that we have to use the delete operator to call its destructor and destroy its memory.
* We should be very careful not to use the superseding method in production code. If the objects that are superseding manage other resources, we can cause some serious resource problems.
* Supersede instance variable is very dangerous. The potential for resouce-management problems is too great.

### The case of the Irritating Global Dependency

* Frameworks often manage the lifecycle of an application, and we write code to fill in the holes. The xUnit frameworks behave this way. We write test classes; xUnit calls them and displays their results.
* Global variable usage is one of the hardest kind of dependency to deal with. We can usee `Parameterize Constructor`, `Parameterize method` and `Extract and override call` to get past these dependencies.
* `getInstance` is a static method whose job is to return the only instance of a class that can exist in our application. The field that hold that instance is static also. You can recognize the `getInstance` method as an example of the _Singleton Design Pattern_.
* The singleton pattern is one of the mechanisms people use to make global variables.
* In general, global variables are a bad idea because of its lack of _opacity_:
    1. **Opacity:** when we look at a  piece of code, it is nice to be able to know what it can affect.
* When we use global variables, we look at the use of a class, and we do not have a clue whether it is accessing or modifying variables declared someplace else in the program. This can make it harder to understand programs.
* The tough part in a testing situation is that we have to figure which globals are being used by a class and set them up with the proper state for a test. And we have to do that before each test if the setup is different.
* To run code containing singletons in a test harness, we have to relax the singleton property:
    1. Add a new static method to the singleton class. The method allows us to replace the static instance in the singleton. We'll call it `setTestingInstance`.
    2. We can create a testing instance of the singleton class and set it in our test setup.
* Introduce static setter is not the only way of handling this situation. We can add a `resetForTesting()` method to the singleton. If we call this method in our test `setUp` and `tearDown`, we can create fresh singleton for every test. The singleton will reinitialize itself for every test.
* Reasons to have singletons:
    1. We are modeling the real world, and there is only one of these things in the real world.
    2. If two of these things are created, we could have a serios problem.
    3. If someone creates two of these things, we'll be using too many resouces.
* People can enforce a singleton instance for some of the provious reasons.
* Sometimes, they create singletons because they want to have a global variable. In that case, there really isn't any reason to keep the singleton property.
* To relax the singleton property, we can make the constructor public.
* At times, the singleton might be doing things that we would not want to have happen in a test harness, such as talk to a database in the background. In this case, we can "subclass and override mehotd" and make derived classes that make teseting easier.
* At other times, the dependencies are so extensive that it is easier to use "Extract Interface" on the singleton and change all of the references in the application so that they use the interface name.
* When we make a concerted effort to separate responsibilities in an application, dependencies become localized; we might not need a reference to a database in every object. Some classes store and retrieve data, while other do other things.
* In most cases, variables that are global are not globally used. They are used in a relatively small number of places. How can we get that object to the objects that need it, if it couldn't be a global variable?
* If there is a global variable that is being used everywhere, it means that there isn't any layering in your code.

### The case of the Horrible Include Dependencies

* There was much more leverage in making languages easier to work with.
* If we want to create a test for a class that has many imports, the easiest thing that we can do is try to build them in the same directory, in another file. In the presence of the preprocessor, it is often just easier.
* In simple cases, the header file includes everything we need to be able to create the implementation class, but in some cases, it doesn't.
* We can get some reuse for the fakes that we create. Instead of putting the definitions of classes inline in the test file, we can put them in a separate include file that can be used accross a set of test files.

### The case of the onion parameter

* Sometimes, we have objects to create objects, which in turn create a parameter for the constructor of the class we want to test.
* We need to write tests, but what do we really need from the parameters passed into the constructor? If we don't need anything from them in the test, we can pass null. If we just need some rudimentary behavior we can use "Extract Interface" or "Extract Implementer", and use the interface to create a fake object.
* We can create an interface for the object we want to test, that includes methods from the class from which it is inheriting.

### The case of the Aliased Parameter

* If only pieces of a class are problems, we can take another approach and just sever the connection to them. We can use "subclass and override method" to make a fake class that supplies methods that make it easy to change the validation flag. Then, in subclasses, we can override the validate method, and set the validation flag any way that we need to while we are testing the initial class.
* We can create classes "on the fly" in methods, when we are testing.

## 10. I can't run this method in a test harness

* Sometimes we can test a method without instantiating the class. If the method doesn't use much instance data, we can use "expose static method" to get access to the code. If the method is very long, we can use "Break Out method object" to move the code to a class that we can instantiate more easily.
    * When we are breaking dependencies without tests, "Preserve Signatures" of methods whenever possible. If you cut/copy and paste whole method signatures you have less of a chance of introducing errors.
    * When na method is static, you know that it doesn't access any of the private data of the class; it is just a utility method.
* Some problems that we can run into:
    * The method could be private or have some other accessibility problem.
    * It is hard to construct the parameters we need to call the method.
    * The method has bad side effects.
    * We might need to sense through some object that the method uses.

### The case of the hidden method

* If we need to test a private method, we should make it public. If making it public bothers us, in most cases, it means that our class is doing too much, and we ought to fix it.
* Reasons to have a private method:
    1. The method is just a utility; it isn't something clients would care about.
    2. If clients use the method, they could affect results from other methods of a class.
* Private methods can be moved to a new class. They can be public on that class, and our first class can create an internal instance of it. That makes the methods testable and the design better.
* One of the reasons of not being able to test a huge class is that is has too many responsibilities. It would be great to break it down into smaller classes. If we can't afford to separate the responsibilities we can make a private method, protected, and then we can subclass that class to get access to that method.

### The case of the "helpful" language feature

* The "final" keyword is used to mak a class that is particularly sensitive when it comes to security. If anyone could create a subclass of a final class, they could write some malicious code and pass it around in code that uses those classes.
* We can extract an interface and write a wrapper to some API class.
* When we depend directly on libraries that are out of our control, we are just asking for trouble.
* Adapt Parameter: we can create an adapter for a class, which can return some values of the adapted object.

### The case of the undetected side effect

* Sometimes we call some object's methods, they do some work, but we (the calling code) never get to know about it. The object calls methods on other objects and we never have a clue how things turned out.
* We have to separate work that is independent of the GUI from work that is really dependent on the GUI.
* A method should be a command or a query. A command is a method that can modify the state of the object but that doesn't return a value. A query is a method that returns a value but that doesn't modify the object.
    * If a method is a query we are certain about not causing any side effect.
* After those extractions, we can subclass and override method and test whatever code is left in the `performCommand` method.

## 11. I need to make a change. What methods should I test?

### Reasoning about effects

* If your code is well structured, most of the methods in your software have simple effect structures.
* When we are working with legacy code, we often have to ask a different question: if we make a particular change, how could it possibly affect the rest of the results of the program?

### Reasoning forward

* In characterization tests, we look at a set of objects and try to figure out what will change downstream if they stop working.
* The tests are just a description of how we expect to use the class. We could probably write them without even looking at the code, because we have a good idea of what the class is supposed to do.
* We need to figure out where we are going to make our changes. Once we've identified the points of change, we can start to sketch effects.
* We have to writee tests at the methods that can sense effects of what we modify.
* If your class has a superclass or subclasses, there might be other clients that you haven't considered. If everything is private, there is nothing to worry about.
* Not only we have to look for changes and effects on the class itself, but we have to check what other classes the class we want to modify, can affect.

### Effect Propagation

* Unless method's return values aren't being used, they propagate effects to code that calls them.
* Effects can also propagate in silent ways. If we have an object that accepts some objects as parameter, it can modify its state.
* Some languages have keywords that you can use to make it impossible to modify the state of an object that is passed to them (like the keyword `const` in C++).
* The sneakiest way that a piece of code can affect other code is through global or static data. Information hiding is great, unless it is information that we need to know.
* Effects propagate in code in three basic ways:
    1. Return values that are used by callers.
    2. Modification of objects passed as parameters.
    3. Modification of static or global data.
* Heuristic to look for effects:
    1. Identify a method that will change
    2. If the method has a return value, look at its callers.
    3. See if the method modifies any values. Look at the methods that use those values, and the methods that use those methods.
    4. Look for superclasses and subclasses that might be users of those instante variables.
    5. Look at parameters to the methods.
    6. Look for static data or global variables.

### Tools for Effect Reasoning

* In every language there are things that prevent event propagation.
* If variables are private, we don't neeed to look for the effect of a variable outside a class.
* The `const` keyword after a method declaration means that the method can't modify the instance ariables of the object. However, this can be circumvented by means of the `mutable` keyword. So, take care of language constructs that can be circumvented.

### Learning from Effect Analysis

* Programming gets easier as we narrow effects in a program. If we are given a list that won't change, our reasoning is made easier.

### Simplifying Effect Sketches

* When we remove tiny pieces of duplication, we often end up getting effect sketches with a smaller set of endpoints. This often translates into easier testing decisions.
* Encapsulation isn't an end in itself, it is a tool for understanding. Breaking encapsulation can make reasoning about our code harder, but it can make it easier if we end up with good explanatory tests afterward. Some dependency-breaking techniques can break encapsulation.

## 12. I need to make many changes in one area. Do I have to break dependencies for all the classes involved?

* Higher-level tests are important during refactoring. However, they are not a substitute for unit tests.

### Interception Points

* Interception point: A point in your program where you can detect the effects of a particular change.
* Identify where you need to make changes, and start tracing effects outward from those change points. Each place where you can detect effect is an interception point.

#### The simple case

* In general, it is good idea to pick interception points that are very close to your change points.
    * The more steps betwen a change point and an interception point you have, the harder it is know that the test is right.

#### Higher-level interception points

* We can write test on every class and method before making a change. However, it can be more efficient to start out by trying to find a higher-level interception point that we can use to characterize this area of code. We could have less dependency breaking to do.
    * You could define an interception point where you can detect effects from changes in a cluster of classes.
* **Pinch point:** A narrowing in an effect sketch, where it is possible to write tests to cover a wide set of changes. A pinch point is determined by change points. A set of changes to a class might have a good pinch point, even if the class has multiple clients.
* Sometimes a pinch point can be set on a couple of methods. The important thing is that setting that pinch point can detect changes in many more methods.
* If you can't find any pinch point for only one or two changes at a time, just try to write tests for individual changes as close as you can.
* A method might have three users, but that doesn't mean that it is being used in three distinct ways.
    * Would it be okay to write tests at only one of those classes and not the other?
    * If I break this method, will I be able to sense it in this place?
    * If the method is used the same way on objects that have comparable values, it could be okay to test in one place and not the other.

### Judging Design with Pinch Points



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