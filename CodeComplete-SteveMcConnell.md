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

* Note two charatcteristics of these names. First, they're easy to decipher. In fact, they don't need to be deciphered at all because you can simply read them. But second, some of the names are long -too long to be practical.

* Names should be as specific as possible. Names like "X", "temp" and "i" that are general enough to be used for more than one purpose are not as informative as they could be and are ussually bad names.

#### Problem Orientation

* A good mnemonic name generally speaks to the problem rather than the solution. A good name tends to express the _what_ more than the _how_.

* A record of employee data could be called "inputRect" or "employee". "inputRec" is a computer term that refers to computing ideas. "employee" refers to the problem, rather than the computer universe.

#### Optimum Name Length

* Names that are too short don't convey enough meaning.
* Names that are too long are hard to type and can obscrure the visual structure of the program.
* The effort required to debug a program was minimized when variables had names that averaged 10 to 16 characters. Programs with names averaging 9 to 20 characters were almost easy to debug.
* If you look over your code and see many names that are shorter, you should check to be sure that the names are as clear as they need to be.

#### The Effect of Scope on Variable Names

* When you give a variable a short name like "i", the length itself says something about the variable-namely, that the variable is a scrtch value with a limited scope of operation.
* A programmer reading such a variable should be able to assume that its value isn't used outside a few lines of code.
* Short names are subject to many problems, however, and some careful programmers avoid them altogether as a matter of defensive-programming policy.
* Use qualifiers on names that are in the global namespace:
    * If you have variables that are in the global namespace, cosider whether you need to adopt a convention for partitioning the global namespace and avoiding naming conflicts.
    * You can accomplish the same thing by using packages.

#### Computed-Value qualifiers in variable names

* If you modify a name with a qualifier like "Total", "Sum", "Average", "Max", "Min", "Record", "String" or "Pointer", put the modifier at the end of the name.
* The most significant part of the variable name, the part that gives the variable most meaning, is at the front, so it's most prominent and gets read first.
* The names are semantically equivalen, and the convention would prevent their being used as if they were different.
* The consistency improves readability and eases maintenance.
* Because using "Num" so often creates confusion, it's probably best to side-step the whole issue, by using "count" or "total" to refer to a total number of customers and "index" to refer to a specific customer. Thus "customCount" is the total number of customers and "customIndex" refers to a specific customer".

#### Common Opposites in Variable Names

* Use opposites precisely. Using naming conventions for opposites helps consistency which helps readability. Here are some common opposites:
    * begin/end
    * first/last
    * lock/unlock
    * min/max
    * next/previous
    * old/new
    * open/close
    * visible/invisible
    * source/target
    * source/destination
    * up/down

### 11.2 Naming Specific Types of Data

#### Naming Loop Indexes

* The names "i", "j" and "k" are customary.
* If a variable is to be used outside the loop, it should be given a name more meaningful than a few lines, it's easy to forget what "i" is supposed to stand for and you're better off giving the loop index a more meaningful name.
* Because code is so often changed, expanded and copied into other programs, many experienced programmers avoid names like "i" altogether.
* If you have several nested loops, asign longer names to the lop variables to improve readability.
* Carefully chosen names for loop-index variables avoid the common problem of index cross-talking. They also make array accesses clearer.
* If you have to use "i", "j" and "k", don't use them for anything other than loop indexes for simple loops - the convention is too well established, and breaking it to use them in other ways is confusing.

#### Naming Status Variables

* A flag should never have "flag" in its name because that doesn't give you any clue about what the flag does. For clarity, flags should be assigned values and their values sshould be tested with enumerated types, named constants or global variables that act as named constants.

#### Naming Temporary Variables

* Temporary variables are used to hold intermediate results of calculations, as temporary placeholders and to hold housekeeping values.
* In one way or another, most of the variables in your program are temporary. Calling a few of them temporary may indicate that you aren't sure of their real purposes.

#### Naming Boolean Variables

* Keep typical boolean names in mind
    * Done (something is done)
    * Error (an error has occurred)
    * Found (a value has been found)
    * Success (An operation has been successful.)
        * If you can, replace "success" with a more specific name that describes precisely what it means to be successful.
* Give boolean variables names that imply true or false
    * Names like status and sourceFile are poor boolean names because they are not obviously true or false.
    * Some programmers like to put "is" in front of their boolean names, then the variable becomes a question.
        * A benefit of this approach is that it won't work with vague names. IsStatus? makes no sense at all.
        * A drawback is that it makes simple logical expressions less readable: `if (isFound)` is slightly less readable than `if (found)`.
* Use possitive boolean variable names.

#### Naming Enumerated Types

* In some languages, enumerated types are treated more like classes, and the members of the enumeration are always prefixed with the enum name, like `Color.Color_Red` or `Planet.Planet_Earth`. In that case, it makes little sense to repeat the prefix.

