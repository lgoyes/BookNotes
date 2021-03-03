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
