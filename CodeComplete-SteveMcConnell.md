# Code Complete

**Author**: Steve McConnel

**Language**: English

**Start date**: Jul 28th, 2020

**End date**: Dec 31st, 2020.

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

* A table-driven method is a scheme that allows you to look up information in a table rather than using logic statements (if and case) to figure it out.
* Virtually anything you can select with logic statements, you can select with tables instead.

### 18.1 General Considerations in Using Table-Driven Methods

* You put your program's knowledge into its data rather than into its logic.

#### Two issues in using table-driven methods

* The first issue you have to address is the question of how to lookup entries in the table.
* The second issue if you're using a table-driven method is what you should store in the table.

### 18.2 Direct Access Tables

* You don't have to jump through any complicated loops to find the information you want in the table; you can pick out the entry you want directly.

##### Fudging Lookup Keys.

* Diplicate information to make the key work directly.
    * The benefits of this approach are that the table structure itself is straightforward and the table accesses are also straghtforward.
    * The drawbacks are that the duplication would waste space for redundant information and increase the possibility of errors in the table.
* Transform the key to make it work directly
    * You can transform all ages above 66 to another key, say 66.
    * Creating the transformation function requires that you recognize a pattern in the data you want to use as a key.
* Isolate the key transformation in its own routine.
    * If your environment provides ready-made key transformations, use them. For example, Java provides HashMaps, which can be used to associate key/value pairs.

### 18.3 Indexed Access Tables

* When you use indexes, you use the primary data to lookup a key in an index table and then you use the value from the index table to lookup the main data you're interested in.
    * The arrray of 10.000 entries is empty except for the 100 entries that correspond to part numbers of the 100 items in your warehouse.
* If each of the entries in the main lookup table is large, it takes a lot less space to create an index array with a lot of wasted space than it does to create a main lookup table with a lot of wasted space.
* It is sometimes cheaper to manipulate entries in an index table than entries in a main table. You can create one index that accesses the table by employee name, another that accesss the table by hiring date, and a third that accesses the table by salary.

### 18.3 Stair-step Access Table

* The general idea of stair-step structures is that entries in a table are valid for ranges of data rather than for distinct data points.
* To use the stair-step method, you put the upper end of each range into a table and then write a loop to check a score against the upper end of each range. When you find the point at which the score first exceeds the top of a range, you know what the grade is.
* The advantage of this approach over other table-driven methods is that it works well with irregular data.
* Few subtleties to consider
    * Watch the endpoints
        * Make sure that the loop terminates properly with values that fell into the top ranges and that the range boundaries are handled correcctly.
        * Be careful about mistaking `<` for `<=`.
        * Consider using a binary search rather than a sequential search.
        * Consdier using indexed access instead of the stair-step technique.
            * It's better to strive for a good solution and svoid disaster rather than trying to find the best solution.
        * PUt the stairstep table lookup into its own routine.

## 19. General Control Issues.

### 19.1 Boolean Expressions

#### Using true and false for Boolean Tests

* Use the identifiers `true` and `false` in boolean expressions rather than using values like `0` and `1`.
* Use terms named `true` and `false` for tests with boolean expressions. If your language doesn't support such terms directly, create them using preprocessor macros or global variables.
* Compare boolean values to `true` and `false` implicitly.
    * Write `while(!done)` rather than `while(done == false)`.
* Break complicated tests into partial tests with new boolean variables.
* If a test is repeated often or distracts from the main flow of the program, move the code from the test into a function and test the value of the function.
* Putting the test into a well-named function improves readability and makes it easier for you to see what your code is doing, and that's a sufficient reason to do it.
    * The new function name introduces an abstraction into the program that documents the purpose of the test in code.
* Use decision tables to replace complicated conditions.
* If your data changes, you can change a decision table without changing the code; you only need to update the contests of the data structure.

#### Forming Boolean Expressions Positively

* In `if` statements, convert negatives to positives and flip-flop the code in the `if` and `else` clauses.
    * Alternatively, you could choose a different variable name, one that would reverse the truth value of the test.
* Apply DeMorgan's Theorems to simplify boolean tests with negatives.

#### Using Parenthesis to Clarify Boolean Expressions

* Rather than relying on the language's evaluation order, parenthesize to make your meaning clear.
* Fully parenthesize logical expressions.

#### Knowing How Boolean Expressions Are Evaluated

* Compilers for some languages evaluate each term in a boolean expression before combining the terms and evaluating the whole expression.
    * Compilers for other languages have "short-circuit" evaluation. This is particualary significant when, depending on the results of the first test, you might not want the second test to be executed.
* Java further complicated this picture by providng "logical" operators. Java's logical `&` and `|` operators guarantee that all terms will be fully evaluated regardless of whether the truth or fasity of the expression could be determined without a full evaluation.
* Since a reader of your code might not be as sharp as you are, use nested tests to clarify your intentions instead of depending on evaluation order and short-circuit evaluation.

#### Writing Numeric Expressions in Numer-Line Order

* Organize tests so that they follow the points on a numeric line. Ingeneral, structure your numeric tests so that you have comparisons like these:
    * `MIN_ELEMENTS <= i && i < MAX_ELEMENTS`
    * `i <= MIN_ELEMENTS && MAX_ELEMENTS < i`
* The idea is to order the elements left to right, from smallest to largest.

#### Guidelines for comparisons to 0.


* Compare logical variables implicitly.
* Compare numbers to 0 explicitly.
* Compare characters to the null terminator (`\0`) explicitly in C.
* Compare pointers to `NULL` explicitly.

#### Common Problems with Boolean Expressions

* In C-derived languages, put constants on the left side of the comparison.
    * If you have problems mistyping `=` instead of `==`, consider the programming convention of putting constatns and literals on the left sides of expressions.
    * The compiler should flag the single `=` as an error since assigning anything to a constant is invalid.
    * In Java, know the difference between `a==b` and `a.equals(b)`.
        * `a==b` tests for whether `a` and `b` refer to the same object.
        * `a.equals(b)` tests for whether the objects have the same logical value.

### 19.2 Compound Statements (Blocks)

* A "compound statement" or "block" is a collection of statements that are trested as a single statement for purposes of controlling the flow of a program.
* Write pairs of braces together.
* Use braces to clarify conditionals, regardless of whtether the code inside the block is `1` line or `20`.

### 19.3 Null statements

* Call attention to null statements
    * Use a semicolon in a single line.
    * Use a set of empty braces to emphasize.
* Create a preprocessor `DoNothing()`.
    * The statement doesn't do anything but make indisputably clear the fact that nothing is supposed to be done.
    * In addition to using `DoNothing()` in empty `while` and `for` loops, you can use it for unimportant choises of a switch statement; including `DoNothing()` makes it clear that the case was considered and nothing is supposed to be done.
* Most of the code that results in loops with empty bodies relies on side effects in the loop-control code. In most cases, the code is more readable when the side effects are made explicit.

### 19.4 Taming Dangerously Deep Nesting.

* Many researchers recommend avoiding nesting to more than three or four levels.
* If the nesting gets too deep, you can decrease the number of nesting levels by retesting some of the conditions.
* A nested if can be simplified by using a `do-while` loop with only one iteration (`do-while(false)`), and breaking the block if some condition in the middle of the block fails.
    * This is a very uncommon technique.
* Convert a nested `if` to a set of `if-then-elses`.
* Convert a nested `if` to a `case` statement.
* Factor deeply nested code into its own routine.
* Use a more object oriented approach.
    * Create an abstract base class, and some subclasses.
    * Convert the switch statement to use a factory method.
* Redesign deeply nested code.
    * Case statements virtually always indicate poorly factored code in object-oriented programming and are rarely needed.

### 19.5 A Programming FOundation: Structured Programming.

* The core of structured programming is the simple idea that a program should use only one-in, one-out control constructs.
* A structured program progresses in an orderly, disciplined way, rather than jumpling around unpredictably.

#### The Three Components of Structured Programming

##### Sequence

* A sequence is a set of statements executed in order. Typical sequential statements include assignments and calls to routines.

##### Selection

* A selection is a control structure that causes statements to be executed selectively. The `if-then-else` statement is a common example. One of the clases is "selected" for execution.

##### Iteration

* An iteration is a control structure that causes a group of statements to be executed multiple times. An iteration is commonly referred to as a "loop".

* The core thesis of structured programming is that any control flow whatsoever can be created from these three constructs of sequence, selection and iteration.

* Use of any control structure other than the three standard structured programming constructs - that is, the use of `break`, `continue`, `return`, `throw-catch` and so on - should be viewed with a critical eye.

### 19.6 Contorl Structures and Complexity.

* One measure of "programming complexity" is the number of mental objects you ohave to keep in mind simultaneously in order to understand a program.
* Contorl flow is at least one of the largest contributors to complexity, if not the largest.

#### How Important Is Complexity?

* The competent programmer is fully aware of the strictly limited size of his own skull; therefore he approches the proggramming task with full humility.
    * It implies that you can never deal with enormous complexity, and must take steps to reduce it wherever possible.

#### General Guidelines for Reducing Complexity

* You can decrease the complexity of your programs and the amount of concentration required to understand them.

#### How to Measure Complexity

* Complexity is measured by counting the number of "decision points" in a routine.
    * Start with 1
    * Add 1 for each `if`, `while`, `repeat`, `for`, `and`, `or`.
    * Add 1 for each `case` in a `case` statement.

#### What to Do with Your Complexity Measurements

* 0 to 5: The routine is probably fine.
* 6 to 10: Start to think about ways to simplify the routine.
* More than 10: Break part of the routine into a second routine and call it from the first routine.

* Moving part of the routine into another routine doesn't reduce the overal complexity of the program; it just moves the decision points around. But it reduces the amount of complexity you have to deal with at any one time.

#### Other Kinds of Complexity

* Amount of Data used.
* Number of lines between successive references to variables (span)
* Number of lines that a variable is in use ("live time").
* The amount of input and output.

## 20. The Software-Quality Landscape

### 20.1 Characteristics of Software Quality

* External characteristics are characterics that a user of the software product is aware of.
    * **Correctness:** Free from faults in its specification, design and implementation.
    * **Usability:** Ease with which users can learn and use a system.
    * **Efficiency:** Minimal use of system resources, including memory and execution time.
    * **Reliability:** The ability of a system to perfom its required functions under stated conditions whenever required, having a long mean time between failures.
    * **Integrity:** The degree to which a system prevents unauthorized or improper access to its programs and its data.
    * **Adaptability:** The extent to which a system can be used, without modifications, in applications or environments other than those for which it was specifically designed.
    * **Accuracy:** The degree to which a system, as built, is free from error, especially with respect to quantitative outputs. Accuracy deffers from correctess; it is a determination of how well a system does the job it's built for rather than whether it was built correctly.
    * **Robustness:** The degree to which a system continues to function in the presence of invalid inputs or stressful environmental conditions.
* Interal characteristics:
    * **Maintainability:** THe ease with which you can modify a software system to change or add capabilities, improve performance or correct defects.
    * **Flexibililty:** The extent to which you can modify a system for users or environments other than those for which it was specifically designed.
    * **Reusability:** The extent to which and the ease with which you can use parts of a system in other systems.
    * **Readability:** The ease with which you can read and understand the source code of a system.
    * **Testability:** The degree to which you can unit-test and system-test a system; the degree to which you can verify that the system meets its requirements.
    * **Understandability:** Coherence of both system-organizational and detailed-statement levels.
* Some quality characteristics are emphasized to make life easier for the user and some are emphasized to make life easier for the programmer.
* The attempt to maximize certain characteristics inevitably conflicts with the attempt to maximize others.
* It's useful to think about your specific quality goals and whether each pair of goals is mutually benefitial or antagonistic.

### 20.2 Techniques for Improving Software Quality

* Setting explicit quality objectives from among the external and internal characteristics.
* Quality can be perceived as a secondary goal. That's why organizations must show programmers that quality is a priority. Making the quality-assurance activity explicit makes the priority clear, and programmers with respond accordingly.
* Developers in many projects rely on testing as the primary method of both quality assessment and quality improvement.
* Guidelines should controrl the technical character of the software as it's developed.
* Review your work informally before turning it over for formal review.
* One part of managing a software-engineering process is catching problems at the time at which the least investment has been made and at which problems cost the least to correct.
    * Periodic tests or reviews are used to determine whether the quality of the product at one stage is sufficient to support moving on to the next.
* An external audit is a specific kind of technical review used to determine the status of a project or the quality of a product being developed.

#### Development Process

* One big obstacle to achieving software quality is uncontrolled changes.
    * Uncontrolled requirements changes can result in disruption to design and coding.
    * Uncontrolled changes in design can result in code that doesn't agree with its requirements, inconsistencies in the code, or more time spent modifying code to meet the changing design than spent moving the project forward.
    * Uncontrolled changes in the code itself can result in internal inconsistencies and uncertainties about which code has been fully reviewed and tested and which hasn't.
* Unless results of a quality-assurance plan are measured, you'll have no way to know whether the plan is working.
* Prototyping is the development of realistic models of a system's key functions. Prototyping can lead to better designs, better matches with user needs, and improved maintainability.

#### Setting Objectives

* If you set explicid and reasonable quality objectives, programmers with work to achieve them. They can't respond to a set of objectives that change daily or that are impossible to meet.

### 20.3 Relative Effectiveness of Quality Techniques

* Some defect-detection methods:
    * Informal design reviews
    * OFrmal design inspections.
    * Informal code reviews
    * Formal code inspections
    * Model or prototyping
    * Personal desk-checking of code
    * Unit test
    * New function (component) test
    * Integration test
    * Regression test
    * System test
    * Low-volume beta test (<10 sites)
    * High-volume beta test (>1000 sites)
* Glenford Myers points out that human processes (inspections and walkthroughs, for instance) tend to be better than computer-based testing at finding certain kinds of errors and that the opposite is fine for other kinds of errors.
* The upshot is that the defect-detection methods work better in combination that they do singly.

#### Cost of Finding Defects

* Most studies have found that inspections are cheaper than testing.

#### Cost of Fixing Defects

