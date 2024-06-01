#keywords #Inheritance #OOP #Polymorphism 

- Access base class virtual members from derived classes: A derived class that has replaced or [[Override Keyword]]en a method or property can still access the method or property on the base class using the base keyword
- **NOTE:** it is recommended that virtual members use base to call the basse class implementation of that member in their own implementation. If the base class implementation is not called, it is up to the derived class to make their behavior compatible with the behavior of the base class
![[Base keyword example.png]]
base keyword example