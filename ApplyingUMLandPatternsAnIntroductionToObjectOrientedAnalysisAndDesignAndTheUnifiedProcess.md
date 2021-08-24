# Applying UML and Patterns: An Introduction To Object Oriented Analysis And Design, And The Unified Process.

**Author**: Craig Larman

**Language**: English

**Start date**: Aug 23rd, 2021.

**Estimated end date**: Nov 23rd, 2021.

## Index

0. [Foreward](#0-foreward)
1. [Object Oriented Analysis and Design](#1-object-oriented-analysis-and-design)
2. [Iterative development and the unified process](#2-iterative-development-and-the-unified-process)

## 0. Foreward

* Programming: Analysis and design, defining how to solve the problem, what to program, capturing this design in ways that are easy to communicate, to review, to implement, and to evolve is what lies at the core of this book.
* Patterns give a name and form to abstract heuristics, rules and best practices of object oriented techniques.

## 1. Object Oriented Analysis and Design

### 1.1 Applying UML and Patterns in OOA/D

* Owning a hammer doesn't make one an architect. Knowing an object-oriented language is a necessary but insufficient first step to create object systems.
* Patterns: Named problem-solution formulas that codify exemplary design principles.

### 1.2 Assigning Responsibilities

* A critical, fundamental ability in OOA/D is to skillfully assign responsibilities to software components.
    * It strongly influences the robustness, maintainability and reusability.
    * On a real project, a developer might not have the opportunity to perform any other analysis or design activities - the "rush to code" development process. Yet even in this situation, assigning responsibilities is inevitable.

### 1.3 What is analysis and design

* Analysis emphasizes an investigation of the problem and requirements, rather than a solution.
* Design emphasizes a conceptual solution that fulfills the requirements, rather that its implementation. Ultimately, designs can be implemented.
* Do the right thing (analysis), and do the thing right (design).

### 1.4 What is Object-Oriented Analysis and Design?

* During OOA, there is an emphasis on finding and describing the objects -or concepts- in the problem domain.
* During OOD, there is an emphasis on defining software objects and how they collaborate to fulfill the requirements.
* During object-oriented programming, design objects are implemented.

### 1.5 An example

* A dice game, in which a player rolls two die. If the total is seven, they win; otherwise, they lose.

#### Define Use Cases

* Use cases are not object-oriented artifacts - They are simply written stories

#### Define a Domain Model

* A decomposition of the domain involves an identification of the concepts, attributes and associations that are considered noteworthy. The result is ilustrated in a set of diagrams that show domain concepts or objects.
* A domain model is not a description o software objects, it is a visualization of concepts in the real-world domain.

#### Define Interaction Diagrams.

* A common notation to illustrate software objects and their collaborations is the interaction diagram. It show the flow of messages between software objects, and thus the invocation of methods.
* Software object designs and programs do take some inspiration from real-world domains, but they are not direct models or simulations of the real world.

#### Define Design Class Diagrams

* An inspection of the interaction diagram leads to a partial design class.
* In contrast to the domain model, this diagram does not illustrate real-world concepts; rather, it shows software classes.

### 1.6 The UML

* The Unified Modeling Language (UML) is a language for specifying, visualizing, constructing, and documenting the artifacts of software systems, as well as for business modeling and other non-software systems.

## 2. Iterative development and the unified process

* Software development process: An approach to building, deploying, and possibly maintaining software.

### 2.1. The most important UP idea: Iterative development

* Development is organized into a series of short, fixed-length mini-projects, called interations; the outcome of each is a tested, integrated and executable system. Each iteration includes its own requirements analysis, design, implementation, and testing activities.
* The reasult of each iteration is an executable but incomplete system; it is not ready for deliver into production. The system may not be eligible for production deployment until after many iterations; for example, 10 or 15 iterations.
* The output of an iteration is not a throw-away prototype. Rather, the output is a production-grade subset of the final system.
* An iteration may occasionally revisit existing software and improve it.

#### Embracing change: feedback and adaption

* UP balances the need to agree upon and stabilize a set of requirements, with the reality of changing requirements, as stakeholders clarify their vision or the marketplace changes.
* "Yes...buts" are a skillful way to make progress and discover what is of real value to the stakeholders, instead of being a sign of failure.
* Activities such as load testing will prove if the partial design is on the right path, or if in the next iteration, a change in the core architecture is required.

#### Iteration length and timeboxing

* The OPrecommends an iteration length between two and six weeks.
    * Long iterations increase project risk.
    * ess than two weeks and it is difficult to complete sufficient work to get meaningful throughput and feedback.

### 2.3 The UP phases and schedule-oriented terms.

* There are 4 phases in a UP project.
    1. **Inception** - approximate vision, vague estimates.
    2. **Elaboration** - Refined vision, iterative implementation of the core architecture, resolution of high risks, identification of most requirements and scopes, and more realistic estimates.
    3. **Construction** - Iterative implementation of the remaining lower risk and easier elements.
    4. **Transition** - Beta tests, deployments.
* Inception is not a requirements phase; it's a phase where just enough investigation is done to support a decision to continue or stop.

### 2.4 The OP Disciplines (was workflows)