#principles #DesignPatterns #OOP #cSHARP #JavaScript

## [[S - Single Responsibility Principle]]

- a class should only have a single responsibility
- Single reason for change and encapsulated class
- Create different-2 interface
- Keep it simple
- Small is good

![[before single responsibility principle.png]]
before
![[after single responsibility principle.png]]
after 

## [[O - Open Closed Principle]]

- Classes or software entities should be open for extension, but closed for modification '
- Use abstract/interface class as a base class for most common abstract features and use the separated classes for different implementation of abstract methods and create the child class object and assign to parent.

![[before OCP principle.png]]
before
![[After OCP.png]]
after


## **[[L - Liskov Substitution Principle]]**

- objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program
- Base class instance replaced/substitutions by its sub type instance with no change in functionality
- extension of the open class principle

![[before liskov principle.png]]
before
![[After liskov principle.png]]
after


## **[[I - Interface Segregation Principle]]**

- many client specific interfaces are better then one general-purpose big interface
- implement only useful interfaces. do not implement big interfaces
- breakdown the big interfaces into useful smaller interfaces
- implement multiple interfaces where required

![[Before ISP.png]]
Before
![[after ISP.png]]
After


## **[[D - Dependency Inversion Principle]]**

- one should "depend upon abstractions, not concretions"
- details should depend on abstractions and abstractions should not depend on details
- high level module should not depend on low level module and both should depend on abstractions
- adapter design patterns implement the dependency inversion principle
- example. Implement the repository layer between business and data base layer
- Now, in programming, this is a bit like Dependency Inversion. Normally, in your code, you might have one part that depends on another part to work. But with Dependency Inversion, you flip it around. Instead of one part depending on another directly, both parts depend on something abstract in the middle. So, just like the toy car, instead of you telling one part what to do, it tells you what it needs. This makes your code more flexible and easier to change later on, just like how you can change what you do with the toy car by pressing different buttons.

![[Before DIP.png]]
before
![[after DIP.png]]
After