* The longer a defect remains in the system, the more expensive it becomes to remove.
* A detection technique that finds the error earlier therefore results in a lower cost of fixing it.
* Some techniques, such as inspections, detect the symptoms and causes in one stem; other, such as testing, find symptoms but require additional work to diagnose and fix the root cause.
* Here's a recommended combination for achieving higher-than-average quality:
    * Formal inspections of all requirements, all architecture, and designs for critical parts of a system.
    * Modeling or prototyping.
    * Code reading or inspections.
    * Execution testing.

### 20.4 When to Do Quality Assurance

* The earlier an error is inserted into software, the more entagled it becomes in other parts of the software and the more expensive it becomes to remove.
* Defects creep into software at all stages. Consequently, you should emphasize quality assurance work in the early stages and throughout the rest of the project. It should be planned into the project as work begins; it should be part of the technical fiber af the project as work continues, and it should punctuate the end of the project.

### 20.5 The General Principle of Software Quality

* The general principle of software quality is that improving quality reduces development costs.
* The best way to improve productiviy and quality is to reduce the time spent reworking code, whether the rework arises from changes in requirements, changes in design, or debugging.
* The most obvious method of shortening a development schedule is to improve the quality of the product and decrease the amount of time spent debugging and reworking the software.
* Software defects removal is actually the most expensive and time-consuming form of work for software.
* Compared to the traditional code-test-debug cycle, an enlightened sofware-quality program saves money. It redistributes resources away from debuggina and refactoring into upstream quality-assurance activities.

## 21. Collaborative Construction

* All collaborative construction techniques are attepts to formalize the process of showing your work to someone else for the purpose of flushing out errors.

### 31.1 Overview of Collaborative Development Practice

* All collaborative construction techniques, despite their differences, are based on the ideas that developers are blind to some of the trouble sports in their work, that other people don't have the same blind spots, and that it's beneficial for developers to have someone else look at their work.

#### Collaborative Construction Complements Other Quality-Assurance Techniques

* Pair programming can achieve a code-quality level similar to formal inspections. The cost of full-up pair programming is on the order of 10-25 percent higher than the cost of solo development. The reduction in development time appears to be on the order of 45 percent.
* A study of large programs found that each hour spent on inspections avoided an average of 33 hours of maintenance and that inspections were up to 20 times more efficient than testing.
* Reducing the number of defects in the software also improves the development time.
* In addition to being name effective at catching errors than testing, collaborative practices find different kinds of errors than testing does.
* A human reviewer can spot unclear error messages, inadequate comments, hard-coded variable values, and repeated code patterns that should cbe consolidated. Testing won't.
* When people know their work will be reviewed, they scrutinize it more carefully.

#### Collaborative Construction Provides Mentoring in Corporate Culture and Programming Expertise.

* The code, the standards, and the reasons for making the code meet the standards are good topics for review discussions.
* In addition to feedback about how well they follow standards, programmers need feedback about more subjective aspects of programming: formatting, comments, variable names, local and global variable use, design approaches, the-way-we-do-things-around-here, and so on.

#### Collaborative Ownership Applies to All Forms of Collaborative Construction

* Better code quality arises from multiple sets of eyes seeing the code and multiple programmers working on the code.
* The impact of someone leaving the project is lessened because multiple people are familiar with each section of code.
* Defect-correction cycles are shorter overall because any of several programmers can potentially be assigned to fix bugs on as as-available basis.
* SOme methodologies, such as Extreme Programming, recommend formally pairing programmers and rotating their work assignments over time.

### 21.2 Pair Programming

* When pair programming, one programmer types in code at the keyboard and the other programmer watches for mistakes and thinks strategically about whether the code is being written correctly and whether the right code is being written.

#### Keys to Success with Pair Programming

* Pair programming will not be effective if the two people in the pair spend their time arguing about coding style.
* The person without the keyboard should be an active participant in the programming. That person is analyzing the code, thinking a head to what will be coded next, evaluating the design, and planning how to test the code.
* Don't force pair programming of the easy stuff.
    * One group that used pair programming for the most complicated code found it more expedient to do detailed design at the whiteboard for 15 minutes and then to program solo.
* Rotate pairs and work assignments regularly.
    * In pair programmin, benefit arises from different programmers learning different parts of the system.
* Encourage pairs to match each other's pace.
    * The faster partner need to slow down, or the pair should be broken up and reconfigured with different partners.
* Make sure both partners can see the monitor.
* Don't force people who don't like each other to pair.
* Pair programming works best when at least one of the partners has paired before.
* If your whole teams wants to do 100 percent of its programming in pairs, you'll still need to assign one person to coordinate work assignments, be held accountable for results, and act as the point of contact for people outside the project.

#### Benefits of Pair Programming

* Pairs encourage each other to keep code quality high even when there's pressure to write quick and dirty code.
* The readability and understandability of the code tends to rise to the level of the best programmer on the team.
* Pairs tend to write code faster and with fewer errors. The project team spends less time at the end of the project correcting defects.
* Disseminating corporate culture, mentoring junior programmers, and fostering collective ownership.

### 21.3 Formal Inspections

* An inspection is a specific kind of review that has been shon to be extremely effective in detecting defects and to be relatively economical compared to testing.
    * Checklists focus the reviewer's attention.
    * Inspections focus on defect detection, not correction.
    * Reviewers prepare for the inspection meeting before hand, and arrive with a list of programs they've discovered.
    * Distinct roles are assigned.
    * The moderator of the inspection isn't the author of the work.
    * The moderator receives specific training in moderating inspections.
    * General management doesn't attend the inspection meeting.
* Individual inspections typically catch about 60 percent of defects.
* Formal inspections result in 20-30 percent fewer defects per 1000 lines of code than less formal review practices.
* Designers and coders learn to improve their work through participating in inspections, and inspections increase productivity by about 20 percent.
* On a project that uses inspections for design and code, the inspections will take up about 10-15 percent of the project budget and will typically reduce overall project cost.

#### Roles during Inspections

* Roles:
    * Moderator
        * Responsible for keeping the inspection moving at a rate that's fast enough to be productive but slow enough to find the most errors possible.
        * SHould distribute the design or code to be reviewed, distribute the inspection checklist, setup a meeting room, reporting inspection results, follow-up on the actions required.
    * Author
        * Since the design or code should speak for itself, the author should explain parts of the design or code that are unclear.
        * The author might also present an overview of the project.
    * Reviewer
        * Finds errors.
    * Scribe
        * Records detected errors, and assigned action items.
* Under no circumstances should inspections results be used for performance appraisals.
* Overal, an inspection should have no fewer than three participants (moderator, author and reviewer).

#### General Procedure for an Inspection

* Planning
    * The author gives the design or code to the moderator. The moderator decides who will review the material and when and where the inspection meeting will occur.
* Overview
    * When reviewers aren't familiar with the project they are reviewing, the author can spend up to an hour or so, describing the tecnical environment within which the design or code has been created.
* Preparation
    * Each reviewer works alone to scrutinize the design or code for errors. The reviewers use the checklist to stimulate and direct their examination of the review materials.
    * An additional variation in inspection preparation is to assign each reviewer one or more scenarios to check.
    * A scenario might also involve a specific task that a reviewer is assigned to perform, such as listing the specific requirements that a particular design element satisfies.
* Inspection meeting
    * The moderator chooses someone other than the author to paraphrase the design or read the code.
    * During the presentation, the scribe records errors as they are detected.
    * Don't discuss solutions during the meeting. The group should stay focused on identitying defects. Some inspection groups don't even allow discussion about whether a defect is really a defect. They assume that if someone is confused enough to think it's a defect, the design, code or documentation needs to be clarified.
    * The meeting generally should not last more than two hours.
* Inspection report
    * Within a day of the inspection meeting the moderator produces an inspection report (email or equivalent) that lists each defect, including its type and severity.
    * If you collect data on time spent and the number of errors found over time, you can respond to challenges about inspection's efficacy with hard data.
* Rework
    * The moderator assigns defects to the author, for repair.
* Follow-up
    * The moderator is responsible for seeing that all rework assigned during the inspection is carried out.
    * Depending on the number of errors found and the severity of those errors, you might follow up by having the reviewers reinspect the entire work product, having the reviewers reinspect only the fixes, or allowing the author to complete the fixes without any follow up.
* Third-hour meeting
    * You can allow interested parties to discuss solutions after the official inspection is over.

#### Fine-Tuning the Inspection

* Companies have often found that removing or combining any of the stages costs more than is saved. If you're tempted to change the inspection process without measuring the effect of the change, don't.
* As you do inspections, you'll notice that certain kinds of errors occur more frequently than other kinds. Create a checklist that calls attention to those kinds of errors so that reviewers will focus on them.

#### Egos in Inspection

* The point of the inspection is to discover defects in the design or code. It is not to explore alternatives or to debate who is right and who is wrong. The point is most certainly not to criticize the author of the design or code.
* The author should acknowledge each alleged defect and move on. Acknowledging a criticism doesn't imply that the author agrees with the content of the criticism. The author should not try to defend the work under review. After the review, the author can think about each point in private and decide whether it's valid.
* Reviewers must remember that the author has the ultimate responsibility for deciding what to do about a defecdt each reviewer must respect the author's ultimate right to decide how to resolve an error.

### 21.4 Other Kinds of Collaborative Development Practices

#### Walk-Throughs

* Where two or three are gathered toether, there is a walkthrough.
* The walkthrough is usually hosted and moderated by the author of the design or code under review.
* The walk-through focuses on technical issues.
* All participants prepare for the walk-through by reading the design or code and looking for errors.
* The walk-through is a chance for senior programmers to pass on experience and corporate culture to junior programmers.
* A walk-through usually lasts 30 to 60 minutes.
* The emphasis is on error detection, not correction.

##### What Results Can You Expect from a Walk-Through

* Used intelligently and with discipline, a walk-through can typically find between 20 and 40 percent of the errors in a program.
* In general, walk-throughs are significatly less effective than inspections.
* Used unintelligently, walk-throughs are more trouble than they're worth. When project pressure increase, walk-throughs become nearly impossible.
* If you're going to incur the overhead of holding a meeting, it's worthwhile to structure the meeting as a formal inspection. If the work product you are reviewing doesn't justify the overhead of a formal inspection, it doesn't justify the overhead of a meeting at all.
* If you have a large review group, a walk-through is a good review choice because it brings many diverse view points to bear on the item under review.
* If reviewers from other organizations are involved, a walk-through might also be preferable.
* Inpsections are more focused than walk-throuhts and generally pay off better.

#### Code Reading

* You read source code and look for errors. You also comment on qualitative aspects of the code, such as its design, style, readability, maintainability, and efficiency.
* Code reading detected about 3.3 defects per hour of effort. Testing detected about 1.8 errors per hour.
* A code reading usually involves two or more people reading the code independently and then meeting with the author of the code to discuss it.
    * Two or more people read the code.
    * Reviewers read the code independently.
    * When the reviewers have finished reading the code, the code reading meeting is hosted by the author of the code.
    * The meeting lasts one or two hours and focuses on problems discovered by the code readers. No one makes any attempt to walk through the code line by line. The meeting is not even strictly necessary.
    * The author of the code fixes the problems identified by the errors.
* Each reviewer's time is focused on finding problems in the code.
* Code readings are especiallly valuable in situations in which reviewers are geographically dispersed.

#### Dog-and-Pony Shows

* Reviews in which a software product is demostrated to a customer.
* The purpose of this review is to demonstrate to the customer that the project is OK, so it's a management review rather than a technical review.

#### Comparison of Collaborative Construction Techniques

* If pair programming and formal inspections produce similar results for quality (40-60% vs 45-75% in error detection, respectively), cost and schedule, the choice between them becose a matter of personal style rather than one of tecnical substance.

## 22. Developer Testing

* **Unit testing:** Execution of a program element, writen by a single programmer which is tested in isolation frorm the more complete system.
* **Component testing:** Execution of a program element that involves the work of multiple programmers, which is tested in isolation from the more complete system.
* **Integration testing:** Combined execution of two or more program elements that have been created by multiple programmers.
    * Starts as soon as there are two classes to test.
* **Regression testing:** Repetition of previously executed test cases from the purpose of finding defects in software that previously passes the same set of tests.
* **System testing:** Execution of the software in its final configuration including integration with other software and hardware system.
* Testing is usually broken into two broad categories: blackbox testing and whitebox testing. "Black-box testing" refers to tests in which the tester cannot see the inner workings of the item being tested. "White-box testing" refers to tests in which the tester is aware of the inner workings of the item being tested.

### 22.1 Role of Developer Testing in Software Quality

* Collaborative development practices in their vaious forms have been shown to find a higher percentage of errors than testing does, and they cost less than half as much per error dound as testing does.
* Testing is a hard activity for most developers to swallow for several reasons:
    * The goal is to find errors. The goal of every other development activity is to prevent errors.
    * Testing can never completely prove the absence of errors.
    * Teseting by itself does not improve software quality. If you want to improve software, don't just test more, develop better.
    * Testing requires you to assume that you'll find errors in your code. You must hope that it's you who finds the errors and not someone else.

#### Testing During Construction

* You generally want to design a class to be a black-box - a user of the class won't have to look past the interface to know what the class does. In testing, if you know what's inside the box, you can test the class more thoroughly.
* If you are writting several routines you should test them one at a time. If you add one routine at a time to a collection of previously tested routines, you know that any new errors are the result of the new routine or of interactions with the new routine. The debugging job is easier.

### 22.2 Recommeded Approach to Developer Testing

* Test for each relevant requirement to make sure that the requirements have been implemented.
* Test for each relevant design concern to make sure that the design has been implemented.
* Use "basis testing" to add detailed test cases to those that test the requirements and the design.
* Use checklist of the kinds of errors you're made on the project to date.

#### Test First or Test Last?

* Writing test cases first will minimize the amount of time between when a defect is inserted into the code and when the defect is detected and removed.
    * Writing test cases before writing the code doesn't take any more effort than writting test cases after the code.
    * When you write test cases first, you detect defects earlier and you can correct them more easily.
    * Writing test cases first forces you to think at least a little about the requirements and design before writing code.
    * Writing test cases first exposes requirements problems sooner, before the code is written, because it's hard to write a test case for a poor requirement.

#### Limitations of Developer Testing

* Developers tend to test for whether the code works (clean tests) rather than test for all the ways the code breaks (dirty tests).
    * Mature testing organizations tend to have five dirty tests for every clean test.