#### Naming Constants

* When naming constants, name the abstract entity the constant represents rather than the number the constant refers to.

### 11.3 The Power of Naming Convention

#### Why Have Conventions?

* By making one global decision rather than many local ones, you can concentrate on the more important characteristics of the code.
* They help you transfer knowledge across projects.
* They help you learn code more quickly on a new project. All team mebers must write the same uniform/consisten code.
* They reduce name proliferation. Without naming conventions, you can easily call the same thing by two different names.
* They compensate for language weaknesses.
* They emphasize relationships among related items. Programming conventions can make up for the weakness of the language you're using.
* The key is that any convention at all is often better than no convention.


#### When you should have a naming convention

* When multiple programmers are working on a project.
* When you plan to turn a program over to another programmer for modifications and maintenance.
* When your programs are revieweed by other programmers in your organization.
* When your program is so large that you can't hold the whole thing in your brain at once and must think about it in pieces.
* When the program will be long-lived enough that you might put it aside for a few weeks or months before working on it again.
* When you have a lot of unusual terms that are common on aproject and want to have standard terms or abbreviations to use in coding.

#### Degrees of Formality

* The degree of formality you need is dependent on the number of people working on a program, the size of the program, and the program's expected life span.

### 11.4 Informal Naming Conventions

#### Guidelines for a Language-Independent Convention

* Differentiate between variable names and routine names.
    * Begin variable and object names with lower case and routine names with uppercase.
* Differentiate between classes and objects (types and variables)
    * Via initial capitalization
    * Via all caps.
    * Via "t_" prefix for types.
    * Via "a" prefix for variables.
    * Via using more specific names for variables.
* Identify global variables
    * Give all global variable names a "g_" prefix
* Identify member variables
    * Identify class member variables with an "m_" prefix.
* Identify type definitions
    * Explicitly identify a name as a type name, and avoid naming classes with variables.
    * You can prefix the type names with "t_", such as "t_Color".
* Identify named constants
    * Use a prefix like "c_"
    * Use all uppercase letters, possibly with underscores to separate words.
* Identify elements of enumerated types
    * You can use all caps or an "e_" or "E_" prefix for the name of the type itself.
    * Use a prefix based on the specific type like "Color_" or "Planet_" for the members of the type.
* Identify input-only parameters in languages that don't enforce them
    * If you modify an input variable, it is returned whether you like it or not. This is specially true when passing objects.
    * If you establish a naming convention in which input-only parameters are given a "const" prefix, you will know that an error has ocurred when you see anything with a "const" prefix on the left side of the equal sign.
* Format names to enhance readability
    * You can use capitalization and spacing characters to separate words.
    * Try not to mix these tecniques; that makes the code hard to read.
    * As long as you and your team are consistent, it doesn't matter whether the first character in a name should be capitalized.

#### Guidelines for language-specific conventions

##### C conventions

* Variable and routine names are in `all_lowercase`.
* The underscore (_) character is used as a separator.

##### C++ Conventions

* Constants, typedefs, and preprocessor macros are in `ALL_CAPS`.
* Variable and function names use lowercase for the first word, with the first letter at each following word capitalized.
* Underscore is not used as separator within names, except for names in all caps and certain kinds of prefixes.

##### Java Conventions

* Constants are `ALL_CAPS`.
* Class and interfaces names capitalize the first letter of each word, including the first word.
* Variable and method names use lowercase for the first word, and capitalize the first letter of the following words.
* The underscore is not used.
* Get and set prefixes are used as accessor methods.

##### Mixed-language Programming Conventions

* When programming in a mixed-language environment, the naming conventions can be optimized for overall consistency and readability.
* Even if that means going against conventions for one of the languages that's part of the mix.

### 11.5 Standardized Prefixes

* Standardized prefixes are composed of two parts: the used-defined type (UDT) abbreviation and the semantic prefix.

#### User-Defined Type Abbreviations

* The UDT abbreviation identifies the data type of the object or variable being named.
* A UDT abbreviation doesn't refer to any of the predefined data types offered by the programming language.
* UDTs are described with short codes that you create for a specific program and then standardize on for use in that program.
    * e.g. "wn" for "window", or "scr" for "screen region".

#### Semantic Prefixes

* Describe how the variables or object is used.
* Semantic prefixes are somewhat standard across projects.
    * c: count
    * first
    * g: global variable
    * i: index
    * last
    * lim: upper limit. "lim" is not a valid index. Generally `lim=last+1`.
    * m: class member variable
    * max
    * min
* Semantic prefixes are combined with the UDT, and are formatted in lowercase or mixed uppercase and lowercase.
* e.g. The paragraph count would be cPa.
* If iPa unambiguosly designates an index into an array of paragraphs, it's tempting not to make the name more meaningful like `ipaActiveDocument`. For readability, come up with a descriptive name.

