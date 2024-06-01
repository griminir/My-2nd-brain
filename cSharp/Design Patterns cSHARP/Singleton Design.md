#DesignPatterns #SingeltonDesignPattern #cSHARP #CreationalDesignPattern 

**Definition:** ensure a class has only one instance and provide a global point of access to it

**Concept:** A particular class should have only one instance. you can use this instance whenever you need it and therefor avoid creating unnecessary objects

**Example:** In some software systems, you may decide to maintain only one file system so that you can use it for the centralized management of resources

**Key Characteristics:** The constructor is private in this example. so you cannot instantiate like normal (using new)

before you attempt to create an instance of a class, you check whether you already have an available copy. if you do not have any such copy, you create it, otherwise, you simply reuse the existing copy

there are many approaches. each of them has pros and cons. one is called double checked locking(thread safe)

this approach can help you create the instances when they are really needed . but you must remember that, in general, the locking mechanism is expensive

![[Pasted image 20240517234509.png]]

![[Pasted image 20240517234731.png]]
Red X = important parts 
- first this class is sealed prevents any unintended modifications to the class
- when the class is made we make one new instance of the class singleton that is private static and `readonly`
- we are creating i private variable called number of instances so we know how many is exists
- the only public method returns the main (only) instance of the class

![[Pasted image 20240517235246.png]]
This is the thread safe class with double check locking
- this is the same pattern as the other above but this one has an extra check
![[Pasted image 20240517235800.png]]
![[Pasted image 20240517235855.png]]
output

**Notable characteristics:**
- the common language runtime (CLR) takes care of the variables initialization process
- you can create instance when any member of the class is referenced
- the sealed keyword prevents the further derivation of the class (so that its subclass cannot misuse it), and `readonly` ensures that the assignment process takes place during the static initialization
- the contractor is private. so you cannot instantiate the singleton class inside `main()` this will help you refer to the one instance that can exist in the system
- the public static member ensures a global point of access. it confirms that the instantiation process will not start until you invoke the instance property of the class (in other words, it supports lazy instantiation)

**Why volatile in thread safe singleton example?**
- lets see what C# specification tells you: "the volatile keyword indicates that a field might be modified by multiple threads that are executing at the same time. fields that are declared volatile are not subject to compiler optimizations that assume access by a single thread.". This ensures that the most up to date value is present in the field at all times. in simple terms the volatile keyword can help you to provide a serialized access mechanism. all threads will observe the changes by any other thread as per their execution order. you will also remember that the volatile keyword is applicable for class (or struct) fields, you cannot apply it to local variables.

**Why are multiple objects creations a big concern?**
- object creation in the real world are threated as costly operations. sometimes you may need to implement a centralized system for easy maintenance. this also helps you to provide a global access mechanism

**Why are you using the keyword sealed?**
- it is not needed since the constructor is private and its not mandatory, but it is always better to show your intentions clearly. i have used it to guard one special case. if you are tempted to use a derived nested class.