* Developer testing tends to have an optimistic view of test coverage.
* A better coverage standard is to meet what's called "100% branch coverage", with every predicate term being tested for at least one `true` and one `false` value.
* As valuable as developer testing is, it isn't sufficient to provide adequate quality assurance on its own and should be supplemented with other practices, including independent testing, and collaborative construction techniques.

### 22.3 Bag of Testing Tricks

* To use testing to prove that a program works, you'd have to test every conceivable input value to the program, and every conceivable combination of input values.

#### Incomplete Testing

* You need to concentrate on picking a few test cases, most likely to find errors, that tell you different things rather than a set that tells you the same thing over and over.

#### Structured Basis Testing

* You need to test each statement in a program at least once. If the statement is a logical statement - an `if` or a `while`, for example- you need to vary the testing according to how complicated the expression inside the `if` or `while` is to make sure that the statement is fully tested.
* "Code coverage" testing or "logic coverage" testing are approaches in which you test all the paths through a program.
* You can compute the minimum number of cases needed for basis testing in this way:
    1. Start with 1
    2. Add 1 for each of the following keywords: `if`, `while`, `repeat`, `for`, `and`, and `or`.
    3. Add 1 for each `case` in a `case` statement. If the case statement doesn't have a default case, add 1 more.
* Each keyword in the code represents something that can be either `true` or `false`; make sure you have at least one test case for each `tru` and at least one for each `false`.
* This kind of testing assures you only that all of the code will be executed. It doesn't account for variations in data.

#### Data-Flow Testing

* Data usage is at least as error prone as control flow.
* Data can exist in one of three states:
    1. **Defined:** The data has been initialized, but it hasn't been used yet.
    2. **Used:** The data has been used for computation.
    3. **Killed:** The data was once defined, but it has been undefined in someway.
* Regarding routines:
    1. **Entered:** The control flow enters the routine immediately before the variable is acted upon.
    2. **Exited:** The control flowleaves the routine immediately after the variable is acted upon.

#### Combination of Data States

* Some suspicious patterns:
    * **Defined-Defined:** There's an error if you need to define a variable twice before the value sticks.
    * **Defined-Exited:** It doesn't have sense to define a local variable and exit without using it. If it's a global variable, it's all right.
    * **Defined-Killed:** Defined a variable and then killing it suggest that there's some code missing.
    * **Entered-Killed:** A local variable doesn't need to be killed before it's been defined or used.
    * **Entered-Used:** A local variable needs to be defined before it's used.
    * **Killed-Killed:** A variable shouldn't need to be killed twice.
    * **Killed-Used:** Using a variable after it has been killed, is a logical error.
    * **Used-Defiend:** You should not use a variable before defining it.
* Check for anomalous sequences of data states.
* A good way to develop test cases is to start with structred basis testing. Then add the cases you still need to have a complete set of defined-used data flow test cases.

#### Equivalence Partitioning

* An equivalence ">" or "<" break sets into two related equivalence classes.

#### Error Guessing

* Create test cases based upon guesses about where the program might have errors, although it implies certain amount of sophistication in guessing.

##### Boundary Analysis

* Write test cases that exercise the boundary conditions. If you're testing for a range of values that are less than `max`, there are three boundary cases: just less than `max`, `max` itself, and just greater than `max`.

##### Compound Boundaries

* A more subtle kind of boundary condition occurs when the boundary involves a combination of variables. For example, if two variables are multiplied together.

#### Classes of Bad Data

* Typical bad-data test cases include
    * too little data (or no data)
    * Too much data
    * The wrong kind of data (invalid data, e.g. negative salary)
    * Uninitialized data.

#### Classes of Good Data

* Following are other kinds of good data that are worth checking:
    * Nominal cases-middle-of-the-road, expected values.
    * Minimum normal configuration
    * Maximum normal configuration
    * Compatibility with old data.
* Testing for compatibility with old data comes into play when the program or routine is a replacement for an older program or routien. The new routine should produce the same result with old data that old routine did, except in cases in which the old routine was defective.

#### Use Test Cases that Make Hand-Check Convenient

* When you try to do hand-calculations with an ugly number like 949871234, however, you are as likely to make an error in the hand-calc as you are to discover one in your program.
    * A nice, even number, like 20.000 makes number crunching a snap.

### 22.4 Typical Errors

#### Which Classes Contain the Most Errors?

* It's wrong to assume that defects are distributed evenly throughout your source code.
* Eighty percent of the errors are found in 20 percent of a project's classes or routines.
* Fifty percent of errors are found in 5 percent of a project's classes.
* The implication of expensive routines for development is clear. As the old expression goes, "time is money". This is a clear illustration of the general principle of software quality: improving quality improves the development schedule and reduces development costs.
* Maintenance activities should be focused on identifying, redesigning, and rewriting from the ground up those routines that have been identified as error prone.

#### Erros by Classification

* The cope of most errors is fairly limited. Most errors can be corrected without modifying more than one routine.
* The three most common sources of errors were thin application-domain knowledge, fluctuating and conflicting requirements, and communication and coordination breakdown.
* Most construction errors are the programmers' fault.
* Typos (clerical errors) are a common source of problems.
* Many errors result from misunderstanding the design.
* Most errors are easy to fix.
* Start measuring your development process so that you know where the problems are.

#### Proportion of Errors Resulting from Faulty Construction

* On small projects, construction defects make up the vast bulk of all errors.
* Construction defects account for at least 35% of all defects regardless of project size.
* Construction errors, although cheaper to fix than requirements and design errors, are still expensive.

#### How Many Errors SHould You Expect to Find?

* The application division at Microsoft experiences about 10-20 defects per 1000 lines of code during in-house testing and 0,5 defects per 1000 lines of code in released product.
    * The technique used to achieve this level is a combination of code-reading technquies and independent testing.
* A few projects achieved a level of 0 defects in 500.000 lines of code by using a system of formal development methods, peer reviews and statistical testing.

#### Errors in Testing Itself

* Test cases are often as likely or more likely to contain errors than the code being tested. Test cases tend to be created on the fly rather than through careful design and construction process.
* Develop test cases as carefully as you develop code. Such care certainly includes double checking your own testing.
* Effective planning for testing should start at the requirements stage or as soon as you get the assignment for the program.
* Write code for unit tests first, but integrate them into a system wide test framework (like JUnit) as you complete each test.

### 22.5 Test Support Tools

#### Building Scaffolding to Test Individual Classes

* Software scaffolding is built for the purpose of making it easy to exercise code.
* One kind of scaffolding is a class that's dummied up so that is can be used by another class that's being tested such a class is called a "mock object".
* On "mock objects" or "stub routines", the scaffolding can:
    * Return control without taking no action.
    * Test the data fed to it.
    * Log a message.
    * Get return values from interactive input.
    * Return a standard answer regardless of the input.
    * Burn up the number of clock cycles.
    * Function as a slow version of the real object.
* Another kind of scaffolding is a fake routine that calls the real routine. This is called a "driver" or a "test harness". This scaffolding can:
    * Call the object with a fixed set of inputs.
    * Prompt for input and call the object with it.
    * Take arguments from the command line, and call the object.
    * Read arguments from a file and call the object.
    * Run through predefined sets of input data in multiple calls to the object.
* A final kind of scaffolding is the dummy file, a small version of the real thing that has the same types of components that a full-size file has.
* If you use scaffolding, the class can also be tested without the risk of its being affected by interactions with other classes.
* It's easy to get stuck in a rut in which it takes several minutes to execute each test case because the code being exercised is embedded in other code. Scaffolding allows you to exercise the code directly.
* If your environment isn't supported by one of the existing test frameworks you can write a few routines in a class and include a `main()` scaffolding routine in the file to test the class.

#### Diff Tools

* Regression testing, or retesting, is a lot easier if you have automated tools to check the actual output against the expected outputs.

#### Test-Data Generators

* Properly designed random-data generators can generate unusual combinations of test data that you wouldn't think of.
* Random-data generators can exercise your program more thoroughly than you can.
* You can refine randomly generated test cases over time so that they emphasize a realistic range of input. This concentrated testing in areas most likely to be exercised by users, maximizing reliability in those areas.
* Modular design pays off during testing. I was able to pull out the encryption and decryption code and use it independently of the user-interface code.
* You can reuse the test driver if the code it tests ever has to be changed.

#### Coverage Monitors

* Testing done without measuring code coverage typically exercises only about 50-60% of the code.

#### Data Recorder / Logging

* Strong logging aids eerror diagnosis and supports effective service after the software has been released.
* You can build your own data recorder by logging significat events to a file. If you implement logging with self prunning storage and thoughtful placement and content of error messages, you can include logging functions in release versions.

#### Symbolic Debuggers

* A debugger has the capacity to setp through code line by line, keep track of variables' values, and always interpret the code the same way the computer does.

#### System Perturbers

* You want to be sure you don't have any uninitialized variables. Some tools fill memory with arbitrary values before you run your program so that uninitialized variables aren't set to 0 accidentally.
* In multitasking systems, some tools can rearrange memory as your program operates.
* A memory driver can simulate low-memory conditions in which a program might be running out of memery, fail on a memory request, grant an arbitrary number of memory requests before failing, or fail on an arbitrary number of requests before granting one.
* Memory access checkers watch pointer operations to make sure your pointers behave themselves.

#### Error Databases

* One powerful test tool is a database of errors that have been reported.
* It allows you to check for recurring errors, track the rate at which new errors are being dtected and corrected, and track the status of open and closed errors and their severity.

### 22.6 Improving Your Testing

#### Planning to Test

* Putting testing on the same level of importance as dsign or docidng means that time will be allocated to it, it will be viewed as important, and it will be a high-quiality process.

#### Retesting

* Testing designed to make sure the software hasn't taken a step backward or "refressed" is called "regression testing".
* It's nearly impossible to produce a high-quality software product unless you can systematically retest it after changes have been made.
* Regression testing must run the same tests each time.

#### Automated Testing

* The only practical way to manage regression testing is to automate it.
* Benefits of test automation:
    * An automated test has a lower chance of being wrong than manual test.
    * Once you automate a test, it's readily available for the rest of the project.
    * If tests are automated, they can be run frequently to see whether any code check-ins have broken the code.
    * Automated tests improve your changes of detecting any given problem at the earliest possible moment.
    * Automated tests increase your chance of quickly detecting defects inserted during the modifications.
    * Automated tesets are especially useful in new, volatile technology environments because they flush out changes.
* The main tool used to support automated testing provide test scaffolding, generate input, capture output, and compare actual output with expected output.

### 22.7 Keeping Test Records

* Some kinds of data that can be collected to measure a project:
    * Administrative description of the defect (date reported, date fixed, person who reported it, a title or description).
    * Steps to repeat the problem.
    * Full description of the problem.
    * Suggested workaround for the problem.
    * Related defects.
    * Severity of the problem
    * Origin of the defect (requirement, design, code, testing)
    * Subclassification of a coding defect.
    * Classes and routines changed by the fix.
    * Number of lines of code affected by the defect.
    * Hours to find the defect.
    * Hours to fix the defect

#### Personal Test Records

* You might find it useful to keep track of your personal test records.

## 23. Debugging

* Debugging is the process of identifying the root cause of an error and correcting it.

### 23.1 Overview of Debugging Issues

#### Role of Debugging in Software Quality

* Like testing, debugging isn't away to improve the quality of your software per se; it's a way to diagnose defects.

#### Defects as Opportunities

* Having a defect means that you don't fully understand what the program does.
* If you don't know exactly what you are telling the computer to do, you're only a small step away from merely trying different things until something seems to work - that is, programming by trial and error.
* An error in your program provides a powerful opportunity for you to learn many things:
    * Learn about the program you're working on.
    * Once you find the mistake, ask yourself how and why you made it. How could you have found it more quickly? How could you have prevented it? Does the code have other mistakes just like it? Can you correct them before they cause problems af their own?
    * When you read your code to find the defect, look critically at the quality of your code. Is it easy to read? How could it be better?
    * Learn about how you debug (find defects).
    * Learn about how you fix the defects you find.

#### An ineffective Approach

##### The Devil's Guide to Debugging.

* To find a defect, scatter print statements randomly throughout a progrm. Examine the output to see where the defect is. If you can't find the defect with print statements, try changing things in the program until something seems to work.
* Don't waste time understanding the problem.
* It's usually good just to fix the specific problem you see, rather than wasting a lot of time making some big, ambitious correction that's going to affect the whole program.

##### Debugging by Superstition

* If you have a problem with a program you've written, it's your fault. It's not the computer's fault, and it's not the compiler's fault. The program doesn't do something different every time. It didn't write itself; you wrote it, so take responsibility for it.

### 23.2 Finding a Defect

* Effective approach for finding a defect
    1. Stabilize the error (make it occur reliably).
    2. Locate the source of the error (the "fault").
        1. Gather the data that produces the defect.
        2. Analyze the data that has been gathered, and form a hypothesis about the defect.
        3. Determine how to prove or disprove the pypothesis, either by testing the program or by examining the code.
        4. Prove or disprove the hypothesis.
    3. Fix the defect.
    4. Test the fix.
    5. Look for similar errors.
* The defect is easier to diagnose if you can stabilize it.

#### Stabilize the Error

* An error that doesn't occur predicably is usually an initialization error, a timing issue, or a dangling-pointer problem.
* Stabilizing an error usually requires more than finding a test case that produces the error. It includes narrowing the test case to the simplest one that still produces the error. The goal of simplifying the test case is to make it so simple that changing any aspect of it changes the behaviour of the error.

#### Locate the source of the error

* You might suspect that the defect is a result of a specific problem. You could then vary the parameter you suspect is causing the problem and determine whether your hypothesis is correct.

### Tips for Finding Defects

* It's all right that the hypothesis doesn't account for all of the data at first, as long as you keep refining the hypothesis so that it does eventually.
* Refine the test cases that produce the error.
* Defects tend to be easier to find in small fragments of code than in large integrated programs. Use your unit tests to test the code in isolation.
* Use available tools. The right tool can make a difficult job easy.
* Reproduce the error several different ways.
    * Sometimes trying cases that are similar to the error producing case but not exactly the same is instructive.
    * Once you think you've identified the defect, run a case that's close to the cases that produce error but that shouldn't produce an error itself. If it does produce an error, you don't completly understand the problem yet.
