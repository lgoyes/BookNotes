# Clean Agile: Back to Basics

**Author**: Robert Martin

**Language**: English

**Start date**: Jan 22nd, 2021.

**End date**: Feb 17th, 2021.

## Index

1. [Introduction to Agile](#1-introduction-to-agile)
2. [The reasons for agile](#2-the-reasons-for-agile)
3. [Business Practices](#3-business-practices)
4. [Team Practices](#4-team-practices)
5. [Technical Practices](#5-technical-practices)
    1. [Test Driven Development](#test-driven-development)
    2. [Refactoring](#refactoring)
    3. [Simple Design](#simple-design)
    4. [Pair programming](#pair-programming)
6. [Becoming Agile](#6-becoming-agile)
    1. [Agile Values](#agile-values)
    2. [The menagerie](#the-menagerie)
    3. [Transformation](#transformation)
    4. [Coaching](#coaching)
    5. [Agile tools](#agile-tools)
    6. [Coaching - An alternative view](#coaching---an-alternative-view)
7. [Craftsmanship](7-craftsmanship)
    1. [The Agile Hangover](#the-agile-hangover)
    2. [Expectation Mismatch](#expectation-mismatch)
    3. [Moving apart](#moving-apart)
    4. [Ideology vs Methodology](#ideology-vs-methodology)

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

* The iteratioin begins with the Iteration Planning Meeting (IPM). THe IPM for a two-week iteration should require about a half a day.
* Stakeholders will have previously read the estimated stories and sort them in the order of business value. To do this, they need to know how many story points the programmers think they can complete. This number is called the velocity.
* It's important to realize that velocity is not a commitment.

#### Return of Investment

* The stories that are valuable but cheap will be done right away. Those that are valuable but expensive will be done later. Those that are naither valuable nor expensive might got done one day. Those that are not valuable but are expensive will never get done.

#### The midpoint check

* At the midpoint of the iteration, many stories should be done. What should the point total of those stories add up to? - 15.
* At the midpoint review meeting, the stakeholds remove enough stories from the plan to reduce the remaining points to 10.
* By the end of the iteration, there is a demo. It turns out that only 18 points out of 20 were completed. Has this iteration failed? No! **Iterations do not fail** The purpose of an iteration is to generate data for managers. It would be nice if the iteration also generated working code, but even when it doesn't, it has still generated data.

#### Yesterday's Weather.

* How many points should the stakeholders plan for the next iteration? The number of points that we could do on the last iteration. That is yesterday's weather.
* The best predictor of the progress of an iteration is the previous iteration.

#### The End of the Project

* As each iteration completes, the completed velocity is added to the velocity chart, so that everyone can see how fast the team is going.
* The project is not over when all the stories are implemented. The project is over when there are no more stories in the deck worth implementing.

#### Stories

* User stories are simple statements that we use as reminders of features. They have to follow the INVEST principles.
* I: Independent
    * User stories are independt of each other. They do not need to be implemented in any particular order.
    * We try to separate the stories so that there is as little dependence as possible, allowing us to implement the stories in the order of business value.
* N: Negotiable
    * Details are negotiable between the developers and the business.
    * Developers might recommend simpler designs that could be much less expensive to develop.
* V: Valuable
    * The story must have clear and quantifiable value to the business.
    * Refactoring is **never** a story. Architecture is **never** a story.
* E: Estimable
    * A user story must be concrete enough to allow the developers to estimate it.
* S: Small
    * A story should not be bigger than one or two developers can implement it in a single iteration.
* T: Testable
    * Business should be able to articulate tests that will prove that the story has been completed.
    * Even though I don't know all the details of the login story, I know that it is testable because Login is a concrete operation.

#### Story Estimation

* Flying Fingers
    * Every one hold up the number of fingers that correspond to the number of points they think the story deserves.
    * If there is substantial disagreement between fingers, the developers discuss the reasons why, and then repeat the process until agreement is reached.
* Planning Poker
    * Zero (0) means "too trivial to estimate". You may wich to merge a few of them into a bigger story.
    * Infinite representes "too long to estimate", and therefore the story should be split.
    * Question mark (?) means you simply don't know.

#### Splitting, Merging and Spiking

* Merging stories: Clip the cards together.
* Splitting stories: You need to maintain INVEST. Consider _Login_, we could create _Login with No Password_, _Login with Single Password Attempt_, _Allow Multiple Password Attempts_ and _Forgot Password_.
* A spike is a story for estimating another story. We have to develop a long but very thin slice through all the layers of the system.
* Let's say there's a story that you cannot estimate. So you write a new story called "Estimate X". Now you oestimate that story, which is easier to estimate.

#### Managing the iteration

* Focus on driving the stories to completion
* As soon as the planning meeting ends, the programmers should choose the stories for which they will each individually be responsible.

#### QA and Acceptance Tests

* If QA has not already begun to write the automated acceptance tests, they should start as soon as the IPM end. We don't want completed stories waiting for acceptance tests to be written.
* We expect acceptance tests to all be written before the midpoint of the iteration.
* Be sure that the programmers working on a story are not also writing the acceptance tests for that story.
* After the midpoint, if all the acceptance tests are done, QA should be working on the tests for the next iteration.
* The definition of "done" is this: acceptance tests pass.
* When the acceptance tests for a story pass, that story is done. However, when a programmer says that a story is 90% done, we really don't know how close to done it is. So, the only thing we ever want to report on our velocity chart is stories that have passed their acceptance tests.

#### The demo

* The demo should include showing that all the accepted tests run, and all the unit tests. It should also show off the newly added features.

#### Velocity

* The burn down slope predicts the date for the next major milestone. The velocity slope tells us how well the team is being managed.
* The velocity slope will be pretty noise, but after the first few iterations, the noise should reduce to a level that allows an average velocity to become apparent.

##### Rising Velocity

* If we see a positive slope, it probably means that the project manager is putting pressure on the team to go faster. As that pressure builds, the team will unconsciuosly shift the value of their estimates to make it appear that they are going faster.
* Velocity is a measurement, not an objective. It's control theory 101: don't put pressure on the thing you are measuring.

#### Falling velocity

* A consistent negative slope might be because of the quality of the coee. The team is likely not refactoring enough. One reason that teams fail to refactor enough is that they don't write unit tests, so they fear that refactoring will break something that used to work.

#### Small Releases

* If you are releasing every six months, try every three months, then try every month, then try every week.
* To do this, the organization will need to break the coupling between release and deployment. The term "release" means that the software is technically ready to be deployed. The decision to deploy debomes solelly a business decision.

### Acceptance Tests

* Requirements should be specified by the business.
* A specification is, by its very nature, a test.
* The test has to be automated
* Acceptance Tests: The requirements of the system should be written as automated tests

#### Tools and methodologies

* In an attept to make it easier for business people to write automated tests, programmers have written some tools, like Cucumber, to create a formalism that attempts to separate the technical and business sides of an automated test.
* The business can write the business side of the automated tests, and the programmers can write the glue code that binds those tests to the system being tested.

##### Behavior-Driven Development

* Businesses can derive great value by specifying their systems in a formal scenario-based language like _Given-When-Then_, regardless of whether they actually automate those requirements as tests.

#### The practice

* The business writes format tests describing the behaviour of each user story, and developers automate those tests.

#### Business Analysts and QA

* Business Analysts specify the happy paths
* QA's role is to write the unhappy paths.
    * QA are deeply technical people who can foresee all the strange and bizarre things that users are going to do to the system.

#### QA

* QA are not testers on the back end of the project. They are specifiers, operating at the front end of the project.
* QA provide early input to the development team to prevent errors and omissions, instead of supplying late feedback.
* QA must inject quality into the start of each iteration, rather than measuring lack of compliance at the end.

#### Losing the Tests at the End

* Under pressure, QA simply bypasses all the regression tests. QA only tests the new features.

#### The QA Disease

* If QA is finding lots of defects, they are clearly doing their job well. Thus, defects are considered a good thing.
* Who else benefits from defects? Developers who need to meet the schedule deadlines.

#### Developers are the testers

* QA writes the acceptance tests for the stories in an iteration. But QA does not run those tests. It's the programmer'sjob to verify that the system passes the tests.

#### Continuous Build

* The programmers will automate that process by setting up a Continuos Build server. this server will simply run all the tests in the system, including unit tests and all acceptance tests, every thime any programmer checks in a module.

### Whole Team

* The customer is a metaphor for someone who understand the needs of the users.
* In scrum, the customer is called the Product Owner. This is the person who chooses stories, sets priorities, and provides immediate feedback.
* When the Whole Team (managers, testers, technical writers, programmers, etc) sits together in the same space, magic can happen. Some accidental synergy occurs.

#### Co-Location

#### Co-location alternatives

* The ability to send megabits of source-code around the world is not quite the same as having a team of co-located customers and programmers

#### Working Remotely from Home

* No matter how electronically connected the team is, they are still not together in the same space. This puts the people working from home at a distinct disadvantage.
* A team that is mostly co-located but has a member or two who work from home, one or two days per week, will likely not notice any significant impediment.

## 4. Team Practices.

### Metaphor

* In order for the team to communicate effectively, they require a constrained and disciplineed vocabulary of terms and concepts.
* A metaphor relates a project to something else about which the teams have common knowledge.
* We called those buffers garbage trucks, running back and forth between the producer of the garbage and the dum. We were saying that our customers were garbage merchants.
* A metaphor can provide a vocabulary that allows the team to communicate efficiently. On the other hand, some metaphor are silly to the points of being offensive to the customer.

#### Domain-Driven Design

* Ubiquitous Language is the name that should be given to the Metaphor practice.
* What the team needs is a model of the problem domain, which is described by a vocabulary that everyone (programmers, QA, customers, managers, users) agrees on.
* Data Disctionaries: simple representation of the data manipulated by the application and the process that manipulated that data.
* The ubiquitous language is used in all parts of the project. The business uses it. The developers use it. QA uses it. Devops use it. It is a thread of consistency that interconnects the entire project during every phase of its lifecycle.

### Sustainable Pace

#### Overtime

* All-nighters became pretty rate.
* As I matured, I realized that my worst technical mistakes were made during those periods of frenetic late-night energy. I realizeed that those mistakes were huge impediments that I had to constantly work around during my truly wakeful hours.

#### Marathon

* A software project is a marathon, not a sprint. In order to win, you must pace yourself. If you run at full speed, you'll run out of energy long before you cross the finish line.

#### Dedication

* Working overtime is not a way to show your dedication to your employer. What is should is that you are a bad planner, that you agree to deadlines to which you shouldn't agree, that you make promises you shouldn't make, that you are a manipulable laborer and not a professional.

#### Sleep

* The most precious ingredient in the life of a programmer is sufficient sleep.

### Collective Ownership

* No one owns the code in an Agile project. The code is owned by the team as a whole. Any member of the team can check out and improve any module in the project at any time. The team owns the code collectively.
* Collective ownership does not mean that you cannot specialize. As systems grow in complexity, specialization becomes an absolute necessity. There are systems that simply cannot be understood in both entirety and detail. However, even as you specialize, you must also generalize. Divide your work between your specialty and other areas of the code. Maintain your ability to work outside of your specialty.
* Each member gains a better understanding of the boundaries between modules and of the overall way that the system works. This drastically improves the ability of the team to communicate and make decisions.

#### The X Files

* The developers writing the stacker code were politically impotent, but if a printer developer spoke in a meeting, everyone else listed closely. Because of this political division, no one shared their code.

### Continuous Integration

* The practice of Continuous Integration meant that developers checked in their source code changes and merged them with the main line every "couple of hours". All unit tests and acceptance tests kept passing. No feature branches remained unintegrated. Any changes that should not be active when deployed were dealt with by using toggles.
* Continuous Integration only works if you integrate continuously.

#### Then came continuous build

* Continuous build tools (like Jenkins) allow the time between integrations to shrink to a minimum.

#### The continuous Build Discipline

* The continuous build should never break. Each programmer runs all the acceptance tests and all unit tests before they check in their code. So if the build breaks, something very strange has happened.

#### Stop the Presses

* A broken build is a "stop the press" event. All the programmers will stop what they are doing and rally around the build to get it passing again.

#### The cost of cheating

* Removing the failing tests with the promise that you will go back and fix them later is a suicidal move. A broken system gets deployed.

### Standup meetings

* Standup meetings:
    * are optional.
    * Can be less often than daily.
    * Should take about 10 min.
* Team members stand in a circle and answer three questions:
    1. what did I do since the last meeting?
    2. What will I do until the next meeting?
    3. What is in my way?
* No discussion. No posturing. No deep explations. No complaints. THen the meeting is over and everyone returns to work.

#### Pigs and chickens?

* Only developers should speak at the standup. Managers and other folks may listen in but should not interject.

#### Shout-out

* just a quick acknowledgement of someone who helped you:
    * Whom do you what to thank?

## 5. Technical Practices

* Without TDD, refactoring, simple design, and pair programming, Agile becomes an ineffective flaccid shell of what it was inteded to be.

### Test Driven Development

#### Double-entry Bookkeeping

* Every required behavior is entered twice: once as a test, and then again as production code that makes the test pass. The two entries are complementary. When executed together, the two entries produce a zero result: zero test failed.
* Programmers enter every behaviour one at a time. This allows them to catch errors quickly.

#### The three rules of TDD

1. Write the test that fails, before writing the production code.
2. Do not write more of a test than is sufficient to fail.
3. Do not write more production code than is sufficient to pass the currently failing test.

#### Debugging

* If everything worked a minute ago, then almost any failure you encounter will be less than a minute old. Debugging a feature that was added in the last minute is often trivial. Indeed, using a debugger to find the problem is probably overkill.

#### Documentation

* The tests you end up writing become the code examples for the whole system. If you want to know how to call an API funtion, there are tests that call that function every way it can be called.
* The tests are a form of documentation that describe the system being tested. This documentation is written in a language that the programmers know fluently. It is utterly unambiguous, it is so formal it executes, and it cannot get out of sync with the application code. The tests are the perfect kind of documentation of programmers: code.

#### Fun

* Every time you make a test pass, it's a small success. It doesn't feel like busy work - it feels like getting stuff working.

#### Completeness

* When you write after-the-fact tests, the only information that the passing tests give you is that nothing tested is broken. The incompleteness of the test suite leaves you with no options. However, if you follow TDD, then every line of production code was written in order to make a test pass. The test suite is very complete. When it passes, you can deploy.
* The goal is to create a suite of automated testes that tells us that it is safe to deploy the system.
* Coverage in the high 90s is likely all that is required for the deployment decision.

#### Design

* When you write the test first, you cannot write a function that is hard to test. How do you keep functions easy to test? You decouple them. Indeed, testability is just a synonym for decoupling.
* The whole system will be testable; therefore, the whole system will be decoupled.

#### Courage

* TDD provides a number of powerful benefits: less debuggin, good low-level ldocumentation, fun, completeness and decoupling.
* The driving reason for practicing TDD is courage.
* When you have a complete test suite, you lose your fear of changing the code. You lose your fear of cleaning the code. So, you will clean the code. You will keep the system neat and orderly. You will keep the design of the system intact.

### Refactoring

* Refactoring is the pracatice of improving the structure of the code without altering the behaviour, as defined by the tests. In other words, we make changes to the names, the classes, the functions, and the expressions without breaking any of the tests.
* To fearlessly refactor the code, we need a test suite that give us very high confidence that we aren't breaking anything.
* The kinds of changes made during refactoring range from trivial cosmetics to deep restructurings.

#### Red/Green/Refactor

* Red/green/refactor cycle
    1. We create a test that fails
    2. Then we make the test pass
    3. Then we clean up the code

* Writing code that works and writing code that is clean are two separate dimensions of programming so we first focus on getting the code working by whatever messy means. Then, once working, with tests passing, we clean up the mess we made.
* Refactoring is a continuous process, not one that is performed on a schedule bases. We make a very small mess, over one or two minutes and then, we clean up that small mess.
* The word "refactoring" should never appear on a schedule.

#### Bigger Refactorings

* Sometimes the requirements change in such a way that you realize the current design and architecture of the system is suboptimal, and you need to make a significant change.
* Such changes are made within the red/green/refactor cycle. We do not create a project specifically to change the design. We do not reserve time in the schedule for such large refactoring. Instead, we migrate the code one small step at a time, while continuing to add new features during the normal Agile cycle.

### Simple Design

* Simple Design is the practice of writing only the coee that is required with a structure that keeps it simplest, smalles and most expressive.
* Rules of simple design
    1. Pass all the tests
    2. Reveal the intent
    3. Remove duplication
    4. Decrease elements
* The goal of simple design is to keep the design weight of the code as small as practical.

#### Design weight

* The more complex the design, the greater the cognitive load praced on the programmers. That cognitive load is Design weight. The greater the weight of that design, the more time and effort are required for the programmers to understand and manipulate the system.
* Complex requirements can be simplified by empmloying a more complex design. Often the tradeoff is favorable.

### Pair programming

* Pairing is optional: no one should be forced to pair.
* Pairing is intermittent: There are many reasons to code alone.

#### What is Pairing?

* Pairing is the act of two people working together on a single programming problem. The pair may work together at the same workstation, or they may work on two connected workstations so long as they see and manipulate the same code.
* One programmer may be the driver and the other, the navigator. The driver has the keyboard and mouse; the navigator takes a longer view and makes recommendations.
* Another role option is for one programmer to write a test, and the other to make it pass and write the test for the first programmer to pass.
* Most often, however, there are no roles at all.
* The goal is to spread and exchange knowledge, not concentrate it.

#### Why pair?

* Pairing is the best way, by far, to share knowledge between team members and prevent knowledge silos from forming. It is the best way to make sure that nobody on the team is indispensable.

#### What about the cost?

* The direct cost of pairing might be about 15%
* A team that pairs 505 of the time would suffer something less than 8% in productivity.
* If the practice of pairing replaces code reviews, then there is likely no reduction in productivity at all.

#### Management

* Generally, managers are please to see programmers collaborating, and working together. It creates the impression that work is being done.

## 6. Becoming Agile

### Agile Values

#### Courage

* The members of an Agile team are not so focused upon political safety that they sacrifice quality and opportunity.
* The belief that quality and discipline increase speed is a courageous belief because it will constantly be challenged by powerful but naivve folks who are in a hurry.

#### Communication

* We value direct and frequent communication that crosses channels.
* A team that sits together and communicates frequently can work miracles.

#### Feedback

* Determine when things are going wrong early enough to correct

#### Simplicity

* When you recognize a problem but silently allow it to pass to someone else, you are engaging in indirection.
* SImplicity is directness - directness in the code, and directness in communicatioin and behaviour.
* On the team, most of the time, you want to be as direct as possible.

### The menagerie

* The symptoms of "Flaccid Scrum" are a slow decline from high productivity in the early days of a project to very low productivity as the project wears on. The reason for this loss of productivity is the corruption and degradation of the code itself.
* Pick on of the agile methods (XP, scrum, etc). Ensure that you address all the disciplines in the circle of lie. Get the team to agree. Then, begin. Remember courage, communication, feedback, and simplicity, and regularly adjust the disciplines and behaviors.

### Transformation

* The transformation from non-Agile to Agile is a transition in values. The values of Agile development include risk-taking, rapid feedback, intense, high-bandwidth communication beween people that ignores barriers and command structures.
* Agile values are diametricaly opposed to the values of large organizations who have invested heavily in middle-management structures that value safety, consistency, comand-and-control, and plan execution.

#### Faking it

* Some software development teams quietly use Agile values to drive their development, while also conforming to the rigors imposed upon them by middle managements.
* So long as middle management is satisfied that their procedures and standards are being followed, they may leave the development team to their own devices.

#### Success in smaller organizations

* Some medium-sized organizations have no middle management, and the values of the executives and developers are strongly aligned.

#### Individual Success and migration

* Sometimes only certain individuals within an organization adopt the Agile values. Individuals who make this transition do not fare well within organizations or teams who do not.

#### Creating Agile Organizations

* We will see larger companies create new divisions that use Agile for their software development.
* Agile consulting companies will be used more by larger organizations that have been unable to transform their existing development staff.

### Coaching

* Agile trainer: Their goal is to inculcate the Agile values and teach the Agile disciplines. Each team should require no more than one or two weeks of training.
* AGile coaches: members of the teams who defend the process within the team. In the heat of development, developers may be tempted to go off process (stop pairing, stop refactoring, ignoring failures in the continuous build).

#### SCRUM masters

* The role of the coach is conflated with the role of the project manager.

#### Certification

* The training that accompanies an Agile certification program is often worthwhile, however, the training should be for everyone on the team.

#### Agile in the large

* Agile is about small software teams
* There is no agile for large teams. Organizing large teams is a matter of organizing them into small teams.
* The problem of large teams is the problem of getting many diverse kinds of teams to cooperate.
* Agile was a necessary innovation for organizing small software teams. But, once organized, those teams fit into the structure that large organizations have used for millennia.

### Agile tools

* We carpenters master their hand tools before moving on to tools that are more sophisticated. They learn the limits of the hand tools so that they know when to reach for a power tool.

#### Software tools

* Software developers must master some hand tools:
    1. At least one programming language
    2. An integrated development environment
    3. Various data formats (JSON, SML, etc) and markup languages
    4. .Command-line and script-base interaction with the operating system.
    5. Source repository tools.
    6. Continuous integration / build tools (Jenkins)
    7. Deployment tools (Docker)
    8. Communication tools (slack).
    9. Testing tools.

#### What makes for an effective tool?

* The tool landscape changes rapidly because we are always learning more effective ways to accomplish our goals.
* A good tool should feel comfortable in you hands and not make you queasy with the dread of having to use it.
* The tool has become transparent.
* A small fraction of Git's capabilities (20%) gets you well over 80% of the day-to-day needs you'll have for source management.
* The tool is exapted (used effectively in ways the originators hadn't intended).
* Great tools do the following:
    * Help people accomplish their objectives.
    * Can be learned "well enough" quickly.
    * Become transparent to users
    * Allow adaptation and exaptation
    * Are affordable.

#### Physical Agile Tools

* Agilists are known for using whiteboards, tape, index cards, markers, and various sizes of sticky notes for visual management of their work.
* Every tool has its limitations. One key limitation of physical tools is that they are not very effective for distributed teams, only for people withing visual range. The phpysical tools also don't automatically maintain history.

#### Pressure to automate

* There is a growing interest in automated software tools. Some reasons for thir are:
    1. Software tools provide a good way to help ensure data is captured in a consistent form.
    2. With consistently captured data, you cana readily cerive professional looking reports, charts and graphs.
    3. Providng history and safe storage is easy.
    4. You can instantly share the information with everyone.
    5. You can have a completely distributed team collaborate in real time.
* One you own a tool, the path of least resistance is to do whatever the tool provides regardless of whether it meets the team's needs.
* Your team should establish the pattern of work compatible with their specific context first and then consider using tools that support their workflow.

#### Agile Lifecycle Management (ALM) systems for the not-poor.

* Great tools can be learned "well enough" quickly.
    * ALMs tend to be complicateed, usually demanding up-front-training.
* Great tools become transparent to users.
    * We constantly see team members watching the designated driver trying to figure out the tool.
* Great tools allow adaptation and exaptation.
    * A five-second turn around for low-tech tools turn into a five-day or five-week delay with an ALM.
* Great tools are affordable.
    * Licensing fees can be very expensive.
* Great tools help people accomplish their objectives.
    * ALM tools rarely work the way your team does.
* Some ALM tools become a weapon used to shame programmers into working harder and longer.
* Where teams would gather for their morning standup, they now gather to update their ALM.

### Coaching - An alternative view

#### The many paths to Agile

#### From Process Expert to Agile Expert

* Agile is an algorithm for finding the highest value-producing features in the market and then turning them into revenue faster.

#### The need for agile coaching

* Becoming agile involves revisiting entrenched beliefs, culture, process, thinking, and ways of working.
* The key to lasting change is to find problems or opportunities that people are aware of and have a desire to invest in and help them achieve their goals, offering expertise only as requested and needed. Everything else will fail.

#### Putting the Coach into Agile Coach

* People get a tremendous amount of value out of the process of coaching itself.
* ICAgile's Certified Agile Coach (ICP-ACC).

#### Going Beyond the ICP-ACC

* Coaching skills of active listening, emotional intelligence, presence, providing clear and direct feedback, asking open-ended and non-leading questions, and remaining neutral.

#### Coaching tools

* Powerful questioning. Asking questions that evoke discovery, insight, commitment, or action.
* There is a growing body of coaching tools. Many of them can be found at `tastycupcakes.org`, `retromat.org` and `liberatingstructure.com`.

#### Progressional Coaching Skills are not enough

* An agile coach may switch to a mode of offering potentially useful expertise.
* If the team is interested, the Agile coach then provides their expertise, teaching, and mentoring the team with the intention of moving back to pure coaching as soon as the team has mastered the new knowledge.
* Areas of expertise that Agile coaches draw from:
    1. Agile frameworks
    2. Agile transformations
    3. Agile product management
    4. Agile technical practices.
    5. Facilitation
    6. Coaching

#### Coaching in a multi-team environment

* Most agile coaching happens within the context of multiple teams, sometimes tens or hundred of teams. And it frequently starts with resources (people) siloed and allocated to three or more unrelated projects.

#### Agile in the large

* Just as it is best to grow your software based on frequent customer interaction, the only process changes that will stick are those that are directly connected to what people affected understand and desire based on their unique circumstances.

#### Using Agile and Coaching to Become Agile

* Rather than implementing one of these recipes (the Agile Manifesto) consider using Agile and coaching to discover and implement a custom recipe that is tailor-made to your specific circumstances.

#### Growing your agile adoption

* Rather than adopting scrum, kanban, xp, or one of the scaling frameworks, consider adopting one of the practices from the list below;
    1. The practices of Kanban: making the work visible (via a card wall), limiting work in progress, pulling work through the system.
    2. The practices of SCRUM and XP: short daily team meetings, a product owner, a process facilitator, retrospectives, a cross-functional team, user stories, small releases, refactoring, TDD and pair programming.
    3. Align team events. Align iteration start and stop times as well as iteration length, from multiple teams.
    4. Escalation trees: Escalate impediments immediately via a well defined escalation path.
    5. Regular interteam interaction. REgular interaction between the Scrum master, product owner and team members who are working together toward a common deliverable.
    6. Portfolio kanban - set work in progress limits to ensure that the organization is focused on the highest-value work at all times. Having fewer projects at a time also vastly simplifies multiteam coordination.
    7. Minimum Viable Increments - What is the shortest path to producing the highest value in the shortest time.

#### Going big by focusing on the small

* Some of the practics associated with team-level Agile that do double duty as enablers of multiteam coordination:
    * The SOLID principles - Dramatically reduce dependencies
    * Small, valuable user stories - Small stories limit the scope of dependencies
    * Small, frequent releases - "The increment must be in useable condition regardless of whether the Product Owner decides to release it".
    * Continuous integration - Integration across the entire product after every checkin.
    * Simple Design - When coordinating the work of multiple teams, monolithic, centralized, preplanned architectures create massive dependencies between teams.

#### The future of AGile coaching

* The scum alliance's advanced certified scrum master (ACSM)

## 7. Craftsmanship

### The Agile Hangover

* Managers willing to push developers to work faster are using the full transparency of the process to micromanage them.
* Roadmaps and milestones are being defined by managers and forced upon development teams - developers can estimate the work, but they are pushed hard to fit their estimates into the imposed milestones.
* Failing to deliver all story points in a sprint means developers must work harder in the next sprint to make up for the delay.
* Focusing on the highest-priority item in the backlog and getting it done as fast as possible results in a long sequence of tactical work and accumulation of technical debt.
* Monoliths become the norm.
* Managers blame developers for not moving quickly. Developers blame managers for not allowing them to do the technical and strategic work needed. Product owners do not consider themselves as part of the team, and do not share the responsibility when things go wrong.

### Expectation Mismatch

* Development teams should deliver production-ready software at the end of each iteration.
* Rarely is there a buget for up-skilling developers during Agile transformations. Business doesn't even know developers have to learn new practices.
* Developers need strategic thinking. They need a modular design that supports parallel work. They need to continuously embrace change while making sure the system can always be deployed to production. They need to build software that is both flexible and robust.

### Moving apart

* Most modern agile coaches do not have enough tecnical skills to coach developers on technical practices, and they rarely talk about engineering.
* Developers started seeing Agile coaches as another layer of management people telling them what to do instead of helping them to get better at what they do.

#### Software Craftsmanship

* We have come to value:
    * Not only working software, but also well-crafted software.
    * Not only responding to change, but also steadily adding value.
    * Not only individuals and interations, but also a community of professionals.
    * Not only customer collaboration, but also productive partnerships.
* Well-crafted software: code that is well designed and well tested.
* Steadily adding value: committed to continuosly provide increasing value to our clients.
* Community of professionals: we are expected to share and learn with each other, raising the bar of our industry. We are responsible for preparing the next generation of developers.
* Productive partnerships: We will have a professional and respectful relationship with our clients and employers.
* We look at our work not as part of our job, but as a professional service we provide.
* We take ownership of our careers, investing our time and money to get better at what we do.
* Craftspeople strive to do the best job they can, not because someone is paying, but based on a desire to do things well.

### Ideology vs Methodology

* An ideology is a system of ideas and ideals.
* A methodology is a sysmtem of methods and practices.
* An ideology defines ideals to be aimed at. One or more methodologies can be used to reach those ideals.
* The main goal of Agile is to provide business agility and customer satisfaction, and that is achieved via close collaboration, iterative development, short feedback loops and technical excellence.
* The obsessive focus ono a methodology or set of practices distracts teams and organizations from their real goals.
* Principles guide practices. Practices instantiate principles.
* We cannot claim to have certain principles and values when our ways of working (methods and practices) are not aligned to them.

### Does software Craftsmanship have practices.

* Software craftsmanship promotes a perpetual search for better practices and ways of working.
* The software craftmanship community considers XP the best set of agile development practices currently available.
* Craftsmanship is not only about technical practices, engineering, and self improvement. It is also about professionalism and enabling clients to achieve their business goals.

### Focus on the value, not the practice.

* How do I convice my manager/colleague/team to do TDD? That is the wrong question. The problem here is that we are offering a solution before agreeing on the problem.
* Instead of pushing TDD, maybe we could start agreeing on the value of reducing the time it takes to test our entire system. What if we could reduce it to 20 minutes? 2 seconds? What if we could do that at any time just by pressing a button?
* If we agree on the problem, we could start talking about practices which could help up achieve that.

### Discussing Practices

* If developers are discussing practices that would enable them to build systems in a better way, there is no reason to involve businesspeople. Business should only be involved when there is a significant impact in the cost or duration of the project.
* Developers should not ask authorization for writing tests. They should not have separate tasks for unit tests or refactoring.
* Everytime developers volunteer details of how they work, they are inviting managers to micromanage them.
* Developers should not let other people decide how they work.

### Craftsmanship impact on individuals

* Craftsmanship promotes software development as a profession. A job is a thing we do but it is not part of who we are. A profession, on the other hand, is part of who we are.
* A profession is something we invest in. It's something we want to get better at. We want to gain more skills and have a long lasting and fulfilling career.

### Caftsmanship Impact on our Industry

* Craftsmanship communities have been promoting XP, and many other technical practices to many developers and companies around the world.

### Craftsmanship impact on Companies

* Managers understand scrum, iterations, demos, retrospectives, collaboration and fast feedback loops. But they are not so interested in programming related techniques.
* Agile coaches in the early 2000s had strong technical background. Most agile coaches today cannot teach XP practices.
* Software craftsmanship promotes a culture of learning, making companies more innovative and responsive.

### Craftsmanship and Agile

* Agile and Craftsmanship want to achieve very similar things. They both want customer satisfactio, desire close collaboration, and value short feedback loops. Both want to deliver high-quality, valuable work, and both want professionalism. In order to achieve business agility, companies need not only collaborative and iterative process, but also good engineering skills.