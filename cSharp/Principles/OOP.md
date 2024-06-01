#cSHARP #abrstraction #Polymorphism #Inheritance #encapsulation #private #protected #public #internal #principles 
# OOP Concepts

## Abstraction

- Show only what is needed
- abstraction are usually implemented as [[Abstract class]]es or Interfaces. some of the most important abstractions in the .NET Framework include Stream, `IEnumerable<t>`, and objects
- If an abstraction has too many members, it becomes difficult or even impossible to implement. Too many abstractions in a frameworks also negatively affects usability of the framework
- Abstractions provide extremely powerful extensibility. They are at the core of many architectural patterns. They are also extremely important for testability of frameworks
- DO NOT provide abstractions unless they are tested by developing several concrete implementations
- DO choose carefully between an abstract class and an interface when designing an abstraction
- CONSIDER providing reference tests for concrete implementations of abstractions. such tests should allow users to test whether their implementations correctly implemented the contract

![[Abstraction through interface example.png]]
abstraction through interface example
![[Abstraction through abstract class example.png]]
abstraction through [[abstract class]] example

## Polymorphism 

- More than one form: An object can behave differently at different levels.
- Polymorphism works on the basis that subclasses have all the features of their base class. A subclass can have their own unique behavior and still share the same behavior from its parent class. A parent class cannot have the behavior of its subclass
- polymorphism simply means that at run time, the program is smart enough to use the method from the correct child class even when that object is declared to be of member type base on its runtime type. At run time, objects of a derived class may be treated as objects of a base class.
- you use polymorphism when you created virtual methods that derived classes could override to create specific behavior

![[Polymorphism.png]]
Also see [[Method Overloading]], [[Operator Overloading]], [[Override Keyword]], [[Method Hiding]].

**Scenario:** You have a drawing application that enables a user to create various kinds of shapes on a drawing surface. You dont know at compile time which specific types of shapes the user will create. however, the application has to keep track of all the various types of shapes that are created, and it has to update them in response to user mouse actions. You can use polymorphism to solve this problem. 
- create a base class called shape, and derived classes such as rectangle, circle and triangle. create a `list<shape>` object and add a circle, triangle and rectangle to it
- at run time, when client code calls the method, the CLR looks up the run-time type of the object and invokes that [[Override Keyword]] of the virtual method
![[polymorphism example.png]]
![[polymorphism example 2.png]]
polymorphism example
## Inheritance

- Parent and Child class relationship
- Inheritance enables you to create new classes that reuse (inherits data and behavior(methods) and properties), extend, and modify the behavior defined in parent/base class that is not defined as sealed, and [[Override Keyword]] base class virtual/abstract methods.
- the class whose members are inherited is called the base class(parent), and the class that inherits those members is called the derived class(child). Conceptually, a derived class is a specialization of the base class automatically contains all the public, protected and internal members of the base class except its constructors and finalizers and private members
- **C# and .NET support single inheritance only**. A derived class can have only 1 direct base class. however, inheritance is transitive, which allows you to define an inheritance hierarchy for a set of types
![[base class inheritance example.png]]
base class inheritance example
![[Derived class Inheritance example.png]]
Derived class Inheritance example
red line shows how you write inheritance
## Encapsulation

- hides the complexity
- A class can specify how accessible each of its members is to code outside of the class
- methods and variables that aren't intended to be used from outside of the class or assembly can be hidden
- Encapsulation is when a group of related methods, properties and other members are threated as a single object
- To promote encapsulations, a type(class) or type(class) member may limit its accessibility to other types and other assemblies by adding on of access modifiers bellow
![[Class types.png]] 
- There is no need for other classes to know about those fields. we have a method inside the class that uses the fields, hence it is appropriate to declare fields as private, this is know as encapsulation. we can safely change the value of fields inside classes without affecting other classes
- By declaring a field as private we can make it so other classes can not freely modify them. This helps to prevent the fields from being corrupted or to limit the malicious exploits
![[encapsulation example.png]]
Encapsulation example