* Generate more data to generate more hypothesis.
* A test case that disproves your hypothesis is also helpful.
* Brainstorm for possible hypothesis. Don't analyze them at first - just come up iwth as many as you can in a few minutes.
* Keep a notepad by your desk, and make a list of things to try.
* Narrow the suspicious region of the code.
    * Systematically remove parts of the program and see whether the error still occurs. If it doesn't, you know it's in the part you took away. If it does, you know it's in the part you've kept.
* Be suspicious of classes and routines that have had defects before.
* If you have a new error that's hard to diagnose, it's usually related to code that's changed recently. If you can find a defect, run an old version of the program to see whether the error occurs.
* It's easy to focus on a small section of code, sure that "the defect must be in this section". If you don't find it in the section, consider the possibility that the dfect isn't in the section.
* If you add a piece of code to a system and encounter a new error, remove the piece and test it separately.
* Check for common defects.
    * Use code quality checklists to stimulate your thinking about possible defects.
* You often discover your own defect in the act of explaining it to another person.
* Take a break. Sometimes you concentrate so hard you can't think.

#### Brute-Force Debugging.

* Some general candidate techniques for brute-force debugging.
    * Perfom a full design and code review on the broken code.
    * Throw away the section of code and redesign/recode.
    * Step through a big loop in the debugger manually until you get to the error condition.
    * Instrument the code with print statements.
    * Replicate the end-user's full machine configuration.
* When you decide to go for the quick victory, set a maximum time limit for trying the quick way. If you go past the time limit, resign yourself to the idea that the defect is going to be harder to diagnose than you originally thought, and flush it out the hard way.
* Make a list of brute-force techniques:
    * If you can identify at least one brute force technique that will fix the problem -including rewriting the code in question- it's less likely that you'll waste hours or days when there's a quicker alternative.

#### Syntax Errors.

