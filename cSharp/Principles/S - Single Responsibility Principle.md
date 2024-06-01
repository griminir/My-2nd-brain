#OOP #DesignPatterns #cSHARP #JavaScript #principles 

- Class is designed to carry responsibilities
- keep it simple, small is good, with single responsibility
- A class should only have 1 reason to change
![[Single responsibility principle search example.png]]
This class is doing all the search operations, (+) means public methods of the class.
new requirement, added in CustomerSearch class as ExportToCSV method.
we could add it to the class.

![[SRP wrong implementation example.png]]**
but now the class contains 2 responsibilities the search methods and a export metode
- a change in either of those responsibilities requires a change in the CustomerSearch class
- This design issue can be corrected if the CustomerSearch class is designed to adhere to single responsibility principle

![[SRP implemented correctly example.png]]
now the search class only deals with search and the export class deals with exporting
the search class remains unaffected by this changed and only export class requires retesting

another example is this one
![[before single responsibility principle.png]]
![[after single responsibility principle.png]]

- if you think about SRP you'll realize that this is just another way to define cohesion and coupling
- we want to increase the cohesion between things that change for the same reasons, and we want to decrease the coupling between those things that change for different reasons

example for the earlier public search methods
![[searching in database cSharp example.png]]

example for the earlier public export methods
![[exporting in data cSharp example.png]]