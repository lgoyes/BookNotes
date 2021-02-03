# Clean Agile: Back to Basics

**Author**: Robert Martin

**Language**: English

**Start date**: Jan 22nd, 2021.

**End date**: Feb 22st, 2021.

## 1. Introduction to Agile

* In febreuary 2001, a group of 17 software experts gathered in Snowbird, Utah, to create a manifesto that introduced a more effective, lighter-weight, approach to develop software.
* Once a movement becomes popular, the name of that movement gets blurred through missunderstanding and usurpation.

### History of Agile

* The idea of choosing small intermediate goals and measuring the progress, after each is just too intuitive, and too human, to be considered any kind of a revolution.
* In "scientific management", managers use scientific techniques to ascertain the best procedures for accomplishing a goal and then direct all subordinates to follow their plan to the letter. There is a big up-front planning followed by careful detailed implementation.
* Pro-Agile took short reactive steps that were measured and refined in order to stagger, in a direct random walk, toward a good outcome.
* Scientific management deferred action until a thoroung analysis and resulting detailed plan had been created.
* Pre-agile worked well for projects that enjoyed a low cost of chnage, and solved partially defined projects with informally specified goals.
* Scientific management worked best for projects that suffered a high cost of change and solve very well-defined problems with extremely specific goals.
* Waterfall was a logical descendant of scientific management. It was all about doing a thorough analysis, making a detailed plan, and then executing the plan to completion.
* Waterfall began to dominate the way we thought.
* It dominated, but it didn't work. For the next thirty years, we tried to get that analysis and design right. But everytime we thought we had it, it slipped through our fingers during the implementation phase. All our months of careful planning were made irrelevant by the inveitable mod dash.
* How could we thoroughly analyzing the problem, carefully designing a solution, and then implmenting that design, fail so spectacularly over and over again? It was inconceivable that the problem lay in the strategy. It had to lie with us.
* Agile manifesto:
    * **Individuals and interactions** over processes and tools.
    * **Working software** over comprehensive documentation.
    * **Customer collaboration** over contract negotiation.
    * **Responding to change** over following a plan.

### Agile Overview

* how do you manage a sotware projects?
    * Hope and prayer
    * Those who don't have faith, often fall back on motivational techniques such as enforcing dates with whips, chains, boiling oil, and pictures of people climbing rocks and seagulls flying over the ocean.
* These approaches almost universally lead to the characteristic symptoms of software management:
    * Development teams who are always late despite working too much overtime.
    * Teams who produce products of poor quality that don't come close to meeting the needs of the customer.

### The Iron Cross

* The fundamental physics of software projects, contraints all projects to obey an unssailable trade off called the Iron Cross of project management: Good, Fast, Cheap and Done: Pick any three you like. You can't have the fourth.

* A good manager manages the coefficients on these attributes rather than demanding that all those coefficients are 100%.

### Charts on the wall

* Agile provides data. An agile development team produces just the kinds of data that managers need in order to make good decisions.
* The velocity graph shows how much the development teams has gotten done every week.
* The burndown chart shows how many points remain until the next major millestone. Notice how it declines each week. Note that it declines less than the number of points in the velocity chart. This is because there is a constant background of new requirements and issues being discovered during development.
* note that you can find glitches on the burn-down chart. They might have been due to the addition of some new features or some other major changes to the requirements. Or it might have been the result of developers re-estimating the remaining work.
* Agile development is first and foremost a feedback-driven approach.
* Without data, the project cannot bee managed.
* Make sure that managers know how fast the team is moving and how much the team has left to accomplish. And present this information in a transparent, public and obvious fashion.

### The first think you know

* The first thing you know about a project is *The Date*. Once *The Date* is chosen, the date is frozen. There's no point trying to regotiate the date, because the date was chosen for good business reasons.
* Whatever the reason, it's a good gusiness reason, and it's not going to change just because some developers think they might not be able to make it.
* At the same time, the requirements are wildly in flux and can never be frozen. The requirements are constantly being re-evaluated and re-thought.
* This is the world of the software development team. It's a world in which dates are frozen and requirements are continuosly changing.

### The analysis phase

* We should be sizing the project and doing basic feasibility and human resources projections. We should be ensuring that the schedule is achievable.

### The design phase

* Software design is where we split the project up into modules and design the interfaces between those modules. It's also where we consider how many teams we need and what the connections between those teams ought to be. In general, we are expected to refine the schedule in order to produce a realistically acievable implementation plan.

