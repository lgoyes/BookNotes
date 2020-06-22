# Clean Architecture. A Craftsman's Guide to Software Structure and Design

**Author**: Robert C. Martin
With contributions by James Grenning and Simon Brown

**Language**: English

**Start date**: May 21st, 2020.

**End date (estimated)**: Jun 30th, 2020.

## Index:

1. [What is Design and Architecture?](#1-what-is-design-and-architecture)
2. [A Tale of Two Values.](#2-a-tale-of-two-values)
3. [Paradigm Overview.](#3-paradigm-overview)
4. [Structured Programming](#4-structured-programming)
5. [Object-Oriented Programming](#5-object-oriented-programming)
6. [Functional Programming](#6-functional-programming)
7. [SRP: The Single Responsility Principle.](#7-srp-the-single-responsility-principle)
8. [OCP: The Open-Closed Principle](#8-ocp-the-open-closed-principle)
9. [LSP: The Liskov Substitution Principle](#9-lsp-the-liskov-substitution-principle)
10. [ISP: The Interface Segregation Principle](#10-isp-the-interface-segregation-principle)
11. [DIP: The Dependency Inversion Principle](#11-dip-the-dependency-inversion-principle)
12. [Components](#12-components)
13. [Component Cohesion](#13-component-cohesion)
14. [Component Coupling](#14-component-coupling)
15. [What is Architecture?](#15-what-is-architecture)
16. [Independence](#16-independence)
17. [Boundaries: Drawing Lines](#17-boundaries-drawing-lines)
18. [Boundary Anatomy](#18-boundary-anatomy)
19. [Policy and Level](#19-policy-and-level)
20. [Business Rules](#20-business-rules)
21. [Screaming Architecture](#21-screaming-architecture)
22. [The Clean Architecture](#22-the-clean-architecture)
23. [Presenters and Humble Objects](#23-presenters-and-humble-objects)
24. [Partial Boundaries](#24-partial-boundaries)
25. [Layers and Boundaries](#25-layers-and-boundaries)
26. [The Main Components](#26-the-main-components)
27. [Services: Great and Small](#27-services-great-and-small)
28. [The Test Boundary](#28-the-test-boundary)
29. [Clean Embedded Architecture](#29-clean-embedded-architecture)
30. [The Database is a Detail](#30-the-database-is-a-detail)
31. [The Web is a Detail](#31-the-web-is-a-detail)
32. [Frameworks are Details](#32-frameworks-are-details)
33. [Case Study: Video Sales](#33-case-study-video-sales)
34. [The Missing Chapter](#34-the-missing-chapter)


---

## 1. What is Design and Architecture?

* All the little details support all the high-levels decisions. Therefore, both the former- and the later- details are part of the whole design.
* The goal of software architecture is to minimize the human resources required to build and maintain the required system.
* If the effort required to meet the needs of the customer is low, and stays low throughout the lifetime of the system, the design is good.
* Getting to market first simply means that you've now got a horde of competitors on your tail, and you have to stay ahead of them by running as fast as you can.
* The bigger lie that developers buy into is the notion that writing messy code makes them go fast in the short term.
* The best option is for the development organization to recognize and avoid its own overconfidence and to start taking the quality of its software architecture seriosly.

> Making messes is always slower than staying clean.
> The only way to go fast, is to go well.

## 2. A Tale of Two Values.

* Every software provides two different values to the stakeholders: _behavior_ and _structure_.
* Developers help stakeholders develop a functional specification, or requirements document.
* It is this difference between scope and shape that often drives the growth in software development costs.
* From the developers' point of view, the stakeholders are giving them a stream of jigsaw puzzle pieces that they must fit into a puzzle of ever-increasing complexity.
* Software developers often feel as if they are forced to jam square pegs into round holes.
* Architectures should be as shape agnostic as practical.
* The cost of change exceeds the benefit of change.
* Current functionality is more important than any later flexibility.
* If a the cost of a change is unaffordably high, the business managers will likely be furios that you allowed the system to get to the point where the change was impractical.

> Give me a program that works perfectly but is impossible to change, then it won't work when the requirements change, and I won't be able to make it work. **Therefore the program will become useless**

* Behavior is urgent but not always particularly important. Architecture is important but never particularly urgent.
* Business manager fail to separate those feature that are urgen but not important from those feature that truly are urgent and important.
* Business managers are not equipped to evaluate the importance of architecture.
* It is the responsibility of the software development team to assert the importance of architecture over the urgency of features.

> If architecture comes last, then the system will become ever more costly to develop, and eventually change will become practically impossible for part or all the system.

## 3. Paradigm Overview.

### Structured Programming

* Jumps were replaced with the more familiar `if/then/else` and `do/while/until` constructs.

> Structured programming imposes discipline on direct transfer of control.

### Object-Oriented Programming

> Object-oriented programming imposes discipline on indirect transfer of control.

### Functional Programming

* A foundational notion of `lamba`-calculus is immutability (i.e. the notion that the values of symbols do not change).

> Functional programming imposes discipline upon assignment.

### Food for Thought

* None of them adds new capabilities. Each imposes some kind of extra discipline that is negative in its intent.
* The three paradigms together remove `goto` statements, function pointers, and assignments.

## 4. Structured Programming.

### Proof

* A program of any complexity contains too many details for a human brain to manage without help.
* Dijkstra's solution was to apply the mathematical discipline of proof.
* Dijkstra realized that he would have to demonstrate the technique for writing basic proofs of simple alhorithms.
* Dijkstra discovered that certain uses of `goto` statements prevent modules from being decomposed recursively into smaller and smaller units, thereby preventing use of the _divide-and-conquer_ approach necessary for reasonable proofs.
* Dijstra realized that there "good" uses of `goto` corresponded to simple selection and interaction control structures.
* Böhm and Jacopini, proved that all programs can be constructed from just three structures: sequence, selection and interaction.
* The very control structures that made a module provable were the same minimum set of control structure from which all programs can be built. **Thus, structured programming was born**.
* Most modern languages do not have a `goto` statement.
* Our languages don't give us the option to use undisciplined direct transfer of control.

### Functional Decomposition

* Structured programming allows modules to be recursively decomposed into provable units.

### No Formal Proofs

* Few of today's programmers believe that formal proofs are an appropriate way to produce high-quality software.

### Science to the Rescue

* Science does not work by proving statemets tru, but rather by _proving statements false_.

### Tests

* Testing shows the presence, not the absence, of bugs.
* All the tests can do, after sufficient testing effort, is allow us to deem a program to be correct enough for our purposes.
* Such proofs of incorrectness can be applied only to _provable_ programs.
* Structured programming forces us to recursively decompose a program into a set of small provable functions.

> If such tests fail to prove incorrectness, then we deem the functions to be correct enough for our purposes.

## 5. Object-Oriented Programming.

* When Dahl and Nygaard moved the function call stack frame to the heap and invented OO.
* OO makes software easier to understand because it has a closer relationship to the real world.
* Nature of OO: _encapsulation_, _inheritance_ and _polimorphism_.

### Encapsulation?

* Provide easy and effective encapsulation of data and functions.
* We see this concept in action as the private data members and the public member functions of a class.
* The C++ compiler, for technical reasons (it needs to know the size of the instances of each class), needed the member variables of a class to be declared in the header file of that class.
* Many OO languages have little or no enforced encapsulation.
* OO certainly does depend on the idea that programmers are well-behaved enough to not circumbent encapsulated data.

### Inheritance?

* Inheritance is simply the redeclaration of a group of variables and functions within an enclosing scope.

### Polymorphism?

* The bottom line is that polymorphism is an application of pointers to functions. Programmers have been using pointers to functions to achieve polymorphic behavior since Von Neumann architectures were first implemented in the late 1940s.
* OO languages may not have given us polymorphism, but they have made it mush safer and much more convenient.

#### The Power of Polymorphism

* The IO devices have become plugins to the `copy` program.
* Our programs should be _device_ independent.
* We discovered that we really wanted tose programs to do the same job, but use a different device.
* OO allows the plugin architecture to be used anywhere, for anything.

#### Dependency Inversion

* Any source code dependency, no matter where it is, can be inverted.
* Any of those source code dependencies can be turned around by inserting an interface between them.
* Software architects working in systems written in OO languages have _absolute control_ over the direction of all source code dependencies in the system.

> Independent Deployability: If the source code in a component changes, only that component needs to be redeployed.
> OO is the ability, through the use of polymorphism, to gain absolute control over every source code dependency in the system.

## 6. Functional Programming.

* The Java program uses a _mutable_ variable - a variable that changes state during the execution of the program. That variable is `i`-the loop control variable. No such mutable variable exists in the Clojure program. **In the Clojure program, variables like `x` are initialized, but they are never modified**.
* Variables in functional languages do not vary.

### Immutability and Architecture.

* All race conditions, deadlock conditions, and concurrent update problems are due to mutable variables. You cannot have a race condition or a concurrent update problem if no variable is ever updated.
* Is immutability practicable? Yes, immutability can be practicable, if certain compromises are made.

### Segregation of Mutability

* The immutable components perform their tasks in a purely functional way, without using any mutable variables.
* Since mutating state exposes those components to all the problems of concurrency, it is common practice to use some kind of _transactional memory_ to protect the mutable variables from concurrect update and race conditions.
* The point is that well-structured applications will be segregated into those components that do not mutate variables and those that do.
* Push as much processing as possible into the immutable components.

### Event Sourcing

* The more memory we have, and the faster our machines are, the less we need mutable state.
* To make this scheme work forever, we would need infinite storage and infinite processing power.
* Event sourcing is a strategy wherein we store the transactions, but not the state.
* More importantly, nothing ever gets deleted or updated from such a data store. As a consequence, our applications are not CRUD; they are just CR. Also, because neither updates nor deletions occur in the data store, there cannot be any concurrent update issues.
* If we have enough storage and enough processor power, we can make our applications entirely immutable -and, therefore, _entirely functional_.

## 7. SRP: The Single Responsility Principle.

* A _function_ should do one, and only one, thing. We use that principle when we are refactoring large funcitons into smaller functions; we use it at the lowest levels. But it is not one of the SOLID principles -it is not the SRP.
* Historycally, the SRP has been described as follows:
> A module should have one, and only one, reason to change.

* However, the SRP principle actually is:
> A module should be responsible to one, and only one, actor.

* To understand this principle, we can look at the symptoms of violating it.

### Symptom 1: Accidental Duplication.

* A developer is tasked to make the change, and sees the convenient `regularHours()` function called by the `calculatePay()` method. Unfortunately, that developer does not notice that the functioni is also called by the `reportHours()` function.

> SRP: Separate the code that differt actors depend on.

### Symptom 2: Merges.

* Two different developers, possible from two different teams, check out the `Employee` class and begin to make changes. Unfortunately their changes collide. The result is a merge.
* In our example, the merge puts both the CTO and the COO at risk. It's not inconceivable that the CFO could be affected as well.
* There are many other symptoms that we could investigate, but they all involve multiple people changing the same source file for different reasons.

### Solutions

* There are different solutions. Each moves the functions into different classes.
1. Separate the data from the functions. Each class holds only the source code necessary for its particular function. The classes are not allowed to know about each other. Thus, any accidental duplication is avoided.
2. A common solution to the several classes dilemma is to use the _Facade_ pattern.
3. One can prefer to keep the most important business rules closer to the data. This can be done by keeping the most important method in the original `Employee` class, and then using that class as a Facade for the lesser functions.

## 8. OCP: The Open-Closed Principle.

> A software artifact should be open for extension but closed for modification.

* A good software architecture would reduce the amount of changed code to the barest minimum. Ideally, zero.
* Separaing the things that change for different reasons, and then organizing the dependencies between those things properly.
* All the dependencies are _source code_ dependencies. An arrow pointing from class A to class B means that the source code of class A mentions the name of class B, but class B mentions nothing about A.
* Each boundary is crossed in _one direction only_. This means that all component relationships are unidirectional.
* These arrows point toward the components that we want to protect from change.
* If component A should be protected from changes in component B, then component B should depend on component A.
* Why should the Interactor hold such a privileged prosition? Because it contains the business rules.
* The interactor deals with the central concerns.
* Notice how this creates a hierarchy of protection based on the notion of "level".
* Architects separate functionality based on how, why, and when it changes, and then organize that separated functionality into a hierarchy of components.

### Information Hiding

* The (...) interface serves a different purpose. It is there to protect the `Controller` from knowing too much about the internals of the _Interactor_. If that interface were not there, then the `Controller` would have transitive dependencies on the `Entities`.
* Transitive dependencies are a violation of the general principle that software entities should not depend on things they don't directly use.

### Conclusion

* Arranging those components into a dependency hierarchy that protects higher-level components from changes in lower-level components.

## 9. LSP: The Liskov Substitution Principle.

> What is wanted here is something like the following substitution property: If for each object `o1` of type `S` there is an object `o2` of type `T` such that for all programs `P` defined in terms of `T`, the behavior of `P` is unchanged when `o1` is substituted for `o2`, then `S` is a subtype of `T`.

### Guiding the Use of Inheritance

* Application does not depend, in any way, on which of the two subtypes it uses. Both of the subtypes are subtitutable for the `License` Type.

### The Square/Rectangle Problem

* Since the behavior of the `User` depend on the types it uses, those types are not substitutable.

### LSP and Architecture

* over the years, the LSP has morphed into a broader principle of software design that pertains to interfaces and implementations.
* The LSP is applicable because there are users who depend on well-defined interfaces (Java-stype interface, Ruby classes, or REST interface), and on the substitutability of the implementations of those interfaces.

### Exampmle LSP Violation

* Our architect would have to insulate the system from bugs like this by creating some kind of dispatch command creation module that was driven by a configuration database keyed by the dispatch URI.
* Our architect has had to add a significant and complex mechanism to deal with the fact that the interfaces of the restful services are not all substitutable.

### Conclusion

* The LSP can, and should, be extended to the level of architecture. A simple violation of substitutability, can cause a system's architecture to be polluted with a significant amount of extra mechanisms.

## 10. ISP: The Interface Segregation Principle

* Let's assume that `User` uses only `op1`, `User2` uses only `op2`, and `User3` uses only `op3`.
* The source code of `User1` will inadvertently depend on `op2` and `op3`, even though it doesn't call them.
* By segregating the operations into interfaces, then the source code of `User1` will depend on `U1Ops`, and `op1`, but will not depend on `OPS`. Thus a change to `OPS` that `User1` does not care about will not cause `User1` to be recompiled and redeployed.

### ISP and Language

* In dynamically typed languages like Ruby and Python, such declarations don't exist in source code. Instead, they are inferred at runtime. Thus there are no source code dependencies to force recompilation and redeployment.
* Dynamically typed languages create systems that are more flexible and less tighly coupled that statically typed languages.

### ISP and Architecture

* It is harmful to depend on modules that contain more than you need.
* Even worse, a failure of one of the features within D may cause failures in F and S.

### Conclusion

> Depending on something that carries baggage that you don't need can cause you troubles that you didn't expect.

## 11. DIP: The Dependency Inversion Principle

* The most flexible systems are those in which source code dependencies refer only to abstractions, not to concretions.
* `use`, `import`, and `include` statements should refer only to source modules containing interfaces, abstract classes, or some other kind of abstract declaration.
> Nothing concrete should be depended on.
* For dynamically typed languages, a concrete module is any module in which the functions being called are implemented.
* `String` class is very stable. Changes to that class are very rare and tighly controlled. Programmers and architects do not have to worry about frequent and capricious changes to `String`.
* We tolerate those concrete dependencies because we know we can rely on them not to change.
* It is the _volatile_ concrete elements of our system that we want to avoid depending on. Those are the modules that we are actively developing, and that are undergoing frequent change.

### Stage Sbstractions

* Interfaces are less volatile than implementations.
* Stable software architectures are those that avoid depending on volatile concretions, and that favor the use of stable abstract interfaces.
* **Don't refer to volatile contrete classes.** Refer to abstract interfaces instead.
* **Don't derive from volatile concrete classes.**
* **Don't override concrete functions.** Concrete functions often require source code dependencies. When you override those functions, you do not eliminate those dependencies -indeed, you _inherit_ them.
> To manage those dependencies, you should make the function abstract and create multiple implementations.
* **Never mention the name of anything concrete and volatile.**

### Factories

* The creation of volatile concrete objects requires special handling.
* In most object-orientes languages, such as Java, we would use an Abstract Factory to manage this undesirable dependency.
* All source code dependencies cross that curved line pointing in the same direction, toward the abstract side.
> The abstract component contains all the high-level business rules of the application. The concrete component contains all the implementation details that those business rules manipulate.
* The source code dependencies are inverted against the flow of control -which is why we refer to this principle as Dependency Inversion.

### Concrete Components

* DIP violations cannot be entirely removed, but they can be gathered into a small number of concrete components and kept separate from the rest of the system.
* Most systems will contain at least one such concrete component.

### Conclusion

* The way the dependencies cross that curved line in one direction, and toward more abstract entities, will become a new rule that we will call the _Dependency Rule_.

## 12. Components

* Components are the units of deployment.
* In Java, they are jar files.
* In all languages, they are the granule of deployment.
* Regardless of how they are eventually deployed, well-designed components always retain the ability to be independently deployable and, therefore, independetly developable.

### A Brief History of Components

* In those days, programs were not relocatable.
* Programmers included the source code of the library functions with their application code, and compiled them all as a single program. Librearies were kept in source, not in binary.
* To shorten the cpile times, programmers separated the source code of the function library from the applications.

#### Relocatability

* The compiler was changed to output binary code that could be relocated in memory by a smart loader.
* Usually this just meant adding the starting address to any memory reference addresses in the brinary. Now the programmer could tell the loader where to load the function library and where to load the application.
> If a program called a library function, the compiler would emit that name as an _external reference_. If a program defined a library function, the compiler would emit that name as an _external definition_. Then the loader could _link_ the external references to the external definitions once it had determined where it had loaded those definitions.
> And the linking loader was born.

#### Linkers

* The linking loaders had to read dozens, if not hundreds, of binary libraries to resolve the external references.
* THe output of the linker was a linked relocatable that a relocating loader could load very quickly. This allowed programmers to prepare an executable using the slow linker.
* Compiling each individual module was relatively fast, but compiling all the modules took a bit of time.
* Loading time remained fast, but compile-link times were the bottleneck.
> Programs will grow to fill all available compile and link time.
* For small jobs, the idea of a linking loader became feasible again.
* COmpiters and devices had gotten so fast that we could, once again, do the linking at load time. We could link together soveral `.jar` files, or several shared libraries in a matter of seconds, and execute the resulting program. And so, the component plugin architecture was born.

### Conclusion

* These dynamically linked files, which can be plugged together at runtime, are the software components of our architectures.

## 13. Component Cohesion.

* Which classes belong in which components?
  * REP: The Reuse/Release Equivalence Principle
  * CCP: The Common Closure Principle
  * CRP: The Common Reuse Principle

### The Reuse/Release Equivalence Principle

* We are now living in the age of software reuse -a fulfillment of one of the oldest promises of the object-oriented model.
* People who want to reuse software components cannot, and will not, do so unless those components are tracked through a release process and are given release numbers.
* Without release numbers, there would be no way to ensure that all the reused components are compatible with each other.
* Which changes those new releases will bring.
* The release process must produce the appropriate notifications and release documentation so that users can make informed decisions about when and whether to integrate the new release.
* Classes and modules that are formed into a component must belong to a cohesive group.
* There must be some overarching theme or purpose that those modules all share.
> Classes and modules that are grouped together into a component should be releasable together.

### Common Closure Principle

* CCP Says that a component should not have multiple reasons to change.
> If the code in an application must change, you would rather that all the changes occur in one component, rather than being distributed across many components.
* The CCP prompt us to gather together in one place all the classes that are likely to change for the same reasons.
* We design our classes such that they are closed to the most common kinds of changes that we expect or have experienced.

### The Common Reuse Principle

* It states that classes and modules that tend to be reused together belong in the same component.
* Classes are seldom reused in isolation. More typically, reusable classes collaborate with other classes that are part of the reusable abstraction. The CRP states that these classes belong together in the same component. In such a component we would expect to see classes that have lots of dependencies on each other.
* Perhaps the using component uses only one class within the used component -but that still doesn-t weaken the dependency.
* Every time the used component is changed, the using component will likely need corresponding changes.
* When we depend on a component, we want to make sure we depend on every class in that component.
* CRP tells us more about which classes shouldn't be together. The CRP says that classes that are not tighly bound to each other should not be in the same component.

#### Relation to ISP

> Don't depend on things you don't need

### The Tension Diagram for Component Cogesion

* An architect who focuses on just the REP and CRP will find that too many components are impacted when simple changes are made. In contrast, an architect who focuses too strongly on the CCP and REP will cause too many unneeded releases to be generated.
* A good architect finds a position in that tension triangle that meets the current concerns of the development team, but is also aware that those concerns will change over time.
* Early in the development of a project, the CCP is much more important than the REP, because develop/ability is more important than reuse.

### Conclusion

* The composition of the components will likely jitter and evolve with time as the focus of the project changes from develop-ability to reusability.

## 14. Component Coupling

### The Acyclic Dependencies Principle

* The "morning after syndrome" occurs in development environments where many developers are modifying the same source files.
* It is not uncommon for weeks to go by without the team being able to build a stable version of the project.
* Everyone keeps on changing and changing their code trying to make it work with the last changes that someone else made.

#### The Weekly Build

* All the developers ignore each other for the first four days of the weeek. They all work on private copies of the code, and don't worry about integrating their work on a collective basis. THen, on Friday, they integrate all their changes and build the system.
* The integration time continues to grow with project size.

#### Eliminating Dependency Cycles

* The solution to this problem is to partition the development environment into releasable component.
* The components become units of work that can be the responsibility of a single developer, or a team of develops. When developers get a component working, they release it for use by the other developers.
* As new release of a component are made available, other teams can decide whether they will immediately adopt the new release. If they decide not to, they simply continue using the old release. Once they decide that they are ready, they begin to use the new release.
* Each team can decide for itself when to adapt its own components to new releases of the components.
* If there are cycles in the dependecy structure, then the "morning after syndrome" cannot be avoided.
* Notice that this structure is a directed graph. The components are the nodes, and the dependency relationships are the directed edges.
* This structure has no cycles. It is a directed acyclic graph (DAG).
* WHen the developers working on the `Presenters` component would like to run a test of that componen, they just need to build their version of `Presenters` with the versions of `Interactors` and `Entities` components that they are currently using.

#### THe Effect of a Cycle in the Component Dependency Graph

* They will be stepping all over one ahother because they must all use exactly the same release of one another's component.
* You may have wondered why you have to include so many different libraries, and so much of everybody else's stuff, just to run a simple unit test of one of your classes.
* Unit testing and releasing become very difficul and error prone.

#### Breaking the Cycle

It is always possible to break a cycle of components and reinstate the dependency graph as a DAG.

1. Apply the Dependency Inversion Principle (DIP). We could create an interface that has the methods that `User` needs. We could then put that interface into `Entities` and inherit it into `Authorizer`.
2. Create a new component that both `Entities` and `Authorizer` depend on.

#### The Jitters

* As the application grows, the component dependency structure jitters and grows.
* When cycles occur, they must be broken somehow. Sometimes this will mean creating new components, making the dependency structure grow.

### Top-Down Design

* Inescapable conclusion: The component structure cannot be designed from the top down.
* It is not one of the first things about the system that is designed, but rather evolves as the system grows and changes.
* We have come to expect that large-grained decompositions, like components, will also be high-level _functional_ decompositions.
* We believe that the components ought to somehow represent the functions of the system. Yet this does not seem to be an attribute of component dependency diagrams.
* Component dependency diagrams have very little to do with describing the function of the application. Instead, they are a map to the _buildability_ and _maintainability_ of the application.
* We want to keep changes as localized as possible, so we start paying attention to the SRP and CCP and collocate classes that are likely to change together.
* We don't want components that change frequently and for capricious reasons to affect components that otherwise ought to be stable.
* The component dependency graph is created and molded by architects to protect stable high-value components from volatile components.
* If we tried to design the component dependency structure before we designed any classes, we would likely fail rather badly. We would not know much about common closure, we would be unaware of any reusable elements, and we would almost certainly create components that produced dependency cycles.

### The Stable Dependencies Principle

> Depend in the direction of stability

* By conforming to the COmmon Closure Principle (CCP), we create components that are sensitive to certain kinds of changes but immune to others.
* A module that you have dsigned to be easy to changed can be made difficult to change by someone else who simply hangs a depdency on it.
* By conforming to the Stable Dependencies Principle (SDP), we ensure that modules that are intended to be easy to change are not depended on by modules that are harder to change.

#### Stability

* Stability is related to the amount of work required to make a change.
* The standing penny is not stable because it requires very little work to topple it.
* A able is very stable because it takes considerable amount of effort to turn it over.
* A component with lots of incoming dependencies is very stable because it requires a great deal of work to reconcile any changes with all the dependent components.
* Three component depend on `X`, so it has three good reasons not to change. We say that `X` is _responsible_ to those three components.
* `X` depends on nothing, so it has no external influence to make it change. We say it is _independent_.
* No ther components depend on `Y`, so we say that it is irresponsible. `Y` also has three components that it depends on, so changes may come from three external sources. We say that `Y` is dependent.

#### Stability Matrics

* _Fan-in:_ Incoming dependencies. Number of classes outside this component that depend on classes within the component.
* _Fan-out:_ Outgoing dependencies. Number of classes inside this component that depend on classes outside the component.
* _I: Instability: I= Fan-out / (Fan-in + Fan-out)._ _I=0_ indicates a maximally stable component. _I=1_ indicates a maximally unstable component.
* THe _I_ metric is easiest to calculate when you have organized your source code such that there is one class in each source file.
* Its lack of dependents gives the component no reason not to change, and the components that it depends on may give it ample reason to change.
* It is as stable as it can get. Its dependencies make it hard to change the component, and its has no dependencies that might force it to change.

> The SDP says that the _I_ metric of a component should be larger that the _I_ metrics of the componets that it depends on.

#### Not All Components Should be Stable

* If all the componets in a system were maximally stable, the system would be unchangeable.
* This violates the SDP because the _I_ metric for `Stable` is much smaller that the _I_ metric for `Flexible`. As a result, `Flexible` will no longer be easy to change. A change to `Flexible` will force us to deal with `Stable` and all its dependents.
* We can fix this by employing the DIP. We create an interface class called `US` and put it in a component named `UServer`. We make sure that this interface declares all the methods that `U` needs to use. We then make `C` implement this interface.

#### Abstract Components

* These abstract components are very stable and, therefore, are ideal targets for less stable components to depend on.

### The Stable Abstractions Principle

> A component should be as abstract as it is stable.

#### Where do We Put The High-Level Policy?

* Some software in the system should not change very often. This software represents high-livel architecture and policy decisions.
* The software that encapsulates the high-level policies of the system should be placed into stable components (_I=0_).
* Unstable components (_I=1_) should contain only the software that is volatile.
* If the high-level policies are placed into stable components, then the source code that represents those policies will be difficult to change. This could make the overall architecture inflexible.

#### Introducing the Stable Abstractions Principle

The Stable Abstractions Principle (SAP) sets up a relationship between stability and abstractness.
* A stable component should also be abstract so that its stability does not prevent it from being extended.
* An unstable component should be concrete since its instability allows the concrete code within it to be easily changed.
* If a component is to be stable, it should consist of interfaces and abstract classes so that it can be extended.
* The SDP says that dependencies should run in the direction of stability, and the SAP says that stability implies abstraction.
> Dependencies run in the direction of abstraction.

#### Measuring Abstraction

* The _A_ metric is a measure of the abstracness of a component. Its value is simply the ratio of interfaces and abstract classes in a component to the total number of classes in the component.
  * _Nc:_ The number of classes in the component.
  * _Na:_ The number of abstract classes and interfaces in the component.
  * _A:_ Abstractness. _A = Na / Nc_.

A value of 0 implies that the component has no abstract classes at all. A value of 1 implies that the component contains nothing but abstract classes.

#### The Main Sequence

* We create a graph with A on the vertical axis and I on the horizontal axis.
* We will find the components that are maximally stable and abstract at the upper left at (0,1).
* The components that are maximally unstable and cocrete are at the lower right at (1,0).
* Not all components fall into one of these two positions, because components often have degrees of abstraction and stability.
* For example: It is very common for one abstract class to derive from another abstract class.
* Since we cannot enforce a rule that all components sit at either (0,1) or (1,0), we must assume that there is a locus of points on the _A/I_ graph that defines reasonable positions for components.

#### The Zone of Pain

* Consider a component in the area of (0, 0). This is a highly stable and concrete component.
* It cannot be extended because it is not abstract, and it is very difficult to change because of its stability.
* Some software entities do, in fact, fall within the Zone of Pain. An example would be a database schema. Database schemas are notoriously volatile, extremely concrete, and highly depended on.
* Another example of software that sits near the area of (0, 0) is a concrete utility library. Although such a library has an _I_ metric of 1, it may actually be nonvolatile. Consider the `String` component, for example. Even though all the classes within it are concrete, it is so commonly used that changing it would create chaos. Therefore `String` is nonvolatile.
* Nonvolatile components are harmless in the (0, 0) zone since they are not likely to be changed.
* It is only volatile software components that are problematic in the Zone of Pain.

#### The Zone of Uselessness

* Consider a component near (1, 1). This location is undesirable because it is maximally abstract, yet has no dependents. Such components are useless.
* They are often leftover abstract classes that no one ever implemented.

#### Avoiding the Zones of Exclusion

* It seems clear that our most volatile components should be kept as far from both zones of exclusion as possible.
* Good architects strive to position the majority of their components at those endpoints.
* Some small fraction of the components in a large system are neither perfectly abstract nor perfectly stable. Those components have the best characteristics if they are on, or close, to the Main Sequence.

#### Distance from the Main Sequence

* _D:_ Distance. _D = |A+I-1|_. THe range of this metric is [0, 1]. A value of 0 indicates that the component is directly on the Main Sequence. A value of 1 indicates that the component is as far as possible from the Main Sequence.
* Any component that has a _D_ value that is not near zero can be reexamined and restructured.
* They are either very abstact with few dependents or very concrete with many dependents.
* THe plot shows a control threshold at _D = 0.1_. The R2.1 point has exceeded this control limit, so it would be worth our while to find out why this component is so far from the main sequence.

## 15. What is Architecture?

* Software architects are the best programmers, and they continue to take programming tasks, while they also guide the rest of the team toward a design that maximizes productivity.
* The architecture of a software system is the shape given to that system by those who build it.
* The form of that shape is in the division of that system into components, the arrangement of those components, and the ways in which those components communicate with each other.
* THe purpose of that shape is to facilitate the development, deployment, operation and maintenance of the software system contained within it.
> The strategy behind that facilitation is to leave as many options open as possible, for as long as possible.
* This is not to say that architecture plays no role in supporting the proper behavior of the system.
* But the role is passive and cosmetic, not active or essential.
* Good architecture makes the system easy to understand, easy to develop, easy to maintain, and easy to deploy.

### Development

* A software system that is hard to develop is not likely to have a long and healthy lifetime.
* A small team of five devlopers can quite effectively work together to develop a monolithic system without well-defined components or interfaces.
* A system being developed by five different teams, each of which includes seven developers, cannot make progress unless the system is divided into well-defined components with reliably stable interfaces.

### Deployment

* To be effective, a software system must be deployable.
* The higher the cost of deployment, the less useful the system is.
* A goal of a software architecture, then, should be to make a system that can be easily deployed with a single action.
* Deployment strategy is seldom considered during initial development.
* For example, in the early development of a system, the developers may decide to use a "micro-service architecture".
* This approach is easy to develop since the component boundaries are very firm and the interfaces relatively stable.
* Configuring the connections between them, and the timing of their initiation, may also turn out to be a huge source of errors.

### Operation

* Software systems that have inefficient architectures can often be made to work effectively simply by adding more storage and more servers.
* The fact that hardware is cheap and people are expensive means that architectures that impede operation are not as costly as architectures that impede development, deployment, and maintenance.
* The architecture of a system makes the operation of the system readily apparent to the developers.
* Architecture should reveal operation.

### Maintenance

* THe never-ending parade of new features and the inevitable trail of defects and corrections consume vast amounts of human resources.
* THe primary cost of maintenance is in _spelunking_ and risk. Spelunking is the cost of digging through the existing software, trying to determine the best place and the best strategy to add a new feature or to repair a defect.
* While making such changes, the likelihood of creating inadvertent defects is always there, adding to the cost of risk.

### Keeping Options Open

* Software has two types of value: the value of its behavior and the value of its structure.
* The way you keep software soft is to leave as many options open as possible, for as long as possible.
* All software systems can be decomposed into two major elements: policy and details.
* The policy element embodies all the business rules and procedures.
* The details are those things that are necessary to enable humans, other systems, and programmers to communicate with the policy, but that do not impact the behavior of the policy at all.
* The goal of the architect is to create a shape for the system that recognizes policy as the most essential element of the system while making the details _irrelevant_ to that policy.
* If you can develop the high-level policy without commiting to the details that surround it, you can delay and defer decisions about those details for a long time.
* THe longer you wait to make those decisions, _the more information you have with which to make them properly_.
* This also leaves you the option to try different experiments.
* The longer you leave options open, the more experiments you can run, the more things you can try, and the more information you will have when you reach the point at which those decisions can no longer be deferred.
* A good architect pretends that the decision as not been made, and shapes the system such that those decisions can still be deferred or changed for as long as possible.
> A good architect maximizes the number of decisions not made.

### Device Independence

* The operating systems of the day abstracted the IO devices into software functions that handled unit records that looked like cards.
* The programs would invoke operating system services that dealt with abstract unit-record devices.
* Operators could tell the operating systems whether those abstract services should be connected to card readers, magnetic tape, or any other unit-record device.

### Junk Mail

* Our program had a shape. That shape disconnected policy from detail. The policy was the formatting of the name and address records. The detail was the device. We deferred the decision about which device we would use.

### Physical Addressing

* We change the high-level policy of the system to be agnostic about the physical structure of the disk. That allowed us to decouple that decision about disk drive structure from the application.

### Conclusion

* Good architects carefully separate details from policy, and then decouple the policy from the details so thoroughly that the policy has no knowledge of the details and does not depend on the details in any way.
* good architects design the policy so that decisions about the details can be delayed and deferred for as long as possible.

## 16. Independence

* A good architecture must support:
  * The use cases and operation of the system.
  * THe maintenance of the system.
  * The development of the system.
  * The deployment of the system.

### Use Cases

* THe architecture of the system must support the intent of the system.
* This is the first concern of the architect, and the first priority of the architecture.
* Architecture does not wield much influence over the behavior of the system.
* The most important thing a good architecture can do to support behavior is to clarify and expose that behavior so that the intent of the system is visible at the architectural level.
* A shopping cart application with a good achitecture will _look_ like a shopping cart application.
* Developers will not have to hunt for behaviors, because those behaviors will be first-class elements visible at the top level of the system.
* Those elements will be classes or functions or modules that have prominent positions within the architecture.

### Operation

* Architecture plays a more substantial, and less cosmetic, role in supporting the operation of the system.
* If the system must handle 100.000 customers per second, the architecture must support that kind of throughput and response time for each use case that demands it.
* THis decision is one of the options that a good architectd leaves open.
* An architeture that maintains the proper isolation of this components, and does not assume the means of communication between those components, will be much easier to transition through the spectrum of threads, processes, and services as the operational needs of the system change over time.

### Development

* Arhictecture plays a significant role in supporting the development environment.
> Any organization that designs a system will produce a design whose structure is a copy of the organization's communication structure.
* A system that must be developed by an organization with many teams and many concerns, must have an architecture that facilitates independent actions by those teams, so that the teams do not interfere with each other during development.

### Deployment

* THe architecture also plays a huge role in determining the ease with which the system is deployed.
* A good architecture does not rely on dozens of little configuration scripts and property file tweaks.
* A good architecture helps the system to be immediately deployable after build.
* This is achieved through the proper partitioning and isolation of the components of the system, including those master components that tie the whole system together and ensure that each component is properly started, integrated and supervised.

### Leaving Options Open

* A good architecture makes the system easy to change, in all the ways that it must change, by leaving options open.

### Decoupling Layers

* The architect wants the structure of the system to support all the necessary use cases, but does not know what all those use cases are. However, the architect DOES know the basic intent of the system.
* Separate those things that change for different reasons, and to collect those things that change for the same reasons.
* User interfaces change for reasons that have nothing to do with business rules.
* A good architect will want to separate the UI portions of a use case from the business rule portions in such a way that they can be changed independently of each other, while keeping those use cases visible and clear.
* THe validation of input fields is a business rule that is closely tied to the application itself.
* The calculation of interest on an account and the counting of inventory are business rules that are more closely associated with the domain.
* They should be separated so that they can be independetly changed.
* The database, the query language, and even the schema are technical details that have nothing to do with the business rules or the UI.
* The architecture should separate them from the rest of the system so that they can be independetly changed.
* Some decoupled horizontal layers are: The UI, application-specific business rules, application-independent business rules, and the database.

### Decoupling Use Cases

* The use case for adding an order to an order entry system almost certainly will change at a different rate, and for different reasons, tham the use case that deletes an order from the system.
* Each use case uses some UI, some application-specific business rules, some application-independent business rules, and some database functionality.
* If you decouple the elements of the system that change for different reasons, then you can continue to add new use cases without interfering with old ones.
* If you also group the UI and database in support of those use cases, so that each use case uses a different aspect of the UI and database, then adding new use cases will be unlikely to affect older ones.

### Decoupling Mode

* If different aspects of the use cases are separated, then those that must run at a high throughput are likely already separated from those that must run at a low throughput.
* If the UI and the database have been separated from the business rules, then they can run in different servers.
* To run in separate servers, the separated components cannot depend on being together in the same address space of a processor.
* An architecture based on services is often called a service-oriented architecture.
* I'm not going to tell you that SoA is the best possible architecture, or that microservices are the wave of the future.
* Sometimes we have to separate our components all the way to the service level.
* A good architecture leaves options open. _The decoupling mode is one of those options_.

### Independent Develop-Ability

* When components are strongly decoupled, the interference between teams is mitigated.
* So long as the layers and use cases are decoupled, the architecture of the system will support the organization of the teams.

### Independent Deployability

* The decoupling of the use cases and layers also affords a high degree of flexibility in deployment.

### Duplication

* When code is truly duplicated, we are honor-bound as professionals to reduce and eliminate it.
* There is true duplication, in which every change to one instance necessitates the same change to every duplicate of that instance.
* If two appartently duplicated sections of code evolve along different paths, then _they are not true duplicates_. They are a false or accidental dupplication.
* When you are vertically separating use cases from one another, you will run into this issue, and your temptation will be to couple the use cases because they have similar screen structures, or similar algorithms, or similar database queries and/or schemas. Be careful. Resist the temptation to commit the sin of knee-jerk elimination of duplication. Make sure the duplication is real.
* When you are separating layers horizontally, you might notice that the data structure of a particular database record is very similar to the data structure of a particular screen view. You may be tempted to simply pass the database record up to the UI, rather than to create a view model that looks the same and copy the elements across. Be careful: This duplication is almost certainly accidental.

### Decoupling Modes (Again)

* **Source level.** Changes to one module do not force changes or recompilation of others. The components all execute in the same address space, and communicate with each other using simple function calls.
* **Deployment level.** We can control the dependencies between deployable units such as jar files, DLLs, or shared libraries so that changes to the source code in one module do not force others to be rebuild and redeployed. Decoupled components are partitioned into independently deployable units such as jar files, Gem files, or DLLs.
* **Service level.** We can reduce the dependencies down to the level of data structures, and communicate solely through network packets such that every execution unit is entirely independent of souce and binary changes to others.

* It's hard to know which mode is best during the early phases of a project.
* As the project matures, the optimal mode may change.
* While the system runs on a single server, the source-level decoupling might be sufficient. Later, however, it might require dcoupling into deployable units, or even services.
> Dealing with service boundaries where none are needed is waste of effort, memory and cyles. Specially effort.
* Push the decoupling to the point where a service _could_ be formed; but then, leave the components in the same address space as long as possible.
* As the development, deployment and operational issues increase, I carefully choose which deployable units to turn into services, and gradually shift the system in that direction.
* A good architecture will allow a system to be born as a monolith, but then to grow into a set of independtly deployable units, and then all the way to independent services and/or micro-services.

### Conclusion

* The decoupling mode of a system is one of those things that is likely to change with time, and a good architect foresees and _appropriately_ facilitates those changes.

## 17. Boundaries: Drawing Lines

* Boundaries separate software elements from one another, and restrict those on one side from knowing about those on the other.
* Those that are drawn early are drawn or the purposes of deferring decisions for as long as possible, and of keeping those decisions from polluting the core business logic.
* A good system architecture is one in which decisionslike these are rendered ancillary and deferrable.
* A good system architecture allows those decisions to be made at the latest possible moment, without significant impact.

### A Couple of Sad Stories

* The tragedy is that the architects, by making a premature decision, multiplied the development effort enormously.
* There's nothing intrinsically wrong with a software system that is structured around services. The error at `W` was the premature adoption and enforcement of a suite of tools that promised SoA - that is, the premature adoption of a massive suite of domain object services.

### FitNesse

* We purposely delayed that decision by employing a design that made the decision irrelevant. That design was simply to put an interface between all data accesses and the data repository itself.
* We didn't implement those methods at first: we simply stubbed them out while we worked on features that didn't involve fetching and saving the data.
* Three months later, we reached the conclusion that the flat file solution was good enough; we decided to abandon the idea of MySQL altogether. We deferred that decision into nonexistence and never looked vack.
* He came back _a day later_ with the whole system working in MySQL. He simply wrote a `MySqlWikiPage` derivative and got it working.
* Warly in the development of `FitNesse`, we drew a _boundary_ line between business rules and databases. That line prevented the business rules from knowing anything at all about the database, other than the simple data access methods.
* It also meant that all our tests ran fast, because there was no database to slow them down.
* In short, drawing the boundary lines helped us delay and defer decisions, and it ultimately saved us an enormous amount of time and headaches. And that's what a good architecture should do.

### Which LInes Do You Draw, and When Do You Draw Them?

* You draw lines between things that matter and things that don't. The GUI doesn't matter to the business rules, so there should be a line between them.
* THe database doesn't matter to the GUI, so there should be a line between them.
* THe database doesn't batter to the business rules, so there should be a line between them.
* The database is a tooll that the business rules can use _indirectly_.
* THe business rules don't need to know about the schema, or the query language, or any of the other details about the database.
* All the business rules need to know is that there is a set of functions that can be used to fetch or save data.
* THis allow us to put the database behind an interface.
* The boundary is drawn across the inheritance relationship.
* Note the two arrows leaving the `DatabaseAccess` class. Those two arrows point away from the `DatabaseAccess` class. That means that none of these classes knows that the `DatabaseAccess` class exists.
* The `BusinessRules` do not know about the `Database`. This implies that the `DatabaseInterface` classes live in the `BusinessRules` component, while the `DatabaseAccess` classes live in the `Database` component.
* `Database` does not matter to the `BusinessRules`, but the `Database` cannot exits without the `BusinessRules`.
* The `Database` component contains the code that translated the calls made by the `BusinessRules` into the query language of the database.
* The `BusinessRules` could use _any_ kind of database. The `Database` component could be replaced with many different implementations -the `BusinessRules` don't care.

### What About Input and Output?

* The _IO_ is irrelevant.
* We often think about the behavior of the system in terms of the behavior of the IO.
* Your experience is dominated by the interface: the screen, the mouse, the buttons, and the sounds.
* More importantly, that model (some data strctures and functions) does not need the interface.
* The _GUI_ could be replaced with any other kind of interface -and the `BusinessRules` would not care.

### Plugin Architecture

* These two decisions about the database and the GUI create a kind of pattern for the addition of other components.
* The history of software development technology is the story of how to conveniently create plugins to establish a scalable and maintainable system architecture.
* The core business rules are kept separate from, and independent of, those components that are either optional or that can be implemented in many different forms.
* Because the user interface in this design is considered to be a plugin, we have made it possible to plug in many different kinds of user interfaces.
* THe same is true of the database. Since we have chosen to treat it as a plugin we can replace it with any of the vaious SQL database, or a NOSQL database.
* These replacements might not be trivial. Even so, by starting with the presuption of a plugin structure, we have at very least made such a change practical.

### The plugin Argument

* That's a deeply asymmetric relationship, and it is one that we desire to have in our own systems. We want certain modules to be immune to others.
* We don't want changes in one part of the system to cause other unrelated parts of the system to break.
* Arranging our systems into a plugin architecture creates firewalls across which changes cannot propagate.

### Conclusion

* Dependency arrows are arranged to point from lower-level details to higher-level abstractions.

## 18. Boundary Anatomy

* The architecture of a system is defined by a set of software components and the boundaries that separate them.

### Boundary Crossing

* A boundary crossing is nothing more than a function on one side of the boundary calling a function on the other side and passing along some data.
* When one source code module changes, other source code module may have to be changed or recompiled, and then, redeployed.

### The Deaded Monolith

* The simplest and most common of the architectural boundaries has no strict physical representation. It is simply a disciplined segregation of functions and data within a single processor and a single address space.
* From a deployment point of view, this amounts to nothing more than a single executable file -the so-called monolith.
* THe fact that the boundaries are not visible during the deployment of a monolith does not mean that they are not present and meaningful.
* Even when statically linked into a single executable, the ability to independently develop and marshal the various components for final assembly is immensely valuable.
* Such architectures almost always depend on some kind of dynamic polymorphism to manage their internal dependencies.
* The simplest possible boundary crossing is a function call from a low-level client to a higher-level service.
* When a high-level client needs to invoke a lower-level service, dynamic polymorphism is used to invert the dependency against the flow of control.
* All dependencies cross the boundary from right to left _toward the higher-level component_.
* The definition of the data structure is on the calling side of the boundary.
* This kind of disciplined partitioning can greatly aid the job of developing, testing, and deploying the project.
* High-level components remain independent of lower-level details.
* Since the deployment of monoliths usually requires compilation and static linking, components in these systems are typically delivered as source code.

### Deployment Components

* The simplest physical reprsentation of an architectural boundary is a dynamically linked library like a .Net DLL, a Java jar file, a Ruby Gem, or a UNIX shared library. Deployment does not involve compilation.
* Instead, the components are delivered in binary, or some equivalent deployable form.
* This is the deployment-level decoupling mode. The act of deployment is simply the gathering of these deployable units together in some convenient form.
* As with monoliths, communications across deployment component boundaries are just function calls and, therefore, are very inexpensive.

### Threads

* Threads are not architectural boundaries or units of deployment, but rather a way to organize the schedule and order of execution.

### Local Processes

* Local processes run in the same processor, or in the same set of processors withing a multicore, but run in separate address spaces.
* Most ofthen, local processes communicate with each other using sockets, or some other kind of operating system communications facility such as mailboxes or message queues.
* The segregation strategy between local processes is the same as for monoliths and binary components. Source code dependencies point in the same direction across the boundary, and always toward the higher-level component.
* Communication across local process boundaries involve operating system calls, data marshaling and decoding, and interprocess context switches, which are moderately expensive.

### Services

* The strongest boundary is a service.
* Services do not depend on their physical location.
* The services assume that all communications take place over the network.
* Communications across service boundaries are very slow compared to function calls.
* Care must be taken to avoid chatting where possible.
* Communications at this level must deal with high levels of latency.

### Conclusion

* This means that the boundaries in a system will often be a mixture of local chatty boundaries and boundaries that are more concerned with latency.

## 19. Policy and Level

* A computer program is a detailed description of the policy by which inputs are transformed into outputs.
* That policy can be broken down into many different smaller statements of policy. Some of those statements will describe how particular business rules are to be calculated. Other will describe how certain reports are to be formatted. Still others will describe how input data are to be validated.
* Part of the art of developing a software architecture is carefully separating those policies from one another, and regrouping them based on the ways that they change.
* The art of architecture often involves forming the regrouped components into a directed acyclic graph. THe nodes of the graph are the components that contain policies at the same level.
* Those dependencies are source code, compile-time dependencies.
* Low-level components are designed so that they depend on high-level components.

### Level

* The farther a policy is from both the inputs and the outputs of the system, the higher its level.
* The policies that manage input and output are the lowest-level policies in the system.
* The data flows and the source code dependencies do not always point in the same direction.
* We want source code dependencies to be decoupled from data flow and _coupled to level_.
* Keeping these policies separate, with all source code dependencies pointing in the direction of the higher-level policies, reduces the impact of change.
* Trivial but urgent changes at the lowest levels of the system have little or no impact on the higher, more important, levels.

## 20. Business Rules

* What business rules actually are: It turns out there are several different kinds.
* Business rules are rules or procedures that make or save the business money.
* THe fact that a bank charges _N%_ interest for a loan is a business rule that makes the bank money. It doesn't matter if a computer program calculates the interest, or if a clerk with an abacus calculates the interest.
* We shall call these rules _Critial Business Rules_, because they are critical to the business itself, and would exist even if there were no system to automate them.
* Critial Business Rules usually require some data to work with.
* We shall call this data _Critial Business Data_. This is the data that would exist even if the system were not automated.

### Entities

* An Entity is an object withing our computer system that embodies a small set of critical business rules operating on Critical Business Data.
* The Entity object either contains the Critical Business Data or has very easy access to that data.
* This class stands alone as a representative of the business.
* It could serve the business in any system, irrespective of how that system was presented, or how the data was stored, or how the computers in that system were arranged. The Entity is pure business and _nothing_ else.

### Use Cases

* Some business rules make or save money for the business by defining and constraining the way that an _automated_ sytem operates.
* The bank may decide that it does not want the loan officers to offer loan payment estimates until they have first gathered, and validated, contact information and ensured that the candidate's credit score is 500 or higher.
* A use case is a description of the way that an automated system is used.
* It specifies the input to be provided by the user, the output to be returned to the user, and the processing steps involved in producing that output. A use case describes _application-specific_ business rules as opposed to the Critical Business Rules within the Entities.
* Use cases contain the rules that specify how and when the Critical Business Rules within the Entities are invoked.
* Use cases control the dance of the Entities.
* The use case does not describe the user interface other than to informally specify the data coming in from that in from that interface, and the data going back out through that interface. From the use case, it is impossible to tell whether the application is delivered on the web, or on a thick client, or on a console, or is a pure service.
* Use cases do not describe how the system appears to the user.
* Use cases describe the application-specific rules that govern the interaction between the users and the Entities.
* How the data gets in and out of the system is irrelevant to the use cases.
* Entities have no knowledge of the use cases that control them.
* High-level concepts, such as Entities, know nothing of lower-level concepts, such as use cases.
* Use cases are specific to a single application and, therefore, are closer to the inputs and outputs of that system.
* Entities are generalizations that can be used in many different applications, so they are farther from the inputs and outputs of the system.

### Request and Response Models

* The use case class accepts simple request data structures for its input, and returns simple response data structures as its output. THese data structures are not dependent on anything.
* If the request and response models are not independent, then the use cases that depend on them will be indirectly bound to whatever dependencies the models carry with them.
* You might be tempted to have these data structures contain references to Entity objects. Avoid this temptation!

### Conclusion

* Ideally, the code that represents the business rules should be the heart of the system, with lesser concerns being plugged in to them.

## 21. Screaming Architecture

* When you look at the top-level directory stucture, and the source files in the highest-level package, do they screal "Health Care System", or "Accounting System", or "Inventory Management System"? Or do they scream "Rails", or "Sprint/Hibernate" or "ASP"?

### The Theme of and Architecture

* Just as the plans for a house or a library scream about the use cases of those buildings, so should the architecture of a software application scream about the use cases of the application.
* Architectures are not (or should not be) about frameworks. Architecrures should not be supplied by frameworks. Frameworks are tools to be used, not architectures to be conformed to.

### The Purpose of and Architecture

* Good architectures are centereed on use cases so that architects can safely describe the structures that support those use cases without committing to frameworks, tools and environments.
* Consider the plans for a house. The first concern of the architect is to make sure that the house is usable - Not to ensure that the house is made of bricks.
* A good architecture emphasizes the use cases and decouples them from peripheral concerns.

### But What About the Web?

* The web is a delivery mechanism -an IO device- and your application architecture should treat it as such.
* The fact that your application is delivered over the web is a detail and should not dominate your system structrue.

### Frameworks Are Tools, Not Ways of Life

* Look at each framework with a jaded eye. View it skeptically. Tes, it might help, but at what cost?
* Think about how you can preserve the use-case emphasis of your architecture. Develop a strategy that prevents the framework from taking over that architecture.

### Testable Architectures

* If your system architecture is all about the use cases, and if you have kept your frameworks at arm's length, then you should be able to unit-test all those use cases without any of the frameworks in place.
* You shouldn't need the web server running to run your tests. You shouldn't need the database connected to run your tests.
* Your Entity objects should be plain old objects that have no dependencies on frameworks or databases or other complications.
* Your use case objects should coordinate your Entity objects.
* All of them together should be testable in situ.

### Conclusion

* Your architecture should tell readers about the system, not about the frameworks you used in your system.

## 22. The Clean Architecture

* There are several architectures, such as "Hexagonal Architecture", "DCI" and "BCE" that have the same objective, which is the separation of concerns.
* THey all achieve this separation by dividing the software into layers.
* Each of these architectures produces systems that have the following characteristics:
  * Independent of frameworks: This allows you to use such frameworks as tooks, rather than forcing you to cram your system into their limited constraints.
  * Testable: The business rules can be tested without any external element.
  * Independent of the UI: A web UI could be replaced with a console UI, for example, without changing the business rules.
  * Independent of the database.
  * Independent of any external agency: Your business rules don't know anything at all about the interfaces to the outside world.

### The Dependency Rule

* In general, the further in you go, the higher level the software becomes. The outer circles are mechanisms. The inner circles are policies.
* Source code dependencies must point only inward, toward higher-level policies.
* Nothing in an inner circle can know anything at all about something in an outer circle.
* The name of something declared in an outer circle must not be mentioned by the code in an inner circle.
* We don't want anything in an outer circle to impact the inner circles.

#### Entities

* Entities encapsulate enterprise-wide Critial Business Rules. An entity can be an object with methods, or it can be a set of data structures and functions.
* They encapsulate the most general and high-level rules.
* They are the least likely to change when something external changes.

#### Use Cases

* The software in the use cases layer contains _application-specific_ business rules.
* It encapsulates and implements all of the use cases of the system.
* These use cases orchestrate the flow of data to and from the entities, and direct those entities to use their Critical Business Rules to achieve the goals of the use case.
* We do expect that changes to the operation of the application will affect the use cases and, therefore, the software in this layer.
* If the details of a use case change, then some code in this layer will certainly be affected.

#### Interface Adapters

* The software in the interface adapters layer is a set of adapters that convert data from the format most convenient for the use cases and entites, to the format most convenient for some external agency such as the database or the web.
* The presenters, views and controllers all belon in the interface adapters layer.
* Data is converted, in this layer, from the form most convenient for entities and use cases, to the form most convenient for whatever persistence framework in being used.
* Also in this layer is any other adapter necessary to convert data from some external form, such as an external service, to the internal form used by the use cases and entities.

#### Frameworks and Drivers

* Generally you don't write much code in this layer, other than glue code that communicates to the next circle inward.
* We keep these things on the outside where they can do little harm.
* The Dependency Rule always applies. Souce code dependencies always point inward. As you move inward, the level of abstraction and policy increases.

#### Crossing Boundaries

* It show the controllers and presenters communicating with the use cases in the next layer.
* Note the flow of control: It begins in the controller, moves through the use case, and then winds up executing in the presenter.
* Note also the source code dependencies: Each points inward toward the use cases.
* Suppose the use case needs to call the presenter. This call must not be direct because that would violate the Dependency Rule: No name in an outer circle can be mentioned by an inner circle.
* So we have the use case call an interface in the inner circle, and have the presenter in the outer circle implement it.
* We take advantage of dynamic prolymorphism to create source code dependencies that oppose the flow of control, so that we can conform to the Dependency Rule, no matter which direction the flow of control travels.

#### Which Data Crosses the Boundaries

* Typically the data that crosses the boundaries consists of simple data structures.
* The important thing is that isolated, simple data structures are passed across the boundaries. We don't want to cheat and pass Entity objects or database rows.
* Many database frameworks return a convenient data format in response to a query. We might call this a "row structure". We don't want to pass that row structure inward across a boundary.

### A Typical Scenario

* The `Controller` packages the data into a plain old Java object and passes this object through the `InputBoundary` to the `UseCaseInteractor`.
* The `UseCaseInteractor` interprets that data and uses it to control the dance of the `Entities`.
* It also uses the `DataAccessInterface` to bring the data used by those `Entities` into memory from the `Database`.
* `UseCaseInteractor` gathers data from the `Entities` and constructs the `OutputData` as another plain old Java object. The `OutputData` is then passed through the `OutputBoundary` interface to the `Presenter`.
* The job of the `Presenter` is to repackage the `OutputData` into viewable form as the `ViewModel`, which is yet another plain old Java object.
* Whereas the `OutputData` may contain `Date` objects, the `Presenter` will load the `ViewMOdel` with corresponding `Strings` already formatted properly for the user.
* `Button` and `MenuItem` names are placed in the `ViewModel`, as are flags that tell the `View` whether those `Buttons` and `MenuItems` should be gray.
* This leaves the `View` with almost nothing to do other than to move the data from the `ViewMOdel` into the `HTML` page.

### Conclusion

* By separating the software into layers and conforming to the Dependency Rule, you will create a system that is intrinsically testable, with all the benefits that implies.

## 23. Presenters and Humble Objects

* Presenters are a form of the _Humble Object_ pattern, which helps us identify and protect architectural boundaries.

### The Humble Object Pattern

* The _Humble Object_ pattern is a design pattern that was identified as a way to help unit testers to separate behaviors that are hard to test from behaviors that are easy to test.
* Split the behaviors into two modules or classes. One of those modules is humble; it contains all the hard-to-test behaviors stripped down to their barest essence. The other module contains all the testable behaviors that were stripped out of the humble object.
* Using the _Humble Object_ pattern, we can separate these two kinds of behaviors into two different classes called the Presenter and the View.

### Presenters and Views

* The View is the humble object that is hard to test. The code in this object is kept as simple as possible.
* The Presenter is the testable object. Its job is to accept data from the application and format it for presentation so that the View can simply move it to the screen.
* If the application wants a date displayed in a field, it will hand the Presenter a `Date` object. The Presenter will then format that data into an appropriate string and place it in a simple data structure called the `View Model`, where the View can find it.
* Every button on the screen will have a name. That name will be a string in the View Model, placed there by the presenter. If those buttons should be grayed out, the Presenter will set an appropriate boolean flag in the View model.
* Every menu item name is a string in the View model, loaded by the Presenter.
* Anything and everything that appears on the screen, and that the application has some kind of control over, is represented in the View Model as a string, or a boolean, or an enum. Thus, the View is humble.

### Testing and Architecture

* The separation of the behaviors into testable and non-testable parts often defines an architectural boundary.

### Databse Gateways

* Between the use case interactors and the database are the database gateways. These gateways are polymorphic interfaces that contain methods for every create, read, update or delete operation that can be performed by the application of the database.
* Recall that we do not allow SQL in the use cases layer; instead, we use gateway interfaces that have appropriate methods. Those gateways are implemented by classes in the database layer. That implementation is the humble object.
* The interactors are not humble because they encapsulate application-specific business rules. Although they are not humble, those interactors are _testable_, because the gateways can be replaced with appropriate stubs and test-doubles.

### Data Mappers

* There is no such thing as an object relational mapper (ORM). The reason is simple: Objects are not data structures.
* The users of an object cannot see the data, since it is all prive.
* A data structure, in contrast, is a set of public data variables that have no implied behavior.
* ORMs would be better named "data mappers", because they load data into data structures from relational database tables.
* Where should such ORM systems reside? In the database layer.
* ORMs form another kind of _Humble Object_ boundary between the gateway interfaces and the database.

### Service Listeners

* The application will load data into simple data structures and then pass those structures across the boundary to modules that properly format the data and send it to external services.
* The service listeners will receive data from the service interface and format it into a simple data structure that can be used by the application.

### Conclusion

* At each architectural boundary, we are likely to find the _Humble Object_ pattern lurking somewhere nearby.
* The boundary will frequently divide something that is hard to test from something that is easy to test.

## 24. Partial Boundaries

* Full-fledged architectural boundaries are expensive. They require reciprocal polymorphic `Boundary` interfaces, `Input` and `Output` data structures, and all of the dependency management necessary to isolate the two sides into independently compilable and deployable components.
* A good architect might judge that the expense of such a boundary is too high.
* This kind of anicipatory design is often frowned upon by many in the Agile community as a violation of YAGNI: "You Aren't Going to Need it". Architects, however, sometimes look at the problem and think, "Yeah, but I might". In that case, they may implement a partial boundary.

### Skip the Last Step

* One way to construct a partial boundary is to do all the work necessary to create independently compilable and deployable components, and then simply keep them together in the same component.
* Obviosly, this kind of partial boundary requires the same amount of code and preparatory design work as a full boundary.
* Over time, as it became clear that there would never be a need for a separate web component, the separation between the web component and the wiki component began to weaken.
* Dependencies started to cross the line in the wron direction.

### One-Dimensional BOundaries

* A simpler stucture that serves to hold the place for later extension to a full-fledged boundary, exemplifies the traditional _Strategy_ pattern. A `ServiceBoundary` interface is used by clients and implemented by `ServiceImpl` classes.
* Without reciprocal interfaces, nothing prevents this kind of backchannel other than the diligence and discipline of the developers and architects.

### Facades

* An even simpler boundary is the _Facade_ pattern. In this case, even the dependency inverseion is sacrificed.
* The boundary is simply defined by the _Facade_ class, which lists all the services as methods, and deploys the service calls to classes that the client is not supposed to access.
* Note, however, that the _Client_ has a trasitive dependency on all those service classes.

### Conclusion

* Each of these approaches has its own set of costs and benefits. Each is appropriate, in certain contests, as a placeholder for an eventual full-fledged boundary.
* Each can also be degraded if that boundary never materializes.

## 25. Layers and Boundaries

### Hunt the Wumpus

### Clean Architecture?

* It should be clear that we could easily apply the clean architecture approach in this context, with all the use cases, boundaries, entities, and corresponding data structures But, have we really found all the significant architectural boundaries?

### Crossing the Streams

* So, as systems become more complex, the component structure may split into many such streams.

### Splitting the Streams

* At this point you may be thinking that all the streams eventually meet at the top in a single component. The reality, of course, is much more complex.
* `MoveManagement` is handled locally within the player's computer, but `PlayerManagement` is handled by a server. `PlayerManagement` offers a micro-service API to all the connected `MoveManagement` components.
* A full-fledged architectural boundary exists between `MoveManagement` and `PlayerManagement` in this case.

### Conclusion

* This example is intended to show that architectural boundaries exist everywhere. We, as architectus, must be careful to recognize when they are needed.
* We also have to be aware that such boundaries, when fully implemented, are expensive.
* When such boundaries are ignored, they are very expensive to add in later -even in the presence of comprehensive test-suites and refactoring discipline.
* Some very smart people have told us, that we should not anticipate the need for abstraction (You aren't going to need it).
* Over-engineering is often much worse thatn under-engineering.
* WHen you discover that you truly do need an architectural boundary where none exists, the costs and risks can be very high to add such a boundary.
* O software Architect, you must see the future. You must guess -intelligently.
* You pay attention as the system evolves. You note where boundaries may be required, and then carefully watch for the first inkling of friction because those boundaries don't exist.
* Your goal is to implement the boundaries right at the inflection point where the cost of implementing becomes less than the cost of ignoring.

## 26. The Main Component

* In every system, there is at least one component that creates, coordinates, and oversees the others. I call this component `Main`.

### The Ultimate Detail

* It is the initial entry point of the system. Nothing, other than the operating system, depends on it.
* Its job is to create all the Factories, Strategies, and other global facilities and then hand control over to the high-level abstract portions of the system.
* It is in this `Main` component that dependencies should be injected by a Dependency Injection framework.
* Once they are injected into `Main`, `Main` should distribute those dependencies normally, without using the framework.
* This of `Main` as the dirtiest of all the dirty components.
* Notice also that `main` creates the input stream and contains the main loop of the game, interpreting the simple input commands, but then defers all processing to other, higher-level components.
* The point is that `Main` is a dirty low-level module in the outermost circle of the clean architecture. It loads everything up for the high level system, and then hands control over to it.

### Conclusion

* Think of `Main` as a plugin to the application -a plugin that sets up the initial conditions and configurations, gathers all the outside resources, and then hands control over the high-level policy of the applications. Since it is a plugin, it is possible to have many `Main` components, one for each configuration of your application.
* When you think about `Main` as a plugin component, sitting behind an architectural boundary, the problem of configuration becomes a lot easier to solve.

## 27. Services: Great and Small

* Service-oriented "architectures" and micro-service "architectures" have become very popular of late. The reasons for their current popularity include the following:
1. Services seem to be strongly ddecoupled from each other.
2. Services appear to support independence of development and deployment. 

### Service Architecture?

* The architecture of a system is defined by boundaries that separate high-level policy from low-level detail and follow the Dependency Rule. Services that simply separate application behaviors are little more that expensive funciton calls, and are not necessarily architecturally significant.
* This is not to say that all services _should_ be architecturally significant. There are often benefits to creating services that separate functionality across processes and platforms
* It's just that services, in and of themselvs, do not define an architecture.
* Services are, after all, just function calls across process and/or platform boundaries. Some of those services are architecturally significat, and some aren't.

### Service Benefits?

#### The Decoupling Fallacy

Yes, services are decoupled at the level of individual variables. However, they can still be coupled by shared resources withing a processor, or on the network. What's more, they are strongly coupled by the data they share.
* For example, if a new field is added to a data record that is passed between services. Those services are strongly coupled to the data record and therefore, indirectdly coupled to each other.
* Service interfaces are no more formal, no more rigorous, and no better defined than functions interfaces.

#### The Fallacy of Independent Development and Deployment

* It is believed that large enterprise systems can be created from dozens, hundreds, or even thousands of independently developable and deployable services.
* History has shown that large enterprise systems can be built from monoliths and component-based systems as well as service-based systems.
* Services cannot always be independently developed, deployed and operated. To the extend that they are coupled by data or behavior, the development, deployement and operation must be coordinated.

### The Kitty Problem

* This system knows about many taxi providers in a given city, and allows customers to order rides.
* We wanted our system to be scalable, so we chose to build it out of lots of little micro-services.
* How many of those services will have to change to implement this feature? All of them.
* The services are all coupled, and cannot be independently develop, deployed and maintained.
* This is the problem with cross-cutting concerns. Every software system must face this problem, whether service oriented or not. Functional decompositions, are very vulnerable to new features that cut across all those functional behaviors.

### Objects to the Rescue

Careful consideration of the SOLID design principles would have prompted us to create a set of classes that could be polymorphically extended to handle new features.
* Much of the logic in the original services is preserved withing the base classes of the object model.
* These two components override the abstract base classes in the original components usuing a pattern such as _TEmplate Method_ or _Strategy_.
* Note also that the classes that implement those features are created by factories under the control of the UI.

### Component-Based Services

* Services do not need to be little monoliths. Services can, instead, be designed using the SOLID principles, and given a component structure so that new components can be added to them without changing the existing components withing the service.
* Deploying a new feature then becomes not a matter of redeploying the services, but rather a matter of simply _adding_ the new jar files to the load paths of those services.
* Adding new features conforms to the Open-Closed Principle.
* The services still exist as before, but each has its own internal component design, allowing new features to be added as new derivative classes.

### Cross-Cutting Concerns

* Architectural boundaries do not fall _between_ services. Rather, those boundaries run _through_ the services, dividing them into components.
* Services must be designed with internal component architectures that follow the Dependency Rule.
* Those services do not define the architectural boundaries of the system; instead, the components withing the services do.

### Conclusion

* As useful as services are to the scalability and develop-ability of a system, they are not, in and of themselves, architecturally significant elements.
* The architecture of a system is defined by the boundaries drawn within that system, and by the dependencies that cross those boundaries. That architecture is not defined by the physical mechanisms by which elements communicate and execute.

## 28. The Test Boundary

* _The tests are part of the system_, and they participate in the architecture just like every other part of the system does.

### Tests as System Components

* From an architectural point of view, all tests are the same.
* Tests, by their very nature, follow the Dependency Rule; they are very detailed and concrete; and they always depend inward toward the code being tested. In fact, you can think of the tests as the outermost circle in the architecture.
* Tests are also independently deployable. In fact, most of the time they are deployed in test systems, rather than in production systems.
* Tests are the most isolated system component. They are not necessary for system operation. No user depends on them. Their role is to support development, not operation.

### Design for Testability

* Tests that are not wel integrated into the design of the system tends to be fragile, and they make the system rigid and difficult to change.
* Tests that are strongly coupled to the system must change along with the system. Even the most trivial change to a system component can cause many coupled tests to break or require changes.
* Changes to common system components can cause hundreds, or even thousands, of tests to break. This is known as the _Fragile Test Problem_.
* Fragile tests often have the perverse effect of making the system rigid. When developers realize that simple changes to the system can cause massive tests failures, they may resist making those changes.
* The solution is to design for testability. The first rule of software design is always the same: _Don't depend on volatile things_. GUIs are volatile. Test suites that operate the system through the GUI m_must be fragile_. Therefore design the system, and the tests, so that business rules can be tested without using the GUI.

### The Testing API

* The way to accomplish this goal is to create a specific API that the tests can use to verify all the business rules.
* This API should have supperpowers that allow the tests to avoid security constraints, bypass expensive resources, and force the system into particular testable states.
* This API will be a superset of the suite of _interactors_ and _interface adapters_ that are used by the user interface.

#### Structural Coupling

* Imagine a test suite that has a test class for every production class, and a set of test methods for every production method. Such a test suite is deeply coupled to the structure of the application.
* When one of those production methods or classes changes, a large number of tests must change as well. Consequently, the tests are fragile, and they make the production code rigid.
* The role of the testing API is to hide the structure of the application from the tests.
* This separation of eveolution is necessary because as time passes, the tests tend to become increasingly more concrete and specific. In contrast, the production code tends to become increasingly more abstract and general.

#### Security

The superpowers of the testing API could be dangerous if they were deployed in production systems. If this is a concern, then the testing API and the dangerous parts of its implementation, should be kept in a separate, independently deployable component.

### Conclusion

* Tests that are not designed as part of the system tend to be fragile and difficult to maintain.

## 29. Clean Embedded Architecture

* Although software does not wear out, firmware and hardware become obsolete, thereby requiring software modifications.
* _Software_ is this thing that can have a long useful life, but _firmware_ will become obsolete as hardware evolves.
* _Although software does not wear out, it can be destroyed from within by unmanaged dependencies on firmware and hardware_.
* Firmware does not mean code lives in ROM. It's not firmware because of where it is stored; rather, it is firmware because of what it depends on and how hard it is to change as hardware evolves. Hardware does evolve, so we should structure or embedded code with that reality in mind.
* You non-embedded developers essentially write firmware whenever you bury SQL in your code or when you spread platform depdencies throughout your code. Android app developers write firmware when they don't separate their business logic from the Android API.
* The existing implementation had no separation between TDM (Time-Division Multiplexing) and the business logic of making calls. The whole product was hardware/technology dependent from top to bottom and could not be untangled. The whole product had essentially become firmware.
* Unsurprisingly, there is a message processor/dispatcher. The message processor knows the format of messages, is able to parse them, and can then dispatch the message to the code that can handle the request.
* None of this is surprising, except that the message processor/dispatcher resides in the same file as code that interacts with a UART hardware. THe message processor is polluted with UART details. The message processor could have been software with a potentially long useful life, but instead it is firmware.

### App-titude Test

* Most of the emphasis is on getting the embedded code to work, and not so much emphasis is placed on structuring it for a long useful life.
* Kent Beck describes three activities in building software:
  1. "First make it work". _You are out of business if it doesn't work_
  2. "Then make it right". _Refactor the code so that you and others can understand it and evolve it as needs change or are better understood._
  3. "Then make it fast". _Refactor the code for "needed" performance._
* Most non-embedded apps are build just to work, with little regard to making the code right for a long useful life.
* Getting an app to work is what I call the _App-titude test_ for a programmer.
* There is much more to programming than just getting an app to work.
* This application works: The engineer passed the App-titude test. But the application can't be said to have a clean embedded architecture.

### The Target-Hardware Bottleneck

* There are many special concerns that embedded developers have to deal with that non-embedded developers do not -for example, limited memory space, real-time constraints and deadlines, limited IO, unconventional user interfaces, and sensors and connections to the real world.
* When embedded conde is structured without appltying clean architecture principles and practices, you will often face the scenario in which you can test your code only on the target. If the target is the only place where testing is possible, the target-hardware bottleneck will show you down.

#### A Clean Embedded Arhcitecture Is A Testable Embedded Architecture

##### Layers

* There is nothing that keeps hardware knowledge from polluting all the code. If you are not careful about where you put things and what one module is allowed to know about another module, the code will be very hard to change.
* Software and firmware intermingling is an anti-pattern. Code exhibiting this anti-pattern will resist changes.
* If you have not created externally instrumented tests, expect to get bored with manual tests- and then you can expect new bug reports.

##### The Hardware Is a Detail

* The name of the boundary between the software and the firmware is the hardware abstraction layer (HAL).
* The HAL exists for the software that sits on top of it, and its API should be tailored to that software's needs.
* The software should not be concerned that the name/value pairs are stored in flash memory, a spinning disk, the cloud, or core memory.
* What is the LED indicating? Suppose that it indicadted low battery power. At some level, the firmware could provide `Led_TurnOn(5)`, while the HAL provides `Indicate_LowBattery()`. You can see the HAL expressing services needed by the application.

#### Don't Reveal Hardware Details To The User Of The HAL

##### The Processor Is a Detail

* Sometimes vendor-supplied C compilers provide what look like global variables to give access directly to processor registers, IO ports, clock timers, IO bits, interrpt controller, and other processor functions.
* It is helpful to get access to these things easily, but realize that any of your code that uses these helpful facilities is no longer C. It won't compile for another processor, or maybe even with a different compiler for the same processor.
* You will have to limit which files are allowed to know about the C extensions.
* If that is not bad enough, one day you'll want to port your application to another processor, and you will have made that task much more difficult by not choosing portability and by not limiting what files know about ACME.
* Certainly, all of the _software_ should be processor independent, but not all the _firmware_ can be.
* It's likely your product uses this micro controller so that you can use its integrated peripherals.
* THe uppercase variables actually access micro-controller built-in peripherals. If you want to control interrupts and output characters, you must use these peripherals. Yes, this is convenient - but it-s not C.
* A clean embedded architecture would use these device access registers directly in very few places and confine them totally to the _firmware_. Anything that knows about these registers becomes _firmware_ and is consequently bout to the silicon.
* If you use a micro-controller like this, your firmware could isolate these low-level functions with some form of a _processor abstraction layer_ (PAL). Firmware above the PAL could be tested off-target, making it a little less firm.

#### The Operating System Is a Detail

* In bare-metal embedded systems, a HAL may be all you need to keeps your code from getting to addicted to the operating environment.
* You have to treat the operating system as a detail and protect against OS dependencies.
* WHat if your needs change and your RTOS does not have the capabilities that you now require? You'll have to change lots of code. These won't just be simple syntactical changes due to the new OS's API, but will likely have to adapt semantically to the new OS's different capabilities and primities.
* A clean embedded architecture isolates software from the operating system through an _operating system abstraction layer_ (OSAL). In some cases, implementing this layer might be as simple as changing the name of a function. In other cases, it might involve wrapping several functions together.
* Which would you rather do: modify a bunch of complex existing code, or write new code to a defined interface and behavior? This is not a trick question. I choose the latter.
* THe layer becomes the place where much of the duplicatio naround using an OS is isolated.

#### Programming to Interfaces and Substitutability

* THe idea of a layered architecture is build on the idea of programming to interfaces. When one module interacts with another though an interface, you can substitute one service provider for another.
* Limit the visibility of the implementation details. Expect the implementation details to change. The fewerplaces where code knows the details, the fewer places where code will have to be tracked down and modified.

#### DRY Conditional Compilation Directives

* There is a tendency to use conditional compilation to turn on and off segments of code. I recall one especially problematic case where the statement `#ifdef BOARD_V2` was mentioned several thousand times in a telecom application. 
* If I see `#ifdef BOARD_V2` once, it's not really a problem. _Six thousand times_ is an extreme problem.
* Conditional compilation indentifying the target-hardware's type is often repeated in embedded systems.
* THe hardware type would become a detail hidden under the Hardware Abstraction Layer (HAL). If the HAL provides a set of interfaces, instead of using conditional compilation, we could use the linker or some form of runtime binding to connect the software to the hardware.

### Conclusion

* Letting all code become firmware is not good for your product's long-term health. Being able to test only in the target hardware is not good for your product's long-term health.

## 30. The Database Is a Detail

### Relational Databses
### Why Are Database System So Prevalent?
### Whay If There Were No Disk?
### Details
### But What about Performance?
### Anecdote
### Conclusion

## 31. The Web Is A Detail

### The Endless Pendulum
### The Upshot
### Conclusion

## 32. Frameworks Are Details

### Framework Authors
### Asymmetric Marriage
### The Risks
### The Solution
### I Now Pronounce You...
### Conclusion

## 33. Case Study: Video Sales

### The Product
### Use Case Analysis
### Component Architecture
### Dependency Management
### Conclusion

## 34. The missing CHapter

### Package by Layer
### Package by Feature
### Ports and Adapters
### Package by Component
### The Devil Is in the Implementation Details
### Organization versus Encapsulation
### Other Decoupling Modes
### Conclusion: The Missing Advice

## Afterword
