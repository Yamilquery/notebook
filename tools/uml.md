# Unified Modeling Language (UML)

*From: [Wikipedia](https://en.wikipedia.org/wiki/Unified_Modeling_Language)*

> A general-purpose, developmental, modeling language in the field of software engineering, that is intended to provide a standard way to visualize the design of a system

## Diagrams

![UML Diagram Chart](https://upload.wikimedia.org/wikipedia/commons/e/ed/UML_diagrams_overview.svg)

### Sequence Diagram

*From: [Wikipedia](https://en.wikipedia.org/wiki/Sequence_diagram)*

> An interaction diagram that shows how processes operate with one another and in what order. It is a construct of a Message Sequence Chart. A sequence diagram shows object interactions arranged in time sequence. It depicts the objects and classes involved in the scenario and the sequence of messages exchanged between the objects needed to carry out the functionality of the scenario. Sequence diagrams are typically associated with use case realizations in the Logical View of the system under development. Sequence diagrams are sometimes called event diagrams or event scenarios.

> A sequence diagram shows, as parallel vertical lines (lifelines), different processes or objects that live simultaneously, and, as horizontal arrows, the messages exchanged between them, in the order in which they occur. This allows the specification of simple runtime scenarios in a graphical manner.

![Sequence Diagram](https://upload.wikimedia.org/wikipedia/commons/9/9b/CheckEmail.svg)

## [PlantUML](http://plantuml.com) using [Gravizo](http://g.gravizo.com)

*From: [github](https://github.com/TLmaK0/gravizo/blob/master/README.md)*

![Alt text](http://g.gravizo.com/g?
  digraph G {
    aize ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf}
    init -> make_string;
    edge [color=green];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
)

```sh
![Alt text](http://g.gravizo.com/g?
  digraph G {
    aize ="4,4";
    main [shape=box];
    main -> parse [weight=8];
    parse -> execute;
    main -> init [style=dotted];
    main -> cleanup;
    execute -> { make_string; printf};
    init -> make_string;
    edge [color=red];
    main -> printf [style=bold,label="100 times"];
    make_string [label="make a string"];
    node [shape=box,style=filled,color=".7 .3 1.0"];
    execute -> compare;
  }
)
```

---

![Alt text](http://g.gravizo.com/g?
@startuml;
actor User;
participant "First Class" as A;
participant "Second Class" as B;
participant "Last Class" as C;
User -> A: DoWork;
activate A;
A -> B: Create Request;
activate B;
B -> C: DoWork;
activate C;
C --> B: WorkDone;
destroy C;
B --> A: Request Created;
deactivate B;
A --> User: Done;
deactivate A;
@enduml
)

```sh
![Alt text](http://g.gravizo.com/g?
@startuml;
actor User;
participant "First Class" as A;
participant "Second Class" as B;
participant "Last Class" as C;
User -> A: DoWork;
activate A;
A -> B: Create Request;
activate B;
B -> C: DoWork;
activate C;
C --> B: WorkDone;
destroy C;
B --> A: Request Created;
deactivate B;
A --> User: Done;
deactivate A;
@enduml
)
```

---

## Tools

-   [Gliffy](https://www.gliffy.com)
-   [Plant Text](http://www.planttext.com/planttext)
-   [PlantUML](http://plantuml.com)
-   [StarUML](http://staruml.io)
-   [Web Sequence Diagrams](https://www.websequencediagrams.com)

## References

-   [IBM: UML basics: The class diagram](http://www.ibm.com/developerworks/rational/library/content/RationalEdge/sep04/bell)
-   [SourceMaking: UML](https://sourcemaking.com/uml)
-   [StackOverflow: What's the best UML diagramming tool?](http://stackoverflow.com/questions/15376/whats-the-best-uml-diagramming-tool)
-   [TraceModeler: A Quick Introduction to UML Sequence Diagrams](http://www.tracemodeler.com/articles/a_quick_introduction_to_uml_sequence_diagrams)
-   [Wikipedia: UML](https://en.wikipedia.org/wiki/Unified_Modeling_Language)
