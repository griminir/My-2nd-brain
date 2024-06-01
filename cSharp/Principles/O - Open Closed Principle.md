#OOP #cSHARP #JavaScript #principles #Interface 

- a class should be open for extension but closed for modification
- extend the behavior of a system without having to modify the system
- a small change in the functionality is carried out by modifying the class itself. although this might work in simple applications, there is always a risk
- when you change a class, it's possible that the change may adversely affect some other part of the system. this requires retesting of the class
- wouldn't it be nice if we could add functionality without touching the class that has already been tested and is working as expected, that's what OCP ([[O - Open Closed Principle]]) is for.
- a module will be said to be open if it is available for extension, for example, it should be possible to add new elements to the set of functions it performs
- a module will be said to be closed if it is available for use by other modules
- in programming language, a closed module is one that may be compiled and stored in a library or publishing its interface for the benefit of others
![[OCP taxcalculator example.png]]
**1st Solution:** a switch statement then checks the country of the user. depending on the country, tax is calculated. there is a catch. it considers only some countries.
![[1st solution to OCP tax calculator example.png]]
If you want to expand your business through out the world this solution will not work
![[How to set up OCP taxCalculator exmaple.png]]
here we can see that we make an interface that all the different classes uses then we can pass the object we get from the classes to the TaxCalculator class

**2nd Solution:** in interface; create the child class obj and assign to parent (each of the countries are the child classes, and the interface being the parent)
![[Interface for OCP tax calculator.png]]
the parent ^
![[Implementation of OCP children classes tac calculator.png]]
how the implementation looks like in each of the children classes ^
![[OCP tax calculator class.png]]
![[OCP tax calculator used.png]]
**NOTE:** if we want to extend the behavior of the calculator function to calculate a new country tax, all we need to do is add a new derivative of the ICountryTaxCalculator. the calculate function does not need to change. thus, calculate conforms to OCP ([[O - Open Closed Principle]]). its behavior can be extended without modifying it
- the use of [[abstract class]] as a base class for most common abstract feature and use the separate classes for different implementation of abstract method
- You can accomplish this by abstracting the class design using either inheritance or interfaces
**Advantages:**
- Follows SRP ([[S - Single Responsibility Principle]])
- flexibility to add new features
- reusability 
- maintainability 
- easier to test
- plugin architecture: when your fundamental business rules are the core of a plugin architecture, then you are never bound to a particular feature set, interface database, framework or anything else
**NOTE:** Conforming to OCP is expensive. it takes development time and effort to create the appropriate abstractions. those abstractions also increase the complexity of the software design