### 11.6 Creating Short Names that Are Readable

* In modern languages, you can create names of virtually any length; you have almost no reason to shorten meaningful names.

#### General Abbreviation Guidelines

* Use standard abbreviations
* Remove all non leading vowel ("computer" becomes "cmptr")
* Remove articles: "and", "or", "the".
* Use first few letters of each word.
* Use every significant word in the name, up to a maximum of three words.
* Remove useless suffixes, -ing, -ed.
* Be sure not to change the meaning of the variable.

#### Phonetic Abbreviations

* it's not recommended to abbreviate based on the sound of the words, rather than the spelling.

#### Comments on Abbreviations

* Don't abbreviate by removing one character froma word
    * Instead of "Jun" or "Jul", write "June" or "July", respectively.
* Abbreviate consistently.
* Create names that you can pronounce
    * If you can't read your code to someone over the phone, rename your variables to be more distinctive.
* Avoid combinations that result in misreading or mispronunciation
    * To refer to the end of B, favor ENDB over BEND.
* Use a thesaurus to resolve naming collisions.
* Document extremely short names with translation tables in the code.
    * Include a translation table to provide a reminder of the mnemonic content of the variables.
* Documnt all abbreviations in a project-level "standard abbreviation" document.
* Abbreviations in code create two general risks:
    * A reader of the code might not understand the abbreviation
    * Other programmers might use multiple abbreviations to refer to the same word, which creates needless confusion.
* You can create a "Standard Abbreeviation" document that captures all the coding abbreviations used on your project.
    * The document is checked into version control and checked out anytime anyone creates a new abbreviation in the code. Entries in the document should be sorted by the full word, not the abbreviation.
    * The fact that a programmer can't create a new abbreviation without the overhead of checking the standard abbreviations document is a good thing. It means that an abbreviation won't be created unless it's so common that it's wordth the hassle of documenting it.
    * This approach addresses the second risk by reducing inconvenience, but programmers over the lifetime of a system spend far more time reading code than writting code. This approach increases read-time convenience.
* Remember that names matter more to the reader of the code than to the writter.

### 11.7 Kind of Names to Avoid

* Avoid misleading names or abbreviations
* Avoid names with similar meanings
* Avoid variables with different meanings but similar names.
    * Avoid names like "clientRects" and "clientReps".
* Avoid names that sound similar, such as "wrap" and "rap"
* Avoid numerals in names.
    * If the numerals in a name are really significant, use an array instead of separate variables.
* Avoid mispelled words in names.
* Avoid words that are commonly misspelled in english.
* Don't differentiate variable names solely by capitalization.
* Avoid multiple natural languages.
* Avoid the names of standard types, variables and routines.
    * Do not use "if", "else", and "then" as variable names.
* Don't use names that are totally unrelated to what the variables represent.
* Avoid names containing hard-to-read characters:
    * Pais that are hard to distinguish include (l and 1), (l and I), (0 and O), (2 and Z), (S and 5), (6 and G).

## 12. Fundamental Data Types

### 12.1 Numbers in General

* Avoid "magic numbers"
    * Magic numbers are literal numbers, such as 100 or 47592, that appear in the middle of a program without explanation.
    * Avoiding magic numbers yields three advantages
        * Changes can be made more reliably
        * Changes can be made more easily
        * Your code is more readable
* Use hard coded 0s and 1s if you need to
    * The values 0 and 1 are used to increment, decrement, and start loops at the first element of an array.
    * The only literals that should occur in the body of a program are 0 and 1.
* Anticipate divide-by-zero errors
    * Each time you use the division symbol, think about thether it's possible for the denominator of the expression to be 0. If the possiblity exists, write code to prevent a divide-by-zero error.
* Make type conversions obvious.
* Avoid mixed type comparisons.
* Many modern compilers tell you when you have different numeric types in the same expression

### 12.2 Integers

* Check for integer division
    * When you're using integers, 7/10 doesn't equal 0.7, but usually equals 0.
* Check for integer overflow.
    * Be aware of the largest possible integer, when doing integer multiplication or addition.
    * The easiest way to prevent integer overflow is to think through each of the terms in your arithmetic expression and try to imagine the largest value each can assume.
* Check for overflow in intermediate results
    * `(1_000_000 * 1_000_000 / 1_000_000) = -727_379_968 / 1_000_000 = -727`.
    * You can handle overflow in intermediate results the same way you handle integer overflow, by switching to a long-integer or floating-point type.

### 12.3 Floating-Point Numbers

* The main consideration in using floating-point numbers is that many fractional decimal numbers can't be represented accurately using hte 1s and 0s available on a digital computer.
* Avoid additions and subtractions on numbers that have greatly different magnitudes.
    * With a 32-bit floating point variable, `1_000_000 + 0.1` probably produces an answer of `1_000_000` because 32 bits don't give you enough significant digits to encompass the range.
    * If you have a sequence of numbers that contains huge differences like this, sort the numbers first, and then add them starting with the smallest values.
