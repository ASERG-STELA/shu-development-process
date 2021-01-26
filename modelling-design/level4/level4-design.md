# Design - Level 4 <!-- omit in toc -->

## 1. Table of Contents
- [2. Introduction](#2-introduction)
- [3. Diagrams That You Will Need](#3-diagrams-that-you-will-need)
  - [3.1. UML Class Diagram](#31-uml-class-diagram)
    - [3.1.1. The Technical Details](#311-the-technical-details)
  - [3.2. Entity Relationship Diagram](#32-entity-relationship-diagram)
  - [3.3 Sequence Diagram](#33-sequence-diagram)
  - [3.4. Linking You Diagrams](#34-linking-your-diagrams)
- [4. References](#4-references)  

## 2. Introduction
The design step is focused on the modelling of the solution. It usually involves decisions around architecture, data structure, user-interface, classes, algorithms, etc. At Level 4 it is not expected that you will overly complex diagram, more you will just need to create feasible basic diagrams that link well where necessary. You will need to create at a minimum 3 diagrams which are.

* UML Class Diagram
* Entity Relationship Diagram
* Sequence Diagram

This document will go through what these documents are and provide examples as we go through that you can look at to give you an idea what your document should look like. There will also be some blank templates you can use to get started. At Level 4 you only need to worry about **Inheritance** in your class diagrams. More on this later.

## 3. Diagrams That You Will Need
### 3.1. UML Class Diagram
When designing a system, before you start to implement a bunch of classes, it is good to have a conceptual understanding of the system that you will be creating. The questions you need to think about are.

* What classes do I need?
* What functionality and information will these classes have?
* How will they interact with each other
* Who can see these classes? (`public`?, `protected`?, `private`?)  

This is where class diagrams come in. They are a neat way of vizualising the classes in your system *before* you actually start coding them up. They're a static representation of your system structure.  

![](https://miro.medium.com/max/847/1*TYRSuON0vVxy8olllrBVEw.png)  
*Figure 1: An example Class Diagram for a Banking System*  

The Diagram in figure 1 shows an example of a pretty simple Class Diagram, with the aim to give a general idea of how they look. You may be asking yourself, why do we need these diagrams anyway.

1. Planning and Modeling ahead of time makes programming much easier.  
2. Making changes to class diagrams is easy, whereas making changes in your code is not as easy.  
3. Having a design blueprint makes things go by smoother, this design plan helps you analyse and modify the system.  
4. Not a lot of technical / language specific knowledge is required.  

#### 3.1.1. The Technical Details
We represent classes in a Class Diagram as a box with three compartments. The uppermost is the **class name**, the middle section contains the **class attributes**, and the bottom section contains the **class methods**.


![](https://miro.medium.com/max/552/1*vY53qi20_IryBWOBDnCHpg.png)  
*Figure 2: An example of a Class, represented in UML*  

The convention is.
* attribute name: type
* method name: (parameter:type)  

If you want to set a default, you can do so, just like in figure 2, where **balance: Double = 0.0**, which indicates a default is present, otherwise this would be **balance: Double**. If your method parameters don't take in a value, then you can leave them empty, for e.g. **checkBalance()**.  

#### Class Visibility  
Class members (attributes and methods) have a specific visibility assigned to them. See figure 3 below for more details on these.

|         Class Visibility      | Icon |                             Who Can See It?                                | 
|-------------------------------|------|----------------------------------------------------------------------------|
|            `public`           |   +  | anywhere in the program and may bbe called by any object within the system |
|           `private`           |   -  | the class that definies it                                                 |
|          `protected`          |   #  | (a) the class that defines it or (b) a subclass of that class              |
|          `package`            |   ~  | instances of other classes within the same package                         |  

*Figure 3: Table representing the Visibility of Class members*  

![](https://miro.medium.com/max/547/1*TPgpSIX9iP8L9yYHH6CRfA.png)  
*Figure 4: A Class represented in UML, with added Visibility*

#### Relationships
There are different relationships that you can define witin your class diagrams, but this document will only be covering **Inheritance** at this level. You are encouraged to do some further reading if you want to learn about the other relationships available in the mean time.  

**Inheritance** indicates the child (subclass) that is considered to a specialized form of the parent (super class) For example.
![](https://miro.medium.com/max/847/1*szU8ngrWSXmBNPYReMyK5w.png)  
*Figure 5: Inheritance within a Class Diagram*  

In figure 5 we can see what Inheritance looks like. In this example we have an **Animal** parent class with all public member fields. The arrows represent the direction of Inheritance. Where the arrow connects the child class to the parent class is naturally labeled as **Inherits from**, indicated by the direction of this clear arrow. The child classes in this example not only inherit methods and attributes from the parent, but they also have some of their own unique methods too, such as **quack()** in Duck and **run()** in Zebra, whilst all child classes inherit the **swim()** method from the parent. 

### 3.2. Entity Relationship Diagram

### 3.3. Sequence Diagram

### 3.4. Linking your Diagrams

## 4. References
- [Medium.com: UML Class Diagrams Step by Step](https://medium.com/@smagid_allThings/uml-class-diagrams-tutorial-step-by-step-520fd83b300b)
