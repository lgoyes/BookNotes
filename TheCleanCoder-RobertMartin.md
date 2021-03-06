# The Clean Coder: A Code of Conduct for Professional Programmers

**Author**: Robert Martin

**Language**: English

**Start date**: Feb 17th, 2021.

**End date**: Mar 26th, 2021.

## Index

1. [Professionalism](#1-professionalism)
2. [Saying No](#2-saying-no)
3. [Saying Yes](#3-saying-yes)
4. [Coding](#4-coding)
5. [Test Driven Development](#5-test-driven-development)
6. [Practicing](#6-practicing)
7. [Acceptance Testing](#7-acceptance-testing)
8. [Testing Strategies](#8-testing-strategies)
9. [Time Management](#9-time-management)
10. [Estimation](#10-estimation)
11. [Pressure](#11-pressure)
12. [Collaboration](#12-collaboration)
13. [Teams and Projects](#13-teams-and-projects)
14. [Mentoring, Apprenticeship, and Craftsmanship](#14-mentoring-apprenticeship-and-craftsmanship)
15. [Appendix A. Tooling](#appendix-a-tooling)

## 1. Professionalism

### Be careful what you ask for

* Professionalism is a bagde of honor and pride, but it is also a marker of responsibility and accountability.
* It's a lot easier to be a nonprofessional. Nonprofessionals don't take responsibility for the job they do.
* If a nonprofessional makes an error, the employer cleans up the mess. But when a professional makes a mistake, he cleans up the mess.

### Taking REsponsibility

* Upon reflection, I realized that shipping without testing the routine had been irresponsible. The reason I neglected the test was so I could say I had shipped on time.
* I had not been concerned about the customer, nor about my employer.
* I should have taken responsibility early and told Tom that the tests weren't complete and that I was not prepared to ship the software on time.


### First, Do not harm.

* A software developer can do harm to both the function and structure of the software.

#### Do not harm to function

* The first thing you omust practice is apologizing. Apologies are necessary, but insufficient.
* As you mature in your profession, your error rate should rapidly decrease towards the asymptote of zero.

#### QA should find nothing

* It is unprofessional in the extreme to purposelly send code that you know to be faulty to QA: any code you aren't certain about.
* Some folks use QA as the bug catchers. They seend them code that they haven't thoroughly checked.
* Will QA find bugs? probably, so get ready to apologize -and then, figure out why those bugs managed to escape your notice and do something to prevent it from happening again.

#### You must know it works

* How can you know your code works? Test it.
* Write unit tests that you can execute on a moment's notice, and run those tests as often as you can.
* I am demanding 100% test coverage. Every single line of code that you write should be tested.
* You only write code because you expect it to get executed. If you expect it to get executed, you ought to know that it works. The only way to know this is to test it.
* The best way to design your code to be easy to test is to write your testes first, before you write the code that passes them.

#### Automated QA

* You as a developer need a relatively quick and reliable mechanism to know that the code you have written works and does not interfere with the rest of the system.
* Some systems are so mission critical that a short automated test suite is insufficient to determine readiness for deployment.

### Do not harm to structure

* It is the structure of your code that allows it to be flexible. If you compromise the structure, you compromise the future.
* You must be able to make changes without exorbitant costs.
* When you find that changes aren't as easy as you thought, you refine the design so that the next change is easier.
* Always check in a module cleaner than when you checked it out. Always make some random act of kindness to the code whenever you see it.
* If you have an automated suite of tests that covers virtuallyl l100% of the code, you simply will not be afraid to change the code.

#### Work ethic

* Your career is your responsibility
* It is also not your employer's responsibility to give you the time you need to learn.
* You owe your employer a certain amount of time and effort. Those 40 hours should be spent on your employer's problems, not on your problems.
* You should plan on working 60 hours per week. The first 40 hours are for your employer. The remaining 20 hours are for you. During this remaining 20 hours you should be reading, practicing, learning and otherwise enhancing your career.
* Sometimes these two are aligned with each hother. Sometimes the work you do for your employer is greatly beneficial to your career. But remember, those 20 hours are for you. They are to be used to make yourself more valuable as a professional.

#### Know your field

* Here's a minimal list of the things that every software professional should be conversant with.
    * **Design patterns** - You ought to be able to describe all 24 patterns in the GOT book and have a working knowledge of many of the patterns in the POSA books.
    * **Design principles** - You should know the SOLID principles
    * **Methods** - You should understand XP, Scrum, Lean, Kanban.
    * **Dissciplines** - You should practice TDD, Object Oriented Design, Conotinuous Integration, and Pair Programming.
    * **Artifacts** - You should know how to use UML, DEFDs, State Transition Diagrams and Tables, flow charts and decision tables.
#### Continuous Learning
* The frenetic rate of change in our industry means that software developers must continue to leaern copius quantities to keep up.
* Why should employers hire developers who don't keep current?

#### Practice
* Professionals practice. True professionals work hard to keep their skills sharp and ready. It is not enough to simply do your daily job and call that practice. Doing your daily job is performance, not practice. Practice is when you specifically exercise your skills outside of the performance of your job the sole purpose of refining and enhancing those skills.
* I'll use a kata to sharpen a particular skill, such as keeping my fingers used to hitting shortcut keys, or using certain refactorings.

#### Collaboration
* Professional software developers make a special effort to collaborate with other people (programming, practice, designing, planing).

#### Mentoring
* The best way to learn is to teach.

#### Know your domain
* It is the responsibility of every software professional to understand the domain of the solutions they are programming.
* You don't have to be a domain expert, but there is a reasonable amount of due diligence that you ought to engage in.
* You should know enough about the domain to be able to recognize and challenge specification errors.

#### Identify with your employer/customer
* As you develop a system you need to put yourself in your employer's shoes and make sure that the ffeatures you are developing are really going to address your employer's needs.

#### Humility

* When a professional finds himself the butt of a joke, he'll be the first to laugh. He will never ridicule others, but will accept ridicule when it is deserved and laugh it off when it's not. he will not demean another for making a mistake, because he knows he may be the next to fail.

## 2. Saying No

* Professionals speak truth to power. Professionals have the courage to say no to their managers.
* Slaves are not allowed to say no. Laborers may be  hesitant to say no. But professionals are expected to say no.

### Adversarial Roles

* My own experience has been that the hard decisions are best made through the confrontation of adversarial roles.
* Managers are people with a job to do. Part of that job is to persue and defect their objectives as aggressively as they can.
* By the same token, programmers are also people with a job to do, if they are professionals, they will persue and defend their objectives as aggressively as they can.
* If you know full well that getting the login page done by tomorrow is impossible, then you are not doing your job if you say "OK, I'll try". The only way to do your job at that point is to say "No, that's impossible".
* Instead of asking whether two week would be OK, Paula should have been more assertive: "It's going to take me two weeks". Mike, on the other hand, just accepted the date without questioning, as though his own objectives didn't matter.
* The conversation was a bit adversarial, and there were a few uncomfortable moments, but that's to be expected when two people assertively persue goals that aren't in perfect alignment.

#### What about the why?

* The why is a lot less important than the fact.
* Still, knowing why might help mike to understand and therefore to accept the fact.
* In situations where Mike has the technical expertise and temperament to understand, such explanations might be useful.
* Providing too much detail can be an invitation for micro-management.

### High Stakes

* When the cost of failure is so high that the survival of your company depends upon it, you MUST be absolutely determined to give your managers the best information you can. And that often means saying no.

### Being a "Team Player"

* A team-player communicates frequently, keeps an eye out for his or her team mate, and executes his or her own responsabilities as well as possible.
* Mike wanted Don to see him as a team player, and he has faith in his ability to wheedle and manipulate Paula into trying for the six-week deadline.

#### Trying

* The worst thing Paula could do in response to Mike's manipulations is saying "OK, well. I'll try".
* If there is some extra effort she could apply, then she and her team must not have been applying all their effort before.
* By promising to try, you are committing to succeed. If your "trying" does not lead to the desired outcome, you will have failed.
* If you are NOT holding back some energy in reserve, if you don't have a new plan, if you aren't going to change your behavior, and if you're reasonably confident in your original estimate, then promising to try is fundamentally dishonest. You are lying. And you are probablly doing it to save face and to avoid a confrontation.

#### Passive Aggression

* Paula could just left Mike walk off the end of the cliff. This is passive agression. She'd just left Mike hang himself.
* Or, she could try to head off the disaster by communicating directly with Don. It's what being a team player is really about.

### The cost of saying yes

* Managers and developers in well-run teams will negotiate with each other util they come to mutually agreed upon plan of action.
* Sometimes, the only way to get to the _right_ yes is to be unafraid to say no.

### Code Impossible

* Instead of "is good code impossible?", the real question is "is professionalism impossible?".
* Why did John do this? John was trying to be a hero.
* Professionals are often heroes, but not because they try to be one. Professionals become heroes when they get a job done well, on time, and on budget.
* By trying to become the man of the hour, John was not acting like a professional.
* John accepted that the only way to succeed was to behave unprofessionally, so he reaped the appropriate reward.
* Saying yes to dropping our professional disciplines is not the way to solve problems.

## Saying yes

### A Language of Commitment

* There are three parts to making a commitment
    1. You _say_ you'll do it
    2. You _mean_ it.
    3. You _actually_ do it.
* There are very few people who, when they say something, they mean it and then actually get it done.

#### Recognize lack of commitment

* Here are some examples of words and phrases to look for, that are signs of noncommitment:
    1. **need/should**: "We need to get this done"
    2. **hope/wish** "I hope we can meet again some day"
    3. **Let's** "Let's meet sometime"
* We tend to be very busy not taking responsibility for things. And that's _not_ ok when you or someone else relised on those promises as part of the job.

#### What does commitment sound like?

* The phrases of the previous section assume things are out of my hards, or they don't take personal responsibility.
* People behave as if they were victims of a situation instead of in control of it.
* You, personally, always have something that's under your control.
* Look for sentences that sould like "I will... by..."
* You are stating a fact about something you owill do with a clear end time.
* If you don't get it done, people can hold you up to your promises.
* The start of commitment: putting yourself in the situation that forces you to do something.

#### It wouldn't work because I rely on person X to get this done.

* You can only commit to things that you have full control of.
* If the end goald depends on someone else, you should commit to specific actions that bring you closer to the end goal.

#### It wouldn't work because I don't really know if it can be done.

* If it can't be done, you can still commit to actions that will bring you closer to the target.

#### It wouldn't work because sometimes I just won't make it

* If you can't make your commitment, the most important thing is to raise a red flag as soon as possible, to whoever you committed to.
* The earlier you raise the flag, the more likely there will be time to decide if something can be done or changed.

### Learning How to Say "Yes"

#### The other side of "try"

* Instead of fuzzy responses (with) try, you should be clear, even describing your own uncertainty.

#### Commiting with Disciplilne

* He could do a few hours of work on Saturday too if things take longer than he hopes.
    * Peter: "look, marge, there's a good chance that I can get everything done by monday morning if I put in a few extra hours on Saturday."
    * Marge: "Can I count on Monday morning then?"
    * Peter: "Probably, but not definetely"
* Peter might be tempted to break discipline at this point. This is where the professional draws the line.
* Peter starts to think about working some significant overtime, and probably most of the weekend. He needs to be very honest with himself about his stamina and reserves.
* Peter knows that he can get the modifications and documentations done if he works the overtime. He also know he will be useless for a couple of days after that.

## 4. Coding

### Preparedness

* Coding requires you to juggle many factors at once:
    1. You must understand the problem. You must ensure that the code you write is a faithful representation of that solution.
    2. Often, the customer's requirements do not actually solve the customer's problems. You have to negotiate with the him/her.
    3. Your code must fit well into the existing systems, following the SOLID principles.
    4. Your code must be readable by other programmers. Craft your code in such a way that it reveals your intent.
* If you are tired or distracted, do not code. You will only wind up redoing what you did.

#### 3am code

* Don't write code when you are tired. Dedication and professionalism are more about discipline that hours. Make sure that your sleep, health, and lifestyle are tuned so that you can put in _eight good hours per day_.

#### Worry code

* When I am worried about an argument, I can't maintain focus. My concentration wavers. I find myself with my eyes on the screen and my fingers on the keyboard, doing nothing.
* Instead of coding, I need to resolve the worry.
* The trick is to learn how to shut down the background process, or at least reduce its priority so that it's not a continuous distraction.
* You should specifically set aside time at home to settle your snxieties so that you don't bring them to the office.
* If you find yourself at the office and the background anxieties are sapping your productivity, then it is better to spend an hour quieting them than to use brute force to write code.

### The flow zone

* You will write more code in the zone. The problem is that you lose some of the big picture while you are in the zone, so you will likely make decisiones that you will later have to go back and reverse.
* There are times when the zone is exactly where you want to be when you are practicing.

#### Music

* The music does not help me focus.
* Maybe the music helps you to write some code.

#### Interruptions

* You may resent being dragged out of the Zone, or you may resent someone interfering with your attempt to enter the Zone.
* When interruptions happen, remember that next time you may be the one who needs to interrupt someone else. So the professional attitude is a polite willingness to be helpful.

### Writer's Block

* What causes such blockages? A major factor is sleep. Others are worry, fear and depression.
* The solution: find a pair partner.
* The typical reaction to pairing is a recovery of my momentum.

#### Creative Input

* Creative output depends on creative input. I read a lot, and I read all kinds of material. Science fiction best primes the pump of creative output.
* Creativity breeds creativiy.

### Debugging

#### Debugging Time

* Debugging time is just as expensive to the business as coding time is, and therefore, anything we can do to avoid or diminish it is good.
* I achieved this truly radical reduction in debugging time by adopting the practice of TDD.

### Pacing yourself

* Software development is a marathon, not a sprint. You win by conserving your resources and pacing yourself.

#### Know when to walk away.

* Can't go home till you solve this problem? You should
* When you are stuck, when you are tired, disengage for a while.

#### Driving Home

* Driving requires a lot of noncreative mental resources. You must dedicate your eyes, hand and portions of your mind to the task. That disengagement allows your mind to hunt for solutions in a different and more creative way.

#### The shower

* You miss elegant solutions because the creative part of your mind is suppressed by the intensity of your focus.

### Being late

* You will be late. Sometimees we just blow our estimates and wind up.
* The trick to managing lateness is early detection and transparency.
* Do not incorporate hope into your estimates! Regularly measure your progress against your goal.
* What are the best, nominal and worst case scenarios?

#### Hope

* Hope is the project killer. Hope destroys schedules and ruins reputations. Hope will get you into deep trouble.
* If the trade show is in ten days, and your nominal estimate is 12, you are not going to make it, even though your best case estimate is 8.

#### Rushing

* What if the manager asks you to make the deadline? Hold your estimates. Tell your boss that you've already considered the options and that the only way to improve the schedule is to reduce scope.
* There is no way to rush. You can't make yourself code faster. If you try, you will just make a mess that slows everyone else down, too.

#### Overtime

* Overtime can work, and sometimes it's necessary. Sometimes you can make an otherwise impossible date by putting in some ten-hour days and a Saturday or two.
* You should not agree to work overtime unless:
    1. You can personally afford it.
    2. It is short term, two weeks or less.
    3. Your boss has a fall-back plan in case the overtime effort fails.

#### False Delivery

* The worst behavior is saying you are done when you know you aren't. We convince ourselves that we are done "enough", and move onto the next task. We rationalize that any work that remains can be dealth with later, when we have more time.

#### Define "done"

* Avoid false deliviery by creating an independent definition of "done".
* Have your business analysts and testers create automated acceptance tests that must pass before you can say that you are done. These tests should be written in cucumber, so they are understandable by the business people.

### Help

* Programming is so hard, in fact, that is beyond the capability of one person to do it well. No matter how skilled you are, you will certainly benefit from another programmer's thoughts and ideas.

#### Helping others

* Be available to help your teammates.
* You can let it be known that between the hours of 10 am and noon you should not be bothered, but from 1pm to 3pm your door is open.
* It is not that you are so much smarter than the other person, it's just that a fresh perspective can be very useful.

#### Being helped

* Just as you oare honor bound to offer help, you are honor bound to accept help.
* When you are stuck, or just can't wrap your mind around a problem, ask someone for help. It is unprofessional to remain stuck when help is easily accessible.
* Programmers tend to be arrogant, self-absorbed introverts.

#### Mentoring

* The training of less experienced programmers is the responsibility of those who have more experience.
* Nothing can bring a young software developer to high performance quicker than his own drive and effective mentoring by his seniors.
* Young programmers have a professional duty to seek out such mentoring from their seniors.

## 5. Test Driven Development

### The jury is in

* How can you consider yourself to be a professional if you do not know that all your code works?
* How can you know all your code works if you don't test it every time you make a change?

### The tree laws of TDD

1. You are not allowed to write any production code until you ohave first written a failing unit test.
2. You are not allowed to write more of a unit test than is sufficient to fail - and not compiling is failing.
3. You are not allowed to write more production code that is sufficient to pass the currently failing unit test.

#### The letany of benefits

##### Certainty

* Whenever I make a change to any part of the project, I simply run the unit tests. If they pass, I am nearly certain that the change I made didn't break anything. How certain is "nearly certain"? Certain enough to ship!

##### Defect Injection Rate

* There is a defect reduction of 2X, 5X, and even 10X.

##### Courage

* Why don't you fix bad code when you osee it? Because you know that if you touch it you risk breaking it; and if you break it, it becomes yours.
* What if you could click a button and know within 90 seconds that your changes had broken nothing, and had only done good?
* When programmers lose the fear of cleaning, they clean!

##### Documentation

* Where's the first place you go in that manual? If you are a programmer, you go to the code examples. You know the code will tell you the truth.
* Each of the unit tests you write is an example, written in code, describing how the system should be used.
* For anything you need to know how to do, there will be a unit test that describes it in detail.
* Tests are unambiguous, accurate, written in a language that the audience understands, and are so formal that they execute.

#### Design

* To write a test for a function, you've got to figure out some way to decouple the function from all the others. In other words, the need to test first forces you to think about good design.
* If you owrite your tests later, you may be able to test the inputs and the outputs of the total mass, but it will probably be quite difficult to test individual functions.
* The tests you write after the fact are defense. The tests you write first are offense.

#### The professional option

* TDD is a discipline that enhances certainty, courage, defect reduction, documentation and design.

### What TDD is not?

* You can still write bad code even if you write your tests first. Indeed, you can write bad tests.

## 6. Practicing

* When performance matters, professionals practice.

### Some background on Practicing

#### Twenty-two zeros

* What am I doing with this increase in power of 22 factors of ten? I'm writing `if` statements, `while` loops, and assignments.
* I've got better tools and better languages to write these statements with. But the nature of the statements hasn't changes in all that time.

#### Turnaround time

* The way we work has changed dramatically.
* Programmers today don't wait for compiles. You can spin around the red-green-refactor cycle in seconds.
* Doing anything quickly requires practice. Spinning around the code/test loop quickly requires you to make very quick decisions. Making decisions quickly means being able to recognize a vast number of situations and problems and simply know how to address them.

### The coding Dojo

* Many programmers have adopted a martial arts mataphor for their practice sessions.

#### Kata

* A kata is a precise set of choreographed movements that simulates one side of a combat. The goal is perfection.
* The purpose is to train our mind and body how to react in a particular combat situation.
* A programming kata is a precise set of choreographed key strokes and mouse movements that simulates the solving of some programming problem. You aren't solving the problem because you already know the solution. Rather, you are practicing the movements and decisions involved in solving the problem.
* Many katas are recorded at `katas.softwarecraftsmanship.org`, and `codekata.pragprog.com`.

#### Wasa

* `ping-pong`. The two partners choose a kata, or a simple problem. One programmer writes a unit test and then the other must make it pass. Then, they reverse roles.

#### Randori

* Randori is free-form combat.
* With the screen projected on the wall, one person writes a test and then sits down. The next person makes the test pass and then writes the next test.

#### Broadening your experience

#### Open source

* one way to stay ahead of the curve is to contribute to an open source project.

#### Practice Ethics

* Professional programmers practice on their own time.
* Since your practice time is your own time, you don't have to use the same language or platforms that you use with your employer.

## 7. Acceptance Testing

### Communicating Requirements

* It was clear that his emphasis had changed from learning how to do it himself to making sure that what I did wasa what he wanted.
* It became very clear to me that he was the sculptor and I was the tool he was wielding.
* The customer's vision of the features does not often survive actual contact with the computer.

#### Premature precision

* Business people want to know exactly what they are going to get before they authorize a project.
* Developers want to know exactly what they are supposed to deliver before they estimate the project.
* Both sides want a precision that simply cannot be achieved.

#### The uncertainty principle

* When you demonstrate a feature to the business, it gives them more information than they had before, and that new information impacts how they see the whole system.
* The more precisee you make your requirements, the less relevant they become as the system is implemented.

#### Estimation Anxiety

* Professional developers understand that estimates can, and should, be made based on low precision requirements and recognize that those estimates _are estimates_. To reinforce this, professional developers include error bars with their estimates so that the business understands the uncertainty.

#### Late ambiguity

* It is responsibility of professional developers (and stakeholders) to make sure that all ambiguity is removed from the requirements

### Acceptance tests

* An acceptance test is a test written by a collaboration of the stakeholders and the programmers in order to define when a requirement is done.

#### The definition of "Done".

* Professional developers have a single definition of done: "Done" means all code written, all tests passed, QA ant the stakeholders have accepted.
* Professional developers drive the definition of their requirements all the way to automated acceptance tests. They work with stakeholders and QA to ensure that these automated tests are a complete specification of done.

#### Communication

* The purpose of acceptance tests is communication, clarity, and precision. By agreeing to them, the developers, stakeholders, and testers will understand what the plan for the system behavior is.

#### Automation

* Acceptance tests should always be automated
* Cucumber and Selenium are some open-source tools that facilitate the automation of acceptance tests. Those tools allow you to specify automated tests in a form that non programmers can read, understand and even author.

#### Extra work

* Writing acceptance tests is simply the work of specifying the system.
* Specifying at this level of detail is the only way that the stakeholds can ensure that the system they are paying for really does what they need.

#### Who writes acceptance tests, and when?

* Take care that the developer who writes the tests is not the same as the developer who implements the tested feature.
* Typically business analysts write the "happy path" versions of the tests, because those tests describe the feature that have business value. QA typically writes the "unhappy path" testes. This is because QA's job is to ohelp think about what can go wrong.
* Acceptance tests should be written as late as possible, typically a few days before the feature is implemented.

#### The developer's role

* The developer's job is to connect the acceptance tests to the system, and then to make those tests pass.

#### Test negotiation and passive aggression

* Test authors are human and make mistakes. It is your job to negotiate with the test author for a better test.
* You should never take the passive-aggressive option: "Well, that's what the test says, so that's what I'm going to do".

#### Acceptance tests and Unit Tests

* Unit tests are written by programmers for programmers. They are formal design documents that describe the lowest level structure and behavior of the code.
* Acceptance tests are written by the business for the business. They are formal requirements developments that specify how the system should behave from the business point of view.
* Unit and acceptance tests are not redundant. Their primary purpose is to formally document the design, structure and behavior of the system.

#### GUIs and Other complications

* GUIs are constantly in flux.
* Rather than creating tests that click on those buttons based on their positions on the page, you may be able to click on them based on their names or any other unique `ID` that you can use.

##### Testing through the Right Interface

* Write your business rule tests to go through an API below the GUI.
* It is a good idea to decouple the GUI and the business rules and replace the business rules with stubs while testing the GUI itself.
* Keep the GUI tests to a minimum. They are fragile, because the GUI is volatile. The more GUI tests you have, the less likely you are to keep them.

#### Continuous Integration

* Make sure that all your unit tests and acceptance tests are run in a continuous integration system, every time some one commits a module.

#### Stop the Presses

* If the CI fails, then the whole team should stop what they are doing and focus on getting the broken tests to pass again.

## 8. Testing Strategies

* Every professional team needs a good testing strategy.

### QA should find nothing

* It should be the goal of the development group that QA find nothing wrong.

#### QA is part of the team

* QA and development should be working together to ensure the quality of the system. The best role for the QA part of the team is to act as specifiers and characterizers.

##### QA as specifiers

* QA should work with business to create the automated acceptance tests that become the true specification and requirements documents for the system. Business writes the happy-path tests, while QA writes the unhappy-path tests.

##### QA as Characterizers

* QA uses exploratory testing to identify the actual behavior of the system.

### The test automation pyramid

#### Unit tests

* The intent of these tests is to specify the system at the lowest level.
* Developers write these tests before writing production code as a way to specify what they are about to write.
* Unit tests provide as close to 100% coverage as is practical.

#### Component tests

* The components of the system encapsulate the business rules, so the tests for those components are the acceptance tests for those business rules.
* Any other system components are decoupled from the test using appropriate mocking and test-doubling techniques.
* The intent is that the business should be able to read and interpret these tests, if not author them.
* Component tests cover rougly half the system. They are directed more towards happy-path situations and very obvious alternate-path cases. The vast majority of unhappy-path cases are covered by unit tests and are meaningless at the level of component tests.

#### Integration tests

* These tests only have meaning for larger systems that have many components.
* Integration tests assemble groups of components and tests how well they communicate with each other.
* Integration tests are choreography tests that make sure that the components are properly connected and can clearly communicate with each other.
* These tests are typically not executed as part of the continuous integration suite, because they often have longer runtimes. Instead, these test are run periodically.

#### System tests

* Their intent is not to ensure correct system behaviour, but correct system construction.
* They test that the system has been wired together correctly and its parts interoperate according to plan.

#### Manual Exploratory Tests

* These tests are not automated, nor are they scripted.
* Explore the system for unexpected behaviours while confirming expected behaviors.
* We are not going to prove out every business rule and every execution pathway with these tests. Rather, the goal is to ensure that the system behaves well under human operation and to creatively find as many "pecularities" as possible.

## 9. Time management

### Meetings

* Meetings cost about 200 USD per hour per attendee.
* Meetings are necessary and they are huge time wasters.
* Professionals are aware of the high cost of meetings, therefore, they actively resist attending meetings that don't have an immediate and significant benefit.

#### Declining

* You need to use you time wisely. So be very careful about which meetings you attend and which you politely refuse.
* Don't accept a meeting invitation, unless it is a meeting for which your participation is immediately and significantly necessary to the job you are doing now.
* Your reponsibility is to your project first.
* Sometimes your presence at a meeting will be requested by someone in authority. You will have to choose whether that authority outweights your work schedule. Your team and your supervisor can be of help in making that decision.

#### Leaning

* If you find yourself stuck in a meeting that is not a good use of your time, you need to find a way to politely exist that meeting.
* Remaining in a meeting that has become a waste of time for you, and to which you can no longer significantly contribute is unprofessional. You have an obligation to wisely spend your employer's time and money.

#### Have an agenda and a goal

* Make sure you know what discussions are on the table, how much time is allocated for them, and what goal is to be achieved. If you can't get a clear answer on these things, then politely decline to attend.

#### Stand-up meetings

* Answer three questions
    1. What did I do yesterday?
    2. What am I going to do today?
    3. What's in my way?
* Wach question should require no more than twenty seconds.

#### Iteration planing meetings

* These meetings are meant to select the backlog items that will be executed in the next iteration. Estimates should already be done for the candidate items. Assessment of business value should already be done. Acceptance tests will already be done.
* Each candidate backlog item will be briefly discussed and then either selected or rejected. No more than five or ten minutes should be spent on any given item.
* For a one week iteration (40 hours) the meeting should be over within 2 hours.

#### Iteration retrospective and demo

* Those meetings are conducted at the end of each iteration
* Team members duscuss what went wrong and what went right.
* Stakeholders see a demo of the newly working features.
* 20 minutes for retrospective and 25 minutes for the demo.

#### Arguments and disagreements

* Any argument that can't be settled in five minutes can't be settled by arguing. The reason it goes on so long is probablly religious, as opossed to factual.
* Without data, any argument that doesn't forge agreement within a few minutes simply won't ever forge agreement. The only thing to do is to go get some data.

### Focus-manna

* Programming is an intellectual exercise that requires extended periods of concentration and focus. Focus is a scarce resouce.
* Professional developers learn to manage their time to take advantage of their focus.
* Focus is a decaying resource. If you don't use it when it's there, you are likely to lose it.

#### Sleep

#### Caffeine

#### Recharging

* Focus can be partially recharged by de-focussing. A good long walk, a conversation with friends.
* Once the focus is gone, you can't force it.

#### Muscle focus

* Muscle focus helps to recharge mental focus
* Whatever the activity, there is something about activities that focus on muscles that enhances the ability to work with your mind.

#### Input vs Output

* I am most creative when I am exposed to other people's creativity.

### Time boxing and tomatoes

* Pomodoro technique: 25-minute window of productive time that you aggressively defend against all interruptions.

### Avoidance

#### Priority inversion

* You convice yourself that something else is more urgent, and you do that instead. This is called priority inversion.
* Professionals evaluate the priority of each task, disregarding their professional fears and desires, and execute those tasks in priority order.

### Blind alleys

* When you are in a hole, stop digging.
* You need to quickly realize when you are in a blind alley and have the courage to back out.

### Marshes, bogs, swamps, and other messes

* Starting a mess in unavoidable
* At some point you realize that you made a wrong decision choice when you started, and that your code doesn't scale well in the direction that the requirements are moving - This is the inflexion point where you can go back and fix the design.

## 10. Estimation

### What is an estimate?

* Business views estimates as commitmets
* Developers view estimates as guesses

#### A commitment

* A commitment is something you must achieve
* Professionals don't make commitments unless they know they can achieve them. If you aren't certain, then you have to decline.
* Other people will accept your commitments and make plans upon them.

#### An estimate

* An estimate is a guess. No commitment is implied. The reason we make estimates is because we don't know how long something will take.
* An estimate is not a number. An estimate is a probability distribution.
* Peter's estimate is a probability distribution.
* Peter's original estimate of three days is the highest bar on the chart, so on Peter's mind it is the most likely duration for the task.

#### Implied commitments

* Professionals do not commit unless they know for certain they will succeed. They are careful not to make any implied commitments. They communicate the probability distribution of their estimates as clearly as possible, so that managers can make appropriate plans.

### Program Evaluation and Review Technique (PERT)

* When you estimate a task, you provide three numbers
    1. O: optimistic estimate. Absolutely everything went right.
    2. N: Nominal estimate. Estimate with the greatest chance of success.
    3. P: Pessimistic estimate. Widely pessimistic
* Expected duration of the task, &mu; = (O+4N+P)/6
* For most tasks, this will be a somewhat pessimistic number because of the right-hand tail.
* The standard deviation of the probability distribution for the task, &sigma; = (P-O)/6
* Then, we can combine all of the tasks and come up with a probability distribution for the entire set of tasks
&mu;<sub>sequence</sub> = &sum; &mu;<sub>task</sub>
* The standard deviation of the sequene is the square root of the sum of squares of the standard deviations of the task
&sigma;<sub>sequence</sub> = &radic;(&sum; (&sigma;<sub>task</sub>)<sup>2</sup>)
* If you are a programmer of more than a few years' experience, you've likely seen projects that were estimated optimistically, and that took three to five times longer than hoped.

### Estimating Tasks

#### Wideband delphi

* A team of people assemble, discuss a task, estimate the task, and iterate the discussion and estimation until they reach agreement.

#### Flying Fingers

* Tasks are discussed one at a time. The participants put their hards below the table and raise 0 to 5 fingers based on how long they think the task will take. The moderator counts 1-2-3, and all the participants show their hands at one.
* The simultaneity of displaying the fingers is important. We don't want people changing their estimates based on what they see other people do.

#### Planning Poker

* Planning Poker is like flying finger, but using cards instead.
* Cards for infinity and quation mark are also included.

#### Affinity Estimation

* All the tasks are written onto cards, without any estimates showing.
* The team members do not talk, they simply start sorting the cards relative to one another. Tasks that take longer are moved to the right. Smaller taks are moved to the left.
* Any card moved more than X times is set aside for discussion.
* Eventually, the silent sorting is over, and discussion can begin.
* Next step is to draw lines between cards that represent bucket sizes. These buckets might be days, weeks or points.

#### Trivariate Estimates

* Wideband delphi techniques are good for choosing a single nominal estimate for a task. But most of the time, we need three estimates so that we can create a probability distribution.

### The law of large numbers

* If you break a large task into many smaller taks, and estimate them independently, the sum of the estimates of the small tasks will be more accurate than a single estimate of the larger task.
* Errors in the small tasks tend to integrate out.
* This is optimistic. Errors in estimates tend toward underestimation and not overestimation, so integration is hardly perfect.

## 11. Pressure

* The professional developer is calm and decisive under pressure. As the pressure grows, he adheres to his training and disciplines, knowing that they are the best way to meet the deadline and commitments that are pressing on him.

### Avoiding pressure

#### Commitments

* Avoid commiting to deadlines that we aren't sure we can meet.
* We have to quantify the risk, and present it to the business so that they can manage it appropriately.
* Sometimes we find that our business has made promises to customers without consulting us. When this happens, we have to find a way to meet those commitments. However, we are not forced to accept the commitments.
* When your business is failing, and your paycheck is delayed because of missed commitments, it's hard not to feel the pressure.

#### Staying clean

* Dirty always means slow!
* We don't tolerate messes. We know that messes will slow us down.

#### Crisis discipline

* You know what you believe by observing yourself in a crisis.
* If in a crisis you follow your disciplines, then you truly believe in those disciplines.
* If your disciplines are the best way to work, then they should be followed even in the depths of a crisis.

### Handling Pressure

#### Don't Panic

* Manage your stress. Sleepless nights won't help you get done any faster.
* Calm down. Plot a course to the best possible outcome, and then drive towards that outcome at a reasonable and steady pace.

#### Communicate

* let your team and your superiors know that you are in trouble.

#### Rely on your disciplines

#### Get Help

*  Pair! You will get done faster, with fewer defects.

## 12. Collaboration



## 13. Teams and Projects
## 14. Mentoring, Apprenticeship, and Craftsmanship
## Appendix A. Tooling
