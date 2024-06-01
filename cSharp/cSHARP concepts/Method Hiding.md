#Polymorphism #OOP #MethodHiding 

- Hide base class members with new members
- if you want your derived class to have a member with the same name as a member in a base class, you can use the new keyword to hide the base class member
- the new keyword put before the return type of a class member that is being replaced
- hidden base class members may be accessed from client code by casting the instance of the derived class to an instance of the base class
![[method hiding example.png]]
Method hiding example

also see [[Base keyword]] 