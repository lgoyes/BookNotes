# Head First Design Patterns. Building Extensible & Maintainable Object-Oriented Software. 2nd Edition

**Author**: Eric Feeman and Elisabeth Robson

**Language**: English

**Start date**: Feb 21st, 2021.

**End date**: May 26th, 2021.

## Index

1. [Welcome to Design Patterns: intro to Design Patterns](#1-welcome-to-design-patterns-intro-to-design-patterns)

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

## 2. Keeping your Objects in the Know: the Observer Pattern
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
