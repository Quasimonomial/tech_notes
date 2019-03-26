# Part One: Context
## Chapter One: Philosophy

### Intro
* This book is primarily about Unix programmers, their tradition of approaching code as opposed to other (including object oriented) design philosophies
* These notes concern more the pragmatic concepts that may be useful for all programmers,  rather than the history aspects of the book.  These are all interesting, and there are case studies of real used code through the book that demonstrates these principles; I will be noting these only when I feel they are especially important
* This book was first published in 2003

### Things that Unix gets right
* Open-source software
* Cross-platform portability and open source
* Internet and the World Wide Web ran a lot on unix servers using TCP/IP
* Has lots of flexibility (at the cost of user friendliness)

### Basics of the Unix Philosophy
* From Doug McIlroy
	1. Make each program do one thing well.  To do a new job, build afresh rather than complicate old programs by adding new features
	2. Expect the output of every program to become the input to another, as yet unknown, program
	3. Design and build software, even operating systems, to be tried early, ideally within weeks.  Don’t hesitate to throw away the clumsy parts and rebuild them.
	4. Use tools in preference to unskilled help to lighten a programming task, even if you have to detour to build the tools and expect to throw some of them out after you’ve finished using them.
* Core philosophy: write programs to handle text streams, because that is the universal interface
* From Rob Pike:
	1. You can’t tell where a program is going to spend its time. Bottlenecks occur in surprising places, so prove where the bottleneck is before putting in a speed hack
	2. Measure, don’t tune for speed until you’ve measured, and then don’t do that unless one part of the code overwhelms the rest
	3. Fancy algorithms are slow when n is small, and n is usually small
	4. Fancy algorithms are buggier than simple ones, and they’re much harder to implement and debug.  Use simple algorithms as well as simple data structures
	5. Data dominates.  If you’ve chosen the right data structures and organized things well, then the algorithms will always be self-evident.  Data structures, not algorithms, are central to programming.
	6. There is no Rule 6
* Ken Thompson
	* When in doubt, use brute force
* **Primary Rules of Unix Programming**
	1. _Rule of Modularity:_ Write simple parts connected by clean interfaces
	2. _Rule of Clarity:_ Clarity is better than cleverness
	3. _Rule of Composition:_ Design programs to be connected to other programs
	4. _Rule of Separation:_ Separate policy form mechanism; separate interfaces from engines
	5. _Rule of Simplicity:_ Design for simplicity; add complexity only where you must
	6. _Rule of Parsimony:_ Write a big program only when it is clear by demonstration that nothing else will do
	7. _Rule of Transparency:_ Design for visibility to make inspection and debugging easier
	8. _Rule of Robustness_: Robustness is a child of transparency and simplicity
	9. _Rule of Representation:_ Fold knowledge into data so program logic can be stupid and robust
	10. _Rule of least Surprise:_ In interface design, always do the least surprising thing
	11. _Rule of Silence:_ When a program has nothing surprising to say, it should say nothing
	12. _Rule of repair:_ When you must fail, fail noisily and as soon as possible
	13. _Rule of Economy:_ Programmer time is expensive; conserve it in preference to machine time
	14. _Rule of Generation:_ Avoid hand-hacking; write programs to write programs when you can
	15. _Rule of Optimization:_ Prototype before polishing.  Get it working before you optimize it
	16. _Rule of Diversity:_ Distrust all claims for “one true way”
	17. _Rule of Extensibility:_  Design for the future, because it will be sooner than you think
* 	**Rule of Modularity**
	* *Write simple parts connected by clean interfaces
	* Control complexity as debugging dominates developer time
* **Rule of Clarity**
	* Codebase maintenance is both important and expensive
	* programs should care first about communicating themselves to humans
	* This goes above comments; you code should be clear and reasonable when possible
	* Buying small performance increases with large increases in complexity hurts in the long run
	* Complex code is harder to maintain and is more suspect able to bugs
* **Rule of Composition**
	* Design programs to be connected with other programs
	* Unix likes writing programs with textual input and output
	* This lets you daisy-chain programs together
	* This isn’t clean in GUIs but GUIs make it harder for programs to communicate with each other
* **Rule of Separation**
	* Separate the policy from mechanism; separate interfaces from engines
	* Implement mechanism, not policy
	* for example, make X a generic graphics engine and leave decisions about user-interface style to toolkits and other levels fo the system
	* Policy changes much faster than mechanism so they should be separate if possible
	* This means changing requirements will be much more frustrating to change as it requires additions across all layers
* **Rule of Simplicity**
	* Design for Simplicity; add complexity only where you must
	* Note that your ability to design can outstrip your ability to implement and debug
	* Bloat is bad because it results in huge, buggy programs
	* Small is beautiful
* **Rule of Parsimony**
	* Write a big program only when it is clear by demonstration that nothing else will do
	* large programs are less maintainable
* **Rule of Transparency**
	* Design for visibility to make inspection and debugging easier
	* Design for transparency and discoverability
		* _transparency_ is when you can look at a software system and immediately understand what it is doing and how
		* _discoverability_ is when software has facilities for monitoring and displaying its internal state
	* Debugging options should be designed in from the beginning
	* Programs should be able to demonstrate their correctness
* **Rule of Robustness**
	* Robustness is the child of transparency and simplicity
	* Software is robust when it preforms well under unexpected conditions which stress the designers assumptions
	* Most software is fragile and buggy because most programs are too complicated for a human brain to understand all at once
	* Try to avoid having special cases in your code
	* Systems are robust when they are transparent and simple