* Avoid equality comparisons
    * One effective approach is to determine a range of accuracy that is acceptable and then use a boolean function to determine whether the values are close enough.
    *Typically, you'd write an `Equals()` funciton that returns `true` if the values are close enough and `false` otherwise.
* Anticipate rounding errors
    * Change to a variable type that has greater precision
    * Change to binary coded decimal (BCD) variables
    * Change from floating-point to integer variables
        * You can make these manipulations easier by creating a class that hides the integer representation and supports the necessary numeric operations.
* Some languages, including Visual Basic, have data types such as `Currency` that specifically support data that is sensitive to rounding errors. If your language has a built-in data type that proviedes such functionality, use it.

#### 12.4 Characters and Strings

* Avoid magic characters and strings. Use named constants instead.
    * It's easier to translate strings that are grouped in a string resource file.
    * String literals tend to take up a lot of space.
    * Character and string literals are cryptic. Comments or named constants clarify your intentions.
* Know how your language and environment supports Unicode.
* Decide on an internationalization / localization strategy early in the lifetime of a program.
* If you know you only need to support a single alphabetic language, consider using an ISO 8859 character set.
* If you need to support multiple languages, use Unicode.
* Decide on a consistent conversion strategy among string types
    * Keep all the strings in a single format within the program.

#### 12.5 Boolean Variables

* Instead of merely tsting a boolean expression, you can assign the expression to a variable that makes the implication of the test unmistakable.
* By creating some boolean variables for testing, you make the "if" test simpler: easier to read, less error prone, and easier to modify.
* Create you own boolean type, if necessary.

#### 12.6 Enumerated Types

* Enumerated types are generally used when you know all the possible values of a variable and want to express them in words.
* Use enumerated types for readability:
    * Anytime you see a numeric literal, ask whether it makes sense to replace it with an enumerated type.
    * Enumerated types are especially useful for defining routine parameters.
* With named constants, the compiler has no way of knowing that the only legal values are Color_Red, Color_Blue, and Color_Green.
* Enumerated types make your code easy to modify. You can continue adding elements to the list just by putting them into the type of definition and recompiling.
* Use enumerated types are an alternative to boolean variables. Often a boolean variable isn't rich enough to express the meanings it needs to.
* When you test an enumerated type in an `if` or `case` statement, check for invalid values. Use the `else` clause in a `case` statement to trap invalid values.
* Define the first and last entries of an enumeration for use as loop limits.
* Reserve the first entry in the enumerated type as invalid.
* Define precisely how First and Last elements are to be used in the project coding standard, and use them consistently.
* Beware of pitfalls of assigning explicit values to elements of an enumeration. (One element is assigned a 1, and the next is assigned a 3. This might lead to an error in a for loop).
* If your language doesn't have enumerated types, you can simulate them with global variables or classes.

#### 12.7 Named Constants

* Named constants enable you to refer to fixed quantities, by a name rather than a number - `MAXIMUM_EMPLOYEES` rather than `1000`, for instance.
* Using a named constant is a way of "parameterizing" your program:
    * Putting an aspect of your program that might change into a parameter that you can change in one place rather than having to make changes throughout the program.
    * Using named constants helps program readability and maintainability in data declarations.
    * As a general rule, any technique that centralizes control over things that might change is a good technique for reducing maintenance efforts.
    * Avoid literal, even "save" ones.
    * If your language doesn't support named constants, you can create your own. Simulate named constants with approriately scoped variables or classes.
    * Use named constants consistently.

#### 12.8 Arrays

* Make sure that all array indexes are within the bounds of the array.
* Consider using container classes that you can access sequentially -sets, stacks, queues, and so on- as alternatives beore you automatically choose an array.
* Ask yourself whether the code correctly accesses the first/last element of the array or mistakenly accesses the element before or after the first/last element.
* If an array is multidimensional, make sure its subscripts are used in the correct order.
    * Consider using more meaningful names than `i` and `j` in cases in which their roles aren't immediately clear.
    * Watch out for index cross-talking
        * Switching loop indexes is called "index cross-talk".

#### 12.9 Creating your own types (type aliasing)

* Programmer-defined data types protect your program against unforseen changes and make it easier to read -all without requiring you to design, construct, or test new classes.
* Reasons to create your own types:
    * To make modifications easier.
    * To avoid excesive information distribution
    * To increase reliability
    * To make up for language weakness

##### Guidelines for Creating your own types

* Use type names that refer to the parts of the real-world problem that the new type represents.
* The big advantage of creating your own type is that it provides a layer of insulation between your program and the implementation language
    * Problem-oriented names buy you easy modifiability and data declarations that are self-documenting.
