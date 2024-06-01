#OOP #abrstraction #DesignPatterns #cSHARP #JavaScript #Interface #principles 

- A high level module should not depend on a low level modules. both should depend on abstraction
- Abstraction should not depend on details, details should depend upon abstraction
- Inversion means both layers should depend on abstractions (interfaces) that expose the behavior needed by higher level layers
![[dependency in DIP example.png]]dottet line means UserManager is dependent on EmailNotifier class
![[example of code that is dependent DIP.png]]
**PROBELMS:** 
- EmailNotifier must be available at the time of writing and testing UserManager
- You are forced to finish writing low-level classes (like EmailNotifier) before you code high-level classes (like UserManager)
- future alterations to the notification system may require modifying the UserManager class
- For Example, instead of Email notifications, you may decide to provide SMS notifications, in which case you must change the code of UserManager to replace EmailNotifier with the new notification class
**First:**
- to solve the problem DIP(dependency inversion principle) suggests we should depend on abstraction. this abstraction can be in the form of a base class or an interface. 
![[Implenetation of an interface according to DIP.png]]
- here we can see that UserManager is dependent on the interface and not the low level classes.
- now email sms and popup notifer belongs to the INotifer interface so when Usermanager needs a notificer class, email, sms and popup are valid options.
- The constructor of UserManager recives an instance of a class and implements INotifer from the external world. 
- If you decide to switch from EmailNotifer to SMSNotifer or PopupNotifer, this decision wont have any impact on the UserManager class, as you are supplying the dependency from outside. thus, the direction of dependencies is reversed after applying DIP.

**Second:** 
- You should design the INotifer interface (abstraction) by looking at the need of the UserManager class. The INotifer interface should not be designed while looking at the need of EmailNotifier class (details).
- UserManager class is totally unaware of the exact INotifier implementation that will send the notification. thus, a high level class UserManager no longer depends on Low level classes such as EmailNotifier, SMSNotifier, abd PopupNotifer.
impementation of the INotifier interface below:
![[Implementation of INotifier DIP.png]]
this is a dummy implementation
applying the INotifer to the UserManager below:
![[Applying the INotifier to the UserManager.png]]
we create a public property that is an INotifier.
we then set it when we make the constructor for the UserManager class

(a bit unsure what is happening here)![[Pasted image 20240515235545.png]]
(space for if i find out what this code does)

- Dependency inversion can be applied wherever one class sends a message to another
- this principle encourages writing loosely coupled code to enhance readability and maintenance, especially in a large complex code base
- You must have observed that abstraction and polymorphism plays a very important role in [[SOLID Principles]] designs, as well as in [[Design Patterns for cSHARP]] and in general
- all well structured object oriented architectures have clearly defined layers, with each layer providing some coherent set of services through a well defined and controlled interface