* **Rule of Representation**
	* Fold knowledge into data, so program logic can be stupid and robust
	* Logic is hard to think about
	* Complex data is easy
	* When you see a choice between complexity in data structures and complexity in code, choose the former
* **Rule of Least Surprise**
	* Principle of Least Astonishment
	* In interface design, always do the least surprising thing
	* Demanding learning from the user is bad
	* pay attention to your expected audience
	* pay attention to tradition
	* the worst thing is if your program is _almost_ the same as what the user is used to!
* **Rule of Silence**
	* When a program has nothing surprising to say, it should say nothing
* **Rule of Repair**
	* Repair what you can - but when you must fail, fail noisily and as soon as possible
	* Software should fail in a way that makes diagnosis of the problem as easy as possible
	* be liberal in what you accept, and conservative in what you send
* **Rule of Economy**
	* Programmer time is expensive; conserve it in preference to machine time
	* computing is cheap
* **Rule of Generation**
	* Avoid hand-hacking; write programs to write programs when you can
	* Consider compiles and interpreters
	* Use code generators to automate error-prone detail work
* **Rule of Optimization**
	* Prototype before polishing. Get it working before you optimize it
	* 90% of the functionality delivers snow is better than 100% of it delivered never
	* Premature optimization is the root of all evil - Donald Knuth
	* Premature local optimization hurts global optimization because it increases complexity
* **Rule of Diversity**
	* Distrust all claims for “one true way“
* **Rule of Extensibility**
	* Design for the future, because it will be here sooner than you think
	* When designing protocols or file formats, they should be self-describing as to be extensible
	* Always include a version format
	* Consider changes that might confuse format-reading code
* Applications
	* Everything that can be a source- and destination-independent filter should be one
	* Data streams should if at all possible be textual (so they can be viewed and filtered with standard tools)
	* Database layouts and application protocols should be textual and human readable/ human editable
	* Complexity front ends/ user interfaces should be cleanly separated from complex back ends
	* prototype in interpreted languages
	* Be generous in what you accept, rigorous in what you emit
	* When filtering, never throw away information you don’t need to
	* Small is beautiful. Write programs that do as little as is consistent with getting the job done


## Chapter 2: History
* While this chapter is very fascinating, it has very little in the way of actionable coding advice, so I won’t be covering it in detail
* things that are emphasized are the open source movement, Richard Stallman’s work, the origins of Unix at bell labs,  the rise of Unix based systems in the 90s


## Chapter 3: Contrasts

#### Operating systems
* Design and programming styles associated with different operating systems derives from:
	1. The intentions of the operating system designers
	2. Uniformities forced on designs by costs and limitations in the programming environment
	3. Random cultural draft; early practices become traditional simple because they were first
* Operating systems have unifying ideas
	* “everything is a file“ model
	* “we can pipe datastreams between programs”  

#### Unix operating system properties

* **Mulitasking Capability**
	* We can have a sequential program loader with no multitasking at all (obsolete)
	* _Cooperative multitasking_ - systems can support multiple processes, but a process has to voluntarily give up its hold on the processor before the next one can run
		* obsolete because small errors can lock up the whole machine
	* _Preemptive multitasking_ (Unix) - time slices are allocated by a scheduler, which itself interrupts the running process and hands control to the next process
		* Modern operating systems support this
* **Cooperating processes**
	* We want spawning new processes to be cheap in our operating system.  Otherwise:
		* Giant Monoliths start to make more sense
		* Processes can only communicate with clumsy or insecure ways (temporary files) or need to be tightly coupled
	* Microsoft/Windows at the time was like this - lots of windows programs know a lot about the internals of each other
	* Unix processes want to be able to interact with many programs, not specific programs designed to interact with each other
* **Internal Boundries**
	* Unix assumes the programmer knows best
		* Unix doesn’t stop or request information if you try to do something dangerous
		* `rm -rf *` LOL
	* At the time, Unix was the only system that encourages multiple accounts for a single user with different permissions, partially to sandbox what programs are allowed to access which resources
		* _Role Based Security_
* **File Attributes and Record Structures**
	* Unix files have neither record structure no attributes
* **Binary File formats**
	* All your files should be human readable text formats
	* that means a text editor can edit the files
	* Otherwise data is accessible only through dedicated tools
* **Preferred User Interface Style**
	* _CLIs_ - Command Line interfaces
		* Programs can interact with each other in emergent ways, because outputs are usable as inputs
		* Remote system administration is practical
		* Servers are simpler
	* _GUIs_ - Graphical User Interfaces
		* There is some overhead of GUI or need of scripting interface to do complex transformations of data
	* In case you can’t tell, Unix prefers CLIs (a lot of this book is a by coders for coders vibe)
* **Intended Use**
	* _Client_
		* lightweight
		* supporting a single user
		* able to run on small machines
		* designed to be switched on when needed and off when the user is done
		* lack pre-emptive multitasking
		* optimized for low latency
		* fancy user interfaces
	* _Server_
		* heavyweight
		* capable of running continuously
		* optimized for throughput
		* fully preemptively multitasking to handle multiple sessions
	* Originally all operating systems were server operating systems, until we had inexpensive hardware in the 1970s

#### Operating System overview
* At this point, the book goes into detail with an overview of operating systems; this is circa 2003, so this is less valuable to modern readers, and OSX, for example, has converged more towards the Unix tradition, being more Unix based itself
