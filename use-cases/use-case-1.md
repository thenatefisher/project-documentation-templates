
## Nominal Case
![](http://g.gravizo.com/g?
@startuml;
actor User;
participant "UI" as A;
participant "Controller" as B;
participant "Database" as C;
User -> A: Push Button;
activate A;
A -> B: Create Request;
activate B;
B -> C: Store Event;
activate C;
C --> B: ;
deactivate C;
B --> A: ;
deactivate B;
A --> User: Indicate Complete;
deactivate A;
@enduml;)


## Database Unavailable
![](http://g.gravizo.com/g?
@startuml;
actor User;
participant "UI" as A;
participant "Controller" as B;
participant "Database" as C;
User -> A: Push Button;
activate A;
A -> B: Create Request;
activate B;
B -> C: Store Event;
B -> B: Exception Caught;
B --> A: ;
deactivate B;
A --> User: Indicate Failure;
deactivate A;
@enduml;)