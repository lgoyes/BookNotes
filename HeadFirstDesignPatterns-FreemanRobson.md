# Head First Design Patterns. Building Extensible & Maintainable Object-Oriented Software. 2nd Edition

**Author**: Eric Feeman and Elisabeth Robson

**Language**: English

**Start date**: Feb 21st, 2021.

**End date**: May 26th, 2021.

## Index

1. [Welcome to Design Patterns: intro to Design Patterns](#1-welcome-to-design-patterns-intro-to-design-patterns)
2. [Keeping your Objects in the Know: the Observer Pattern](#2-keeping-your-objects-in-the-know-the-observer-pattern)
3. [Decorating Objects: the Decorator Pattern](#3-decorating-objects-the-decorator-pattern)

## 1. Welcome to Design Patterns: intro to Design Patterns

* Whenever you need to modify a behavior, you're often forced to track down and change it in all the different subclasses where that behaviour is defined, probably introducing new bugs along the way!
* If you've got some aspect of your code that is changin, say with every new requirement, then you know you've got a behaviour that needs to be pulled oout and separate from all the suff that doesn't change.
> Take the parts that vary and encapsulate them, so that later you can alter or extend the parts that vary without affecting those that dont'.
* Now, to separate the "parts that change from those that stay the same," we are going to create two sets of classes (totally apart from Duck), one for _fly_ and one for _quack_.
* And we know that we want to _assign_ behaviors to the instances of Duck.
* And while we're there, why not make sure that we can change the behaviour of a duck dynamically? We should include behaviour setter methods in the Duck classes so that we can _chance_ the Duck's flying behaviour at _runtime_.
> Program to an interface, not an implementation.
* A behaviour came either from a concrete implementation in the superclass Duck, or by providing a specialized implementation in the subclass itself. We were locked into using that speicif implementation and there was no room for changin the behavior.
* The point is to exploit polymorphism by programming to a supertype so that the actual runtime object isn't locked into the code. And we could rephrase "program to a supertype".
> Favor composition over inheritance
* Not only does it let you encapsulate a family of algorithms into their own set of classes, but it also lets you **change behaviour at runtime** as long as the object you're composing with implements the correct behaviour interface.

> The Strategy Pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable. Strategy lets the algorithm vary independently from clients that use it.

* Design patterns give you a shared vocabulary with other developers. Once you've got the vocabulary, you can more easily communicate with other developers and inspire those who don't know patterns to start learning them.

* When you communicate using patterns, you oare communicating not just a pattern name, but a whole set of qualities, characteristics, and constraints that the pattern represents.

* When you use a pattern in a description, other developers wuickly know precisely the design you have in mind.

* Talking about software systems using patterns allows you to keep the discussion at the design level.
* A team well versed in design patterns can move more quickly.
* Design patterns are higher level than libraries. Design patterns tell us how to structure classes and objects to solve ceratin problems, an it is our job to adapt those designs to fit our particular application.
* On of the true misunderstanding of object-oriented development: that by knowing the OO basics we are automatically going to be good at building flexible, reusable, and maintainable systems.

## 2. Keeping your Objects in the Know: the Observer Pattern

> The Observer Patterns degines a one-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.
* The subject is the object that contains the state and controls it. The observers, on the other hand, use the state, even if they don't own it. There are many observers, and they rely on the Subject to tell them when its state changes.
* The observers are dependent on the subject ot update them when the data changes. Many objects control the same data.
> An object is tighly couple to another object when it is **too** dependent on that object.
* All objects depend on other objects. But a loosly coupled object doesn't know or care too much about the details of another object.
* WHen two objects are _loosely coupled_ they can interact, but they typically have very little knowledge of each other. Let's walk through all the ways the patternn achieves loose coupling:
    1. The only thing the subject knows about an observer is that it implements a certain interface (the Observer interface).
    2. We can add new observers at any time.
    3. We never need to modify the subject to add new types of observers.
    4. We can reuse subjects or observers independently of each other.
    5. Changes to either the subject or an observer will not affect the other. As long as the objects still meet their obligations to implement the Subject or Observer interfaces
> Strive for loosely coupled designs between objects that interact.
* With a lambda expression, we create a function object instead, and the function object is the observer.
* Whether we pull or push the data to the Observer is an implementation detail, but in a lot of cases it makes more sense to let Observers retrieve the data they need rather than passing more and more data to them through the `update()` method.

## 3. Decorating Objects: the Decorator Pattern

* Once you know the techniques of decorating, you'll be able to give your (or someone else's) objects new responsibilities without making any changes to the underlying classes.
* By dynamically composing objects, I can add new functionality by writing new code rather than altering existing code. Because I'm not changing existing code, the changes of introducing bugs or causing unintended side effects in pre-existing code are much reduced.
> Classes should be open for extension, but closed for modification
* Feel free to extend our classes with any new behaviour you like. If your needs or requirements change, just go ahead and make your own extensions. On the other hand, we've spent a lot of time getting this code correct and bug free, so we can't let you alter the existing code. It must remain closed to modification.
* Following the Open-Closed Principle usually introdeces new levels of abstraction, which adds complexity to our code. You want to concentrate on those areas that are most likely to change in your designs and apply the principles there.
* Applying the Open-Closed Principle EVERYWHERE is wasteful and unnecessary, and can lead to complex, hard-to-understand code.
* Here's what we know about Decorators:
    * Decorators have the same supertype as the objects they decorate.
    * You can use one or more decorators to wrap an object.
    * Given that the decorator has the same supertype as the object it decorates, we can pass around a decorated object in place of the original (wrapped) object.
    * The decorator adds its own behavior before and/or after delegating to the object it decorates to do the rest of the job.
    * Objects can be decorated at any time, so we can decorate objects dynamicallyl at runtime with as many decorators as we like.

> **The Decorator Pattern** attaches additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.

* It's vital that the decorators have the same type as the objects they are going to decorate. So here we're using inheritance to achieve the _type matching_, but we aren't using inheritance to get _behavior_.
* When we compose a decorator with a component, we are adding new behavior. We are acquiring new behavior not by _inheriting_ it from a superclass, but by _composing_ objects together.
* If we rely on inheritance, then our behavior can only be determined statically at compile time. With composition, we can mix and match decorators any way we like... _at runtime_.
* If you have code that relies on the concrete component's type, decorators will break that code. As long as you only write code against the abstract component type, the use of decorators will remain transparent to your code. However, once you start writing code against concrete components, you'll want to rethink your application design and your use of decorators.
* We typically create decorators by using other patterns like Factory and Builder.
* Decorators are meant to add behavior to the object they wrap. When you need to peek at multiple layers into the decorator chain, you are staring to push the decorator beyond its true intent. Iimage a `CondimentPrettyPrint` decorator that parses the final description and can print "Mocha, Whip, Mocha" as "Whip, Double Mocha".
* Designs using this pattern often result in a large number of small classes that can be overwhelming to a developer trying to use the Decorator-based API.

## 4. Baking with OO Goodness: the Factory Pattern



## 5. One-of-a-Kind Objects: the Singleton Pattern
## 6. Encapsulating Invocation: the Command Pattern
## 7. Being Adaptive: the Adapter and Facade Patterns
## 8. Encapsulating Algorithms: the Template Method Pattern
## 9. Well-Managed Collections: the Iterator and Composite Patterns
## 10. The State of Things: the State Pattern
## 11. Controlling Object Access: the Proxy Pattern
## 12. Patterns of Patterns: compound patterns
## 13. Patterns in the Real World: better living with patterns
## 14. Appendix: Leftover Patterns