* If there is any possibility that a type might change, avoid using predefined types anywhere but in `typedef` or `type` definitions.
* Use of functionally oriented type declarations partially documents the variables declared with them.
* Don't redefine a predefined type.
* Simple `typedefs` can go a long way toward hiding information about a variable's underlying type. In some cases, however, you might want the additional flexibilty and control you'll achive by creating a class.

## 13. Unusual Data Types

### 13.1 Structures

* THe term "structure" refers to data that's build up from other types.
* Use structures to clarify data relationships.
    * Structures bundle groups of related items together.
* Use structures to simplify operations on blocks of data
    * It's easier to operate on the structure than to perform the same operation on each of the elements. It's also more reliable, and it takes fewer lines of code.
    * If you ever add a new piece of data to the set of related information, you have to find every place at which you have a block of assignments and add an assignment for that new data.
* Use structures to simplify parameter lists
    * Rather than passing each of the elements needed individually, you can group related elements into a structure and pass the whole enchulada as a group structure.
    * Careful programmers avoid passing a structure as a parameter when only one or two fields from the structure are needed -they pass the specific field instead.
    * Some information is hidden in routines, and some is hidden from routines.
* Use structures to reduce maintenance
    * Because you group related data when you use structures, chaning a structure requires fewer changes throughout a program.
    * If your employee strcutre has a title fields and you decide to delete it, you don't need to change any of the parameter lists or assignments that use the whole structure.
    * Individual components, such as the "title" field, are referenced merely because they are part of the collection. Such sections of code don't have any logical reason to work with the title field specifically, and those sections are easy to overlook when you change "title".

### 13.3 Global Data

* Global variables are accessible anywhere in a program. THe term is also sometimes used sloppily to refer to variables with a broader scope than local variables - such as class variables that are accessible anywhere within a class. But accessibility anywhere within a single class does not by itself mean that a variable is global.

#### Common Problems with Global Data

* You might change the value of a global variable in one place and mistakenly think that it has remained unchanged somewhere else.
* "Aliasing" refers to calling the same variable by two or more different names. This happens when a global variable is passed to a routine and then used byu the routine as a global variable and as a parameter.
* Multithread code created the possibility that global data will be shared not only among routines, but among different copies of the same program. In such an environment, you have to make sure that global data keeps its meaning even when multiple copies of a program are running.
* If the class you want to reuse reads or writes global data, you can't just plug it into the new program. You have to modify the new program or the old class so that they're compatible.
* If the initialization of a global variable in one file uses a global variable that was initialized in a different file, all bets are off on the second variable's value unless you take explicit steps to ensure the two variables are initialized in the right sequence.
* Global data pokes holes in your ability to modularize. If you use global data, can you concentrate on one routine at a time? No. You have to concentrate on one routine and every other routine that uses the same global data.

#### Reasons to Use Global Data

* Sometimes you have data that applies conceptually to your whole program. This might be a variable that reflects the state of a program, or it might be information that's needed throughout a proggram.
* You can use global variables as substitutes for named constants when your language doesn't support them.
* The disciplined use of global data is a prime example of the distinction between programming in vs. programming into a language.
* Use global variables to emulate enumerated types.
* Sometimes you have so many references to a variables that it appears in the parameter list of every routine you write. Rather than including it in every parameter list, you can make it a global variable.
    * If the data is accessed by a limited set of routines, you can package into a class with the data they work on.
* Sometimes you pass data to a routine or class merely so that it can be passed to another routine or class. When the routine in the middle of the call chain doesn't use the object, the object is called "tramp data".

#### Use Global Data as a Last Resort

* Begin by making each variable local and make variables global only as you need to.
* Some variables are truly global. Others are really class variables, used heavily only within a certain set of routines.
    * If routines outside the class need to use it, provide the variable's value by means of an access routine. Don't access class values directly.
* Use access routines.

#### Using Access ROutines Instead of Global Data

* You can use access routines to centralize control over your data and to protect yourself against changes.

##### Advantages of Access Routines

* You get centralized control over the data.
* You can ensure that all references to the variables are barricaded.
* You get the general benefits of information hiding automatically.
* Access routines are easy to convert to an abstract data type.

##### How to Use Access Routines

* Summary:
    1. Hide data in a class
    2. Declare that data by using the static keyword or its equivalent to ensure that only a single instance of the data exists.
    3. Write routines that let you look at the data and change it.
    4. Require code outside the class to use the access routines rather than working directly with the data.
