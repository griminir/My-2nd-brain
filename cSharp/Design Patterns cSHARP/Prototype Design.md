#DesignPatterns #PrototypeDesignPattern #cSHARP #CreationalDesignPattern #Inheritance 

**Creational design pattern:** deals with the object creation mechanisms. it focuses on how the objects are created and utilized in an application to solve the problem by somehow controlling the object creation.

**Definition:** Prototype design pattern specify the kinds of objects to create using a prototypical instance, and create new objects by copying this prototype

**Concept:** this pattern provides an alternative method for instantiating new objects by copying or cloning and instance of an existing object. you can avoid the expense of creating a new instance using this concept

let's assume that you already have an application that is stable. in the future, you may want to modify the application with some small changes and then analyze further

![[Pasted image 20240517224603.png]]
**Example:** here `BasicCar` is the prototype, `Nano` and `Ford` are the concrete prototypes, and they have implemented the `Clone()` method defined in `BasicCar`. `BasicCar` object have some default price. later modified that price as per the model.

![[Pasted image 20240517224910.png]]
![[Pasted image 20240517225005.png]]
![[Pasted image 20240517225341.png]]
this is the [[abstract class]] that all the other prototypes clone from
![[Pasted image 20240517225538.png]]
here Nano class has inherited the [[Abstract class]] and use the [[Override Keyword]] on the clone making it its own.
![[Pasted image 20240517225809.png]]
same as above but with Ford Class

![[Pasted image 20240517230133.png]]
- here we are making 2 new Prototypes with the [[abstract class]] 1 Nano and one Ford. With the constructor we are setting the name and with the price inherited from base class we are also adding a default price. 
- then we are making an basic car object called bc1
- bc1 then uses the `Nano_base` prototype to clone all its values.
- bc1 then sets its price to the prototypes price + uses the static method in the [[Abstract class]] to add a random number to the price
- then we print out the model of bc1 and the price of bc1
- then we change it to ford and do it again
![[Pasted image 20240517231459.png]]
output

**Shallow copy vs Deep copy explained:**
- I have already used `MemberwiseClone()` method of the object base class in the implementation. it preforms a shallow copy. A shallow copy creates a new object and then copies the non-static fields from the original object to the new object. If there exists a value type field in the original object, a bit by bit copy is preformed. But if the fields is a reference type field, this method will copy the reference, not the actual object copied. so, the original object and the cloned object both refers to the same object. If you need a deep copy in your application, that can be expensive. 

**why do we need to clone objects?:**
- You may want to pass an object to some other module for processing, and you want to ensure that the original instance is not accidently tampered with in the process 
- you just want to get a feel of how the object will be after the changes, but you dont want to actually change the object
- the new object and an existing one might closely match each other. so, you can clone the first one, modify just a few properties that are different, and then use the new instance the way you want 
- at times creating a new instance using the new keyword might add overhead to the object creation process
![[Pasted image 20240517232529.png]]
![[Pasted image 20240517232546.png]]
![[Pasted image 20240517232613.png]]

**Advantages:** 
- you may include or discard products at runtime.
- you can create new instances with a cheaper cost.
- you can focus on the key activities rather then focusing on complicated instance creation process 
- Clients can ignore the complex creation process for objects and instead clone or copy objects 

**Drawbacks:**
- each subclass must implement the cloning or copying mechanism.
- implementing the cloning mechanism can be challenging if the objects under consideration do not support copying or if there are circular references