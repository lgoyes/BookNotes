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