* Require all code to go through the access routines for the data.
* As long as you're writing routines, take a moment to think about which class each global variable belongs in and then package the data and its access routines in that class.
* Similar to concurrency control in a multiuser database environments, locking requires that before the value of a global variable can be used or updated, the variable must be "checked out". After the variable is used, it's checked back in. During the time it's in use, if some other part of the program tries to check it out, the lock/unlock routine displays an error message or fires an assertion.
* Build access routines at the level of the problem domain, rather than at the level of the implementation details.
* Keep all access to the data at the same level of abstraction.
    * If you use an access routine to do one thing to a structure, you should use an access routine to do everything else to it too.

##### How to Reduce the Risks of Using Global Data

* In most instances, global data is really class data for a class that hasn't been designed or implemented very well.
    * In a few instances, data really needs to be global, but accesses to it can be wrapped with access routines to minimize potential problems.
    * In a tiny number of remaining instances, you really need to use global data.
    * Develop a naming convention to make global variables obvios.
    * Create a well-annotated list of all your global variables.
    * Don't use global variables to contain intermediate results.
    * Don't pretend you're not using global data by tutting all your data into a monster object and passing it everywhere.

## 14. Organizing Straight-Line Code

### 14.1 Statements That Must Be in a Specific Order

* The easiest sequential statements to order are those in which the order counts, because there is any kind of dependency between the statements.
* When statements have dependencies that require you to put them in a certain order, take steps to make the dependencies clear.
* Organize code so that dependencies are obvious.
    * Why should initialization be done in a given routine instead of one of the others? Unlessyou can think of a good reason, you should write another ruotine, `InitializeData()`, to initialize the member data. The routine's name is a clear indication that it should be called before the other routines.
* Name routines so that dependencies are obvious.
* Use routine parameters to make dependencies obvious.
    * A better approach might be to convert the routines to functions that take `expenseData` as inputs and return updated `expenseData` as outputs, which makes it even clearer that the code includes order dependencies.
* Document unclear dependencies with comments.
* Check for dependencies with assertions or error-handling code:
    * If the codee is critical enough, use status variables and error-handling code or assertions to document critical sequential dependencies.
    * This tecnique creates new code, which creates additional possibilities for error. The benefits of this technique should be weighted against the additional complexity and increased chance of secondary errors that this technique creates.

### 14.2 Statements Whose Order Doesn't Matter.

* Principle of Proximity: _Keep related actions together_.

#### Making Code Read from Top to Bottom

* Make the program read from top to bottom rather than jumping around.
* References to each object are kept close together; they are "localized". The number of lines of code in which the objects are "live" is small. And perhaps most important, the code now looks as if it could be broken into separate routines for marketing, sales and travel data.

#### Grouping Related Statements

* Put related statements together. THey can be related because they operate on the same data, perform similar tasks, or depend on each other's being performed in order.

## 15. Using COnditionals

* A conditional statement controls the execution of other statements; execution of other statements is "conditioned" on statements such as "if", "else", "switch" and "case.

### 15.1 If statements

#### Plain If-then statements

* Write the nominal path through the code first; then write the unusual cases.
* Make sure that you branch correctly on equality.
* Put the normal case after the "if" rather than after the "else".
    * Try not to mix the nominal cases and the error cases together.
    * If the error conditions are sometimes processed in the "if" clause rather than the "else" clause, then it will be hard to figure out which "if" test the normal case goes with.
* Follow the "if" clause with a meaningful statement
    * Instead of having an empty "if" clause, negate the predictae in the "if" statement, move the code from the else clause to the if clause, and eliminate the else clause.
* Consider the else clause
    * When you have an "if" test without an else, unless the reason is obvious, use comments to explain why the else clause isn't necessary.
* Test the else clause for correctness.

#### Chains of if-then-else statements

* Simplify complicated tests with boolean function calls.
* Put the most common cases first
    * You improve efficiency because you minimize the number of tests the code does to find the most common cases.
* Make sure that all cases are covered.
    * Code a final "else" clause with an error message or assertion to catch cases you didn't plan for.
* Replace if-then-else chains with other constructs if your languages supports them.

### 15.2 Case statements

#### Choosing the Most Effective Ordering of Cases

* Order cases alphabetically or numerically, if cases are equally important.
* If you have one normal case and several exceptions, put the normal case first.
* Put the most frequently executed cases first and the least frequently executed last.

#### Tips for Using "case" statements

* If the actions performed for a case are complicated, write a routine and call the routine from the case, rather than putting the code into the case itself.
* A case statement should be used for simple data that's easily categorized. If your data isn't simple, use chains of if-then-elses instead.
* If you have one case remaining, don't code it as the default case.
    * You lose the automatic documentation provided by case staement labels, and you lose the ability to detect errors.
* If the default clause in a case statement isn't being used for other processing and isn't supposed to occur, put a diagnostic message in it.
* Avoid dropping through the end of a case statement.
* If you intentionally write code to drop through the end of a case, clearly comment the place at which it happens and explain why it needs to be coded that way.

## 16 Controlling Loops.