* When your compiler reports a mysterious syntax error, look immediately before and after the error.
* Compilers try to tell you exactly what's wrong, but compilers are dissembling little rascals, and you often have to read between the lines to know what one really means.
* When your compiler generates a series of cascading error messages don't worry if you can't quickly find the source of the second or third error message. Fix the first one and recompile.
* If you have a troublesome syntax error, remove part of the code and compile again. You'll either get no error (because the error's in the part you removed), get the same error (meaning you need to remove a different part), or get a different error (because you'll have tricked the compiler into producing a message that makes more sense).
* Find misplaced comments and quotation marks:
    * To find the extra comment or quotation mark, insert the following sequence into your code: `/*"/**/`.

### 23.3 Fixing a Defect

* Before you fix a problem, make sure you understand it to the core. Triangulate the defect both with cases that should reproduce the error and with cases that shouldn't reproduce the error.
* If you understand the context in which a problem occurs, you're more likely to solve the problem completly rather than only one aspect of it.
* Before you rush to fix a defect, make sure that you've diagnosed the problem correctly.
* Hurrying to solve a problem is one of the most time-ineffective things you can do. It leads to rushed judegments, incomplete defect diagnosis, and incomplete corrections.
    * Relax long enough to make sure your solution is right. Don't be tempted to take shortcuts. It might take more time, but it will probably take less.
* Before you begin fixing the defect, be sure to archive a version of the code that you can return to later.
* The focus should be on fixing the underlying problem rather than wrapping it in programming duct tape.
    * Fixes might not work most of the time. Initialization defects are, by definition, unpredictable.
    * Fixes are unmaintainable, when code is special-cased to work around errors, the special cases become the code's most prominent feature.
    * Computers are good at prodictable, systematic calculations, but humans are better at fudging data creatively.
* Don't change code randomly. That's voodoo programming. The more different you make it without understanding it, the less confidence you will have that it works correctly.
* Make one change at a time.
* Check your fix. Use an automated suite of regression tests in JUnit.
* When you encounter an error that wasn't exposed by your test suite, add a test case to expose the error so that it won't be reintroduced later.
* Look for similar defects.

### 23.4 Psychological Considerations in Debugging.

#### How "Psychological Set" Contributes to Debugging Blindness

* People expect a new phenomenon to resemble similar phenoma they've seen before.
    * You see what you expect to see and thus overlook differences.
* What does sychological set have to do with debugging?
    1. Good programming practices help structure the programming backgrorund so that likely defects appear as variabtions and stand out.
    2. Programmers who debug most effectively mentally slick away parts of the program that aren't relevant during debugging.

#### How "Psychological Distance" Can Help.

* Psychological distance can be defined as the ease with which two items can be differentiated.
    * As you debug, be ready for the problems caused by insufficient psychological distance between similar variable names and between similar routine names.
    * As you construct code, choose names with large differences so that you avoid the problem.

### 23.5 Debugging Tools

#### Source-Code Comparators

* If you make several changes and need to remove some than can't quite remember, a comparator can pin point the differences and job your memory.

#### Compiler Warning Messages

* Set your compiler's warning level to the highest, pickeiest level possible and fix the error it reports.
* Treat warning as errors.
* Set a standard that requires everyone on your team to compile code using the same compiler settings.

#### Extended Syntax and Logic Checking

* The lint utility pain stakingly checks for use of uninitialized variables and similar subtle problems.

#### Execution Profilers.

* A few minutes spent studying a prorgam profile can uncover some surprising (and hidden) defects.
* Examine the output of an execution profiler to satisfy yourself that your program spends a reasonable amount of time in each area.

#### Test Framework / Scaffolding

* Pulling out a troublesome piece of code, writing code to test it, and executing it by itself is often the most effective way to exorcise the demons from an error-prone program.

#### Debuggers

* The debugger isn't a subtitute for good thinking. But, in some cases, thinking isn't a subtitute for a good debugger either. The most effective combination is good thinking and good debugger.

## 24. Refactoring

* Many of the changes seen during initial coding are at least as dramatic as changes seen during maintenance.
* Even on well-managed projects, however, requirements change by about one to four percent per month.
* If you fix errors with logical duct tape and superstition, quality degrades. If you treat modifications as opportunities to tighten up the original design of the program, quality improves.
* Changes during construction can be more freewheeling - the system is in a more dynamic state, and the penality for making mistakes is low. These circumstances imply a style of software evolution that's different from what you'd find during software maintenance.

#### Philosophy of Software Evolution

* When you have to make a change, strive to improve the code so that future changes are easier.

### 24.2 Introduction to Refactoring

* **Refactoring:** A change made to the internal structure of the software to make it easier to understand and cheaper to modify without changing its observable behavior.

#### Reasons to Refactor

* Duplicate code sets you up to make parallel modifications - whenever you make changes in one place, you have to make parallel changes in another place.
* A routine is too long
    * One way to improve a system is to increase its modularity - increase the number of well-defined, well-named routines that do one thing and do it well.
    * If a routine would be cleaner if part of it were made into a separte routine, create a separate routine.
* A loop is too long or too deeply nested.
    * Reduce the loop's complexity by converting its content into a routine.
* A class has poor cohesion.
* A class interface does not provide a consistent level of abstraction.
* A parameter list has too many parameters.
* Sometimes a class has two or more distinct responsibilities. Then, the class should be cleared into multiple clases along the lines of the separate responsibilities.
* Changes require parallel modifications to multiple classes.
    * When you find yourself routinely making changes to the same set of classes, that suggests the code in those classes could be rearranged so that changes affect only one class.
* Finding yourself making a subclass of one class every time you make a subclass of another class is a special kind of parallel modification and should be addressed.
* If you find yourself making parallel modifications to similar case statements in multiple parts of the program, you should ask whether inheritance might be a better approach.
* Related data items that are used together are not organized into classes.
* A routine uses more features of another class than of its own class.
    * This suggests that the routine should be moved into the other class and then invoken by its old class.
* If your program uses a primitive data type like an integer to represent a common entity such as money, consider creating a simple `Money` class so that the compiler can perform type checking on Money variables.
* A class doesn't do very much, then consider assign all the class's responsibilities to other classes.
* Finding yourself passing data to one routine just so that routine can pass it to another routine is called "tramp data". This might be OK, but ask yourself whether passing the specific data in question is consistent with the abstraction presented by each of the routine interfaces.
* If you find that most of the code in a class is just passing off calls to routines in other classes, consider whether you should eliminate the middleman, and call those other classes directly.
* Anytime you see one class that knows more about another class than it should - including derived classes knowing too much about their parents - err on the side of stronger encapsulation rather than weaker.
* If a routine has a poor name, change it.
* Public data members are always a bad idea. They blur the line between interface and implementation, and they inherently violate encapsulation and limit future flexibility. Consider hiding public data members behind access routines.
* A subclass uses only a small percentage of its parent's routines.
    * This indicates that that parent class happened to contain the routines that subclass needed, not because the subclass is logically a descent of the supper class.
    * Consider switching the subclass's relationship to its supperclass from an `is-a` relationship to a `has-a` relationship.
* Comments are used to explain difficult code, not bad code.
* Isolate global variables in access routines.
* A program contains code that seems like it might be needed someday.
    * Any "design ahead" code is useless.

#### Reasons Not to Refactor

* "Refactoring" is used loosely to refer to making any change to the code whatsoever. purposeful change, can be the key strategy that supports steady improvement in a program's quality.

### 24.3 Specific Refactorings

#### Data-Level Refactorings

* Replace a magic number with a named constant
* Rename a variable with a clearer or more informative name.
* Replace the intermediate variable that was assigned the result of an expression with the expression itself.
* Replace an expression with a routine.
* Introduce an intermediate variable.
* Convert a multiuse variable to multiple single-use variables.
* Use a local variable for local purposes rather than a parameter.
* If a data primitive needs additional behavior (including stricter type checking) or additional data, convert the data to an object and add the behavior you need.
* Convert a set of type codes to an enumeration.
* Convert a set of type codes to a class with subclasses, if the different elements associated with the different types might have different behavior.
* Change an array to an object.
* Encapsulate a collection.
* Create a class that contains the members of a record.

#### Statement-Level Refactorings

* Decompose a boolean expression by introducing well named intermediate variables.
* Make a complex boolean expression into a well-named boolean function.
* Consolidate fragments that are duplicated within different parts of a conditional.
* Use break or return instead of a loop control variable.
* Return as soon as you know the answer instead of assigning a return value withing nested `if-then-else` statement.
* Replace conditionals with polymorphism.
* Create and use null objects instead of testing for null values.

#### Routine-Level Refactorings

* Extract routine/extract method.
* Move a routine's code inline.
* Convert a long routine to a class.
* Substitute a simple algorithm for a complex algorithm.
* Add a parameter to provide more information to a routine.
* If a routine no longer uses a parameter, remove it.
* Separate query operations (which are not supposed to change the object state) from modification operations.
* Combine similar routines by parameterizing them.
* Separate routines whose behavior depends on parameters passed on.
* Pass a whole object rather than specific fields.
* Pass specific fields rather than a whole object.
* If a routine returns an object, it normally should return the most specific type of object it knows about.

#### Class Implementation Refactorings

* Chagne value objects to reference objects.
* Change reference objects to value objects.
* Replace virtual routines with data initialization.
* Extract specialized code into a subclass.
* Combine similar code into a superclass.

#### Class Interface Refactorings

* Move a routine to another class.
* Convert one class to two.
* Eliminate a class.
* Hide a delegate. (Do not make chained calls)
* Remove a middleman.
* Replace inheritance with delegation.
* Replace delegation with inheritance.
* If you can't modify a class, you can subclass the original class and add new routines, or you can wrap the class and expose the routines you need.
* Encapsulate an exposed member value.
* Remove `set()` routeines for fields that cannot be changed.
* Hide routines that are not intended to be used outside the class.
* Encapsulate unused routines with a specific interface.
* If a subclass doesn't provide much specialization, combine it into its superclass.

#### System-Level Refactorings

* SOmetimes you have data maintained by the system that you can't consistently access. In that cas, you can create a single class, which will serve as the definite source of data, and that will fetch the data, wherever it's located.
* Change unidirectional class association to bidirectional class association.
* Change bidirectional class association to unidirectional class association.
* Provide a factory method rather than a simple constructor.
* Replace error codes with exceptions.

### 24.4 Refactoring Safely

* Sve the code you start with.
* Keep refactorings small.
* Do refactoring one at a time.
* Make a list of steps you intend to take.
* Make a list of the changes that you'd like to make at some point, but that don't need to be made right now.
* In addition to saving the code you started with, save checkpoints at various steps in a refectoring session so that you can get back to a working program if you find a dead end.
* Use your compiler warnings.
* Retest.
* Remove any test cases that have been made obsolete by the refactorings, and add new unit tests to exercise your code.
* Review the changes.
    * Treat every simple change as if it were complicated.
* For easier refactorings, you might streamline our refactoring process to do more than one refactoring at a time. For riskier refactorings, err on the side of caution. Do the refactorings one at a time, and have some one else review the refactoring.

#### Bad Times to Refactor

* Refactoring refers to changes in working code that do not affect the program's behavior. Programmers whoa re tweaking broken code aren't refactoring; they are hacking.
* If you find yourself in a major refactoring session, ask yourself whether instead you should be redesigning and reimplementing that section of code from the ground up.

### 24.5 Refactoring Strategies

* Spend your time on the 20 percent of the refactorings that provide 80 percent of the benefit.
* When you add a routine, check whether related routines are well organized.
* Adding a class often brings issues with existing code. Refactor other classes that are closely related to the class you're adding.
* When you fix a defect, use the understanding you gained to improve other code that might be prone to similar defects.
* Is there a section of code that you are afraid of? Targeting these challending sections for refactoring can be one of the most effective strategies.
* Target high-complexity modules.
* In a maintenance environment, improve the parts you touch.
* Define an interface between clean code and ugly code, and then move accross the interface.
    * Anytime you touch a sectino of messy code, you are required to bring it up to current coding standards, give it clear variable names and so on.

## 25. Code-Tuning Strategies

* Programmers realized how much their focus on performance had hurt readability and maintainability and ode tuning received less attention.

### 25.1 Peformance Overview

#### Quality Characteristics and Performance

* Users are more interested in tangible program characteristics than they are in code quality.
* Delivering software on time, providing a clean user interface and avoiding downtime are often more significant.

#### Performance and Code Tuning

##### Program Requireements

* Performance is stated as a requirement far more often than it actually is a requirement.
* Before you invest time solving a performance problem, make sure that you're solving a problem that needs to be solved.

##### Program Design

* Setting individual resources oals makes the system's ultimate performance predictable. If each feature meets its resouce goals, the whole system will meet its goals.
* The mere act of making goals explicit improves the likelihood that they'll be acieved.
* You can set goals that don't achieve efficiency directly but promote efficiency in the long run. For example, achieving a high degree of modifiability can provide a better basis for meeting efficiency goals than explicitly setting an efficiency target.

##### Class and Routine Design

* The choice of data types and algorithms usually affect both the program's memory use and execution speed.

##### Operating-System Interactions.

* If performance isn't good, it might be because the operating system routines are slow or fat.

##### Code Compilation

* Choosing the right compiler will allow you not to think about optimizing speed.

##### Hardware

* Sometimes the cheapest and best way to improve a program's performance is to buy a new hardware.

##### Code Tuning

* Code tuning is the practice of modifying correct code in ways that make it run more efficiently.
* "Tuning" refers to small-scale changes that affect a few lines of code.

### 25.2 Introduction to Code Tuning

* It's incredibly satisfying to take a routine that executes in 20 microsends, tweak a few lines, and reduce the execution speed to 2 microseconds.
* The problem with code tuning is that efficient code isn't necessarily "better" code.

#### The Pareto Principle

* 20 percent of a program's routines consume 80 percent of its execution time.
* "The best it the enemy of the good". Working toward perfection might prevent completion. Complete it first, and then perfect it.

#### Old Wives' Tales

* Some misapprehensions about code tuning.
    * Reduce the lines of code in a high-level language improves the speed or size of the resulting machine code - **false!**.
    * Certain operations are probably faster or smaller than others - **fake!**
        * If you change compilers or upgrade, the new compiler might automatically optimize code the way you were hand-tuning it and your work will have been wasted. Even worse, your code tuning might defect more powerful compiler optimization that have been designed to work with straightforward code.
    * You should optimize as yo go - **false!**
        * It's almost impossible to identify performance bottle necks before a program is working completly.
        * Premature opimization's primary drawback is its lack of perspective.
    * A fast program is just as important as a correct one - **false!**
        * It's hardly ever true that programs need to be fast or small before they need to be correct.

#### When to Tune.

* Use a high-quality design. Make the program right. Make it modular and easily modifiable so that it's easy to work on later. When it's complete and correct, check the performance. If the program lumbers, make it fast and small. Don't optimize until you know you need to.

#### Compiler Optimizations

* Opimizing compilers are better at optimizing straighforward code than they are at optimizing tricky code. If you do "clever" things like fooling around with loop indexes, your compiler has a harder time doing its job and your program suffers.

### 25.3 Kinds of Fat and Molasses.

* You must profile the program to know with any confidence whih parts are slow and fat.

#### Common Sources of Inefficiency.

* **Input/Output operations**
    * If you have a choice of working with a file in memory vs. on disk, in database, or across a network, use a in-memory data structure unless space is critical.
* **Paging**
    * An operation that causes the operating system to swap pages of memory is much slower than an operation that works on only one page of memory.
* **System Calls**
    * Calls to system routines are often expensive. They often involve a context switch - saving the program's state, recovering the kernel's state, and the reverse.
    * System routines include input/output operations to disk, keyboard, scren, pointer, or other device; memory-management routines; and certain utility routines.
    * If system routines are expensive, consider:
        1. Writing your own services.
        2. Avoid going to the system.
        3. Work with the system vendor to make the call faster.
* **Interpreted languages**
    * Interpreted languages must process each programming-language instruction before creating and executing machine code.
* **Errors**
    * Errors include leaving debugging code turned on, forgetting to deallocate memory, improperly designing database tables, polling non-existing devices until they time out.
    * Simply indexing the table improved performance by a factor of 30 for some operations. Defining an index on a commonly used table is not optimization; it's just good programming practice.

### 25.4 Measurements.

* Measure your code to find the hot spots. Once you've found the hot spots and optimized them, measure the code again to assess how much you've improved it.
* Experince doesn't help much with optimization either. A person's expercience might have come from an old machine, language or compiler.
* The only result of opimization you can usually be sure of without measuring performance is that you've made you're code harder to read. If it's not worth measuring to know that it's more efficien, it's not worth sacrificing clarity for a performance gamble.

#### Measurements Need to Be Precise

* Make sure that you're measuring only the execution time of the code you're tuning.
    * Try to factor out measurement overhead and program-startup overhead so that neither the original code nor the tuning attempt is unfaily penalized.

### 25.6 Summary of the Approach to Code Tuning

1. Develop the software by using well-designed code that's easy to understand and modify.
2. If performance is poor.
    1. Save a working version of the code.
    2. Measure the system to find hotspots.
    3. Determine whether code tuning is appropriate.
    4. Tune the bottleneck.
    5. Measure each improvement one at a time.
    6. If the improvement doesn't work, revert to step 1.


## 26. Code-Tuning Techniques

* Performance usually refers to both speed and size, but size reductions tend to come more frfom redesigning classes and data, rather than from tuning code. Coe tuning refers to small-scale changes rather than changes in large-scale designs.
* Code-tuning changes might seem cosmetically rimilar to store refactorings, however, refactorings are changes that improve a program's internal structure. The changes in code-tuning might better be called "anti-refactorings". Far from "improving in the internal structure", these changes degrade the internal structure in exchange for gains in performance.
    * If changes didn't degrade the internal structre, we wouldn't consider them to be optimizations; we would use them by default and consider them to be standard coding practice.

### 26.1 Logic

#### Stop testing when you know the answer

* Suppose you have a statement like `if (5<x) and (x<10) then`, the second part of the statement is not necessary.
* Prevent from iterating in a loop when it can already be broken.

#### Order Tests by Frequency

* Arrange tests so that the one that's fastest and most likely to be true is performed first.

#### Compare Performance of Similar Structures

* Depending on the environment, either approach (`case` statement or an `if-then-else` statement) might work better.

#### Substitute Table Lookups for Complicated Expressions

* In some circumstances, a table lookup might be quicker than traversing a complicated chain of logic.
    * The point of a complicated chain is usually to categorize something and then to take action based on its category.

#### Use Lazy Evaluation

* If a program uses lazy evaluation, it avoids doing any work until the work is needed.
    * If the program uses only a small percentage of the entries of a table, it might make more sense to compute them as they're needed rather than all aat once. Once an entry is computed, it can still be stored for future reference.

### 26.2 Loops

#### Unswitching

* Switching refers to making a decision inside a loop every time it's executed.
    * If the decision doesn't change while the loop is executing, you can unswitch the loop by putting the loop inside the conditional rather than the conditional inside the loop.

#### Jamming

* Jamming or "fusion" is the result of combining two loops that operate on the same set of elements.
    * Usually this means the loop counters have to be the same.

#### Unrolling

* The goal of loop unrolling is to reduce the amount of loop house keeping.
* Unrolling a loop is not a practical solution when you have a large number of elements or when you don't know in advance how many elements you'll have.
* To unroll the loop partially, you handle two or more cases in each pass through the loop instead of one.

#### Minimizing the Work inside loops

* Try to evaluate a statement or part of it, outside a loop so that only the result is used inside the loop.

#### Sentinel Values

* To reduce the amount of tests performed in a loop search, you can put a "sentinel" at the end of the seach range to stop the loop.
    * You can simply assign the value you're looking for to the element just beyond the end of the search range. (Remember to leave space for that element when you declare the array).
    * YOu then check each element, and if you don't find the element until you find the one you stucket at the end, you know that the value you're looking for isn't really there.

#### Putting the Busiest Loop on the Inside

* Each time the loop executes, it has to initialize the loop index, increment it on each pass through the loop, and check it after each pass.
    * The loop that executes more often must be the inner one.

#### Strength Reduction

* Reducing strength means replacing an expensive operation such as multiplication with a cheaper operation such as addition.

### 26.3 Data Transformations

#### Use Integers Rather than Floating-Point Numbers

* Integer addition and multiplication otend to be faster than floating point.

#### Use the Fewest Array Dimensions Possible

* If you can structure youor data so that it's in a one-dimensional array rather than a two dimensional or three-dimensional array, you might be able to save some time.

#### Minimize Array References.

* It's advantageous to minimize array access. A loop that repeatedly uses one element of an array is a good cadidate for the application of this technique.

#### Use Supplementary Indexes.

* String-length index
    * It's ofthen more efficient to keep track of the length of the structure rather than computing the length each time you need it.
* Independent, Parallel Index Structure.
    * If each data item is large, you can create an auxiliary structure that consists of key values and pointers to the detailed information.
    * All searching and sorting is done in memory, and you have to access the disk only once, when you know the exact location of the item you want.

#### Use Cahing

* Cachin means saving a few values in such a way that you can retrieve the most commonly used values more easily than the less commonly used values.
* The success of the cache depends on the relative cost of accessing a cached element, creating an uncached element, and saving a new element in the cache.
    * Success also depends on how often the cached information is requested.
* The cheaper it is to access a cached element and save new elements in the cache, the more valuable a cache is.

### 26.4 Expressions

#### Exploit Algebraic Identities.

* Since `sqrt(x) < sqrt(y)` only when `x` is less than `y`, youo can replace this test with `x < y`.

#### Use Strength Reduction

* Replace expensive operations with cheaper ones.

#### Initialize at Compile Time

* If you're using a named constant or a magic number is a routine call and it's the only argument, that's a clue that you could precompute the number, put it into a constant and avoid the routine call.

#### Be Wary of System Routines

* System routines are expensive and provide accuracy that's often washed. Typical system math routines are designed to put an astronaut on the moon within +/- 2 feet of the target. If you don't need that degree of accuracy, you don't need to spend the time to compute it either.

* Most of the so-called "trascendental" functions are designed for the worst case - that is, they convert to double precision floating point internally even if you give them an integer argument.

#### Use the Correct Type of Constants

* Use named constants and literals that are the same type as the variables they're assigned to. When a constant and its related variable are different types, the compiler has to do a type conversion to assign the constant to the variable.

#### Precompute Results

* A common low-level design decision is the choice of whether to compute results on the fly or compute them once, save them, and look them up as needed. If the results are used many times, it's often cheaper to compute them once and look them up the rest of the time.
    * At the simplest level, you might compute part of the expression outside a loop rather than inside.
    * At a more complicated level, you might compute a lookup table once when program execution beings, using it every time thereafter.

#### Eliminate Common Sub-expressions

* If you find an expression that's repeated several times, assign it to a variable an refer to the variable rather than recomputing the expression in several places.

### 26.5 Routines

#### Rewrite Routines Inline

* In some cases, you might be able to save a few nanoseconds by putting the code from a routine into the program directly where it's needed via the `inline` keyword.
    * Modern machines impose virtually no penalty for calling a routine.

### 26.6 Recoding in a low-level language

1. Write 100 percent of an application in a high-level language.
2. Fully test the application, and verify that it's correct.
3. If performance improvements are needed after that, profile the application to identify hot spots.
4. Recode a few small pieces in a low-level language to improve overall performance.

### 26.7 The More Things Change, the More they Stay the Same.

* Computeers have become so powerful that for many common kinds of programs, the level of performance optimization discusses in this chapter has become irrelevant.

* If an optimization isn't important-enough to haul out the profiling machinary, it isn't important enough to degrade readability, maintainability and other code characteristics.

## 27. How Program Size Affects Construction

### 27.1 Communication and Size

* The typical approach taken to streamlining communication is to formalize it in documents.

### 27.3 Effect of Project Size of Errors

* As project size increases, a larger percentage of errors can usually be attributed to mistakes in requirements and designs.
* On small projects, construction error make up about 75 percent of all the errors found.
* Project size and typical error density:
    * Smaller than `2K` LOC - `[0,25]` errors per thousand lines of code (KLOC).
    * `[2K,16K]` LOC - `[0, 40]` errors / KLOC.
    * `[16K,64K]` LOC - `[0.5, 50]` errors / KLOC.
    * `[64K,512K]` LOC - `[2, 70]` errors / KLOC.
    * More than `512K` LOC - `[4, 100]` errors / KLOC.

### 27.4 Effect of Project Size on Productivity

* At small sizes, the single biggest influence on productivity is the skill of the individual programmer.
* As project size increases, team size and organization become greater influences on productivity.

### 27.5 Effect of Project Size on Development Activities

* If you are working on a one-person project, the biggest influence on the project's success or failure is you.
* If you're working on a 25-person project, your organization will be a stronger influence on the project success or failure.

#### Activity Proportioins and Size

* On small/medium projects, construction (detailed design, coding, debuggin, unit-testing) is the most prominent activity by far.
* On very large projects, architecture, integration, and system testing take up more time and construction becomes less dominant.
* Proportions of activities vary because different activities become critical at different project sizes.
* Regardless of the size of a project, a few techniques are always valuable: disciplined coding practices, design and code inspections, good tool support and use of high-level languages.

#### Programs, Products, Systems and System Products

* The quality and the complexity of the final software influence on a project's size.
* Kinds of software:
    * **Program:** Used by the person who developed it.
    * **Product:** Used by people other than the original developer.
    * **System:** Group of programs that work together.
    * **System Product:** Polish of a product and multiple parts of a system.
* Programmers used to work on "programs" underestimate "system products" by a factor of almost 10.
* As you scale up, construction becomes a smaller part of the total effort in a project. If you base your estimates on construction experience, the estimation error increases.
* The estimation error would be completely attributable to you non understanding the effect of size on developing larger projects.

#### Methodology and Size

* In software development, the more formal the project, the more paper you have to generate to make sure you've done your homework.
* Paperwork is created as a direct result of the communication-overhead: the more people's breains you have to coordinate, the more formal documentation you need to coordinate them.
* The point of your writing a configuration-management plan is to force you to think carefullly about configuration management and to explain your plan to everyone else.
* You'll usually do better if you start you methods small and scale up for a large project.

## 28. Managing Construction

### 28.1 Encouraging Good Coding

* If someone on a project is going to define standards, have a respected architect define the standards rather than the manager. Software projects operate as much on an "expertise hierarchy" as on an "authority hierarchy".

#### Techniques for Encouraging Good Coding

* Assign two people to every part of the project
    * Pair programming
    * Mentor-trainee pairs
* Review every line of code
    * A code review involves the programmer and at least two reviewers.
    * Decisions are made by the group during reviews, and over time the group derives its own standards.
* Require code sign-offs.
    * Before code is considered to be complete, senior technical personnel must sign the code listing.
* Route good code examples for review.
    * Provide a clear example of the code quality you're aiming for.
* Emphasize that code listings are public assets.
    * Programmers sometimes feel that the code they've written is "their code", as if it were private property. Although it is the result of their work, code is part of the project and should be freely available to anyone else on the project who needs it.
* Reward good code
    * Use the organization's reward system to reinforce good coding practices.
    * The reward should be something that the programmer wants.
    * Code that receives an award should be exceptionally good.
* If you have a programming backgorund, an effective technique for eliciting good work is to say "I must be able to read and understand any code written for the project".

### 28.2 Configuration Management

#### What is Configuration Management?

* Configuration management is the practice of identifying project artifacts and handling changes systematically so that a system can maintain its integrity over tiime. Anotoher name for it is "change control".
* If you odon't control changes to requirements, you can end up writing code for parts of the system that are eventually eliminated.
* If chages to code aren't controller, you might change a routine that someone else is changing at the same time.
* Software Configuration Management (SCM) focuses on program's requirements, source code, documentation and test data.
* The systemic problem with SCM is overcontrol. The surest way to prevent software development problems is to stop all software development.
* On a large project, you'll probably need a full-blown SCM cheme, including faily formal procedures for backups, change control for requirements and design, and control over documents, source code, content, test cases, and other project artifacts.

#### Requirements and Design Changes.

* Follow a systematic change-control procedure.
* Handle change requrests in groups.
    * Write down all ideas and suggestions, no matter how easy they would be to implement, and save them until you have time to work on them. Then, viewing them as a group choose the ones that will be the most beneficial.
* Whenever your customer, your boss, or youo are tempted to change the system, estimate the time it would take to make the change, including review of the code for the change and retesting the whole system.
    * Regardless of how optimistic you ofeel when the change is first suggested, refrain from getting an off-the-cut estimate. Such estimates are often mistaken by a factor of 2 or more.
* A high volume of change requrest is a key warning sign that requirements, architecture or top-level designs weren't done well enough to support effective construction.
* Anyone who wants to propose a change submits the change request to the change-control board: An idea for a new feature, a change to an existing feature, and "error report" that might or might not be reporting a real error.
* Change control ltends to drift toward bureaucracy, so it's important to look for ways to streamline the change-control process. If you'd rather not use traditional change requests, set up a simple "change board" email alias and have people email change requests to the address.

#### Software Code Changes.

* If you happen to find an error after you've modified some code, you will compare the new version of the code to the old, by means of version-control tools that keep track of multiple versions of source code.
* Version control software.
    * You don't step on anyone's toes by working on a file while some one else is working on it.
    * You can update your copies of all the projects files to the current versions, by issuing a single command.
    * You can backtrack to any version.
    * You can get a list of the changes to any version of any file.
    * You don't have to worry about personal backups because the version control copy is a safely net.

#### Tool versions

* It may be necesasry to reconstruct the exact environment used to create each specific version of the software, including compilers, linkers, code libraries, and so on.

#### Machine Configurations

* A standarized development machine configuration can be created, as a disk image, including all the common developer tools, office applications and so on.
    * That image helps to avoid a raft of problems associated with slightly different configuration settings.

#### Backup Plan

* You should have a backup plan, including backups on a periodic basis and periodic transfer of backups to off-site storage, and it should encompass all the important materials on your project - documents, graphics, and notes- in addition to source code.
* Test your backup plan by doing a restore at some point to make sure that the backup contains everything youo need and recovery works.

### 28.3 Estimating a Construction Schedule

* Developers' estimates tend to have an optimism factor of 20 to 30 percent.

#### Estimate Approaches

* Several ways to estimate:
    1. Use estimating software.
    2. Use an algorithmic approach, such as `Cocomo II`.
    3. Have outside estimation experts estimate the project.
    4. Have a walk-through meeting for estimates
    5. Estimate pieces of the project, and then add the pieces tohether.
    6. Have people estimate their own tasks, and then add the task estimates together.
    7. Refer to experience on previous projects.
    8. Keep previous estimates and see how accurate they were.

* Establish Objectives.
* Allow time for the estimate, and plan it
    * Rushed estimates are inaccurate estimates.
* It's unreasonable for anyone to expect you to be able to estimate the amount of work required to build something when "something" has not yet been defined. Define requirements or plan a preliminary exploration phase before making an estimate.
* Estimate at a low level of detail.
* Use several different techniques, and compare the results.
* Reestimate periodically.

#### Estimating the Amount of COnstruction

* The best answer to the question of how much construction a project will call for is that the proportion will vary from project to project and organization to organization.

#### What to do if you're behind

* Hope that you'll catch up
    * Delays and overviews generally increase toward the end of a project.
* Expand the team
    * Adding people to a late software project makes it later. New people need time to familiarize themselves with a project before they can become productive. Their training takes up the time of the people who have already been trained. And merely increasing the number of people increases the compmlexity and amount of project communication.
    * If tasks are partitionable, you ocan divide them further and assign them to different people, even to people who are added late in the project.
* Reduce the scope of the project.
    * If you eliminate a feature, you eliminate the design, coding, debugging, testing, and documentatioin of that feature.
    * When you plan the product initially, partiion the product's capabilities into "must-have", "nice-to-have" and "optionals". If you fall behind, prioritize the "optionals" and "nice to have" and drop the ones that are the least important.
    * You might provide a version of a feature that's on time but that hasn't been tuned for performance.
    * Reestimate development time for the least important features.

### 28.4 Measurement

* For any project attribute, it's possible to measure that attribute in a way that's superior to not measuring it at all.
    * Measurement might not be precise, it might be difficult to make, and it might need to be refined over time, but measurement will give you a handle on your software development process that you don't have without it.
* Be aware of measurements side effects
    * People tend to focus on work that's measured and to ignore work that isn't.
* To argue against measurement is to argue that is better not to know what's really happening on your project.
    * Most measurements are useful meainlyl for identifying routines that are "outliers"; abnormal measurements in a routine are a warning sign that you should reexamine that routine, checking for unusually low quality.
    * Make sure you're collecting data for a reason. Set goals, determine the questions you need to ask to meed the goals and then measure to answer the questions.

### 28.5 Treating Programmers as People

#### How Do Programmers Spend Their Time?

* About 30 percent of a programmer's time is pent in nontechnical activities that don't directly help the project: walking, personal business, and so on.

#### Variation in Performance and Quality

* One study found that in a variety of professions, the top 20 percent of the people produced about 50 percent of the output.

#### Individual Variation

* "There are order-of-magnitude differences among programmers"
* The ratio of initial coding time between the best and worst programmers was about 20 to 1, the ratio of debuggin times over 25 to 1, of program size 5 to 1, and of program execution speed about 10 to 1.

#### Team Variation

* Good Programmers tend to cluster, as do bad programmers.
* 5-to-1 difference in program size and a 2.6-to-1 variation in the time required for a team to complete the same project.
* Develping a program with a team in the 15th percentile of programmers ranked by ability typically requires about 3.5 times as many work months as developing a program with a team in the 90th percentile.
*The implication for recruiting and hiring is clear. If you have to pay more to get a top-10 percent programmer rather than a bottom-10-percent programmer, jump at the chance.

#### Religious Issues

* Aa programmer's position on each religious issue is a reflection of personal style.
* Use "suggestions" or "guidelines" with respect to the area
    * Avoid setting rigid "rules" or "standards".
* Finesse the issues you can by sidestepping explicit mandates
    * Require source doe to be run through a pretty-printer formatter before it's declared finished. Let the pretty printer do the formatting.
* Have your programmers develop their own standards.

#### Physical Environment

* The programmers who performed in the top 25 percent had bigger, quieter, more private offices, and fewer interruptions from people and phone calls.

### 28.6 Managing your manager

* In software development, nontechnical managers are common, as are managers who have technical experience but who are 10 years behind the imes. Technically competent, technically current managers are rare.
* "Managing your manager" means that you need to tell your manager what to do, rather than the other way around, in a way that allows your manager to continue believing that you are the one being managed.
    * Focus on your manager's interest, doing what he or she really wants you oto do and don't distrct your manager with unnecessary implementation details.

## 29. Integration

* The term "integration" refers to the software-development activity in which you combine separate software components into a single system.
    * It might consist of a morning spend hooking a handful of classes together, on small projects.
    * Ono large projects, it might consist of weeks or months of hooking sets of programs together.
* The order in which you build classes or components affects the order in which you can integrate them.

### 29.1 Importance of the Integration Approach

* If you construct and integrate software in the wrong order, it's harder to code, harder to test, and harder to debug. If none of it will work until all of it works, it can seem as though it will never be finished.

### 29.2 Integration Frequency - Pashed or Incremental?

#### Phased Integration

* Steps:
    1. Design, code, test and debug each class ("Unit development")
    2. Combine the classes into one whopping-big system (system integration)
    3. Test and debug the whole system (System dis-integration)
* Since you have a large number of classes that have never worked together before, when they are put together the first time, new problems inevitably surface and the causes of the problems could be anywhere.

#### Incremental Integration

* You write and test a program in small pieces and then combine the pieces one at a time.
* Steps:
    1. Develop a small, functional part of the system. Thorougly test and debug it. It will serve as a skeleton on which to hand the remaining parts of the system.
    2. Design, code, test and debug a class.
    3. Integrate the new class with the skeleton. Test and debug the combination of the skeleton and new class.

##### Benefits of Incremental Integration

* When new problems surface during increemental integration, the new class is obviously involved. Either its interface to the rest of the program contains an error or its interaction with a previously integrated class produces an error. Either way, you know exactly where to look.
* WHen the code is integrated and running, even if the system isn't usable, it's apparent that it soon will be.
* When you integrate frequently, the features that are present and not present are obvious.
* You'll improve customer relations.
* The units of the system are tested more fully.
* If integration is planned carefully, you can design part of the system while another part is being coded.

### 29.3 Incremental Integration Strategies

* With incremental integration, most systems will call for the integration of some components before the integation of others.* Planning for integration thus affects planning for construction; the order in which components are constructed has to support the order in which they will be integrated.

#### Top-Down Integration

* The class at the top of the hierarchy is written and integrated first. Stubs have to be written to exercise the top class. Then, as classes are integrated from the top down, stub classes are replaced with real ones.
* Interfaces between classes must be carefully specified. The most troublesome errors to debug are not the ones that affect single classes but those that arise from subtle integrations between classes. Careful interface specification can reduce the problem.
* All the classes at the top of the hierarchy are exercised a lot so that big conceptual, design problems are exposed quickly.
* A good alternative to pure top-down integration is the vertical slice approach, in which the system is implemented top-down in sections pehaps fleshing out areas of functionality one by one, and then moving to the next area.

#### Bottom-Up Integration

* You write and integrate the classes at the bottom of the hierarchy first.
* The main problem with bottom-up integration is that it leaves integrations of the major, high-level system interfaces until last. If the system has conceptual design problems at the higher levels, construction won't find them until all the detailed work has been done. If the design must be changed significantly, some of the low-level work might have to be discarded.

#### Sandwich Integration

* You first integrate the high-level business-object classes at the top of the hierarchy. Then you integrate the device-interface classes and widely used utility classes at the bottom.

#### Risk Oriented Integration

* Tends to integrate the classes at the top and the bottom first, saving the middle-level classes for last.
* You identify the level of rist associated with each class. You decide which will be the most challenging parts to implement, and you implement them first. The remainder of the code, the easy stuff, can wait until later.

#### Feature Oriented Integration

* Integrate one feature (on identifiable function of the system you're integrating) at a time.
* You'll usually want to start with a skeleton you've chosen for its ability to support the other features. You hang the rest of the features on the feature that you integrated first.
* Components are added in "feature trees", hierarchical collections of classes that make up a feature.
* Integration is easier if each feature is relatively independent, perhaps calling the same low-level library code as the classes for other features but having no calls to middle level code in common with other features.
* The skeleton might need a little scaffolding, or some parts of the skeleton might simplme not be operational until particual features have been added.
* Each feature bring an incremental addition in functionality.

#### T-Shaped Integration

* One specific vertical slice is selected for early development and integration. That slice should exercise the system end-to-end and should be capable of flushing out any major problems in the systems design assumptions.

### 29.4 Daily Build and Smoke Test

* A "Smoke test" is a relatively simple check to see whether the product "smokes" when it runs.
* By smoke testing, you bring the system to a known good state, and then you keep it there. You odon't allow it to deteriorate.
* Teams that haven't used the daily build process sometimes feel that daily builds slow their progress to a snail's crawl. What's really happening is that daily builds amortize work more steadily throughout the project.
* Treat the daily build as the heartbeat of the project.
* At a minimum a good build should
    * Compile all files, libraries and other components successfully.
    * Link all files, libraries, and other components successfully.
    * Not contain any showstopper bugs that prevents the program bfrom being launched or that makes it hazardous to operate (should pass the smoke test).
* The smoke test should exercise the entire system from end to end. If the smoke test passes, you can assume that the build is stable enough to be tested more thoroughly.
* The smoke test must evolve as the system evolves.
* Automate the daily build and smoke test.
* Tending the daily build and keeping the smoke test up to date becomes a big enough task to be an excplicit part of someone's job.
* Add revisions to the build only when there are meaningful increments to the system.
* Don't wait too long to add a set of revisions
    * If a develpoer goes more than a couple of days without checking in a set of changes, consider that developer's work to be at rist.
    * Frequent integration sometimes forces you to break the construction of a single feature into multiple episodes.
* The developer must be sure that the new code passes the smoke test before it's allowed to influence other parts of the system.
* Developers need to be able to rely on a known good system. Most groups solve this problem by creating a holding area for code that developers think is ready to be added to the build.
    * New code goes into the holding area, the new build is build, and if the build is acceptable, the new code is migrated into the master sources.
* Create a penality for breaking the build.
    * Make it clear from the beginning that keeping the build healthy is one of the project's top priorities.
    * A broken build should be the exception, not the rule.
* Release builds in the morning
    * Smoke test in the early morning and release new builds in the morning rather than the afternoon.
* Build and smoke test even under pressure.
    * Under stress, developers lose some of their discipline.

#### What Kind of Projects Can Use the Daily Build Process?

* The larger the project, the more important incremental integration becomes.

##### Continuous Integration

* "Continuous" means "at least daily".
* None of top technical executives from important companies think that continuous integration is superior to daily integration.

## 30. Programming Tools

## 31. Layout and Style

* The techniques in this chapter don't affect execution speed, memory use, or other aspects of a program that are visible from outside the program. They affect how easy it is to understand the code, review it, and reuse it months after you write it.

### 31.1 Layout Fundamentals

#### Layout Extremes

* The layout should not be crowded and should offer some clue to the routine's logical organization.
* Routines have to be readable, and the effort put into documentation and good variable names should be evident.

#### The Fundamental Theorem of Formatting.

* Good visual layout shows the logical structure of a program.
* If one technique shows the structure better and another looks better, use the one that shows the structure better.

#### Human and Computer Interpretations of a Program

* A good layout scheme would make the usual structure of a program match the logical structure, or tell the same story to the human that it tells to the computer.
* When program statements were arranged in a sensible order, experts were able to remember them better than novices. WHen statements were suffled, the experts' superiority was reduced.

#### Layout as Religion

* Layout might harm an expert's ability to read a program if the layout is different from the scheme the expert uses.

#### Objectives of Good Layout

* Explicitly, a good layout scheme should do the following:
    * Accurately represent the logical structure of the code.
    * Consistently represent the logical structure of the code.
    * Improve readability.
    * Withstand modifications.

### 31.2 Layout Techniques

#### White Space.

* White space is grouping, making sure that related statements are grouped together.
* Just as it's important to group related statements, it's important to separate unrelated statements from each other.
    * Use blank lines to indicate how a program is organized.
* Use indentation to show the logical structure of a program. As a note, you should indent statements under the statement to which they are logically subordinate.
    * Two-to-four space indentation is optimal.
    * Six-space indentation looks pretty, but turn out to be less readable.

#### Parentheses

* You should use parentheses whenever there's any doubt about how an expression is evaluated.

### 31.3 Layout Styles

#### Pure blocks

* A control construct in Visual Basic always has a `Begin` statement and it always has a corresponding `End` statement. Indenting the inside of the structure isn't a controversial practice, and the options for aligning the other keywords are somewhat limited.

#### Emulating Pure Blocks

* View the begin and end keywords (`{` and `}` tokens) as extensions of the control construct they've used with.
* The control structure opens the block in the first statement, implying that the "begin" should be at the end of the first statement.

#### Using begin-end Pairs to Designate BLock Boundaries.

* View the begin and the end as statements that follow the control construct rather than as fragments that are part of it.
* To treat the begin and the end as parts of the block structure rather than the control statement, you have to put the begin at the beginning of the block (rather than at the end of the control statement) and the end at the end of the block (rather than terminating the control statement).

#### Endline Layout

* The code is indented to the middle or end of the line.
* The endline indentation is used to align a block with the keyword that began it, to make a routine's subsequent parameters line up under its first parameter.
* Endline layout is inaccurate, hard to apply consistently and hard to maintain.

#### Which Style is Best?

* Choose the style you like or the one that is preferred by the majority of people on your team. There is no statistically significat difference between either pure-block emulation or begin-end block boundaries.

### 31.4 Laying out control structures

#### Fine Points of Formatting Control-Structure Blocks

* Avoid unindented begin-end pairs.
    * Unindented begin-end pairs aren't part of the control construct, and they aren't part of the statements after it either.
* Avoid double indentation with begin and end.
    * Prevent from indenting begin and end, and then indenting again the statements they enclose.

#### Other Considerations

* A logical block - a group of statements that belong together - should be treated the way paragraphs in English are: separete them from one another with blank lines.
    * The discipline of putting blank lines throughout a program makes you think harder about which statements really belong together.
* Format single-statement blocks consistently
    * Using the begin-end pair reduces the chance that you'll add statements after the if test and forget to add begin and end.
* For complicated expresions, put separate conditions on separate lines.
* Avoid gotos
    * Use a name in all caps for the label the code goes to.
    * Put the statement containing the goto on a line by itself.
    * Put the label the goto goes to on a line by itself. Surround it with blank lines.
* For the ability to accomodate longer lines, consistency, and maintainability, prefer pure blocks instead of endline indentation.

### 31.5 Laying out individual statements

#### Statement Length

* Try to limit statement line length to 80-90 characters.

#### Using spaces for clarity

* Use spaces to make logical expressions readable
    * You should separte identifiers from other identifiers with spaces.
* Use spaces to make array references readable
    * Use spaces around each index in the array to make the indexes readable.
* Use spaces to make routine arguments readable.

#### Formatting Countinuation Lines

* Make the incompleteness of a statement obvious.
    * Break the statement so that the part on the first line is systactically incorrect if it stands alone.
    * This break helps prevent incorrect modifications.
* An alternative approach is to put the continuation character at the beginning of the continuation line.
    * It makes it easier to scan for the operator at the left edge of the column, where the text is aligned, rather than at the right edge, where it's ragged.
    * It has the additional advantage of iluminating the structure of the operations.
* Keep closely related elements together.
* Indent routine-call continuation lines the standard amount
    * If you normally indent three spaces for statements in a loop, indent the continuation lines for a routine by three spaces.
* Make it easy to find the end of a continuation line.
    * Put each argument in a line of its own and indicate the line end of the group with a closing parentheses.
    * In practice, usually only a few routines needs to be broken into multiple lines. Any formatting style is OK, as long as you use it consistently.
* If you run out of room for a for loop, a while loop, or an if statement, indent the continuation line by the same amount of space that you indent statements in a loop or after an if statement.
* Do not align right sides of assignment statements.
    * If becomes a headache to maintain the alignment of equal signs as variable names change.
* Indent assignment-statement continuation lines the standard amount.

#### Using Only one statement per line

* Putting each statment on a line of its own provides an accurate view of a program's complexity.
* Putting several statements on one line doesn't provide optimization clues to modern compilers.
* With statements on their own lines, the code reads from top to bottom, instead of top to bottom and left to right.
* It's easier to find syntax error when your compiler provides only the line numbers of the errors.
* It's easy to step through the code with line-oriented debuggers.
* It's easier to edit individual statements.
* Avoid using multiple operations per line (side effects).
    * The code that you overlook because you "recognize" it rather than read it can contain the error that's harder to find than it needs to be.
* Improved performance doesn't justify putting multiple operations on the same line either.
* Even if you read statements with side-effects easily, take pity on other people who will read your code. Most good programmers need to think twice to understand expressions with side effects. Let them use their brain cells to understand the larger questions of how your code works rather than the syntactic defaults of a specific expression.

#### Laying Out Data Declarations

* Use only one data declaration per line
    * It's easier to put a comment next to each declaraction
    * It's easier to modify declarations
    * It's easier to find specific variables.
    * It's easier to find and fix syntax errors.
* Declare variables close to where they're first used.
* Order declartions sensibly.
    * If your list of variables is so long that alphabetical ordering helps, your routine is probably too big. Break it up so that you have smaller routines with fewer variables.
* In C++, put the asterisk next to the variablee name in pointer declarations or declare pointer types.

### 31.6 Laying Out Comments

* Indent a comment with its corresponding code.
    * Comments should not interfere with the program's logical structure.
* Set off each comments with at least one blank line.

#### 31.7 Laying out Routines

* Use blank lines to separte parts of a routine
* Use standard indentation for routine arguments
    * The options with routine-header layout are about the same no conscious layout, endline layout, or standard indentation.
    * The main problem with endline layout is that it takes a lot of work to maintain, and styles that are hard to maintain aren't maintained.
    * Standard indentation has an aesthetical appeal and take less work to maintain. In this case, each parameter take one line. As a result, if parameters are added or deleted, only one line has to be modified.

### 31.8 Laying out classes.

#### Laying out class interface

* The convention is to present the class memebers in the following order:
    1. Header comment that describes the class
    2. Constructors and destructors.
    3. Public routines.
    4. Protected routines.
    5. Private routines and member data.

#### Laying Out class Implementation

* Class implementation should layout in this order.
    1. Header comment describing the contents of the file.
    2. Class data
    3. Public routines
    4. Protected routines
    5. Private routines

* If you have more than one class in a file, identify each class clearly.
    * Avoid over emphasizing comments within classes.
    * Avoid using rows of asterisks. Less is moroe.
    * If you must separate parts of a program with long lines of special characters, develop a hierarchy of characters (from densest to lightest) instead of relying exclusively on asterisks.
    * If you're using a language that support multiple source files, put only one class in each file unless you have a compelling reason to do otherwise (such as including a few small classes that make up a single pattern).

#### laying Out Files and Programs

* Put one class in one file.
    * A file should hold a collection of routines that support one and only one purpose.
    * A file reinforces the idea that a collection of routines are in the same class.
* Give the file a name related to the class name.
* Separte routines withing a file clearly.
    * Separte each rutine from other routines with at least two blank lines.
* Sequence routines alphabetically may help.
* Order the source file carefully.
    1. File-description comment.
    2. `#include` files.
    3. Constant definitions that apply to more than one class.
    4. Enums that appy to moore than one class.
    5. Macro function definitions.
    6. Type definitions that apply to more than one class.
    7. Global variables and functions imported.
    8. Global variables and functions exported.
    9. Variables and functions that are private to the file.
    10. Classes, including constant definitions, enums, and type definitions within each class.

## 32. Self-Documenting Code

* Good documentation is a sign of the professional pride a programmer puts into a program.

### 32.1 External Documentation

* External construction documentation tends to be at a high lend compared to the code, at a low level compared to the documentation from the problem definition requirements and architecture activities.
* Unit-Development Folder (UDF)
    * Informal document containing notes used by a developer during construction.
    * Provides a trail of design decisions that aren't documented else where.
    * Has some copies of relevant requirements.
    * Parts of the top level design the unit implements.
    * A copy of the development standards.
    * A current code listing.
* Detailed-design documents.
    * Describes the class-level or routine level design decisions, the alternatives that were considered and the reasons for selecting the approaches that were selected.

### 32.2 Programming Style as Documentation

* Internal documentation is very likely to remain correct as the code is modified because it's most closely associated with the code.
* The main contributor to code level documentation is good programming style:
    * Good program structure.
    * Use of straght forward and easily understandable approaches.
    * Good variable names.
    * Good routine names.
    * Use of named constants instead of literals.
    * Clear layout.
    * Minimization of control-flow and data structure complexity.

### 32.3 To comment or Not to Comment.
* Comments are easier to write poorlly than well, and commenting can be more damaging than helpful.

### 32.4 Keys to Effective Comments

* Bad comments:
    1. Incorrect comments
    2. Accurate comments that add nothing to the code. Commenting merely repeats the code.

#### Kinds of Comments

* Repeat of the Code
    * The comment restates what the code does in different words.
* Explanation of the Code
    * Explain complicated, tricky or sensitive pieces of code.
    * It is usually useful when the code is confusing.
    * If the code is so complicated that it needs to be explained it's nearly always better to improve the code than it is to add comments.
* Marker in the Code
    * A comment that is not intended to be left in the code, it's a note to the developer that the work isn't done yet.
* Summary of the Code.
    * It distills a few lines of code into one or two sentences.
* Description of the code's Intent.
    * Explains the purpose of a section of code.
    * Operate at the level of the problem (business) than at the level of the solution.
* Information that cannot possibly be expressed by the code itself.

#### Commenting Efficiently

* Commenting might be difficultl because the words to describe what the program is doing don't come easily. That's usually a sign that you don't understand what the program does.
* The time you spend "commenting" is really time spent understanding the program better.
* Use styles that don't break down or discourage modification.
    * Any style that's too fancy is annoying to mantain.
    * If you spend a lot of time entering and deleting dashes to make plus signs line up, you're not programming; you're wasting your time.
* Use the pseudocode programming process to reduce commenting time.
* Integrate commenting into your development style.
    * Leaving commenting until the end becomes a task in its own right, which makes it seem like more work than when it's done a little bit at a time.
    * If you have to concentrate so hard on writing code that commenting interrupts your thinking, you need to design in pseudocode first and then convert the pseudo-code to comments.

#### Optimum Number of Comments.

* One comment rougly every 10 statements was the desity at which clarity seemed to peak. Fewer comments made the code hard to understand. More comments reduced code understandability.
* Rather than focusing on the number of comments, focus on whether each comment is efficient. If the comments describe why the code was written, and meet the other criteria established in this chapter, you'll have enough comments.

### 32.5 Commenting Techniques

#### Commenting Individual Lines

* In good code, the need to comment individual lines of code is rare. It might be a sign of that line being complicated enough to need an explanation.
* Avoid self-indulgent comments

#### Endline comments and their problems

* Endline comments appear at the end of lines of code.
* Endline comments are hard to maintain. If the code on any line containing an endline comment grows, it bumps the comment further outand all the other endline comments will have to be bumped out to match.
* Avoid endline comments on single lines.
    * The comments might merely repeat the code.
* Avoid endline comments for multiple lines of code.
* Use endline comments to annotate data declaration
* Avoid using endlines comments for maintenance notes.
    * Comments should explain why the code works now, not why the code didn't work at some point in the past.

#### Commenting Paragraphs of Code.

* Most comments in a well-documented program are one-sentence comment that describe paragraphs of code.
    * The comment doesn't repeat the code, it describes the code's intent.
* Write comments at the level of the code's intent.
* Focus your documentation efforts on the code itself.
    * Use named constants, add a variable to contain the result of the search.
    * If the code is good enough, it begins to read at close to the level of intent, encroaching on the comment's explanation of the code's intent.
* Focus comments on the why rather than the how.
    * It's nearly impossible for a comment that focuses on how and operation is done to explain the intent of the operation.
    * Comments that tell `how` are often redundant.
* A reader should be able to scan only the comments and get a good idea of what the code does and where to look for a specific activity.
* Make every comment count.
    * Rather than writing more comments, put the extra effort into making the code itself more readable.
* Document surprises.
    * If you have used a tricky technique instead of a straight forward one to improve performance, use comments to point out what the straight forward technique would be and quantify the performance gain achieved by using the tricky technique.
* Comments should be unambiguous, readable without the work of figuring out abbreviations.
* Comment an error or undocumented features.
* Don't comment tricky code; rewrite it.
    * If something seems tricky to you, it will be incomprehensible to someone else.
    * Make your code so good that you don't need comments, and then comment it to make it even better.

#### Commenting Data Declarations.

* Comments for variable declarations describe aspects of the variable that the variable name can't describe.
* Comment the units of numeric data
    * Don't assume that the units are obvious.
    * Alternative, in many cases you should embed the units in the variable names rather than in comments.
* If your language supports enumerated types, use them to express coded meaning. If it doesn't, use comments to indicate what each value represents, and use a named constant rather than a literal for each of the values.
* Comment limitations on input data (expected and unexpected data). You can also use assertions to document valid ranges, and make the code more self-checking.
* If a variable is used as a bit field, document the meaning of each bit.
* If you have comments that refer to a specific variable, make sure the comment is updated whenever the variable is updated.
* If global data is used, annotate each piece well at the point at which it's declared. The annotation should indicate the purpose of the data and why it needs to be global.

#### Commenting Control Structures

* Put a coment before each `if`, `case`, `loop`, or block statement.
    * You can provide the reason for a decision and a summary of the outcome.
* Comment the end of each control structure.
    * You don't need to use the technique for short loops that aren't nested. When the nesting is deep or the loops are long, however, the technique pays off.
* Treat end-of-loop comments as a warning indicating complicated code.

#### Commenting Routines

* Heavy routine headers are a recipe for inaccurate comments and maintenance failure.
* Keep comments close to the code they describe.
    * During maintenance, comments that are far from the code tend not to be maintained with the code. The comments and the code start to disagree, and suddenly the comments are worthless.
* Create a boilerplate documentation prolog. Fill out the parts that matter and delete the rest.
* Describe each routine in one or two sentences at the top of the routine. Difficulty in creating a short description is a sign that the design isn't as good as it should be.
* Put comments next to the parameter declarations.
    * If your variable names are good enough, you might be able to skip commenting them.
* Take advantage of code documentation utilities such as Javadoc.
    * If you're not working in an environment that supports document extraction, like Javadoc, you're usually better off keeping the comments closer to the parameter names to avoid inconsistent edits and duplication of the names themselves.
* Differentiate between input and output data.
    * If your language doesn't support input and output data differentiation automatically, put it into comments.
* Documet interface assumptions.
    * If you have made any assumptions about the state of variables you receive -legal and illegal values, arrays being in sorted order, member data being initialized or containing only good data- document them either in the routine prolog or where the data is declared.
* Comment on the routine's limitations.
    * Indicate the accuracy of a numeric result.
    * Document the conditions under which the computations are undefined.
    * Document any default behaviour when a routine gets into trouble.
    * Document any expected size of data.
* If the routine modifies global data, describe exactly what it does to the global data.
* Document the source algorithms that are used (volume, page number, book name, and so on).

#### Commenting Classes, Files and Programs.

##### General Guidelines for Class Documentation

* Describe the class's design philosophy, overall design approach, design alternatives that were considered and discarded and so on.
* Descrbie any limitations by the class's design. Also describe assumptions about input and output data, error-handling responsibilities, global effects, sourcs of algorithms, and so on.
* Can another programmer understand how to use a class without looking at the class's implementation? If not, class encapsulation is seriously at risk.
    * The class's interface should contain all the information anyone needs to use the class.
* Don't document implementation details in the class interface.

#### General Guidelines for File Documentation.

* Describe the purpose, and content of each file.
    * Describe the classes or routines contained in a file.
    * If the purpose of a file is obvious, e.g. contain one specific class, the comment is not necessary.
    * If the file contains more than one class, explain why the classes need to be combined into a single file.
* Authorship and primary responsiblity for specific areas of souce code becomes important on large projects.
    * Let some contact info (name, email address) on the code, so other programmers will be able to contact you.
* Include legal notices in the block comment.
* Give the file a name related to its contents.

## 33. Personal Character

### 33.1 Isn't Personal Character Off the Topic?

* If you want to be great, you're responsible for making yourself great. It's a matter of your personal character.

### 33.2 Intelligence and Humility

* Great intelligence is only loosely connected to being a good programmer.
* The way you focus your intelligence is more important than how much intelligence you have.
* Most of programming is an attempt to compensate for the strictly limited size of our skulls. The people who are best at programming are the people who realize how small their brains are.

### 33.3 Curiosity

* Programmers are so busy working they often don't have time to be curious about how they might do their jobs better.
* The more aware you are of the development process, whether from reading or from your own observations about software development, the better position you're in to understand changes and to move your group in a good direction.
* If you can't learn at your job, find a new one.
* One effective way to learn about programming is to experiment with programming and the development process.
* Read about problem solving.
    * Problem solving is the core activity in building computer software.
* Analyze and plan before you act.
* One especially good way to learn about programming is to study the work of the great programmers.
* Ask to look at the code of programmers you respect. Ask to look at the code of programmers you don't. Compare their code, and compare their code to your own. What are the differences? Why are they different? Which way is better? Why?
* Read!
    * Documentation contains the keys to the castle, and it's worth spending time reading it. Overlooking information that's readily available is such a common oversight that a familiar acronym on newsgroups and bulletin boards is "RTFM!" which stand for "Read the Fucking Manual!".
* Read other books and periodicals.
* Affiliate with other professionals.
* Make a commitmet to professional development.
    * It's no sin to be a beginner or an intermediate. It's no sin to be a competent programmer instead of a leader. The sin is in how long you remain a beginner or intermediate after you know what you have to do to improve.

### 33.4 Intellectual Honesty

* Intellectual honesty commonly manifests itself in several ways:
    * Refusing to pretend you're an expert when you're not.
    * Readily admitting your mistakes.
    * Trying to understand a compiler warning rather than supressing the message.
    * Providing realistic status reports.
    * Clearlly understanding your program -not compiling it to see if it works.
    * Providing realistic schedule estimates and holding your ground when management asks you to adjust them.

### 33.5 Communication and Cooperation

* Keep the person who has to modify your code in mind. Programming is communicating with another programmer first and communicating with the computer second.

### 33.6 Creativity and Discipline

* Without standards and conventions on large projects, project completion itself is impossible.
* A programming masterpiece requires just as much discipline. If you don't try to analyze requirements and design before you begin coding, much of your learning about the project will occur during coding and the result of your labors will look like a mess.

### 33.7 Laziness

* Laziness manifests itself in several ways.
    * Deferring an unpleasant task.
    * Doing an unpleasant task quickly to get it out of the way.
    * Writing a tool to do the unpleasant task so that you never have to do the task again.

### 33.8 Characteristics That Don't Matter as Much as you Think

#### Persitence

* If you want to identify persistence as a bad quality, you say it's "stubbornness". If you want it to be a good quality, you ocall it "tenacity".
* Most of the time, persistence in software development is pigheadedness - it has little value. Persistence when you're stuck on a piece of new code is hardly ever a virtue. Try redesigning the class, try an alternative coding approach, or try coming back to it later. When one approach isn't working, that's a good time to try an alternative.
* "If I don't solve the problem using this approach within the neset 30 minutes, I'll take 10 minutes to brainstorm about different approaches and try the best one for the next hour".

#### Experience

* The value of hands-on experience as compared to book learning is smaller in software development than in many other fields.
* If you work for 10 years, do you get 10 years of experience or do you oget 1 year of experience 10 times? You have to reflect on your activities to get true experience. If you make learning a continuous commitment, you'll get experience. If you don't, you won't. No matter how many years you have under your belt.

### 33.9 Habits

* Good habits matter because most of what you do as programmer you do without consciously thinking about it.
* You're always looking for ways to make code readable or fast, or you're not. If you have to choose between making code fast and making it readable, and you make the same choice every time, you're not really choosing - you're responding out of habit.
* What you do becomes habit, and over time, your good and bad habits determine whether you're a good or a bad programmer.
* When you first learn something, learn it the right way. When you first do it, you're actively thinking about it and you still have an easy choice between doing it in a good way and doing it in a bad way.
* It's easier to replace an old habit with a new one than it is to eliminate one altogether. In programming, try to develop new habits that work. Develop the habits of writing a class in pseudocode before coding it and carefully reading the code before compiling it, for instance. You won't have to worry about losing the bad habits; they'll naturally drop by the wayside as new habits take their places.

## 34. Themes in Software Craftsmanship

### 34.1 Conquer Complexity

* Dividing a system into subsystems at the architecture level so that your brain can focus on a smaller amount of the system at one fime.
* Carefully defining class interfaces so that you can ignore the internal workings of the class.
* Preserving the abstraction represented by the class interface so that your brain doesn't have to remember arbitrary details.
* Avoid global data, because global data vastly increases the percentage of the code you need to juggle in your brain at any one time.
* Avoid deep inheritance hierarchies because they are intellectually demanding.
* Avoid deep nesting of loops and conditionals.
* Avoid gotos because they introduce nonlinearity that is difficult for most people to follow.
* Carefully defining your approach to error handling rather than using an arbitrary proliferation of different error-handling techniques.
* Being systematic about the use of the built-int exception mechanism.
* Not allowing classes to grow into monster classes.
* Keep routines short.
* Using clear, self-explanatory variable names.
* Minimizing the number of parameters passed to a routine, or, more important, passing only the parameters needed to preserve the routine interfaces abstraction.
* Using conventions to spare your brain the challenge of remembering arbitrary, accidental differences between different sections of code.
* Put a complicated test into a boolean function and obstract the purpose of the test.
* Substitute a table lookup for a complicated chain of logic.
* Create a well-defined consistent class interface to eliminate the need to worry about implementation details of the class.
* Conventions are the most useful when they spare you othe trouble of making and defending arbitrary decisions. They're less valuable when they impose restrictions in more meaningful areas.
* Naming variables functionally for the what of the problem rather than the "how" of the implementation-level solution, increases the level of abstraction.
* Using named constants rather than literals also increases the level of abstraction.
* A primary goal lof software design and construction is conquering complexity.

### 34.2 Pick your Process

* On small projects, the talents of the individual programmer are the biggest influence on the quality of the software.
* On projects with more than one programmer, the way in which people work together determines whether their abilities are added to each other or substracted from each other.
    * One example of the way in which process matters is the consequence of not making requirements stable before you begin designing and coding.
* You have to lay a solid foundation of the design before you can begin building on it.
* Testing merely tells you the specific ways in which your software is defective. Testing won't make your program more usable, faster, smaller, more readable, or more extensible.
* Premature optimization wastes time because you spend time polishing sections of code that don't need to be polished.
    * Youo might polish sections that are small enough and fast enough as they are, you might polish code that you later throw away, and you might fail to throw away bad code because you've already spent time polishing it.

### 34.3 Write Programs for People First, Computer Second.

* Readable code doesn't take any longer to write than confusing code does, at least not in the long run.
* Favoring write time convenience over read time convenience is a false economy.
* Be sure that what you're doing is something you want to become a habit.

### 34.4 Program into Your Language, Not in It.

* Don't limit your programming thinking only to the concepts that are supported automatically by your language. The best programmers think of what they want to do, and then they assess how to accomplish their objectives with programming tools at their disposal.

### 34.5 Focus Your Attention with the Help of Conventions

* Conventions save programmers the trouble of answering the same questions again and again. On projects with many programmers, using conventions prevents the confusion that results when different programmers make the arbitrary decisions differently.
* You can establish conventions to eliminate the use of dangerous practices, to restrict such practices to cases in which they're needed, or to compensate for their known hazards.
* Having conventional ways of handling memory requests, error processing, input/output, and class interfaces adds a meaningful structure to your code and makes it easier to another programmer to figure out - as long as the programmer knows your convention.
* Conventions can compensate for language weakness.

### 34.6 Program in Terms of the Problem Domain

* One way of working at a high level of abstraction is to work in terms of the programming problem rather than the computer-science solution.
* Information at the level of detail should be hidden. At the highest level, you shouldn't have any idea how the data is stored.

#### Separating a Program into levels of Abstraction

* The part of the program that works in implementation-level terms must be isolated from the part that works in problem-domain terms.

#### Low level techniques for working in the problem domain.

* Use classes to implement structures that are meaningful in problem domain term.
* Hide information about the low level data types and their implementation.
* Use named constants to document the meanings of strings and of numeric literals.
* Assign intermediate variables to ducment the results of intermediate calculations.
* Use boolean functions to clarify complex boolean tests.

### 34.7 Watich for Falling Rocks.

* Programming is a craft somewhere between art and science.
* Warning signs in programming alert youo to the possibility of problems: "Watch for Fallling rocks".
* "Tricky code" is a code phrase for "bad code".
* A good process wouldn't allow error-prone code to be developed.
* The fact that a class contains more than seven members doesn't necessarily mean that it's poorly designed, but it's a warning that the class is complicated.
    * More than about 10 decision points in a routine, more than three levels of logical nesting, an unusual number of variables, high coupling to other classes or low class or routine cohesion should raise a warning flag.
* Difficulties in writting comments, naming variables and decomposing the problem into cohesive classes with clear interfaces all indicate that you need to think harder about the design before coding.
* Paying attention to warnings about the quality of thinking directly affects the final product.

### 34.8 Iterate, Repeatedlyl, Again and Again

* Iterating on requirements is perhaps as important as any other aspect of the software-development process.
* Projects fail because they commit themselves to a solution before exploring alternatives. Iterations provides a way to learn about a product before you build it.
* A first attempt might produce a solution that works, but it's unlikely to produce the best solution. Taking several repeated and different approaches produces insight into the problem that's unlikely with a single approach.
* Once the software is operational, you can rewrite smalls parts of it to greatly improve overall system performance.

### 34.9 Thou Shat Rend Software and Religion Asunder.

#### Software Oracles.

* Experiment with the exciting, recent methods, but bank on the old and dependable onees.

#### Eclecticism

* Rigid processes are inappropriate and have little hope of success in software development.
* You have to be willing to try several approaches, knowing that some will fail and some will succeed, but not knowing which ones will work until after you try them all.
* If you decide on the solution method before you fully understand the problem, you act prematurely.
* You have to treat the techniques as tools in a toolbox and use your own judgment to select the best tool for the job.
* A dogmatic stance conflicts with the eclectic toolbox approach to software construction.

#### Experimentation

* You need to experiment throughout the development process.
* Open minded experimentation and religious adherence to a predefined approach don't mix.
