
1. Yared Gebreslassie Haftu ID: UUR00479/16

2. Duoth Chiok Guek ID: UU92225R


Answer 1

Software engineering is a layered technology with Quality Focus at the base, followed by Process, Methods, and Tools. Each layer depends on the one below it, so the process model chosen must protect quality. The right model depends on project size, requirements stability, team experience, budget and timeline, and risk tolerance.


Project A: flight-control software



Recommended: Waterfall, or Spiral (Spiral is better when technical risk is high).

Requirements are clear, fixed and safety-critical, which suits Waterfall's sequential phases (Requirements, Design, Implementation, Testing, Deployment, Maintenance), clear milestones and deliverables.

Risk tolerance is almost zero. Spiral is risk-driven: each loop has Planning, Risk Analysis, Engineering and Evaluation, which makes it good for large, high-risk projects.

Agile and RAD are not suitable here because RAD is explicitly unsuitable for mission-critical systems and high technical risk.

Testing timing: Waterfall tests late, which is its weakness. The design must therefore be verified carefully before implementation, or Spiral's repeated evaluation can be used to reduce the risk.


Project B: food-delivery startup app



Recommended: Agile (Scrum or Kanban), or RAD.

Requirements change quickly as the market changes. Agile adapts to change through short sprints, continuous customer feedback and faster time to market.

Risk tolerance is high, and the app is small and customer-driven, so speed matters more than heavy upfront planning.

Testing happens continuously in every sprint instead of at the end, so problems are found early.

Scrum gives sprints and daily stand-ups. Kanban gives visual workflow and continuous delivery. RAD gives quick prototypes and heavy user involvement.


How the three factors influence the decision



Requirements stability: stable requirements favor Waterfall or Spiral; changing requirements favor Agile or RAD.

Risk tolerance: low tolerance favors Spiral or Waterfall; high tolerance favors Agile or RAD.

Timing of testing: late testing (Waterfall) is acceptable only when requirements are fixed and risk is managed. Continuous testing (Agile) suits changing requirements.


Answer 2

RAD focuses on speed. It uses prototyping over heavy planning, iterative development and time-boxed delivery. Skipping extensive upfront planning creates scalability and reliability problems later for these reasons:



Without deep upfront architecture and design, prototypes are quickly extended into the real system. The shortcuts made for speed become architectural debt that must be repaid later.

Time-boxed delivery pushes teams to ship what works now instead of designing for future load, more users and more data. The system can work for a demo but fail when it must scale, hence the risk of reduced scalability.

Little formal risk analysis means technical risks (performance, security, integration, failure handling) are discovered late, when they are expensive to fix. This is why RAD is not suitable for projects with high technical risks or mission-critical systems.

Mission-critical and large-scale systems demand high availability and reliability, which come from careful planning, deep design and extensive testing. RAD's quick iterations and component reuse do not give these guarantees.

RAD depends on high user availability and skilled developers. If users are unavailable, feedback is weak and the prototype drifts from real needs, and weak developers produce fragile code.

RAD is also costly for small projects and works best when a modular system can be built quickly from reusable components with CASE tools.


Answer 3


