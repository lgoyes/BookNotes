# Clean Architecture. A Craftsman's Guide to Software Structure and Design

**Author**: Robert C. Martin
With contributions by James Grenning and Simon Brown

**Language**: English

**Start date**: May 21st, 2020.

**End date (estimated)**: Jun 21st, 2020.

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

### A Couple of Sad Stories

### FitNesse

### Which LInes Do You Draw, and When Do You Draw Them?

### What About Input and Output?

### Plugin Architecture

### The plugin Argument

### Conclusion

