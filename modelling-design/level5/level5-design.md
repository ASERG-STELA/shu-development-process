# Design - Level 5  

## 1. Introduction
The design step is focused on the modelling of the solution. It usually involves decisions around architecture, data structure, user-interface, classes, algorithms, etc. At Level 5, it is expected that you create diagrams for the architectural structure if those are required by your module, as well as detailed software model diagrams that link together well and are in sync. Previous description of what these diagrams are can be found [here](../level4/level4-design.md). The three diagrams you need to create are.

* UML Class Diagram
* Entity Relationship Diagram
* Sequence Diagram

This document is a follow-up to the previous document and will provide examples of some more high level concepts you will need to consider when creating these diagrams. There will be templates provided for you if you wish to use them.

## 2. Table of Contents
- [3. Software Model Diagrams](#3-software-model-diagrams)
  - [3.1. UML Class Diagram](#31-uml-class-diagram)
    - [3.1.1. The Technical Details](#311-the-technical-details)
    - [3.1.2. GUI Class Diagram Example GUI](#312-gui-class-diagram-example)
  - [3.2. Entity Relationship Diagram](#32-entity-relationship-diagram)
    - [3.2.1. Entity Notations and Attributes](#321-entity-notations-and-attributes)
  - [3.3 Sequence Diagram](#33-sequence-diagram)
    - [3.3.1. Sequence Diagram Notation](#331-sequence-diagram-notation)
    - [3.3.2. Message and Focus of Control](#332-message-and-focus-of-control)
    - [3.3.3. Sequence Fragments](#333-sequence-fragments)
  - [3.4. Linking You Diagrams](#34-linking-your-diagrams)
- [4. Architecture Design](#4-architecture-design)
- [5. References](#5-references)  

## 3. Software Model Diagrams 
### 3.1. UML Class Diagram
When designing a system, before you start to implement a bunch of classes, you need to have a conceptual understanding of the system that you will be creating. They're a static representation of your system structure. As the basis of this was covered in the Level 4 documentation, this time we will mainly focus on the technical details, such as higher level relationships, rather than of the structure. If you need a refresher or aren't sure on the basics at this time, revisit the Level 4 document on Design.

#### 3.1.1. The Technical Details
We represent classes in a Class Diagram as a box with three compartments. The uppermost is the **class name**, the middle section contains the **class attributes**, and the bottom section contains the **class methods**.

The convention is.
* attribute name: type
* method name: (parameter:type)  

Remember it is possible to set defaults if you want to.

#### Class Visibility  
Class members (attributes and methods) have a specific visibility assigned to them. See figure 3 below for more details on these.

|         Class Visibility      | Icon |                             Who Can See It?                                | 
|-------------------------------|------|----------------------------------------------------------------------------|
|            `public`           |   +  | anywhere in the program and may bbe called by any object within the system |
|           `private`           |   -  | the class that defines it                                                 |
|          `protected`          |   #  | (a) the class that defines it or (b) a subclass of that class              |
|          `package`            |   ~  | instances of other classes within the same package                         |  

*Figure 1: Table representing the Visibility of Class members*  

![](https://miro.medium.com/max/547/1*TPgpSIX9iP8L9yYHH6CRfA.png)  
*Figure 2: A Class represented in UML*

#### Relationships
There are many different relationships that you can define within your class diagrams. These are;

* Association
* Inheritance
* Dependency
* Aggregation
* Composition
* Realization  
  
![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/07-relationships-between-classes.png)

#### Association
This is a broad term that simply emcompasses just about any logical connection or relationship between classes. We represent Association as a simple straight line between two different classes. It is typical to name our associations using a verb or verb phrase which reflects the real world problem domain. Alongsaide typical Association, There are a couple of other types of Association that can be used, which are;

* Directed Association
  * A directional relationship represented by a line with an arrowhead, where the arrowhead depcicts a container-contained directional flow  
* Reflexive Association
  * This occurs when a class may have multiple functions or responsibilities  

#### Inheritance
This refers to a type of relationship wherein one associated class is a child of another by virtue of assuming the same functionalities of the parent class. The child is a specific type of the parent class and inherits properties from that parent it is inheriting from. A solid line is used to represent Inheritance with an unfilled arrowhead.  

#### Dependency
An object of one class might use an object from another class in the code the method. If the object is not stored in any field, then this is considered, and modeled as a dependency relationship. This is a special type of association, similar to reflexive association, that exists between two classes if making changes to one of the classes will cause changes to another. The first class simply depends on the other class. 

#### Aggregation
This refers to the formation of a particular class as a result of one class being aggregated or built as a collection. In aggregation, the contianed classes are not strongly dependent on the lifecycle of the container. To show aggregation a diagram, draw a line from the parent class to the child class with a diamond shape near the parent class.

#### Composition
This is quite similar to aggregation, with the only difference being its key purpose of emphasizing the dependence of the contained class to the lifecycle of the container class. The contained class will be obliterated when the container class is destroyed. To show compsotion on a diagram, use a directional line connecting the two classes, with a filled diamond shape adjacent to the container class and the directional arrow to the contained class.

#### Realization
This denotes the implementation of the functionality defined in one class by another class. To show the relationship in UML, a broken line with an unfilled solid arrow is drawn from the class that defines the functionality of the class that implements the function. 

#### Cardinality  
Cardinality was touched upon in the [Level 4](../level4/level4-design.md/#32-entity-relationship-diagram) document in the Entity Relationship section. It is what refers to the expression in terms of one to one, one to many and many to many.  
  
![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/11-associations-with-different-multiplicies.png)  

#### 3.1.2. GUI Class Diagram Example
The following example gives a taste of what a class diagram looks like for a GUI system. This diagram highlights all of the key relationships needed and has labels to help you indicate where the correct relationship needs to be used.  
  
![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/18-uml-class-diagram-example-gui.png)  
*Figure 3: A Class Diagram representation of a GUI system*

### 3.2. Entity Relationship Diagram
Looking more at ERDs, this section will further discuss these types of diagrams, following up from the information provided at Level 4. If you are not sure on what the components of an Entity Relationship Diagram are, refer back to [here](../level4/level4-design.md/#321-components-and-features-of-ER-diagrams).

#### 3.2.1. Entity Notations and Attributes
There are primarily four cases where you would want to use an Entity Relationship Diagram during design, which are;
* Database design
* Database debugging
* Database creation and patching
* Aid in requirmement gathering

ER Diagrams are composed of **entities**, **relationships** and **attributes**. They also depict **cardinality**, which defines relationships in terms of numbers. As we went through these in level 4, this time we are going to focus on hese with more detailed examples to help you shape your own work. 

#### **Entity**  
Entities are defineable objects that can have some data stored about it. You should think about entities as nouns. The shape of an entity is typically shown as a **rectangle**. 

#### **Entity Attributes**
Also known as a column, an attribute is a property or characteristic of the entity that holds it. The attribute has a name that helps to describe the property and a type that describes the kind of attribute it is, such as **varchar** for a string, or **int** for an integer.

![](https://cdn-images.visual-paradigm.com/guide/data-modeling/what-is-erd/04-an-erd-entity-with-entities.png)  
*Figure _ Example Entity with properties*  

#### Primary Key
Sometimes known as PK, the primary key is a special kind of entity attribute that is used to **uniquely define** a record in a database table . For example, if we have a unique ID for each purchase in a database, but one of the transactions has the same ID as another transaction, and this transaction ID is our PK, then this is an error and shouldn't be possible, as our PK **must** always be unique. Lets look at an visual example of this.  
![](https://cdn-images.visual-paradigm.com/guide/data-modeling/what-is-erd/05-concept-of-erd-primary-key.png)  
*Figure _ Primary Key example*  

As we mentioned before, this type of ID cannot have a duplicate, so this would be an error that we would need to fix within the database.

#### Foreign Key
Sometimes known as FK, the foreign key is a **reference** to a primary key in **another table**. It is used as a way to identify the relationships between entities. Note that foreign keys don't need to be unique, unlike primary keys. Multiple records can share the same values. The example below shows an entity with some columns, showing where a reference might take place.  
![](https://cdn-images.visual-paradigm.com/guide/data-modeling/what-is-erd/06-concept-of-erd-foreign-key.png)  
*Figure _ Foreign Key example*  



### 3.3. Sequence Diagram _ NEEDS ADJUSTING FOR L5
This style of diagram describes the interactions among classes in terms of an exchange of messages over time. They are sometimes known as **event diagrams**. It is a good way to visualise and validate various runtime scenarios. These can help to predict how a system will behave and to discover responsibilities a class may need to have in the process of modeling a new system.

![](https://cdn-images.visual-paradigm.com/guide/uml/what-is-sequence-diagram/01-sequence-diagram-example.png)  
*Figure 7: An example Sequence Diagram of a Hotel Reservation System*  

#### 3.3.1. Sequence Diagram Notation __
Visual Representations of any notation mentioned here can be found at [[3]](#4-references).

* **Actor**: This is a type of role by an entity that interacts with the subject. It represents roles as human users, external hardware or other subjects. It is important to note that an actor doesn't necessarily represent a specific physical entity but merely a particular role of some entity
* **Lifeline**: A lifeline represents an individual participant in the interaction
* **Call Message**: Call message is a kind of message that represents an invocation of operation of target lifeline
* **Return Message**: Return message is a kind of message that represents the pass of information back to the caller of a corresponded former message
* **Self Message**: Self message is a kind of message that represents the invocation of message of the same lifeline
* **Recursive Message**: Recursive message is a kind of message that represents the invocation of message of the same lifeline. It's target points to an activation on top of the activation where the message was invoked from
* **Create Message**: Create message is a kind of message that represents the instantiation of (target) lifeline
* **Destroy Message**: Destroy message is a kind of message that represents the request of destroying the lifecycle of target lifeline
* **Duration Message**: Duration message shows the distance between two time instants for a message invocation

#### 3.3.2. Message and Focus of Control __
An event is any point in an interaction where something occurs. Focus of control, also called execution occurrence, is shown as a tall, thin rectangle on a lifeline. It represents the period during which an element is performing an operation. The top and the bottom of the rectangle are aligned with the initiation and the completion time respectively.

![](https://cdn-images.visual-paradigm.com/guide/uml/what-is-sequence-diagram/13-message-and-focus-of-control.png)  
*Figure 8: Visual example of message and focus of control*  

#### 3.3.3. Sequence Fragments __
UML 2.0 has helped to introduce sequence fragments, which make it easier to create and maintain accurate sequence diagrams. A sequence fragment is represented as a box, called a combined fragment, which encloses a portion of the interactions with a sequence diagram. TThe fragment operator indicates the type of fragment. More information on these types can be found at [[3]](#4-references).

![](https://cdn-images.visual-paradigm.com/guide/uml/what-is-sequence-diagram/14-fragment.png)  
*Figure 9: A sequence fragment*  

### 3.4. Linking your Diagrams __
When we use our class diagrams and sequence diagrams together, it allows for an extremely effective communication mechanism. We use a class diagram to illustrate relationships, and a sequence diagram to illustrate interactions between these classes. When an object is senidng information to another, this implies a relationship between the two classes. When thinking about how to link these together, if you've already created them beforehand, you can put them side-by-side and use this to help you understand what elements to take from each of them and then combine them into a single image. Examples to do this can be found at [5](#5-references).

## 4. Architecture Design

## 5. References
- [1] Creatly UML Class Diagrams Explained wih Examples <https://creately.com/blog/diagrams/class-diagram-relationships/> 
- [2] Visual Paradigm UML Class Diagram Tutorial <https://www.visual-paradigm.com/guide/uml-unified-modeling-language/uml-class-diagram-tutorial/>
- [3] Visual Paradigm What is Entity Relationship Diagram <https://www.visual-paradigm.com/guide/data-modeling/what-is-entity-relationship-diagram/#:~:text=Entity%20Relationship%20Diagram%2C%20also%20known,inter%2Drelationships%20among%20these%20entities.>
