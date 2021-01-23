# Level 4 Use Case Guidelines

## 1. Abstract

This document will serve to provide Level 4 students with knowledge and guidance of a key phase in modelling analysis. Use Case diagrams. At this level, you are not expected to create anything too advanced, but you will need to know the basics of how to create a simple use case diagram.

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. What Is A Use Case Diagram](#3-what-is-a-use-case-diagram)
  - [3.1. What Does A Use Case Diagram Look Like](#31-what-does-a-use-case-diagram-look-like)
  - [3.2. Components Of A Use Case Diagram](#32-components-of-a-use-case-diagram)
  - [3.3. Relationships](#33-relationships)
- [4. Tools](#4-tools)
- [5. Template](#5-template)
- [6. References](#6-references)
  
## 3. What is A Use Case Diagram

A Use Case diagram is often the primary form of system/software requirements analysis, A **Use Case** specifies what the expected behaviour of the system will be, it does not go into detail of the exact method that will make it happen. Use Cases, can be textual, or visual, the latter in the form of a Use Case diagram.

A key concept of Use Case modeling is that it helps developers design a system from the end user's perspective. It is an effective technique for communicating system behavior in the user's terms by specifying all externally visible system behavior.

A Use Case Diagram is often simple, as it does not show the detail of the Use Cases. It does however:

* Summarize some of the relationships between use cases, actors, and systems.
* Not show the order in which steps are performed to achieve the goals of each Use Case.
* Specify the context of a system
* Captures the requirements of a system
* Validates a systems architecture
* Drives implementation and generate test cases

## 3.1. What Does A Use Case Diagram Look Like

A simple Use Case Diagram can be seen here:

![A simple Use Case Diagram](/modelling-analysis/images/model_use_case.PNG)

*Fig. 1: A simple Use Case Diagram.*

This diagram shows the four main components of a Use Case diagram:

* Actor
* Use Case
* Communication Link
* System Boundary

## 3.2. Components Of A Use Case Diagram

We will now go into detail about the different components of a Use Case diagram.

### Actor

* Someone that interacts with use case (system function).
* Named by noun.
* Actor plays a role in the business
* Similar to the concept of user, but a user can play different roles
* For example:
  * A prof. can be instructor and also researcher
  * plays 2 roles with two systems
* Actor triggers use case(s).
* Actor has a responsibility toward the system (inputs), and Actor has expectations from the system (outputs).

### Use Case

* System function (process - automated or manual)
* Named by verb + Noun (or Noun Phrase).
* Does something
* Each Actor must be linked to a use case, while some use cases may not be linked to actors.

### Communication Link

* The participation of an actor in a use case is shown by connecting an actor to a use case by a solid link.
* Actors may be connected to use cases by associations, indicating that the actor and the use case communicate with one another using messages.

## System Boundary

* The system boundary is potentially the entire system as defined in the requirements document.
* For large and complex systems, each module may be the system boundary.
* For example, for an ERP system for an organization, each of the modules such as personnel, payroll, accounting, etc can form a system boundary for use cases specific to each of these business functions.

These are based from reference [1].

## 3.3. Relationships

There can be 5 relationship types in a Use Case diagram.

* Association between actor and Use Case
* Generalization of an actor
* Generalization of a Use Case
* Extend between two Use Cases
* Include between two Use Cases

At this level, we only expect you to understand and apply Association and Generalization of an actor. So we will go into detail about these.

### Association

This one is straightforward and present in every use case diagram:

* An actor must be associated with at least one use case.
* An actor can be associated with multiple use cases.
* Multiple actors can be associated with a single use case.

An example of Association is shown here in this simple example:

![A simple Use Case Diagram with association](/modelling-analysis/images/association.PNG)

*Fig. 1: A simple Use Case Diagram with association.*

### Generalization Of An Actor

Generalization of an actor means that one actor can inherit the role of the other actor. 
The descendant inherits all the use cases of the ancestor. The descendant has one or more use cases that are specific to that role.
Expanding on the previous diagram, the following now includes generalization:

![A Use Case Diagram with generalization of an actor](/modelling-analysis/images/actor_generalization.PNG)

*Fig. 1: A Use Case Diagram with generalization of an actor.*

These are based from reference [2].

## 4. Tools

There are a variety of software tools that you can use to create Use Case diagrams, some of which we recommend are:

### STARUML
* Download/link: https://staruml.io/
* How to use: https://docs.staruml.io/working-with-uml-diagrams/use-case-diagram

### Draw.io
* Download/link: https://app.diagrams.net/
* How to use: https://drawio-app.com/uml-use-case-diagrams-with-draw-io/

### Visio
* Free on university machines
* How to use: https://support.microsoft.com/en-us/office/create-a-uml-use-case-diagram-92cc948d-fc74-466c-9457-e82d62ee1298#:~:text=You%20can%20create%20a%20UML,such%20as%20a%20software%20application.&text=An%20association%20illustrates%20the%20participation,system%20to%20complete%20a%20process.

### Visual Paradigm
* Download/link: https://www.visual-paradigm.com/
* How to use: https://www.visual-paradigm.com/support/documents/vpuserguide/94/2575/6362_drawinguseca.html

## 5. Template

I will now show you a simple template that you can start with, this is the start of a very simple Use Case diagram, you should add in as many Use Cases and actors as you can think of when are identifying your User Stories:

![A simple Use Case Diagram template](/modelling-analysis/images/use_case_template.PNG)

*Fig. 1: A simple Use Case Diagram template.*

At this stage, you should have already created a set of User Stories. Use these stories to identify the Use Cases and Actors in your Use Case diagrams. After this point, you can then use the Use Case diagram to help you create sequence diagrams (more on this in modelling-design).

## 6. References

[1] Visual Paradigm. What is Use Case Diagram?. <https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-use-case-diagram/>.

[2] Creately. Use Case Diagram Relationships Explained with Examples. <https://creately.com/blog/diagrams/use-case-diagram-relationships/>.
