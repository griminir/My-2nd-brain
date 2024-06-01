#DesignPatterns #FactoryMethod #cSHARP #CreationalDesignPattern #abstract 

![[Factory design patterns learning.png]]

**Definition:** Define and interface for creating an object, but let subclasses decide which class to instantiate. The factory method lets a class defer instantiation to subclasses.

**Real world example:** In an application, you may have different database users. One user may use Oracle and the other may use SQL Server. Whenever you need to insert data into your database, you need to create either a SqlConnection or an OracleConnection and only then can you proceed. If you put the code into if-else (or switch) statements, you need to repeat a lot of code which isn't easily maintainable.

You need to support a **new type of connection**, with some modifications. This type of problem can be resolved using the factory method. Provide and abstract creator class to define the basic structure. as per the definition, the instantiation process will be carried out through the subclasses that derive from this [[abstract class]].

The factory method pattern allows a client to get and object without specifying the class name. It is the job of the factory method to create and object of the intended class and return it to the client.

![[Factory method overview.png]] 
Factory method overview

![[Abstract class example.png]]
This is the [[abstract class]] that will be the blueprint for the factories we are making

![[How to use an abstract class as a blueprint for another class.png]]
![[how to use an abstract class as a blueprint example 2.png]]
here you can see the class inherits the abstract blueprint class and uses [[Override Keyword]] to make a factory to create a new dog/tiger class

![[Interface example.png]]
Interface for the actions the animal classes can do

![[Inheritance from interface 1.png]]
![[Inheritance from interface 2.png]]
Here you can see the specific of the dog/tiger class that is made by the dog factory
(you can replace all the code you dont know with Console.Writeline("");)

![[Factory method chain client side.png]]
(only the lines with the x are important)
**1st Line:** We are creating and instance of the dog factory that will make dog classes
**2nd Line:** We are using the dog factory to print a new instance of a dog
**3d and 4th Line:** We are using the new dog to use its methods
![[Output factory method.png]]

So what are the advantages of using a factory/factory method like this?
- You are separating the code that varies from the code that does not vary (in other words, the advantages of using the simple factory pattern are still present). This helps you to maintain the code easily. The code is not tightly coupled, so you can add new classes such as Lion, Bear, and so on at any time in the system without modifying the existing architecture. in other words, I have followed the "The "O" in [[SOLID Principles]] - Closed for modification but open for extensions".