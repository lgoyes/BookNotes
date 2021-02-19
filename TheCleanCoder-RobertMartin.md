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


## 2. Saying No
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
