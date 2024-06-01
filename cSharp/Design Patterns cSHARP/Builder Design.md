#DesignPatterns #BuilderDesignPattern #cSHARP #CreationalDesignPattern

**Creational design patterns:** deal with object creation mechanisms. it focuses on how the objects are created and utilized in an application

**Definition:** Builder design pattern separates/isolate the construction of a complex object from its representation so that the same construction processes can create different representations

**Concept:** The builder pattern is useful for creating complex objects that have multiple parts. The creation process of an object should be independent of these parts. in other words, the construction process does not care how these parts are assembled.

The complex object being constructed is represented by aggregation of one or more parts 

![[Builder design pattern example.png]]
**Example:** here `product` is the complex object under consideration. `ConcreteBuilder` constructs and assembles the parts of a product object by implementing an abstract interface called `Builder`, `Director` is responsible for creating the final object using the Builder Interface

![[full builder design pattern example.png]]
as shown in the figure there is an abstraction of ta builder in the form of the `AbstractBuilder` class. This class defines the `BuildPart()` method that is suppose to create a part of the complex object under consideration. The Abstract Builder is inherited by three builders `Builder1`, `Builder2` and `Builder3`. each of these builder classes implements `BuildPart`. thus each concrete builder class is responsible for creating the part it is assigned to build

the build process of all the three builder classes finally arrives at a finished product. the product is the complex object constructed by the builder.

The process of constructing the product is ordered by a class often called `Director`. thus, the director class initiates the product construction process through its `Construct()` method

![[All the methods Builder design pattern example.png]]
![[Director class.png]]
director contains 1 method that takes the parameter of 1 builder class
![[Interface Builder example.png]]
this is the blue print for all the Builders classes that inherits this interface must have all these methods
![[Pasted image 20240517145902.png]]
![[Pasted image 20240517150127.png]]
first picture you can see during start operations we make a new product and in the second picture you can see the methods and properties of product
![[Pasted image 20240517150345.png]]
once all the operations are done we return a filled out/finished product
![[Pasted image 20240517150656.png]]
here we make the `Director` then we make a `CarBuilder` from the class `Car` then make a `MotorcycleBuilder` from the `Motorcycle` class. Then we pass one of the Builders that use the `IBuilder` interface to the `Construct()` method of the director. Once the `CarBuilder` is filled up with the information about the car we can use `CarBuilder.GetVehicle()` to return a finished product and show it off. the same line happens to the motorcycle.

![[Pasted image 20240517151436.png]]
**Advantages:** You direct the builder to build the object step by step, and you promote encapsulation by hiding the details of the complex construction process, the director can retrieve the final product from the builder when the whole construction is over using this pattern, the same construction process can produce different products.

**Drawbacks:** it is not suitable if you want to deal with mutable objects (which can be modified later). you may need to duplicate som portion of the code. these duplications may have significant impact in some contexts. to create more products, you need to create more concrete builders.

**Note:** You can use [[abstract class]] instead of interface in this example