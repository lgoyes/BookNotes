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

## 3. Saying Yes
## 4. Coding
## 5. Test Driven Development
## 6. Practicing
## 7. Acceptance Testing
## 8. Testing Strategies
## 9. Time Management
## 10. Estimation
## 11. Pressure
## 12. Collaboration
## 13. Teams and Projects
## 14. Mentoring, Apprenticeship, and Craftsmanship
## Appendix A. Tooling
