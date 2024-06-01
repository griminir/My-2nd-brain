#OOP #Interface #DesignPatterns #cSHARP #JavaScript #principles 

- Clients of a class should not be forced to depend on those of its methods that they dont use
- like SRP ([[S - Single Responsibility Principle]]) for classes, the ISP ([[I - Interface Segregation Principle]]) states that an interface should be limited to containing only methods that are relevant ot a single responsibility
- by reducing the complexity of the interface, the code becomes easier to refactor and understand
![[example of ISP not implemented.png]]
this is a bad interface because the CashOnDeliveryOrderProcessor does not need methods like ValidateCardInfo since no card is used.
- many client specific interfaces are better then one general purpose one.
- an important benefit of adhering to this principle in a system is that it aids in decoupling a system by reducing the number of dependencies
- implement multiple interfaces where required
![[Example of ISP implemented well.png]]here you can see that we split off the extra part and make an extra interface for it that way we can share the IOrderProcessor and we just have to add the new IOnlineOrderProcecessor to the online interface OnlineOrderProcessor will still have the method that is needed for the new interface and the old one, but CashOnDeliveryOrderProcessor does not have to implement a method it will not use

example of refactoring with ISP
![[refactoring with ISP before.png]]
Before ^
![[refactoring with ISP after.png]]
After ^

- when object orientated applications are maintained the interfaces to existing classes and components often change
- sometimes these changes have a huge impact and force the recompilation and redeployment of a very large part of the system
- this impact can be mitigated by adding new interfaces to existing objects rather then changing the existing interface
- if clients of the old interface wishes to access methods of the new interface they can query the object for that interface
- a solution to having a better code always comes down to a word SMALL; small methods, small class, small interface
- so if you split your code into smaller chunks, it will be easier to change and maintain it

implementation of the methods from the first example ![[Example to ISP shopping.png]]
![[example to ISP shopping 2.png]]