### 16.1 Selecting the Kind of Loop

* Types:
    * Counted loop is performed a specific number of times
    * Continuosly evaluated loop doesn't know ahead how many times it will be executed and tests whether it ahs finished in each iteraction
    * Endless loop executes forever
    * Iterator loop performs its action for each element in a container class.
* If the loop is tested at the beginning, its body isn't necessarily executed. If the loop is tested at the end, its body is executed at least once. If the loop is tested in the middle, the preceeding part is executed at least once, but the other part that follows isn't necessarily tested.

#### When to Use a while loop.

* The test for the loop exit is performed only once each time through the loop, and the main issue with respect to while loop is deciding whether to test at the beginning or the end of the loop.

#### When to Use a Loop-with-exit loop.

* The exit condition of a loop appeaers in the middle of the loop rather that at the beginning or at the end.
* You can emulate it with the structured constructs while and break.

#### Normal Loop-with-exit loops

* A typical use of a loop-with-exit loop is for the case in which testing at the beginning or at the end of the loop requires coding a loop-and-a-half.
* Put all the conditions in one place. Spreading them around practically guarantees that one exit condition or another will be overlooked during debugging, modification, or testing.
* In common practice, the loop-with-exit isn't widely used yet.

#### When to Use a For Loop

* A for loop is a good choice when you need a loop that executes a specific number of times.
* Use for loops for simple activities that don't require internal lop controls. Use them when the loop controls involves simple increments or simple decrements, such as iterating through the elements in a ontainer.
* If you have a condition under which execution has to jump out of a loop, use a while loop instead.
* Likewise, don't explicitly change the index value of a for loop to force it to terminate. Use a while loop instead. The for loop is for simple uses. Most complicated looping tasks are better handled by a while loop.

#### When to Use a Foreach loop

* The foreach loop or its equivalent is useful for performing an operation on each member of a collection.
* It has the advantage of eliminating loop-housekeeping arithmetic.

### 16.2 Controlling the Loop.

* To forstall most of the problems of a loop, you have to follow two practices:
    1. Minimize the number of factors that affect the lop
    2. Treat the inside of the loop as if it were a routine. - keep as much of the control as possible outside the loop. Explicitly state the conditions under which the body of the loop is to be executed. Don't make the reader look inside the loop to understand the loop control.

#### Entering the Loop

* Enter the loop from one location only.
* Put initialization code directly before the loop.
* Use `while(true)` for infinite loop.
* Prefer for loops when they're appropriate.
    * In a for loop, all the relevant code is together at the top of the loop, which makes correct modifications easier.
* Don't use a `for` loop when a `while` loop is more appropriate.
    * Reserve the for loop header for loop-control statements - statements that initialize the loop, terminate it, or move it toward termination.
    * If you want to use the `for` loop rather than the while loop, put the loop-control statements in the loop header and leave everything else out.

#### Processing the Middle of the Loop

* Use code brackets to enclose the statements in a loop, EVERY TIME.
* Avoid empty loops.
    * Do not code the work the loop is doing on the same line as the test that checks whether the work is finished.
* Keep look-householding chores at either the beginning or the end of the loop.
    * Loop housekeeping chores are expressions, whose main purpose isn't to do the work of the loop, but to control the loop.
* Make each loop perform only one function.
    * Loops should be like routines in that each one should do only one thing and do it well.

#### Exiting the loop

* Assure yourself that the loop ends.
* Make loop-termination conditions obvios.
    * If you use a while loop and put all the contorl in the while clause, the termination condition will be obvious.
    * If you use a for loop and don't use break to get out of the loop, the termination condition will be obvious.
    * The key is putting the control in one place.
* Don't monkey with the loop index of a for loop to make the loop terminate.
* Avoid code that depends on the loop index's final value.
    * It's better form and more self-documenting if you assign the final value to a variable at the approapriate point inside the loop.
    * Consider using safety pointers
        * A safety counter is a variable you increment each pass through a loop to determine whether a loop has been executed too many times. If you have a program in which an error would be catastrophic, you can use safety counters to ensure that all loops end.

#### Exiting Loops Early

* The `break` statement (or equivalent) causes a loop to terminate through the normal exit channel; the program resumes execution at the first statement following the loop.
* Rather than cousing a loop exit, however, `continue` causes the program to skip the loop body and continue executing at the beginning of the next iteration of the loop.
* Consider using break statements rather than boolean flags in a while loop.
* A loop's containing a lot of breaks can indicate unclear thinking about the lop or its role in the surrounding code.
* Use continue for tests at the top of a loop.
* Use the labeled break structure if your language supports it.
* Use break and continue only with caution.
    * Use of break eliminates the possibility of treating a loop as a black box.

#### Checking Endpoints