### The implementation phase

* It's completly unambiguos what we are doing during the Implementation phase. We are coding. And we'd better be coding like mad banshees too, because we've already blown four months of this project.
* Meanwhile, the requirements are still changing on us.

### The death march phase

* Customers aree angry. Stakeholders are angry. The pressure mounts. Overtime soars. People quit. It's hell.
* We promise ourselves that we will never do another project like this. Next time we'll do it right.

### A better way

* An agile project begins with analysis, but it's an analysis that never ends.
* You set the deadline. Remember, the first thing you know is *The Date*. We subdivide that time into regular increments called iterations or sprints.

* The size of an iteration is typicallly one or two weeks. I prefer one week because too much can go wrong in two weeks.

### Iteration Zero

* The first iteration is used to generate a short list of featuures called stories.
* Iteration zero is also used to set up the development environment, estimate the stories and lay out the initial plan.
* The plan is simply a tentative allocation of stories to the first few iterations.
* Iteration zero is used by developers and architecturs to conjure up an initial tentative design for the system based on the tentative list of stories.
* Every iteration in the project will have some analysis and design and implementation in it.

### Agile Produces Data

* Iteration one begins with an estimate of how many stories will be completed. The odds that the team will finish all the stories that they planned to finish is zero. That's because software is not a reliably estimable process.
* There is no way to know how complicated a task is going to be until the task if finished.
* At the end of the iteration, some fraction of the stories will be done. This gives us our first measurement of how much can be completed in an iteration. This is real data.
* We can use real data to adjust our original plan and calculate a new date for the project.

### Hope versus management

* Agile is not about goinog fast. Agile is about knowing, as early as possible, just how screwed we are.
* Agile produces data. Managers use that data to drive the project to the best possible outcome.
* The best possible outcome is not often the originally desired outcome.

### Managing the Iron Cross

* Given the data produced by the project, it's time for the managers of that project to determine just how good, how fast, how cheap, and how done the project should be.
* Managers do this by making chanes to the scope, the schedule, the staff and the quality.

#### Changing the Schedule

* The date was chosen for good business reasons. A delay often means that the business is going to take a significant hit of some kind.
* There are times when the business simply choosed the date for convenience. Remember, it's still early.

#### Adding staff

* Adding manpower to a late project makes it later.
* The teams is working along at a certain productivity. The new staff is added. Productivity plummets for a few weeks as the new people suck the life out of the old people. Then, hopefully, the new people start to get smart enough to actually contribute.
* Another factor is that adding staff is expensive.

#### Decreasing Quality

* Producing crap does not make you go faster, it makes you go slower. There is no such thing as quick and dirty.
* If we want to shorten our schedule, the only option is to increase quality.

#### Changing scope

* Some of the planned features don't really need to be done by *The Date*. Let's ask the stakeholders.
* Stakeholders will want all the features. Although they have the moral high ground in this argument, programmers have the data. And in any rational organization, the data will win.
* If the organization is rational, then the stakeholders eventually will scrutinize the plan, and identify the features that they don't absolutely need.
* So the plan is adjusted and some features are delayed.

#### Business value order

* Stake-holders will find a feature that we have already implemented, but was not realy needed.
* At the beginning of each iteration we are going to ask the stake holders which features to implement.

#### Here endeth the Overview

* Agile is a process wherein a project in subdivided into iterations. The output of each iteration is measured and used to continuosly evaluate the scope schedule. Features are implemented in the order of business value so that most valuable things are impmlemented first. Quality is kept as high as possible. The schedule is primarily managed by manipulating scope.

### Circle of Life

* All other agile processes are a subset of or a variation of XP
* The circle of life is subdivided into three rings:
    1. The software development team communicates with the business, and how they manage the project.
        * **The planning game:** Break doen a project into features, stories and tasks. Guidance for estimation, prioritization and scheduling of those features, stories and tasks.
        * **Small releases:** Work in bite-size chunks.
        * **Acceptance tests:** Provide the definition of "done" for features.
        * **Whole Team:** A software development team is composed of many different functions
    2. Practices by which the development team manages and communicates with itself.
        * **Sustainable pace**
        * **Collective ownership:** Do not divide the project into knowledge silos.
        * **Continuous integration:** Close the feedback loop frequently enough.
        * **Metaphor:** Creates the vocabulary to communicate about the system.
    3. Practices that constrain the programmers to ensure the highest technical quality
        * **Paring:** Sharing knowledge.
        * **Simple Design:** Prevent wasted effort.
        * **Refatoring:** Continual improvement and refinement.
        * **Test Driven Development:**

