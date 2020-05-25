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

## 8. OCP: The Open-Closed Principle.

## 9. LSP: The Liskov Substitution Principle.