* When you create a loop, mentally run through the first, middle, and last cases, to make sure that the loop doesn't have any off-by-one errors. If you have any special cases that are different from the first or last case, check those too.
* The mental discipline results in fewer errors during initial coding, in more rapid detection of errors during debugging and in better overall understanding of the program.
* The mental exercise means that you understand how your code works rather than guessing about it.


#### Using loop variables

* Loop counters should be integer values.
* Use meaningful variable names to make nested loops readable.
    * If you have a one-dimensional array, you omight be able to get away with `i`, `j`, or `k` to index it. But if you have an array with two or more dimensions, you should use meaningful index names to clarify what you're doing.
* Use meaningful names to avoid loop-index cross-talk.
* Limit the scope of loop-index cross-talk.
* Limit the scope of loop-index variables to the loop itself.

#### How long should a loop be?

* Make your loops short enough to view all at once.
* Limit nesting to three levels
    * If you're going beyond that number of levels, make the loop shorter by breaking part of it into a routine or simplifying the control structure.
* If the loop is well designed, the code of the inside can often be moved into one or more routines that are called from within the loop.
* Make long loops especially clear.
    * If you write a short loop, you can use `break` or `continue`.
    * If you write a longer loop, you'll give the loop a single exit and make the exit condition unmistakely clear.

### 16.3 Creating loops easily -from the inside out

* Start with one case. Then indent it, put a loop around it, and replace the literals with loop indexes or computed expresions. Put another loop around that, if necessary. When you finish, add all the necessary initializations.

### 16.4 Correspondence between loops and arrays

* In many instances, a loop is created to perform an array manipulation.
* You do some programming to solve a problem. The language you use to solve a problem substantially affects your solutions.

## 17. Unusual Control Structures

### 17.1 Multiple Returns from a Routine

* THe `return` statement is a ontrol construct that enables a program to exit frorm a routine at will. It causes the routine to terminate through the normal exit channel, returning control to the calling routine.
* Use a `return` when it enhances readability.
    * In certain routines, once you know the answer, you want to return it to the calling routine immediately.
    * Use guard clauses (early returns or exits) to simplify complex error processing.
    * Minimize the number of returns in each routine.

### 17.2 Recursion

* Recursion is usually called into play when a small part of the problem is easy to solve, and a large part is easy to decompose into smaller pieces.
* Recursion isn't useful often, but when used judiciously, it produces elegant solutions.
* For a small group of problems, recursion can produce simple elegant solutions. For a slightly larger group of problems, it can produce simple, elegant, hard-to-understand solutions. For most problems, it produces massively complicated solutions - in those cases, simple iteration is usually more understandable.
* One key aim in writing a recursive routine is the prevention of infinite recursion.
* Most people experience some initial discomfort using recursion because it's self-referential.

#### Tips for Using Recursion

* Make sure the recursion stops.
* Use safety counters to prevent infinite recursion
* Limit recursion to one routine:
    * Cyclic recursion (A calls B calls C calls A) is dangerous becase it's hard to detect.
    * If you have a cyclic recursion, you can usually redesign the routines so that recursion is restricted to a single routine.
* Keep an eye on the stack
    * Watch for allocation of local variables in recursive functions, especially memory-intense objects. In other words, use `new` to create objects on the heap rather than letting the compiler create auto objects on the stack.
* Don't use recursion for factorials or fibonacci numbers.
* You should consider alternatives to recursion before using it. You can do anything with stacks and iteraction that you can do with recursion.

### 17.3 Goto

#### The Argument Against gogo

* Use of gotyos defeats compiler optimizations. Some optimizations depend on a programs flow of control residing withing fewer statements. An unconditional goto makes the flow harder to analyze and reduces the ability of the compiler to optimize the code.

#### The argument for gotos

* Good programming doesn't mean eliminating gotos. Methodical decomposition refinement, and selection of control structures automatically lead to goto-free programs in most cases. Achieving goto-less code is not the aim but the outcome, and putting the focus on avoiding gotos isn't helpful.

#### goto and Sharing Code in an else Clause

* Normally, writting a new routine is the best approach. Sometimes, however, it's not practical to put duplicated code into its own routine.
* You can restructure the initial condition so that you keep the code in the same routine rather than putting it into a new routine.

#### Summary of Guidelines for Using gotos.

* use gotos to emulate structured control constructs in languages that don't support them directly.
* Don't use the goto when an equivalent build-in construct is available.
* In most cases, you can recode without gotos for improved readability and no loss in efficiency. If your case is the exception, document the efficiency improvement.
* Limit yourself to one goto label per routine.
* Limit yourself to gotos that go forward, not backward.
* Make sure all goto labels are used.
* Make sure a goto doesn't create unreachable code.
* If you're a manager, adopt the perspective that a battle over a single goto isn't worth the loss of the war. If the programmer is aware of the alternatives and is willing to argue, the goto is probably OK.

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