## 2. The reasons for agile

### Professionalism

* High commitment to discipline over ceremony.
* To do Agile right, you had to work in pairs, write tests first, refactor, and commit to simple designs. You had to work in short cycles, producing executable output in each.
* We in this industry need to increase our professionalism. We fail too often. We ship too much crap. We accept to many defects. We make terrible trade-offs.

#### Software is everything

* Nowadays, in our society, virtually nothing of significance can be done without interacting with a software system.

#### We rule the world

* Our society has become utterly and wholly dependent on software.
* And who writes all that software? We, programmers, rule the world.
* How much of that software do you think is properly tested? How many programmers can say that they have a test suite that proves, with a high degree of certainty, that the sofware they have written works?
* Our actions are putting lives and fortunes at stake.

#### The disaster

* When some poor programmer is going to do some dumb thing and kill ten thousand people in a single moment of carelessness, the politicians of the world will rise up in righteous indignation (as they should) and point their fingers squarely at us.

### Reasonable Expectations

* The behaviours below are what any good chief technology officer (CTO) should expect from their staff.

#### We will not ship shit!

* Any system that requires its users to think like programmers in order to enter data in the expected format is crap.
* Managers, customers, and users expect that we will provide systems for them that are high in quality and low in defect.
* Note that Agile's emphasis on Testing, Refactoring, Simple Design and Customer feedback is the obvious remedy for shipping bad code.

#### Continuous Techincal Readiness

* The last thing that customers and managers expect is that we, programmers, will create artificial delays to shipping the system.
* As long as there are features that are half done, or half tested, or half documented, the system cannot be deployed
* The system should be technically deployable at the end of every iteratioin. The work completed in the interation includes all the coding, all the testing, all the documentation, and all the stabilization for the stories implemented in that iteration.
* If the system is tecnically ready to deploy at the end of every iteration then deployment is a business decision, not a technical decision.

#### Stable Productivity

* Customers and managers don't expect software teams to slow down with time. Rather, they expect that a feature similar to one that took two weeks at the start of the project will take two weeks a year later. They expect productivity to be stable over time.
* Developers should expect no less. By continuosly keeping the architecture, design, and code as clean as possible, they can keep their productivity high, and prevent the otherwise inevitable spiral into low productivity and redesign.

#### Inexpensive Adaptability

* If a change to the requirements breaks your architecture, then your architecture sucks.
* Our jobs depend on our ability to accept and engineer changing requirements and to make those changes relatively inexpensive.
* Customer, users and managers expect that software systems will be easy to change, and that the cost of such changes will be small and proportionate.

#### Continuous improvement

* The design and architecture of a software system should get better with time.
* THe fact that we developers expect our systems to get messier and fragile is the most irresponsible attitude possible.
* Users, customers and managers expect that early problems will fade away and that the system will get better and better with time.

#### Fearless competence

* Imagine you are looking at some old code on your screen. Your first thought is: "This is ugly code, I should clean it". Your next thought is: "I'm not touching it!" Because you know if you touch it, you will break it.
* You fear the code, and this fear forces you to behave incompetently.
* Customers, users and managers expect fearless competency. They expect that if you see something wrong or dirty, you will fix and clean it.
* If you follow the agile practice of TDD with discipline and determination, you will be fearlessly competent.

#### QA Should find nothing

* QA should fin no faults with the system. When QA runs their tests, they should come back saying that everything works as required.
* QA should wonder why they are stuck at the back end of the process checking systems that always work.

#### Test automation

* The QA manager is holding this document (the table of contents for a manual test plan) out to me, asking me which half of these tests he shouldn't run. - I told him that no matter how he decided to cut the tests he wouldn't know if half of his system was working.
* Manual tests are expensive and so are always a target for reduction.
* Every test that can feasibly be automated must be automated. Manual testing should be limited to those things that cannot be automatically validated and to the creative discipline of "Exploratory Testing".

#### We cover for each other

* If Bob gets sick, Jill steps in to finish Bob's tasks. This means that Jill had better know what Bob was working on oand where Bob keeps all the source files, and scripts, etc.
* I expect that the members of each software team will cover for each other. I expect that each individual member of a software team makes sure that there is someone who can cover him if he goes down.

#### Hones estimates

