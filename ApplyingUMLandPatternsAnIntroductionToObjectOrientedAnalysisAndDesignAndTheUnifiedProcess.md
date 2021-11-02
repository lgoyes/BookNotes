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
7. [Identifying other requirements](#7-identifying-other-requirements)
8. [From inception to elaboration](#8-from-inception-to-elaboration)
9. [Use case model: drawing system sequence diagrams](#9-use-case-model-drawing-system-sequence-diagrams)
10. [Domain model: visualizing concepts](#10-domain-model-visualizing-concepts)
11. [Domain model: Adding associations](#11-domain-model-adding-associations)
12. [Domain model: adding attributes](#12-domain-model-adding-attributes)
13. [Use-case model: Adding detail with operation contracts.](#13-use-case-model-adding-detail-with-operation-contracts)
14. [From requirements to design in this iteration](#14-from-requirements-to-design-in-this-iteration)
15. [Interaction diagram notation](#15-interaction-diagram-notation)
16. [GRASP: Designing objects with responsibilities](16-grasp-designing-objects-with-responsibilities)

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

* The two-column format emphasizes the fact that there is an interaction going on between the actors and the system.

#### Personal practice

* Two-column format has a clear visual separation in the conversation.
* One-column style is more compact and easier to format.

### 6.7 Explaining the sections

#### Preface elements

* Only important to read elements should be placed before the main success scenario.

#### Important: Stakeholders and Interests list

* The use case, as the contract for behavior, captures all and only the behaviors related to satisfying the stakeholders' interests.
* By writting what the stakeholders and their interests are before writing the remainder use case, we set a reminder for the responsibilities of the system.

#### Preconditions and success guarantees (postconditions)

* **Preconditions:** must always be true before beginning a scenario in the use case. Preconditions are not tested within the use case; rather, they are assumed to be true.
* **Success guaranteed (postconditions):** must be true on successful completion of the use case.

#### Main Success scenario and steps (or basic flow)

* aka "happy path" scenario.
* Typical success path that satisfies the interests of the stakeholders without any conditions or branching.
* Three kinds of steps:
    1. Interactions between actors.
    2. Validation.
    3. State change by the system.
* Repetition idiom:
    * *"actor repeats steps x1-x2 until indicates done"*

#### Extensions (or alternate flows)

* Extension scenarios are branches from the main success scenario, and so can be notated with respect to it.
* Step "3" may have an alternate path. An extension is labeled "3a"; it first identifies the condition and then the response:
    * 3.a. invalid identifier.
        1. System signals error and rejects entry.
* An extension has two parts: the condition and the handling.
* Write the conditions as something that can be detected by the system or an actor, instead of being an interference.
* At the end of the extension handling, by default the scenario merges back with the main success scenario, unless the extension indicates otherwise.
* If a particular extension is quite complex, it can be expressed as a separate use case.
* If an extension conditioin can occur during any step, the labels *a, *b, ..., can be used.

#### Special requirements

* Non functional requirements, quality attributes, or constraints related to the specific use case, can be recorded in the "'Special requirements" section.
* Some people might prefer separating non functional requirements into the "supplementary specification" file, for content management.

#### Technology and Data variation list

* If there are technical variations in *how* something must be done, but not what, it has to be recorded.

### 6.8 Goals and scope of a use case

#### Use cases for elementary business processes

* For requirements analysis for a computer application, focus on use cases at the level of elementary business processes (EBPs).
* EBP is a task performed by one person in one place at one time, in response to a business event, which adds measurable business value and leaves the data in a consistent state. e.g. Approve credit or price order.
* It is not a single small step like "deleting a line item" or "print the document". Rather, the main success scenario is probably five or ten steps long. It doesn't take days and multiple sessions; it's a task done during one session.
* There might be some use cases that can fail the EBP test and can exist at a lower level. The EBP guideline is used to find the dominant level of use cases in requirements analysis for an application.

#### Use cases and goals

* Actors have goals and use applications to help satisfy them. An EBP-level use case is a "user goal"-level use case, to emphasize that it serves to fulfill a goal of a user of the system.
    1. Find the user goals.
    2. Define a use case for each.
* Answers to the question "what are your goals" open up the vision for new and improved solutions, focus on adding business value, and get to the heart of what the stakeholders want from the system under discussion.

#### Example: Applying the EBP guideline.

* "Prevent thef" is higher than a user goal; it might be an enterprise goal.
* "Identify myself and be validated" appears closer to the user goal level, but it does not add observable or measurable business value. As a result, it is not at the EBP level.
* "capture a sale" does fit the criteria of being an EBP.

#### Subfunction goals and use cases

* Although "login" has been eliminated as a user goal, it is a goal at a lower level, called subfunction goal.
* It is not illegal to write use cases for subfunction goal, but it is not always helpful, as it adds complexity to a use-case model; there can be hundreds of subfunction goals.
* The most common motivation to express a subfunction goal as a use case is when the subfunction is repeated in or is a precondition for multiple user-goal-level use cases.

### 6.9 Finding primary actors, goals, and use cases.

#### Step 1: Choosing the system boundary

* What is outside the boundary?
* Identify the external primary and supporting actors.

#### Step 2 and 3: Finding primary actors and goals

* In a requirements workshop, people brainstorm and generate a mixture of both actors and goals.
* Emphasize brainstorming the primary actors first.

##### Primary and Supporting actors.

* Primary actors have user goals fulfilled through using services of the system.
* Supporting actors provide services to the system under design.
* Primary actors can be other computer systems, such as "watchdog" software processes.
* Be suspicious if no primary actors are external computer systems.

##### Primary actor and user goals depends on system boundary

* From the viewpoint of just the POS system (which is the boundary), it services the goal of the cashier (and the store) to process the customer's sale.

#### Step 4: Define use cases

* Define one EBP-level use case for each user goal.
* Collapse CRUD separate goals into one CRUD use case, idiomatically called **"Manage *X*"**.

### 6.10 Congratulations: Use cases have been written, and are imperfect

* The use cases are not going to be correct. Instead of trying harder to record requirements perfect at the start, just do the best you can in the time available.

### 6.11 Write use cases in an essential UI-free style

* By investigating up the goal hierarchy, you can find a mechanism-independent goal, like "identifying myself and get authenticated". As a result, novel solutions might appear, like having a keyboard with biometric readers.

* "keep the user interface out; focus on intent".

* Essential writing style.
    * Avoid UI details and focus on othe real user intent.
    * Narrative expressed at the level of the user's intentions and system's responsibilities, rather than their concrete actions.
    * During the early requirements analysis work, keep the user interface out, focus on intent.

### 6.12 Actors

* **Actor:** Anything with behavior, including the system under discussion (SuD) itself when it calls upon the services of other systems.
    * **Primary actor:** Has user goals fulfilled through using services of the SuD.
    * **Supporting actor:** Provides a service to the SuD.
    * **Offstage actor:** Has an interest in the behavior of the use case, but is not primary or supporting.

### 6.13 Use case diagrams

* Use case diagrams and use case relationships are secondary in use case work. Use cases are text documents.

#### Diagramming suggestions

* Primary actors on the left.
* Supporting actors on the right.
* Show computer system actors with an alternate notation to human actors.
* Notice the actor box with the symbol <<actor>>. It's called a UML stereotype.

### 6.15 Use cases are not object oriented

* Use cases are a broadly applicable requirements analysis tool that can be applied to non-object-oriented projects, which increase their usefulness as a requirements method.

### 6.16 Use cases within the UP

* The work of an iteration is -in part- defined by choosing some use case scenarios, or entire use cases.
* Use-case realizations drive the design.
* Near the end of the first iteration of elaboration, there is a second requirement workshop, during which, perhaps 30% of the use cases are written in detail.
* The use-case model is started in inception, with perhaps only 10% of the use cases written in any detail. The majority are incrementally written over the iterations of the elaboration phase.

## 7. Identifying other requirements

* Documentation, packaging, supportability, licensing are captured in the supplementary specification.
* Flossary captures terms and definitions.
* Vision summarizes the vision of the project.
    * Why the project was proposed.
    * What the problems are.
    * Who the stakeholders are, what they need.

### Commentary: Supplementary specification.

* Elements of the supplementary specification could include:
    * FURPS+ requirements (functionality, usability, reliability, performance, and supportability).
    * Reports
    * Hardware and software constraints.
    * Development constraints.
    * Other design and implementation constraints.
    * Internationalization.
    * Documentation.
    * Licensing.
    * Packaging.
    * Standards.
    * Physical environment concerns.
* Constraints:
    * Must use oragle (we have a licensing arrangement with them).
* Quality attributes refer to the qualities of the system.
    1. Observable at execution (functionality, usability, reliability, performance).
    2. Not observable at execution (supportability, testability).

#### Domain rules

* Company policies, physical laws, and government laws are common domain rules, commonly called business rules.
* Rules are not application requirements. Do not record system features are rules. They describe the constraints and behaviors of how the domain works, not the application.

#### Information in Domains of Interest.

* Provide some explanation of domains related to the new software system, to provide context and deeper insight for the development team. It may contain pointers to important literature or experts, formulas, laws, or other references.

### 7.5 Commentary: Vision

##### The problem statement

* Define a terse problem statement, it will reduce the likelihood that stakeholders are trying to solve slightly different problems.

##### The key high-level goals and problems of the stakeholders

* Summarize the goals and problems at a higher level than task level use cases.

##### What are the root problems and goals?

* Some stakeholders express their goals in terms of solutions.
    * Some solutions are perceptive, because they understand the domain.
    * Some solutions do **not** address the root problems.

#### System features - functional requirements

* An alternative, a complementary way to express system functions is with features, or more specifically in this context, **system features**, which are high-level, terse statements simmarizing system functions.
* Features are things a system can do
    * The system shall do `<Feature X>`.
* System features are a mechanism to summarize in the vission contract what the system will do. This is complementary to the use cases.
* A feature is not a constraint.

##### Notation and organization

* Short high-level descriptions are important. One should be able to read the system features list quickly.
* A vision document might present a two-level hierarchy of system features, but not more. Sometimes, these second level features are essentially equivalent to use case names.
* A vision with less than 50 features is desirable.

#### Other requirements in vision.

* For other requirements, avoid their duplication or near-duplication in both the vision and supplementary specification (SS). Rather, record them only in the SS.

### 7.7 Commentary: Glossary (Data Dictionary).

* **Glossary:** list of noteworthy terms and their definitions.
* The goal is not to record all possible terms, but those that are unclear, ambiguous or which require some kind of noteworthy elaboration, such as format information or validation rules.

#### Glossary as Data Dictionary

* Glossary can include data about data (metadata).
    * Aliases
    * Description
    * Format (type, length, unit).
    * Relationships to other elements.
    * Range of values.
    * Validation rules.

#### Units

* Prices cannot be just a raw number. It must be in a Money or Currency unit that captures the notion of varying currencies.

### 7.8 Reliable specifications: an oxymoron?

* What really matters is building software that passes the acceptance tests defined by the users and stakeholders, and that meets their true goals.
* Writing a Vision and Supplementary Specification is worthwhile as an exercise in clarifying a first approximation of what is wanted.
* Treat written requirements lightly and do not rush to code.

### 7.9 Online artifacts at the project website

### 7.10 Not much UML during inception?

* Moving forward is feasible and if the project is workth serior investigation in the elaboration phase.

## 8. From inception to elaboration

* The majority of requirements are discovered and stabilized
* The major risks are mitigated or retired.

### 8.1 Checkpoint: What happened in inception?

* Some likely lactivities and artifacts in inception include
    1. Most actors, goals and use cases named.
    2. Most use cases written in brief format; 10-20% of the use cases are written in fully dressed detail.
    * Version 1 of the vision and supplementary specification.
    * Risk list.
    * High level candidate architecture. (Not a detailed architectural description, not meant to be final or correct)

### 8.2 On to elaboration

* On is not creating throw-away prototypes; rather, the code and design are production-quality portions of the final system.
* Build the core architecture, resolve the high-risk elements, deefine most requirements, and estimate the overall schedule and resources.

#### What is architectural significant in elaboration?

* Identify the separate processes, layers, packages, and subsystems, and their high-level responsabilities and interfaces. Partially implement these in order to connect them and clarify the interfaces.
* Refine intermodule local and remote interfaces like the interface to the object which will wrap access to third-party accounting systems.
* Integrating existing components.
* Early testing is required:
    * Usability tests.
    * Recovery when remote services fall.
    * High-load to remote services.

### 8.3 Planning the next iteration

* Organize requirements and iteration by risk, coverage and critially.
    * **Risk:** Technical complexity and uncertainty of effort or usability.
    * **Coverage:** All major parts of the system are at least touched on in early iterations.
    * **Critically:** Functions at high business value.
* This criteria is used to rank work across iterations. The plan is adaptive rather than speculatively frozen at the beginning of the project.

## 9. Use case model: drawing system sequence diagrams

* In the first iteration, many tasks related to establishing the environment (tools, processes, and setting) occur.
* A system sequence diagram illustrates inputs and output events related to the systems under discussion.

### 9.1 System behavior

* System behavior is a description of what a system does, without explaining how it does it (black box).

### 9.2 System sequence diagrams

* A system sequence diagram (SSD) is a picture that shows, for a particular scenario of a use case, the events that external actors generate, their order, and inter-system events. All systems are treated as a black-box; the emphasis of the diagram is events that cross the system boundary from actors to system.

* An SSD should be done for the main success scenario of the use case, and frequent or complex alternative scenarios.

### 9.3 Example of an SSD.

* System events may include parameters.
* The ":" and underline imply an instance.
* Box may enclose an iteration area.

### 9.6 System events and the system boundary

* A system event is an external event that directly stimulated the software.

### 9.7 Naming system events and operations

* System event should be expressed at the level of intent rather than in terms of the physical input medium or interface widget level.
* It also improves clarity to start the name of a system with a verb (add, enter, end, make) since it emphasizes the command orientation of these events.
* "enterItem" is better than "scan" because it captures the intent of the operation while remaining abstract and noncommittal with respect to design choices.

### 9.8 Shoing use case text

* It is sometimes desirable to show at least fragments of use case text for the scenario, to clarify or enhance the two views.

### 9.10 SSDs withing the UP

* SSDs are part of the use-case model - a visualization of the interations implied in the use cases.
* Create SSDs or only some chosen scenarios of the current iteration.

## 10. Domain model: visualizing concepts.

* A domain model is a representation of real-world conceptual classes not of software components. It is not a set of diagrams describing software classes or software objects with responsibilities.

### 10.1 Domain models.

* A domain model is a visual representation of conceptual classes or real world objects in a domain of interest.
* A domain model is illustrated with a set of class diagrams in which no operations are defined. It may show:
    1. Domain objects or conceptual classes.
    2. Associations between conceptual classes.
    3. Attributess of conceptual classes.
* The details of the notation are not important at this time.

#### Key idea: Domain model - a visual dictionary of abstraction

* The domain model may be considered a visual dictionary of the noteworthy abstractions, domain vocabulary, and information content of the domain.

#### Domain models are not models of software components

* A domain model is not a visualization of software components such as Java or C++ classes. A domain model does not have software artifacts or responsibilities or methods.

#### Conceptual classes.

* A domain model illustrates conceptual classes, which are an idea, thing or object.
    * **Symbol:** words or images representing a conceptual class.
    * **Intension:** Definition of the conceptual class.
    * **Extension:** Set of examples where the conceptual class applies.
* The concept's symbol and intension are of most practical interest.

#### Domain models and decompositioin.

* Decomposition is common strategy to deal with the system complexity by the division of the problem space into comprehensible units.

### 10.2 Conceptual class identification

* In iterative development, one incrementally builds a domain model over several iterations in the elaboration phase.
* The central task is to identify conceptual classes related to the scenarios under design.
* It is better to overspecify a domain model with lots of fine-grained conceptual classes that to underspecify it.
* Do not exclude a conceptual class simply because the requirements do not indicate any obvious need to remember information about it.
* It is valid to have conceptual classes without attributes: they have a purely behavioral role in the domain.

#### Use a conceptual class category list.

* Start the creation of a domain model by making a list of candidate conceptual classes. List all of the categories worth considering.

#### Finding conceptual classes with noun phrase identification

* Identify the nouns and noun phrases in the use cases. Be careful since not all of nouns can be mapped to classes.
* Due to the imprecision of natural language, noun phrases may represent the same conceptual classes or attributes.

### 10.3 Candidate conceptual classes for the sales domain

* There is not such thing as a "correct" list of candidate conceptual classes for the domain. It's a somewhat arbitrary collection of abstractions and domain vocabulary that the modelers consider noteworthy.

#### Report objects - include receipt in the model?

* A receipt is a record of a sale. Since item returns are not being considered, receipt are excluded.
    * A receipt is a report of a sale, showing information derived from other sources, duplicating information found elsewhere. - One reason to exclude.
    * A receipt confers the right to the bearer of the receipt to return bought items. - One reason to include it.

### 10.4 Domain Modeling Guidelines

#### How to make a domain model

1. List the candidate conceptual classes.
2. Draw them in a domain model.
3. Add some associations to record relationships.
4. Add some attributes to fulfill the information requirements.

#### On naming and modeling things: The mapmaker

* Use the existing names in the territory
    * Use the vocabulary of the domain when naming conceptual classes and attributes. For example, if developing a model for a library, name the customer a "Borrower".
* Exclude irrelevant features.
    * A domain model may exclude conceptual classes in the problem domain.
* Do not add things that are not there.
    * The domain model should exclude things **not** in the problem domain under consideration.

#### A common mistake in identifying conceptual classes.

* If we do not think of an attribute `X` as a number or text in the real world, `X` is probably a conceptual class, not an attribute.
* If in doubt, make it a separate concept. Attributes should be fairly rare in a domain model.

### 10.5 Resolving similar conceptual classes - Register vs "POST"

* **Terminal:** any endpoint device in a system, such as a client PC, a wireless networked PDA, and so forth.
* A register is a thing that records sales and payments.
* A domain model is not absolutely correct or wrong, but more or less useful; it is a tool of communication.

### 10.6 Modeling the unreal world.

* There are some domains that are unrealted to the real world (e.g. telecommunications). Create the domain model for these domains, using a high level of abstraction.

### 10.7 Specification or description conceptual classes

* If description, price and itemID are duplicated for every "Item" instance of same product, there will be some duplicated data, and the model implementation will be space inefficient.

#### The need for specification or description conceptual classes

* To solve the "Item" problem, what is needed is a `ProductSpeicification` (or `ItemSpecification`, `ProductDescription`, ...) conceptual class that records information about items. `Xspecification` describes `X`.

#### Descriptions of Services

* Descriptions of services or service plans are commonly needed. e.g mobile company selling packages such as "bronze", "gold" and so forth. The description of the plan is required.

### 10.8 UML Notation, models and methods: multiple perspectives

* The same diagramming notation may be used for three perspectives and types of models:
    1. Essential or conceptual perspective: Describe things in the domain of interest.
    2. Specification perspective: Describe software abstractions or components with specifications and interfaces.
    3. Implementation perspective: Describe particular technology and language.

#### Superimposing terminology: UML vs methods.

* UML boxes in Domain Model are domain concepts or conceptual classes.
* UML boxes in Design Model are design classes, offering a specification or implementation perspective.

### 10.9 Lowering the representation gap

* Choosing names that reflect the domain vocabulary (sale) enhances quick comprehension and provides a clue as to what to expect from the chunk of code in a `Sale` software class.
* The closer one-to-one mapping between the domain vocabulary and our sofware vocabulary and its chunking reduces the representational gap. This speeds comprehension of existing code and suggests "natural" ways to extend the code in ways that similarly correspond to the domain, or appeal to our intuitions of the domain.

## 11. Domain model: Adding associations

### 11.1 Associations

* An association is a relationship between instances of some types that indicate some meaningful connection.

#### Criteria for Useful Associations

* What objects do we need to have some memory of a relationship? Some `SalesLineItem` are associated with a `Sale` instance. We need this association to reconstruct the `Sale`.

### 11.2 The UML association notation

* The UML association is inherently bidirectional: from instances of either class, logical traversal to the other is possible.
* THe ends of an association may contain a multiplicity indicating the numerical relationship between the instances.
* There can be a "reading direction arrow" indicating the direction to read the association; it does not indicate direction of visibility or navigation.

### 11.5 Roles

* Each end of an association is called a role. Roles may have:
    * Name
    * Navigability
    * Multiplicity

#### Multiplicity

* Multiplicity defines how many instances of a class A can be associated with one instance of a class B, at a particular moment, rather than over a span of time.

### 11.6 How detailed should associations be?

* Finding conceptual classes is more important than finding associations.

### 11.7 Naming associations

* Since an association represents a classifier of links between instances; in the UML, classifiers should start with a capital letter.
* The association name must be based on `<TypeName>-VerbPhrase-<AnotherTypeName>`.

### 11.8 Multiple associations between two types.

* Two types may have multiple associations between them. Different associations should be shown separately.

### 11.9 Associations and implementation

* The presence of an association in a conceptual view of a domain model does not require their implementation.
* The domain model does not need to be updated with insights revealed during implementation work. Avoid making or updating any documentation or model unless there is a concrete justificatioin for future use.

### 11.10 Nextgen POS domain model association

* We should add those associations which the requirements suggest or imply a need to remember, or which otherwise are strongly suggeted in our perception of the problem domain.

#### Associations for need-to-know vs. comprehension

* Deleting some associations that are not strictly demanded on a need-to-know basis can create a model that misses the point - it does not communicate key ideas and relationships.
* Emphasize need-to-know assocations, but add choice comprehension-only associations to enrich critical understanding of the domain.

## 12. Domain model: adding attributes

### 12.1 Attributes

* An attribute is a logical data value of an object.
* Attributes are shown in the second compartment of the class box. Their type may optionally be shown.

### 12.3 Valid attribute types

#### Keep attributes simple

* Most simple attribute types are primitive data types, such as boolean, date, dumber, string, time. Other common types include: Color, enumerated types, geometrics (Point, Rectangle).
* An attribute should not be a complex domain concept, such as an `Airport` or a `Sale`. A more useful way to express the relationship with a complex concept is with an association.

#### Conceptual vs Implementation perspective: What about attributes in code?

* The associations between objects expressed in the domain model will often be implemented as attributes that reference other complex software objects.

#### Data types

* Attributes should generally be data types.
* Data type is a UML term that implies a set of values for which unique identity is not meaningful.
* Two instances of the number 5 might not habe a meaningful distinction; while two instances of a `Person` whose names are both "Jill Smith" might represent two different people with the same name.
* All primitive types (number, string) are UML data types, but not all data types are primites.

### 12.4 Non-primite data type classes

* What may initially be considered a primite data type can be represented as a non-primite class if:
    1. It is composed of several sections.
    2. There are operations usually associated with it, such as parsing or validation.
    3. It has other attributes.
    4. It is a quantity with a unit.
    5. It is an abstraction of one or more types with some of these qualities.

### 12.5 Design creep: No attributes as foreign keys

* Do not relate conceptual classes in the domain model by means of a foreign key attribute (e.g. `currentRegisterNumber`). Relate types with an association, not with an attribute.

### 12.6 Modeling attribute quantities as units.

* Most numeric quantities should not be represented as plain numbers. Consider price or velocity. These are quantities with associated units, and it is common to require knowing the unit, and to support conversion.

### 12.8 Multiplicity from SalesLineItem to Item

* An individual `SalesLineItem` can be associated with more than one instance of an `Item`. The quantity can be calculated from the actual multiplicity value of the relationship, so it may be characterized as a _derived attribute_ - one that may be derived from other information. In UML, a derived attribute is indicated with a `"/"` symbol (e.g. `/quantity`).

## 13. Use-case model: Adding detail with operation contracts.

### 13.1 Contracts

* Contracts describe detailed system behavior in terms of a state change to objects in the domain model, after a system operation has executed.

#### System operations and the system interface

* System operation: Operation that the system as black box offers in its public interface to handle incoming system events.
* Contracts may be defined for system operations.

### 13.3 Contract sections.

* **Operation**: Name of the operation, and parameters.
* **Cross referene**: use cases this operation can occur within.
* **Preconditions**: 
    * Noteworthy assumptions about the state of the system or objects in the domain model before executing the operation.
    * These preconditions will not be tested within the login of this operation.
* **Postconditions**: State of the objects in the domain model after completion of the operations.

### 13.4 Postconditions.

* Postconditions describe changes in the state of objects in the Domain model.
* Domain model changes include "instance creation/deletion", "associations broken or formed" and "attribute modification".
* The important quality is to be declarative and state-change oriented rather than action-oriented, since post-conditions are declarations about state or outcomes rather than a description of actions to execute, or a design of a solution.

#### Post conditions are related to the domain model

* What instances can be created? Those from the domain model
* What associations can be formed? Those from the domain model

#### An advantage of postconditions: analytical detail

* One can focus analytically on _what_ must happen, rather than _how_ it is to be accomplished.

#### The spirit of postconditions: the stage and curatin

* Express postconditions in the past tense, to emphasize they are declarations about a state change in the past.

#### If constracts are used, how complete should postconditions be?

* Treat the creation of the postconditions as an initial best guess, with the understanding that the contracts will not be completed.

### 13.6 Writing contracts leads to domain model updates.

* During the creation of the contracts some new conceptual classes, attributes or associations, might be discovered and should be added to the domain model.

### 13.7 When are contracts useful? Contracts vs use cases?

* Contracts will not be practically motivated very often, so if a team is making contracts for every system operation of every use case, it is a warning that either the use cases are poorly done, there is not enough ongoing collaboration or access to a subject matter expert, or the team is doing to much unnecessary documentation.

### 13.8 Guidelines: Contracts.

* Advice:
    1. Identify system operations
    2. For system operations that are complex and not clear in the use case, construct a contract.
    3. To describe postconditions use the following categories:
        1. Instance creation and deletion.
        2. Attribute modification.
        3. Associations formed and broken.

* Remember to establish memory beween the existing objects or those newly created by defining the forming of an association. It is not enough to create the `SalesLineItem` instance, but it has to be associated to `Sale`.

### 13.11 Contracts, operations and the UML

* Operation (UML): Specification of a transformation or query that an object may be called to execute.
* Method (UML): Implementation of an operation.

### 13.12 Operation Contracts within the UP

* Operation specification contracts for the system level are part of the Use-Case Model

#### Phases

* **Inception**: Contrcts are not motivated during inception.
* **Elaboration**: When most use cases are written, only write contracts for the most complex and subtle system operations.

## 14. From requirements to design in this iteration

### 14.1 Iteratively do the right thing, do the thing right

* Requirements and object analysis has focused on learning to do the right thing: understanding some of the outstanding goals, and constraints.

* Do the thing right: skillfully design solutions to satisfy the requirements.

* It is natural and healthy to discover and change some requirements during the design and implementation work of the **early** iterations.

### 14.3 On the object design

* Interaction diagrams to illustrate how objects collaborate to fulfill the requirements.
* Interaction diagrams and class diagrams summarize the definition of the software classes and interfaces to be implemented.
* There artifacts are part of the design model.

## 15. Interaction diagram notation

### 15.1 Sequence and collaboration diagrams.

* "Interaction diagram" is a generalization of "collaboration diagrams" and "sequence diagrams".
    * **Collaboration diagrams**: Illustrate object interactions in a graph in which objects can be placed anywhere.
    * **Sequence diagrams**: Illustrate interactions in a kind of fence format, in which each new object is added to the right.
* Sequence diagrams clearly show sequence or time ordering of messages, but it consumes horizontal space.

### 15.2 Example collaboration diagram: makePayment

1. The message `makePayment` is sent to an instance of a `Register`. The sender is not identified.
2. The `Register` instance sends the `makePayment` message to a `Sale` instance.
3. The `Sale` instance creates an instance of a `Payment`.

### 15.3 Example sequence diagram: makePayment

* Activation box shows the focus of control.
* The instance box appears right when the instance is created.

### 15.4 Interaction diagrams are valuable
* If the length of the timeboxed iteration is two weeks, perhaps a half or full day near the start of the iteration should be spent on the creation of interaction diagrams and class diagrams, before proceeding with programming.
    * The design might be modified during programming, but it will provide a thoughtful start point during programming.

### 15.5 Common Interaction Diagram Notation

#### Illustrating classes and instances

* **Class:** represented by the name capitalized (`Sale`).
* **Instance:** the name underlined with a `:` preceding (<u>`:Sale`</u>)
* **Named instance:** name of instance followed by instance (<u>`s1 :Sale`</u>)

### 15.6 Basic collaboration diagram notation

#### Links

* A link is a connection path between two objects; it indicates some form of navigation and visibility between objects is possible.

#### Messages

* A message is represented with a message expression and a small arrow indicating the direction of the message. A sequence number is added to show the sequencial order of messages.

#### Messages to "self".

* A message can be sent from an object to itself, illustrated by a link to itself, with messages flowing along the link.

#### Creation of instances

* Use a message named "create" to create an instance.

#### Message number sequencing

* Order of messages is illustrated with sequence numbers.
* The first message is not numbered.
* Nested messages have a number appended to them.

#### Conditional messages

* Conditional message: A sequence number, with a conditional clause in square brackets. The message is sent if the clause evaluates to true.

#### Mutually exlusive conditional paths.

* It is necessary to modify the sequence expresions with a conditioinal path letter.

#### Iteration or looping

* Define the iteration index, and the range in square brackets, after a `*`, e.g. `*[i:1..N]`.

#### Iteration over a collection

* The terms multiobject, in UML, is used to denote a set of instances.
    * Double box indicates a multiobject (collection).
    * Having a `*` in the message, and a multiobject together, imply iteration over the multiobject.

#### Messages to a class object

* To use static methods, send the message to a class box whose name is not underlined.

### 15.7 Basic sequence diagram notation

#### Links

* Sequence diagrams do not have links

#### Messages

* Each message is represented by a line between objects. The time ordering is organized from top to bottom.

#### Focus of control and activation boxes

* An activation box represents an operation on the call stack.

#### Illustrating returns

* The return from a message is a dashed open-arrowed line at the end of the activation box.

#### Creation of instances

* The newly created objects are placed at their creation "height".

#### Object lifelines and object destruction

* Object lifelines - The vertical dashed lines underneath the objects.
* If object destruction is explicit (as in C++, which does not have garbage collector), the `<<destroy>>` stereotyped message with the large `X` and short lifeline indicates explicit object destruction.

#### Conditional message

* A message with a square brackets condition.

#### Mutually exclusive conditional message.

* An angled messaged line emerging from a common point with a condition.

#### Iteration for a single message

* A message line from one instance to another, with the iteration notation before the message expression (e.g. `*[i:1..N]: message()`).

#### Iteration for a series of messages

* Wrap all of the messages that should be iterated over, with a box and write the iteration notation at the bottom border of the box. (e.g `*[i:1..N]`).

#### Iteration over a collection (multiobject)

* Have a "*" at the start of the message, and let the destination of the message be a multiobject (two boxes).

#### Messages to class objects

* Static method calls are shown by not underlining the name of the classifier.

## 16. GRASP: Designing objects with responsibilities

GRASP: General Reponsibility Assignment Software Patterns

### 16.1 Responsibilities and methods

* A responsibility is a contract or obligation of a classifier
* Responsibilities are of the following two types:
    1. Doing:
        * Doing something itself, such as creating an object or doing a calculation.
        * Initiating action in other objects.
        * Controlling and coordinating activities in other objects.
    2. Knowing:
        * Knowing about private encapsulated data.
        * Knowing about related objects.
        * Knowing about things it can derive or calculate.

* Methods are implemented to fulfuill responsibilities. Responsibilities are implemented using methods that either act alone or collaborate with other methods and objects.

### 16.3 Patterns.

* A pattern is a named description of a problem and a solution that can be applied to new contexts, with advice on how to apply it in novel situations and discussion of its trade-offs.

* A pattern is a vehicle for naming, presenting, learning, and remembering useful software engineering principles.

#### Repeating patterns

* Patterns attempt to codify existing tried-and-true knowledge, idioms, and principles; the more honed and widely used, the better.

#### Patterns have names

* Patterns have suggesting names
    1. It supports chunking and incorporating that concept into our understanding and memory.
    2. It facilitates communication.

### 16.6 Information expert (or Expert)

* **Solution:** Assign a responsibility to the information expert - The class that has the information necessary to fulfill the responsibility.
* **Problem:** What is a general principle of assigning responsibilities to objects.
* **Advice:** Start assigning responsibilities by clearly stating the responsibility.
* **Example:** 
    * Who should be responsible for knowing the grand total of a sale? By information expert, we should look for that class of objects that has the information needed to determine the total.
    * Giving the responsibility of knowing the total is expressed with the method named `getTotal`.
* Low representational gap: the software design of objects appeals to our concepts of how the real domain is organized.
* **Discussion:**
    * Objects do things related to the information they have.
    * The fulfillment of a responsibility often requires information that is spread across different classes of objects. This implies that there are many "partial" information experts who collaborate in the task.
* **Contraindications:**
    * Some times, _Expert_ is undesirable, because of problems in couple and cohesion.
    * Keep application logic in one place (such as domain software objects), keep database logic in another place (such as separate persistence services subsystems), rather than intermingling different system concerns in the same component.
* **Benefits:**
    * Information encapsulation is maintained, since objects use their own information to fulfill tasks.
    * Behavior is distributed across the classes that have the information encouraging more cohesive "lightweight" class definitions.

### 16.7 Creator

* **Solution:** Assign class B the responsibility to create an instance of class A, if one or more of the following is true:
    1. B aggregates A objects.
    2. B contains A objects.
    3. B records instances of A objects.
    4. B has the initializing data that will be passed to A when it is created (thus B is an expert with respect of creating A).
* **Problem:** Who should be responsible for creating a new instance of some class?
* **Example:**
    * Since a `Sale` contains (aggregates) many `SalesLineItem` objects, the creatos pattern suggests that `Sale` is a good candidate to have a responsibility of creating `SalesLineItem` instances.
* **Discussion:**
    * Aggregation involves thing that are in a strong Whole-Part of Assembly-Part relationship, such as `Body` aggregates `Leg` or `Paragraph` aggregates `Sentence`.
    * Sometimes a creator is found by looking fot he class that has the initializing data that will be passed in during creation.
* **Contraindications:**
    * When the creation requires significant complexity, such as using recycled instances for performance reasons, conditionally creating an instance from one of a family of similar classes based upon some external property value, and so forth; it is advisable to delegate creation to a helper class called a `Factory` rather than use the class suggested by _Creator_.

### 16.9 Low coupling

* **Solution:** Assign a responsibility so that coupling remains low.
* **Problem:**
    * How to support low dependency, low change impact, and increase reuse?
    * _Coupling_ is a measure of how strongly one element is connected to, has knowlegde of, or relies on other elements.
    * A class with high coupling relies on many other classes and may suffer from the following problems:
        1. Changes in related classes force local changes.
        2. Harder to understand in isolation.
        3. Harder to reuse because it requires the additional presence of the classes on which it is dependent.

* **Example**
    * `Register` can create a `Payment`, and then could send an `addPayment` message to the `Sale`, passing along the new `Payment` as a parameter.
    * We will assume the `Sale` must eventually be coupled to knowledge of a `Payment`. If the `Sale` does the creation of a `Payment`, it will not increase the coupling, while the previous design (`Register` creating a `Payment`) adds coupling of `Register` to `Payment`.
    * The level of coupling alone can't be considered in isolation from other principles such as _Expert_ and _High Cohesion_.

* **Discussion:**
    * Common forms of couping from `X` to `Y` include:
        1. `X` has an attribute that refers to `Y`.
        2. `X` calls on services of `Y`.
        3. `X` has a method that references an instance of `Y`.
        4. `X` is a direct or indirect subclass of `Y`.
        5. `Y` is an interface, which `X` implements.
    * Low coupling supports the design of classes that are more independent, which reduces the impact of change.
    * A subclass is strongly coupled to its superclass.
    * Classes that are inherently very generic in nature, and with a high probability of reuse, should have especially low coupling.
    * If low coupling is taken to excess, it yields a poor design because it leads to a few incohesive, bloated and complex active objects that do all the work with many very passive zero-coupled objects that act as simple data repositories.

* **Contraindications:**
    * High coupling to stable elements (such as the java libraries) is seldom a problem.
    * If is not high coupling per se that is the problem; it is high coupling to elements that are unstable in some dimension, such as their interface, implementation or mere presence.

### 16.9 High cohesion

* **Solution:** Assign a responsibility so that cohesion remains high.
* **Problem:**
    * How to keep complexity manageable?
    * _Cohesion_ is a measure of how strongly related and focused the responsibilities of an element are. An element with highly related responsibilities, and which does not do a tremendous amount of work, has high cohesion.
    * A class with low cohesion does too much work, and suffer from the following problems:
        1. Hard to comprehend.
        2. Hard to reuse.
        3. Hard to maintain.
        4. Delicate; constantly effected by change.
* **Example:**
    * If we continue to make the `Register` class responsible for doing some or most of the work related to more and more system operations, it will become increasingly burdered with tasks and become incohesive.
    * The level of cohesion must be considered along with other principles such as _Expert_ and _Low coupling_.
* **Discussion:**
    * High functional cohesion exists when the elements of a component all work together to provide some well-bounded behavior.
    * Degrees of functional cohesion.
        1. **Very low cohesion** _[A class is responsible for many things in very different areas]_ A class `RBD-RPC` is repsonsible for interacting with relational databases and for handling remote procedure calls.
        2. **Low cohesion** _[A class has responsibility for a complex task in one area]_ A class `RBD` is responsible for interacting with relational database. There is a lot of methods. The class should split into a family of lightweight classes sharing the work.
        3. **High cohesion** _[A class has moderate responsibilities in one area and collaborate with other classes to fulfill tasks]_ A class `RDB` is responsible for interacting with relational database. It interacts with a dozen other classes related to `RDB` access in order to retrieve and save objects.
        4. **Moderate cohesion** [A class has light weight and sole responbilities in a few different areas that are logically related to the class concept, but not to each other] A class `Company` must (a) know its employees and (b) know its finantial information. Both are logically related to the concept of a company, but not stringly related to each other.
    * A class with high cohesion has a relatively small number of methods, with highly related functionality, and does not do too much work. It collaborates with other objects to share the effort if the task is large.
    * Modularity is the property of a system that has been decompsed into a set of cohesive and loosely coupled modules.
    * Modularity is achieved by designing each method with a clear, single purpose, and grouping a related set of concerns into a class.
* **Contraindications**

