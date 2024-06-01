#OOP #cSHARP #JavaScript #principles #DesignPatterns #Inheritance #virtual

- Subtypes must be substitutable for their base types
- extension of the OCP ([[O - Open Closed Principle]]) 
- Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program or without brining any errors in the system and prevent the creation of complex hierarchies for classes
- suppose there isa class/interface Class1, and two classes - Class2 and Class3 both inheriting from Class1
- the objects of Class2 and Class3 can be passed wherever Class1 is expected. just to put this in code, consider this: 
`Class1 obj = null; or Interface obj = null;`
`obj = new Class2(); or obj = new Class3();`
- in this example you can see we have an object that is Class1 we can instantiate a Class2 or Class3 for object since they are the children of Class1 
- Violations of LSP ([[L - Liskov Substitution Principle]]): often results in the use of runetime type checking
![[Basic non-LSP explained.png]]
here orange inherits from apple, and has the same public method called `GetColor` so you can assign the Orange class to the Apple object and the code will not break.
- in this non LSP ([[L - Liskov Substitution Principle]]) example, when you substitute base class instance with child class instance, you will not get the expected responds, **But** if we provide the [[Virtual Keyword]] we can use the override [[Override Keyword]] and it will give Orange
- think about the clean design abstraction and relationship between classes
**Note:** If the child class have properties and methods that dont make sense for them, even if they come from a parent, it is time to refactor or redesign the inheritance
- We will not get any error or exceptions because of the runetime decision, but the behavior that we expect will not happen
- so thing about the design of relationship and functionality that we are making
![[LSP clean solution example.png]]
- now when we run this program we will get the output as expected
- here we are following the LSP ([[L - Liskov Substitution Principle]]) as we are now able to change the object with its subtype without affecting the behavior
- `IFruit` is going to be the base class for both Apple and Orange classes
- now you can replace the `IFruit` variable with its subtypes either apple or orange and it will behave correctly and give correct outputs
- LSP ([[L - Liskov Substitution Principle]]) follows the characteristics of the best inheritance hierarchies
- avoids the traps that will cause us to create hierarchies that do not confirm to OCP ([[O - Open Closed Principle]])
- The importance of this principle becomes obvious when you consider the consequences of violation it
- when using this principle applications are more maintainable, reusable and robust
- LSP ([[L - Liskov Substitution Principle]]) is one of the prime enablers of OCP ([[O - Open Closed Principle]])
- the substitutability of a subtype allows a module, expressed in terms of a base type to be extensible without modification