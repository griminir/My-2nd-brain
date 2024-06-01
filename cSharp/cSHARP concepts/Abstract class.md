#cSHARP #oop #DesignPatterns #Inheritance #abstract 

An abstract class in C# provides a blueprint of what its derived classes must implement before they can use it. An abstract class contains abstract members including abstract methods, abstract properties, abstract indexers, and abstract events. All abstract members of a class must be implemented by its derived classes.

Here are the key characteristics of abstract classes,

- An abstract class cannot be instantiated.
- A class may inherit one abstract class only.
- An abstract class may contain abstract methods, properties, and events.
- An abstract class can’t be modified with the sealed class modifier.
- A derived from an abstract class must implement all inherited abstract methods and accessors

![[Abstract class example.png]]
abstract class example

![[How to use an abstract class as a blueprint for another class.png]]
Here the concrete class inherits from the blueprint (abstract class)
making the method its own with [[Override Keyword]]. 

more info [on abstract classes in C#](https://www.c-sharpcorner.com/UploadFile/0c1bb2/using-abstract-class-in-C-Sharp/#:~:text=An%20abstract%20class%20in%20C%23%20provides%20a%20blueprint%20of%20what,abstract%20indexers%2C%20and%20abstract%20events.) 
