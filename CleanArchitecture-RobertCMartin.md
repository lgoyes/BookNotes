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

## 5. Object-Oriented Programming.

## 6. Functional Programming.

## 7. SRP: The Single Responsility Principle.

## 8. OCP: The Open-Closed Principle.

## 9. LSP: The Liskov Substitution Principle.