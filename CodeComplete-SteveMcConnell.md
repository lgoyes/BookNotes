# Code Complete

**Author**: Steve McConnel

**Language**: English

**Start date**: Jul 28th, 2020

**End date**: Nov 27th, 2020.

## Index:

1. [Welcome to Software Construction](#1-welcome-to-software-construction)
2. [Metaphors for a Richer Understanding of Software Development](#2-metaphors-for-a-richer-understanding-of-software-development)

## 1. Welcome to Software Construction

* Software construction is the central activity in software development; construction is the only activity that's guaranteed to happen on every project.
* The main activities in construction are detailed design, coding, debugging, integration, and developer testing (unit testing and integration testing).
* Other common terms for construction are "coding" and "programming".
* The quality of the construction substantially affects the quality of the software.
* In the final analysis, your understanding of how to do construction determines how good a programmer you are, and that's the subject of the rest of the book.

## 2. Metaphors for a Richer Understanding of Software Development

* Metaphors are heuristics, not algorithms. As such, they tend to be a little sloppy.
* Metaphors help you understand the software-development process by relating it to other activities you already know about.
* Some metaphors are better that others.
* Treating software construction as similar to building construction suggests that careful preparation is needed and illuminates the difference between large and small projects.
* Thinking of software-development practices as tools in an intellectual toolbox suggests further that every programmer has many tools and that no signle tool is right for every job. Choosing the right tool for each problem is one key to being an effective programmer.
* Metaphors are not mutually exclusive. Use the combination of metaphors that works best for you.

## 3. Measure Twice, Cut Once: Upstream Prerequisites

* THe overarching goal of preparing for construction is risk reduction. Be sure your preparation activities are reducing risks, not increasing them.
* If you want to develop high-quality software, attention to quality must be part of the software development process from the beginning to the end. Attention to quality at the beginning has a greater incluence on product quality than attention at the end.
* Part of a programmer's job is to educate bosses and coworkers about the software development process, including the importance of adequate preparation before programming begins.
* The kind of project you're working on significantly affects construction prerequisites -many projects should be highly iterative, and some should be more sequential.
* If a good problem definition hasn't been specified, you might be solving the wrong problem during construction.
* If good requirements work hasn't been done, you might have missed important details of the problem. Requirements changes cost 20 to 100 times as much in the stages following constructdion as they do earlier, so be sure the requirements are right before you start programming.
* If a good architectural design hasn't been done, you might be solving the right problem the wrong way during construction. THe cost of architectdural changes increases as more code is written for the wrong architecture, so be sure the architecture is right, too.
* Understand what approach has been taken to the construction prerequisites on your project, and choose your construction approach accordingly.

## 4. Key Construction Decisions

* Every programming language has strengths and weaknesses. Be aware of the specific strengths and weaknesses of the language you're using.
* Establish programming conventions before you begin programming. It's nearly impossible to change code to match them later.
* More construction practices exist than you can use on any single project. Consciosly choose the practices that are best suited to your project.
* Ask yourself whether the programming practices you're using are a response to the programming language you're using or controlled by it. Remember to program _into_ the language, rather than programming _in_ it.
* Your position on the technology wave determines what approaches will be effective -or even possible. Identify where you are on the technology wave, and adjust your plans and expectations accordingly.

## 5. Design in Construction

* Software's Primary Technical Imperative is _managing complexity_. This is greatly aided by a design focus on simplicity.
* Simplicity is achieved in two general ways: minimizing the amount of essential complexity that anyone's brain has to deal with at any one time, and keeping accidental complexity from proliferating needlessly.
* Design is heuristic. Dogmatic adherence to any single methodology hurts creativiy and hurts your programs.
* Good design is iterative; the more design possibilities you try, the better your final design will be.
* Information hiding is a particularly valuable concept. Asking "What should I hide?" settles many difficult design issues.
* Lots of useful, interesting information on design is available outside this book. The perspectives presented here are just the tip of the iceberg.

## 6. Working Classes

* Class interfaces should provide a consistent abstaction. Many problems arise from violeting this single principle.
* A class interface should hide something - a system interface, a design dcision, or an implementation detail.
* Containment is usually preferable to inheritance unless you're modeling an "is a" relationship.
* Inheritance is a useful tool, but it adds complexity, which is counter to Software's Primary Technical Imperative of managing complexity.
* Classes are your primary tool for managing complexity. Give their design as much attention as needed to accomplish that objective.

## 7. High-Quality Routines

### 7.1 Valid reasons to create a routine

* Reduce complexity,
* Introduce an intermediate, understandable abstraction.
* Avoid duplicate code.
* Support subclassing.
* Hide sequences.
* Hide pointer operations.
* Improve portability.
* Simplify complicated boolean tests.
* Improve performance.
* To ensure all routines are small -> **THIS IS NOT NECESSARY**
* Isolate complexity
* Hide implementation details.
* Limit effects of changes
* Hide global data
* Make central points of control
* Facilitate reusable code
* Accomplish a specific refactoring.

### 7.2 Design at the Routine Level

* Functional cohesion: A routine contains operations that must be performed.
* Sequential cohesion: A routine contains operations that must be performed in _a specific order, that share data from step to step._
* Communicational cohesion: Operations in a routine make use of the same data and aren't related in any other way.
* Temporal cohesion: Operations are combined into a routine because they are all done at the same time. Temporal routines are organizers of other events.
* Procedural cohesion: Operations in a routine are done in a specified order.
* Logical cohesion: One operation is selected by a control flag that's passed in. Instead of having a routine that does all the possible operations, it's better to have several routines, each of which does one distinc operation. It's all right to create a logically cohesive routine if its code consists solely of a series of ir or case statements and calls other routines.

### 7.3 Good Routine Names

* Describe everything the routine does
* Avoid meaningless, vague, or wishy-washy verbs.
* Don't differentiate routine names solely by number.
* Make names of routines as long as necessary
* To name a funciton, use a description of the return value.
* To name a procedure, use a strong verb followed by an object.
* Use opposites precisely.
* Establish conventions for common operations.

### 7.5 How to Use Routine Parameters

* Put parameters in input-modify-output order.
* Consider creating your own in and out keywords.
* If several routines use similar parameters, put the similar parameters in a consistent order.
* Use all the parameters.
* Put status or error variables last.
* Don't use routine parameters as working variables.
* Document interface assumptions about parameters (use _assertions_)
* Limit hte number of a routine's parameters to about seven.
* Consider an input, modify, and output naming convention for parameters.
* Pass the variables or objects that the routine needs to maintain its interface abstraction.
    * If the abstraction expects you to have three specific data elements, and it is only a coincidence that those happen to be provided by the same object, you should pass the three specific data elements individually.
    * If the abstraction is that you will always have that particular object in hand and the routine will do something or other with that object, then you trully do break abstraction when you expose the three specific data elements.
* Using named parameters
* Make sure actual parameters match formal parameters.

### 7.6 Special Considerations in the Use of Functions

* Use a function if the primary purpose of the routine is to return the value indicated by the function name. Otherwise, use a procedure.
* Chack all possible return paths.
* Don't return references or pointers to local data.

## 8. Defensive Programming

In defensive programming, the main idea is that if a routine is passed ba data, it won't be hurt, even if the bad data is another routine's fault.

### 8.1 Protecting your program from invalid Inputs

* Instead of "Garbage in, garbage out", prefer **"Garbage in, nothing out"**, **"Garbage in, error message out"**, **"No garbage allowed"**.
* Make sure that all data falls within the allowable range, numeric values are within tolerances and the strings are short enough to handle (check the values of all data sources).
* Check the values of the routine input parameters.
* Decide how to handle bad input.

### 8.2 Assertions

* Assertion is code that's used during development when an assertion is true, that means everything is operating as expected. When it's false, that means it has detected an unexpected error in the code.
* Use assertions to document assumptions made in the code and to flush out unexpected conditions.
    * Input parameter values falls within its expected range.
    * A file or system is open for read-only, write-only, or both read and write.
    * A pointer is not null.
    * A container is empty when a routine begins executing.
* Your own routines will contain specific assumptions that you can document using assertions.
* Assertions are normally compiled into the code at development time and compiled out of the code at production time.
* Use error-handling code for conditions you expect to occur; use assertions for conditions that should never occur.
* Error handling code checks for off-nominal circumstances that have been anticipated by the programmer.
* Error handling code checks for off-nominal circumstances that have been anticipated by the programmer.
    * Error handling checks for bad input data
    * Assertions check for bugs in the code.
* Error handling will enable the proram to respond to error gracefully. If an assertions is fired for an anomalous condition, the corrective action is to change the programs source code, recompile and release a new version.
* Use assertions to document and verify preconditions and postconditions.
    * Preconditions: Properties that the client code of a routine will be true before it calls the routine.
    * Postconditions: Routine's obligation to the code that uses it.
* A routine will generally use either an assertion or error-handling code, but not both.
* Conditions that should always be true are asserted, but such errors are also handled by error-handling code in case the assertions fails.
* For extremely large, complex, long-lived applications, assertions are valuable because they help to flush out as many development-time errors as possible. But the application is so complex and has gone through so many generations of modification that it isn't realistic to assume that every conceivable error will be detected and corrected before the software ships, so errors must be handled in the production version of the system as well.

### 8.3 Error-Handling Techniques

* Error-handling techniques.
    * Return a neutral value.
    * Substitute the next piece of valid data.
    * Return the same answer as the previous time.
    * Substitute the closest legal value.
    * Log a warning message to a file.
    * Return an error code: some parts might report that an error has been detected and trus that another routine higher up will handle it.
    * Call an error-processing routine/object: Error processing can be centralized, which can make design easier. Tradeoff: Everyone will be coupled to that class.
    * Display an error message wherever the error is encountered: You can spread UI messages a long the entire app.
    * Handle the error in whatever way works best locally. You can spread user interfae code thoughout the system.
    * Shutdown.
* The style of error processing that is most appropriate depends on the kind of software the error occurs in.
    * Correctness: Returning no result is better than returning an inacturate result.
    * Robustness: Always trying to do something that will allow the software to keep operating.
* High-level code handle errors, and low-level code merely report errors.

### 8.4 Exceptions

* If the code in one routine encounters an unexpected condition that it doesn't know how to handle, it throws an exception.
* Exceptions, used judiciously, can reduce complexity. Used imprudently, they can make the code almost impossible to follow.
* Use excepetions to notify other parts of the program about errors that should not be ingored.
* Throw an exception only for conditions that are truly exceptional. Exceptions weaken encapsulation by requiring the code that calls a routine to know which exceptions might be thrown.
* Don't throw an uncaught exception if you can handle the error locally.
* Include in the exception message all the information that led to the exception.
* Avoid empty catch block. If an exception at a lower level really doesn't represent an exception at the level of abstration of the calling routine, at least document by logging a message to a file.
* Know the exceptions your library code throws.
* Consider building a centralized exception reporter. (What kind of exceptions there are, how each exception should be handled, formatting of exception messages).
* Standardize your project's use of exception
    * Consider creating you own project-specific exception class
    * Determine whether a centralized exception reporter will be used.

### 8.5 Barricade your program to contain the damage caused by errors.

* Barricade: Designate certain interfaces as boundaries to "safe" areas.
* Check data crossing the boundaries of a safe area for validity, and respond sensibly if the data isn't valid.
* The class's public methods assume the data is unsafe and they are responsible for checking the data and sanitizing it, once the data has been accepted by the class's public methods, the class's private methods can assume the data is safe.
* Convert input data to the proper form as soon as possible after it's input.
* Routines that are outside the barricade should use error handling because it isn't safe to make any assumptions about the data.
* Routines inside the barricade should use assertions, because the data passed to them is supposed to be sanitized before it's passed across the barricade.

### 8.6 Debugging Aids.

* Be willing to trade speed and resource usage during development in exchange for built-int tools that can make development go more smoothly.
* Make asserts about the prorgam.
* Be sure the code in each case statement's default or else clause fails hard or is impossible to overlook.
* Fail hard during development so that you can fail softer during production.
* Version-control tools can build different versions of a program from the same source files.
* In development mode, you can set the build tool to include all the debug code. In production mode, you can set it to exclude any debug code you don't want in the commercial version.
* If your programming language has a preprocessor, you can include or exclude debug code at the flick of the component switch.

### 8.7 Determining how much defensive programming to leave in production code

* Remove code taht checks for trivial errors.
* Remove code that results in hard crashes: During development, when your program detects an error, you'd like the error to be as noticeable as possible, so that you can fix it. Often, the best way to accomplish that goal is to have the program crash.
* During production, your users need a chance to save their work before the program crashes and they are probably willing to tolerate a few anomalies in exchange for keeping the program going along enough for them to do that.
* Leave in code that helps the program crash gracefully.
* Log errors for your tecnical support personel.
* Make sure that the error messages you leave in are friendly.

### 8.8 Being defensive about defensive programming.

* Think about where you read to be defensive, and set your defensive programming priorities accordingly.

## 9. The Pseudocode Programming Process

### 9.1 Summary of Steps in Building Classes and Routines

* Creating a general design for the class, enumerating specific routines withing the class, constructin specific routines, and checking the class construction as a whole.

#### Steps in Creating a Class

* Degine the class's specific responsibilities, define what "secrets" the class will hide and define exactly what abstractions the class interface will capture. Determine whether the class will be derived from another class and whether other classes will be allowed to derive from it.
* Once you identify the class's major routines, you must construct each specific routines.
* Each routine is tested as it's created. Test the class as a whole, as well.

#### Steps in Building a Routine

* Activities included in creating a routine:
    * Designing the routine
    * Checking the design
    * Coding the routine
    * Checking the code

### 9.2 Pseudocode for Pros

* Avoid syntactic elements from the target programming language. When you use the programming language constructs, you sink to a lower level.
* Describe the meaning of the approach rather than _how_ is going to be implemented.
* Write pseudocode at a low enough level that generating code from it will be nearly automatic.
* The pseudocode must fous on the meaning of the design, rather than how the code will be written.
* Benefits of pseudocode:
    * Pseudocode makes reviews easier. You can review detailed designs without examining source code.
    * Pseudocode supports the idea of iterative refinement.
    * A few lines of pseudocode are easier to change than a page of code.
    * Pseudocode is easier to maintain than other forms of design documentation.

### 9.3 Constructing Routines by Using PPP

#### Design the routine

* Check to see that the job of the routine is well defined and fits cleanly into the overall design.
* State the problem the routine will solve in enough detail to allow creation of the routine.
    * The information the routine will hide
    * Inputs to the routine
    * Outputs from the routine
    * Preconditions that are guaranteed.
    * Postconditions that the routine guarantees.
* Naming the routine
* Design how to test the routine.
* Take a few minutes to look through the code that's already been written and make sure you're not doing more work than necessary.
* Think about all the things that could possible go wrong in the routine. Think about bad input values, invalid returned from other routines and so on.
* In the bast majority of systems, efficiency isn't critical. In the minority of systems, performance is critical. The architecture should indicate how many resources each routine (or class) is allowed to use and how fast it should perform its operations.
* Design the routine so that it will meet its resource and speed goals.
* It's ussually a waste of effort to work on efficiency at the level of individual routines. The big optimizations come from refining the high level design, not the individual routines.
* Before you launch into writting complicated code from scratch, check an algorithms book to see what's already available.
* Write pseudocode. Start with the general, and work toward something more specific.
* Write a concise statement of the purpose of the routine. Express in precise english what the routine needs to do.
* Definitions of key data types are useful to have when you design the logic of a routine.
* Check pseudocode.
* Try a few ideas in pseudocode, and keep the best (iterate).

#### Code the Routine

* Once you've designed the routine, construct it.
* Write the routine declaration.
    * Document any interface assumptions.
* Turn the pseudocode into high-level comments.
* Fill in the code below each comment.
* Check whether code should be further factored.
    * If there's an explosion of code below one of the initial lines of pseudoce:
        * Factor the code below the comment into a new routine.
        * Apply the PPP recoursively.

#### Check the code

* Chck that what you've built is correct.
* One of the biggest differences between hobbyists and professional programmers is the difference that grows out of moving from superstition to understanding. If you often find yourself suspecting that the compiler of the hardware made an error, you're still in the realm of superstition.
* A working routine isn't enough. If you don't know why it works, study it, discuss it, and experiment with alternative designs until you do.
* Avoid the rush to completio by not compiling until you've convinced yourself that the routine is right.
* Once the routine compiles, put it into the debugger and step through each line of code.
* Test the code.
* Remove errors from your routine.
    * Hacks usually indicate incomplete understanding and guarantee errors both now and later.

#### Clean up leftovers

* Check the routine's interface. Make sure that all parameters are used.
* Make sure the routine does one thing and does it well, that it's loosely coupled to other routines, and that it's designed defensively.
* Check for inaccurate variable names, unused objects, undeclared variables, improperly initialized objects and so on.
* Check for off-by-one errors, infinite loops, improper nesting, and resource leaks.

## 10. General Issues in Using Variables

### 10.2 Making Variable Declarations Easy

#### Implicit Declarations.

* Languages that require you to declare data explicitly are, in essence, requiring you to use data more carefully, which is one of their primary advantages. What do you do if you program in a language with implicit declarations?
    * Turn off implicit declarations
    * Declare all variables
    * Use naming conventions
    * Check variable names

### 10.3 Guidelines for initializing variales

* The problems with improper initialization stem from variables containing an initial value that you do not expect it to contain.
    * The variable has never been assigned a value.
    * The value in the variable is outdated.
    * Part of the variable has been a value and part has not.
* Following are guidelines for avoiding initialization problem:
    * Initialize each variable as it's declared.
    * Initialize each variable close to where it's first used.
        * A better practice is to initialize variables as clase as possible to where they're first used.
        * By the time execution of the first example gets to the code that uses "done", "done" could have been modified. If that's not the case, when you first write the program, later modifications might make it so.
        * Throwing all the initializations together creates the impression that all the variables are used throughtout the whole routine -when in fact "done" is used only at the end.
        * Principle of Proximity: keep related actions together.
    * Declare and define each variable close to where it's first used.
        * Ideally, each variable should be defined at the same site it's declared.
        * Use final or const when possible.
        * Reset counters or accumulators before the next time it's used.
        * Initialize a class's member data in its constructor
            * If memory is allocated in the constructor, it should be freed in the destructor.
        * If a variable need to be reinitialized, make sure that the initialization statement is inside the part of the code that is repeated.
        * Initialize true variables in executable code close to where they're used.
            * Variables that are initialized in a program-level start up routine aren't reinitialized the second time through the routine.
        * Before you assign input values to anything, make sure the values are reasonable.

### 10.4 Scope.

* Scope, or visiblity, refers to the extent to which your variables are known and can be referenced throughout a program.
    * A variable with limited or small scope is known in only a small area of the program.
    * A variable with large scope is known in many places in a program.

#### Localize References to Variables

* The code between references to a variable is a "window of vulnerability". In the window, new code might be added, inadvertently altering the variable, or someone reading the coee might forget the value the variable is supposed to contain.
* When you keep references to variables close together, you enable the person reading your code to focus on one section at a time. If the references are far apart, you force the reader to jum around in the program.

#### Keep variables "live" for a short a time as possible.

* A variablee's life begins at the first statement in which it's references; its life ends at the last statement in which its referenced.

* As with the span, the goal with respect to live time is to keep the number low. And as with span, the basic advantege of maintaining a low nuber is that it reduces the window of vulnerability.

* A short live time also reduces the chance of initialization errors. As you modify a program, traigh-line code tends to turn into loops and you tend to forget initializations that were made far away from the loop. By keeping the initialization code and the loop code clase together, you reduce the chance that modifications will introduce initialization errors.

* A short line time makes your code more readable . The fewer lines of coee a reader has to keep in mid at once, the easier your code is to understand.

#### General Guidelines for minimizing Scope

* Initialize variables in a loop immediately before the loop rather than back at the beginning of the routine containing the loop.
    * When you modify the program and put another loop around the initial loop, the initialization will work on each pass through the new loop rather than on only the first pass.
* Don't assign a value to a variable until just before the value is used.
* Group related statements.
    * Put references to variables together so that they are easier to locate.
* Break groups of related statements into separate routines.
* Begin with most restricted visibility, and expand the variable's scope only if necessary.
    * Part of minimizing the scope of a variable is keeping it as local as possible. It's much more difficult to reduce the scope of a variable that has had a large scope, than to expand the scope of a variable that has had a small scope.

#### Comments on Minimizing Scope.

* Maximizing scope might indeed make the program easy to write, but a program in which any routine can use any variable at any time is harder to understand than a program that uses well factored routines. In such a program, you can't understand only one routine; you have to understand all the routines with which that routine shares global data. Such programs are hard to read, hard to debug, and hard to modify.

### 10.5 Persistence

* Some variables persist.
    * For the life of a particular block of code or routine (e.g. variables in a for loop).
    * As long as you allow them (e.g. new and delete)
    * For the life of a program.
    * Forever. These variables might include values that you store in a database between executions of a program.
* Here are a few steps you can take to avoid this kind of problem.
    * Use debug conde or assertions in your program to check critical values for reasonable values.
    * Set variables to "unreasonable values" when you're through with them.
    * Write code that assumes data isn't persistent. For example, if a variable has a certain value when you exit a routine, don't assume it has the same value the next time you enter the routine.
    * Develop the habit of declaring and initializing all data right before it's used.

### 10.6 Binding Time

* Binding time: The time at which the variable and its value are bound together.
* Are they bound together when the code is written? When it is compiled? When it is loaded? When the proggram runs? Some other time?
* Following are the times a variable can be bound to a value:
    * Coding time (use of magical numbers)
    * Compile time (use of named constant)
    * Run time
        1. Load time (read a value from an external source file or property list).
        2. Object instantiation time (reading the value each time the object is created).
        3. Just in time (reading the value each time the object will be used).
* In general, the earlier the binding time, the lower the flexbility and the lower the complexity.
* Beyond that, the greater the flexbility, the higher the complexity at the code needed to support that flexbility and the more error prone the code will be. Because successful programming depends on minimizing complexity, a skilled programmer will build in as much flexibility as needed to meet the software's requirements but will not add flexibility beyond what's required.

### 10.7 Relationship between data types and control structures

* Sequential data translates to sequential statements in a program.
* Selective data translated to if and case statements.
* Iterative data translated to for, repeat and while looping structures in a program.

### 10.8 Using each variable for exactly one purpose

* Use each variable for one purpose only
    * Creating unique variables for each purpose makes your code more readable.
    * Avoid variables with hidden messages
        * **"Hybrid coupling"**: The variable is stretched over two jobs, meaning that the variable is the wrong type for one of the jobs.
        * The variable bytesWritten might be the number of bytes written to an output file, unless its value is negative, in which case it indicates the number of the kisk drive used for the output.
        * The extra clarity you will achieve by using two variables to hold two kinds of information will amaze you.
* Make sure that all declared variables are used.

## 11. The Power of Variable Names

### 11.1 Considerations in Choosing Good Names

* The goodness of badness of a variable is largely determined by its name.
* A good variable name is readable, memorable and appropiate.

#### The most important naming consideration

* The most important consideration in naming a variable is that the name fully and accurately describe the entity the variable represents.

* note two charatcteristics of these names. First, they're easy to decipher. In fact, they don't need to be deciphered at all because you can simply read them. But second, some of the names are long -too long to be practical.



## 12. Fundamental Data Types
## 13. Unusual Data Types
## 14. Organizing Straight-Line Code
## 15. Using COnditionals
## 16. Controlling Loops
## 17. Unusual Control Structures
## 18. Table-Driven Methods
## 19. General Control Issues
## 20. The Software-Quality Landscape
## 21. Collaborative Construction
## 22. Developer Testing
## 23. Debugging
## 24. Refactoring
## 25. Code-Tuning Strategies
## 26. Code-Tuning Techniques
## 27. How Program Size Affects Construction
## 28. Managing Construction
## 29. Integration
## 30. Programming Tools
## 31. Layout and Style
## 32. Self-Documenting Code
## 33. Personal Character
## 34. Themes in Software Craftsmanship
## 35. Where to Find More Information




