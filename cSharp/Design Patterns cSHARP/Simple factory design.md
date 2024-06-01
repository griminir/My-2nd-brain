#OOP #DesignPatterns #cSHARP #Inheritance #Interface #CreationalDesignPattern #abstract #FactoryMethod 

**Definition:** Create an object without exposing the instantiation logic to the client.

**Concept:** In [[OOP]], a factory is such an object that can create other objects.

![[Simple factory pattern overview.png]] 
Example of how the pattern looks

![[Simple factory design part 1.png]]

Capital I is used for Interfaces
Here Tiger and Dog inherits from IAnimal



![[Simple factory design part 2.png]]
class Simplefactory inherits from ISimpleFactory 
ISimpleFactory is an [[Abstract class]] 
The CreateAnimal method is [[Override Keyword]]n 
 
![[Client implementation of Simple factory design.png]] 
Client implementation

![[Console output simple factory design pattern.png]]
Console output