DRY (Don't Repeat Yourself): every piece of knowledge has one unambiguous representation. Avoid duplication and use abstraction. Benefits: easier maintenance, fewer bugs.

KISS (Keep It Simple, Stupid): avoid unnecessary complexity and write clear, understandable code.

YAGNI (You Aren't Gonna Need It): do not add functionality until it is needed. Avoid over-engineering and focus on current requirements.

Separation of Concerns: divide the program into distinct sections, each addressing one concern (MVC, layered architecture, module separation).


Yes, trying too hard to follow DRY or Separation of Concerns can violate KISS and YAGNI.


Example (DRY causing over-engineering): two functions look similar, so a developer merges them into one generic method with many flags and parameters (Process(type, mode, isAdmin, useCache...)). The code is no longer duplicated, but it is harder to read, test and change. This violates KISS, and the generality covers cases nobody needs, which violates YAGNI.


Example (Separation of Concerns causing over-engineering): for a simple calculator or a 100-line program, a developer creates controller, service, repository, interface and factory classes. The structure adds layers that are never needed. This is a trade-off: the extra layers cost more than they give.


Moderation is the answer. Apply abstraction when real duplication or real change appears, not for a feature or flexibility that might never be needed.


Answer 4

The cost of fixing an error grows the later it is found. An error caught during requirements or design needs a small change to a document. The same error found after deployment needs changes to design, code, tests, documentation and deployed systems, plus the cost of failures and unhappy users.


In Waterfall, testing happens late, so design and code flaws travel through several phases. Defects compound: a wrong requirement leads to wrong design, which leads to wrong code, and each stage builds on the earlier flaw. Fixing it means redoing all of them.


How these practices keep the cost low:



TDD (Test-Driven Development): tests are written first, then the code to pass them. This makes requirements clear, catches bugs the moment code is written, and gives a safety net for later changes.

Continuous Integration: code is merged often and built and tested automatically, so integration errors and broken code are found within minutes of being introduced, not at the end.

Regular peer code reviews: another person checks logic, design, naming, error handling, standards and test coverage, which finds design flaws and mistakes before testing or deployment.

Together with unit, integration, system and acceptance testing and automated testing, these practices move error detection to the earliest stages of the SDLC, where correction is cheapest.


Answer 5

How it works: C# or any .NET-compliant language is compiled into MSIL (Microsoft Intermediate Language), a CPU-independent set of instructions. When the program runs, the CLR's JIT (Just-In-Time) compiler converts the MSIL into native machine code for the current physical CPU, on demand. The CLR is not an interpreter. This is similar to Java bytecode and the JVM.


Why the .NET Framework is still platform-dependent: MSIL is independent of the CPU, but the code needs the runtime and class libraries to run. The traditional .NET Framework (the CLR and FCL) works only on Windows because it relies on Windows services such as Win32, GDI+, COM, DirectX, IIS and MSMQ. Platform means the combination of OS and CPU architecture, so the code is portable across CPUs but the runtime is tied to Windows.


How Mono changes that: Mono is a third-party implementation of the .NET runtime and libraries for other operating systems. With Mono, MSIL assemblies can be run on other systems and not only on Windows. This makes .NET applications platform-independent in practice.


Difference between CPU-independent code and OS-dependent runtime and libraries: MSIL is portable code that any compatible runtime can JIT-compile. The CLR, FCL and APIs are the OS-specific part. To run on another OS you need a runtime for that OS (cross-platform runtimes such as Mono) and APIs that do not depend on Windows-specific features.


Answer 6

Managed code



Runs under the CLR and is compiled to MSIL with metadata (a description of classes, interfaces, methods, parameters and so on), packaged as assemblies (.exe or .dll).

The CLR provides CLR services: garbage collection (automatic memory allocation and release), type safety, bounds checking of arrays, exception handling, security and thread management.

Protects the program from problems found in unmanaged code: no memory leaks from forgotten deallocation, no dangling pointers, no buffer overruns, no unsafe casts, and uninitialized variables are caught.

Is object-oriented, secure, reliable and portable between platforms.


Unmanaged (Win32) code



Compiled to machine-dependent code, with no metadata.

No protection of memory and no type safety, which causes reliability and safety problems.

Needs extra overhead (for example COM) and different versions for different platforms, so it is hard to port.


CTS (Common Type System): CTS defines the data types supported by the CLR and the operations on them. Value types and reference types exist, and all types derive from System.Object. Because every .NET language maps to the same types, a string in C# is the same as String in VB.NET (both map to System.String), and arrays and other types follow the same rules.


Result: one part of an application can be written in C# and another part in VB.NET without data conflicts. Both compile to MSIL, share the same type system and metadata, so their MSIL can be linked together. Cross-language inheritance and exception handling are possible.


Answer 7

The problem: before .NET, shared DLLs were registered system-wide with a single version. Installing one application could overwrite a shared DLL with a different version, and another application depending on the old version would break.


How .NET solves it



Assembly: the unit of deployment and version. It is a .exe or .dll containing MSIL, types and resources, and it defines type, version and security boundaries. Each assembly has a unique version number, and the CLR does not understand types outside assemblies.

Manifest and metadata: the manifest stores assembly metadata, including version information, secure identity and references to resources and classes. The metadata is generated by the compiler and describes all classes and members.

Strong name: a unique identity (name, version, culture and public key) that prevents two different assemblies from being confused, so different applications can use different versions of common assemblies without conflict.

GAC (Global Assembly Cache): a machine-wide cache for shared assemblies. An assembly must have a strong name and be shared publicly to be installed in the GAC. Private assemblies stay in the application directory.

Side-by-side execution: different versions of the same assembly can run at the same time in different applications, so a newer version never overwrites an older one. Applications can be installed simply by copy and paste, with no complex registration.


Namespace vs. Assembly



Namespace = logical grouping of classes (used in code to organize and avoid name collisions). A namespace can span multiple assemblies.

Assembly = physical grouping (.exe/.dll unit of deployment), holding the compiled logical units.


Why they are not interchangeable: one namespace such as System can be spread over several assemblies, and one assembly can contain several namespaces. A namespace says how code is organized logically, while the assembly decides how it is deployed, versioned and secured. The namespace name tells you nothing about which DLL file holds the class.


Answer 8

ADO.NET: classes used to communicate with databases such as SQL Server and Oracle: connect, retrieve, insert, update and delete data. The developer works with connections, commands and DataSets by hand.


Why raw ADO.NET was error-prone: the developer had to



open and manage a connection to the database manually,

create a DataSet to fetch or submit data,

convert data from the DataSet to .NET objects and back by hand.


This is a lot of repeated code. Mistakes in SQL strings, column names, type conversion and connection handling are only found at run time.


Entity Framework (EF): an open-source ORM (Object-Relational Mapping) framework. It maps tables to classes, rows to objects and columns to properties, so database tables are translated into .NET objects automatically and the connection, fetch, submit and conversion work is automated. Developers work at a higher level of abstraction with .NET objects and not with SQL, connections and DataSets.


Trade-off: developers gain productivity, less code, fewer errors and easier maintenance, but they give up some control over the exact SQL generated and the performance tuning that manual connections allow, and there can be some overhead.


LINQ (Language Integrated Query): a query language built into C# that gets data from different sources in a consistent way. The same query syntax works over SQL databases, XML and in-memory collections, instead of using different technologies for each (SQL strings, XML parsing, loops over collections). It is checked by the compiler and standardizes the way data is queried.


Answer 9

Console app: it runs sequentially. Execution starts at Main(), statements run in order from top to bottom, and the program ends when Main() finishes. The programmer controls the flow.


Windows Forms app: the flow is determined by events (event-driven programming), so the program waits for the user. Application.Run() in Main() starts the main loop (message loop) that keeps the form open and listens for events until the form is closed.


Trace from the moment a user clicks a Button



The user clicks the button (an external action: mouse click).

The operating system detects the click and puts a message in the application's message queue.

The main loop (started by Application.Run) takes the message from the queue and dispatches it to the right control.

The event listener detects the event trigger, and the Button raises its Click event. An event is a signal to the program that something has happened.

The event is a delegate (a type-safe reference to a method such as EventHandler). It invokes all the methods subscribed to the event, an event handler written as a method or as a lambda expression.

The handler is bound to the event by subscription, for example button1.Click += button1_Click; or button1.Click += (s, e) => { ... };. In Visual Studio the designer generates this binding.

The event handler code runs (for example, it reads a TextBox and changes a Label).

Control returns to the main loop, which continues to wait for the next event until the form is closed. Then Application.Run returns and Main() ends.


Connecting the concepts



Main loop: listens for events and triggers a callback when an event is detected.

Events: signals that something happened (user actions or OS, such as a timer).

Event listener: detects the event trigger and responds.

Delegate: the type-safe method reference that connects the event to its handler.

Lambda expression: a short inline way to write the handler.

Event handler: the method that is run in response to the event.


Answer 10

1. Quick unit-converter utility: SDI (Single Document Interface)



A single task and a single window, with all data encapsulated within one form, like Calculator or Notepad.

Simple to build and use. Each window is independent, with its own taskbar entry. It can have a toolbar and a status bar.

Controls: Label, TextBox, ComboBox (for choosing units) and Button, grouped in a Panel or GroupBox.


2. Multi-tabbed or multi-window financial spreadsheet editor: MDI (Multiple Document Interface)



Users must compare multiple reports inside one workspace, so one parent window acts as a container for several child windows, like Word and Excel.

The parent and children share the menu and toolbar. Child forms show only inside the parent boundaries.

A TabControl can be used to organize the multiple reports as tabs, and a DataGridView to show the spreadsheet data.


3. Company employee directory organized by department hierarchy: Explorer Interface



The data is hierarchical. A TreeView on the left shows departments, and a ListView on the right shows the details of the selected node (employees), like Windows Explorer.

A SplitContainer divides the screen into the two resizable panes.


What happens in an MDI application when the parent form is closed: when the parent form is unloaded, all the child forms are unloaded too. Children live inside the parent and cannot exist without it. This is the parent-child containment and lifecycle.


How Container Controls organize the UI



Panel: groups controls into a region that can be moved, shown or hidden together.

GroupBox: groups related controls (such as radio buttons) with a caption.

TabControl: shows several pages of controls in one area, switched using tabs. It is useful for multiple reports.

SplitContainer: creates two resizable panes, ideal for the TreeView plus ListView layout of the Explorer interface.

Container controls manage layout, and child controls inherit their position from the container, which keeps the interface organized and consistent.

