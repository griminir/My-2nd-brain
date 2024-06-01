#DesignPatterns #FactoryMethod #OOP #cSHARP #Inheritance #Interface #CreationalDesignPattern #abrstraction 

**Definition:** Provide an interface for creating families of related or dependent objects without specifying their concrete classes

**Concept:** An abstract factory is called factory of factories. in this pattern you provide a way to encapsulate a group of individual factories that have a common theme. you do not mention or specify their concrete classes

**Example:** ADO.NET has already implemented similar concepts to establish a connection to a database EG: `DbProviderFactories class` provides static (or shared in visual basic) methods for creating a `DbProviderFactory` instance

In the [[factory method design]], you have two factories; one that creates dogs and another is for creating tigers. but now suppose you want to categorize dogs and tigers further; You choose to get a pet animal (dog or tiger) or a wild animal (dog or tiger) through the factories. to fulfill that demand, you introduce two concrete factories: `WildAnimalFactory` and `PetAnimalFactory`, Wild factory creates wild animals and pet factory creates pet animals

this is a creational design pattern (because it defines the base templates for factories that create objects) which is a category of design patterns to grouping similar objects without needing to specify their concrete classes 

creational design patterns deal with how objects are created and creates instances of families of related classes. The instance then returns a correct strongly typed object based on provided information supplied at run time

![[Abstract factory design pattern.png]]
![[Pasted image 20240517041035.png]]
![[Pasted image 20240517041112.png]]
![[Pasted image 20240517041201.png]]
![[Pasted image 20240517041222.png]]
This is one chain down the factory tree. `IAnimalFactory` has two methods one returns an Object that inherits the `IDog` interface and one method returns an object that inherits the `ITiger` interface
![[Pasted image 20240517041657.png]]
![[Pasted image 20240517041720.png]]
![[Pasted image 20240517041736.png]]
This is the other chain down the factory tree. 
![[Pasted image 20240517042036.png]]
here is the main program file important parts marked with red X

![[Pasted image 20240517042538.png]]

In short with the [[Simple factory design]], you can separate the code that will vary from the rest of the code(basically, you decouple the client code). this approach helps you to manage the code more easily. another key advantage of this approach is that the client is unaware of how the objects are created. so it promotes both security and abstraction

However, this approach can violate the [[O - Open Closed Principle]]. you can overcome this drawback using the [[Factory method design]], which allows subclasses to decide how the instantiation process will be completed, put simply, you delegate the object creation to the subclasses that implement the factory method to create objects

the abstract factory is basically factory of factories. it creates the family of related objects, but it does not depend on the concrete classes

lastly a factory method promotes inheritance, and its subclasses need to implement the factory method to create objects. these factories promote loose coupling by reducing the dependencies of concrete classes and also allows the application to be more portable and extensible

allows new derived types to be added, without changing any core/shared properties/methods

**Challenges of using abstract factory:**
- any change in the abstract factory will force you to propagate the modification to the concrete factories. if you follow the design philosophy that says **"program ot and interface, not to and implementation"**, you need to prepare for this. this is one of the key principles that developers should always keep in mind. in most scenarios, developers do not want to change their abstract factories. in addition, the overall architecture may look complex. also debugging becomes tricky in some scenarios