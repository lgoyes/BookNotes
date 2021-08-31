# Applying UML and Patterns: An Introduction To Object Oriented Analysis And Design, And The Unified Process.

**Author**: Craig Larman

**Language**: English

**Start date**: Aug 23rd, 2021.

**Estimated end date**: Nov 23rd, 2021.

## Index

0. [Foreward](#0-foreward)
1. [Object Oriented Analysis and Design](#1-object-oriented-analysis-and-design)
2. [Iterative development and the unified process](#2-iterative-development-and-the-unified-process)
3. [Case Study: The nextgen POS system](#3-case-study-the-nextgen-pos-system)
4. [Inception](4-inception)
5. [Understanding requirements](#5-understanding-requirements)
6. [Use-case model: writing requirements in context](#6-use-case-model-writing-requirements-in-context)

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

* A discipline is a set of activities (and related artifacts) in one subject area.
* In UP, an artifact is the general term for any work product: code, web graphics, database schema, text document, diagrams, models and so on.
* Artifacts this book focuses on:
    1. **Business modeling** - Domain object model, and dynamic modeling of the business processes.
    2. **Requirements** - Writing use cases and identifying non-functional requirements.
    3. **Design** - Overall architecture, objects, databases, networking.

#### Disciplines and Phases

* During one iteration, work goes on in most or all disciplines. The relative effort across these disciplines change over time.

### 2.5 Process Customization and the development case

#### Optional Artifacts

* Some UP practices and principles are invariant, such as iterative and risk driven development, and continuous verification of quality. 
* All activities and artifacts are optional (except for the code). Focus on a small subset of artifacts that demonstrate high practical value.

#### The development case

* The choice of UP artifacts for a project may be written up in a short document called the "Development Case".

### 2.6 The agile UP

* A **predictive process** is one that attempts to plan and predict the activities and resouce (people) allocation in detail over a relative long time span.
    1. Defining all the requirements.
    2. Detail design
    3. Implementing

* An **adaptive process** is one that accepts change as an inevitable driver, and encourages flexible adaptation.
* The UP is not supposed to be predictive. It is supposed to be adaptive, and encourages flexible adaptation.
* There is a high-level plan (phase plan) that estimates the project end date and other major milestones. A detailed plan (iteration plan) only plans with great detail one iteration in advance.

### 2.7 The sequential "waterfall" lifecycle

### 2.8 You know you didn't understand the UP when

* inception != requirements, elaboration != design, construction != implementation
* You should not fully define and commit to an architecture before iterative programming and testing.
* It shouldn't take long to finish the requirements before programming starts.

## 3. Case Study: The nextgen POS system

### 3.1 The nextgen POS system

* A POS (Point of Sale) system is a computerized application to record sales and handle payments, typically used in a retail store.
* POS systems must still be capable of capturing sales and handling at least cash payments, even if remote services are temporarily unavailable.
* We are creating a commercial POS system that we will still sell to different clients with disparate needs in terms of business rule processing. THerefore, we will need a mechanism to provide this flexibility and customization.

### 3.2 Architectural layers and case study emphasis

* A typical object-oriented information system is designed in terms of architectural layers or sybsystems:
    1. **User interface**
    2. **Application logic and domain objects** - Software objects representing domain concepts.
    3. **Technical Services** - Database or error logging. These are application independent.
* OOA/D is most relevant for modeling the domain and data layers.

## 4. Inception

* WHat is the vision and business case for this project?
* Feaasible?
* Buy and/or build?
* Rough estimate of cost: Is it 10k-100k or in the millions?
* Should we proceed or stop?
* At the risk of over-simplication, the idea is to do just enough investigation to form a rational, justifiable opinion of the overall purpose and feasibility of the potential new system, and decide if it is worthwhile to invest in deeper exploration (the purspose of the elaboration phase).

### 4.3 What artifacts may start in inception?

* Artifacts are partially completed in this phase, will be refined in later iterations, and should not even be created unless it is deemed likely they will add real practice value.
    1. **Vision and business case** - Describes high level goals and constraints.
    2. **Use-case model** - Describes functional and non-functional requirements.
    3. **Glossary**.
    4. **Risk list and risk management plan**.
    5. **Prototypes and poof-of-concepts**.
    6. **Iteration plan for iteration 1**.
* Perhaps only 10% of the use casses are described in detail.
* Some programming work may occur in inception in order to create "proof of concept" prototypes and to clarify a few requirements.
* The point of an artifact is not the document or diagram itself, but the thinking, analysis, and proactive readiness.

## 5. Understanding requirements

* Requirement should find, communicate and remember what is really needed, in a form that clearly speaks to the clients and the developers.

### 5.1 Types of requirements

* FURPS:
    * **Functional** - Features, capabilities, security.
    * **Usability** - Human factors, help, documentation.
    * **Reliability** - Frequency of failure, recoverability, predictability.
    * **Performance** - Response times, throughput, accuracy, availability, resource usage.
    * **Supportability** - Adaptability, maintainability, internationalization, configurability.
* Functional requirements are explored and recorded in the use-case model. Other requirements can be recorded in the use cases they relate to, or in the supplementary specifications artifact.

## 6. Use-case model: writing requirements in context

* Use cases: Stories of using a system.

### 6.1 Goals and stories

* Use cases are a mechanism to help stakeholders to capture customers and end user goals (aka "needs"), in a simple and understandable way.
* It is not necessary to create layers of sophistication over the simple definition of a use-case, by simply writing the story.
* A use case can scale both up and down in terms of sophistication and formality, depending on need.

### 6.3 Use cases and adding value

* Definitions
    * An **actor** is something with behavior, such as a person (identified by role), computer system or organization. e.g a cashier.
    * A **scenario** is a sequence of actions and interactions between actors and the system under discussion. It's also called a use-case instance. It is one particular path through the use case.
    * A **use case** is a collection of related success and failure scenarios that describe actors using a system to support a goal.
* A key attitude in use case work is to focus on the question: *"how can using the system provide observable value to the user, or fulfill their goals?"* rather than merely thinking of system requirements in terms of a "laundry list" of features or functions.
* Use cases place features and functions in a goal-oriented context.

### 6.4 Use cases and functional requirements

* Use cases define a promise or contract of how a system will behave.
* Use cases are text documents, not diagrams.

### 6.5 Use case types and formats.

#### Black box use cases and system responsibilities

* This kind of use case does not describe the internal workings of the system, its components or design. The system is described as having responsibilities.
* By creating black-box use cases, it is possible to specify **what** the system must do without deciding **how** it will do it.

#### Formality types

* Degrees of formality
    1. **brief:** one-paragraph summary, describing the main success scenario.
    2. **casual:** multiple paragraphs covering various scenarios (success, and alternative).
    3. **fully dressed:** most elaborate steps and variations are written in detail, and there are supporting sections, such as preconditions and success.

### 6.6 Fully dressed example: process sale

#### The usecases.org format
#### The two column variation