* You may not know how long it will take to build the "Login" page, but you might be able to tell me that the "Change Password" page will take about half the time as "Login". Relative estimates like that are immensely valuable.
* Or, instead of estimating in relative terms, you may be able to give me a range of probabilities.

#### You need to say "No"

* I expect you to say "no" when no such solution can be found.

#### Continuous aggressive learning

* I expect you to keep learning. Our industry changes quickly. We must be able to change with it. So learn, learn, learn!
* You must find ways to continue learning without the company's help.

##### Mentoring

* I expect you to teach.

### The Bill of Rights

* THe goal of Agile was to heal the divide between business and development

#### Customer Bill of Rights

* You have the right to be informed of schedule, and estimate changes in time, to choose how to reduce the scope to meet a required date. You can cancel at any time and be left with a useful working system reflecting investment to date.

#### Developer Bill of Right

* You have the right to know what is needed with clear declarations of priority.
* You have the right to make and update your own estimates.

#### Customers

* BUsiness needs a plan. Of couse, that plan must include schedule and cost. And, of course, that plan should be as accurate and precise as practical.
* We, developers, have to make sure that our plan, estimates, and schedules properly describe the level of our uncertainty and define the means by which that uncertainty can be mitigated.
* The business has the right to expect that the developers will work on the most important things at any given time, and that each iteration will provide them the maximum possible usable business value.
* The business has the right to see incremental progress. THey have the right to specify the criteria for accepting that progress.
* The customer has the right to change the requirements
* The customers do not have the right to demand conformance to the schedule. Their right is limited to managing the schedule by changing the scope.

#### Developers

* Developers have the right to know what is needed with clear declarations of priority
    * This right only applies within the context of an interation. Outside of an iteration, requirements and priorities qill shift and change. But within an iteration, the developers have the right to consider them immutable.
* The business has no right to tell developers to cut corners or do low-quality work. The business has no right to force developers to run their professional reputations or violate their professional ethics.
* Developers have the right to ask for an receive help from peers, managers and customers.
* Estimates are intelligent guesses. They are guesses that get better with time. Estimates are never commitments.
* Professionals accept work, they are not assigned work. A professional developer has every right to say "no" to a particular task or job.
    * The accepting developer becomes responsible for the quality and execution of the task for continually updating the estimate so that the schedule can be managed, for communicating status to the whole team, and for asking for help when help is needed.

## 3. BUsiness Practices

### Planning

* How do you estimate a project? You break it down, recursively, into smaller pieces, and then estimate those pieces.
* An estimate is a guess, we want some idea of how long the project will take without actually building the project. We want the cost of estimation to be low.
* Estimates should be as accurate as possible, but only as precise as necessary to keep the cost of the estimation low.

#### Trivariate Analysis

* Estimates composed of three numbers: best-case, nominal-case, and worst-case. These numbers are confident estimates. The `worst-case` number is the amount of time within which you feel 95% confident that the task will be completed. The `nominal-case` has only 50% and `best-case` only 5%.
* As powerful as trivariate analysis is for long-term estimation of a whole project, this technique is too imprecise for the day-to-day management that we need within a project.

#### Stories and Points

* A user story is an abbreviated description of a feature of the system, told from the point of view of a user.
* We want to delay the specification of the details as long as possible, right up to the point where the store is developed. So leave the story in abbreviated form as a promise for a future conversation.

#### ATM Stories

* Writing the stories for an automated teller machine (ATM), what are these stories? Withdrawal, Deposit, Transfer, Login and Logout.
* Resist the urge to capture all the details discussed in each story.
* The stories had so much detail on them, that they could not be estimated. They could not be scheduled. They were useless. There was so much effort invested into each story card that they could not be discarded.
* What makes a story manageable, schedulable and estimable is the temporary lack of detail.

#### Estimating the Stories

* We pick a story from the batch that we consider to be of average complexity.
* We choose a number of points for the story. The Login story will cost 3 points of development effort. Login is an average story, and so we give it an average cost of 3, if stories range in cost from 1 to 6.
* Login is our `Golden Story`. It is the standard against which all other stories will be compared.
* What is the development effort measuring? Hours, days, weeks? They are a unit of estimated effort, not real time.
* Effort estimates are vague, fuzzy, imprecise things that do not relate directly to real time.
    * There is a beautiful thing about vague, fuzzy numbers: The Law of Large numbers. When taken in quantity, the fuzziness integrates out.

#### Planning Iteration One