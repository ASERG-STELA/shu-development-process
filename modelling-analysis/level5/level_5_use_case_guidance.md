# Level 5 Use Case Guidance

## 1. Abstract

This document will go into some detail about some of the advanced concepts of Use Case Diagrams. At Level 5, you will need to produce more detailed/advanced Use Case Diagrams and Descriptions than you have previously created at Level 4. 
If you would like a refresher of the basics of Use Case modelling, head over to the Level 4 Use Case guidelines [here](/modelling-analysis/level4/level_4_use_case_guidance.md).

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. Use Case Diagrams](#3-use-case-diagrams)
  -[3.1. Relationships](#31-relationships)
  -[3.2. What You Should Be Doing](#32-what-you-should-be-doing)
- [4. References](#4-references)
  
## 3. Use Case Diagrams

At Level 4, you learned how to create simple Use Case Diagrams and Descriptions. At Level 5, you will need to build on this knowledge and create more advanced diagrams for your modelling analysis.
As with Level 4, at Level 5 you will also need to identify the Use Cases in your diagrams from a set of User Stories that you should have already created by this point. You can look at the guidance for Level 5 User Stories [here](/modelling-analysis/level5/level-5-user-stories.md).
As well as creating a set of User Stories, you should also be using the [MoSCoW prioritisation method](/modelling-analysis/level5/moscow_prioritisation_method.md) to prioritise them.

## 3.1. Relationships

I will now explain the three types of Use Case relationships that were not covered in the Level 4 guidelines. **Generalisation of a Use Case**, **Extend** and **Include** between two Use Cases.

### Extend

Extend and Include can be two confusing concepts at first. As the name implies, **Extend** extends the base use case and adds more functionality to the system. The diagram below shows an example of a system with an **Extend** relationship included:

![A Use Case Diagram with Extend relationship](/modelling-analysis/images/extend.png)

*Fig. 1: A Use Case Diagram with an Extend relationship. Retrieved from reference [1].*

Here are a few things to consider when using the **Extend** relationship:

* The extending Use Case is dependent on the extended (base) use case. In the below diagram the “Calculate Bonus” Use Case doesn’t make much sense without the “Deposit Funds” use case.
* The extending Use Case is usually optional and can be triggered conditionally. In the diagram, you can see that the extending Use Case is triggered only for deposits over 10,000 or when the age is over 55.
* The extended (base) Use Case must be meaningful on its own. This means it should be independent and must not rely on the behavior of the extending Use Case.

The tip of arrowhead points to the base use case and the child use case is connected at the base of the arrow.

### Include

Include relationship show that the behavior of the included use case is **part of** the including (base) use case. The main reason for this is to reuse common actions across multiple use cases. In some situations, this is done to simplify complex behaviors. The diagram below shows an improved version of the previous diagram:

![A Use Case Diagram with Extend relationship](/modelling-analysis/images/include.png)

*Fig. 2: A Use Case Diagram with Extend and Include relationships. Retrieved from reference [1].*

Here are a few things to consider when using the **include** relationship:

* The base Use Case is incomplete without the included use case.
* The included Use Case is mandatory and not optional.

The tip of arrowhead points to the child Use Case and the parent Use Case connected at the base of the arrow.

Another simple example of how to determine which to use would be:

Use Case: Drive to the city.

includes -> drive the car

excludes -> fill up with petrol

Fill up with petrol may not always be required, but may optionally be required based on the amount of petrol left in the car. "Drive the car" is a prerequisite.
More information on the differences between the two can be found in reference [2].

### Generalisation of a Use Case

This is similar to the generalization of an actor and is all about inheritance. The behavior of the ancestor is inherited by the descendant. This is used when there is common behavior between two use cases and also specialized behavior specific to each use case.

Here are a few things to remember:

* The child use case is an enhancement of the parent use case.
* Generalization is shown as a directed arrow with a triangle arrowhead. The same way generalisation of an actor is done.
* The child use case is connected at the base of the arrow. The tip of the arrow is connected to the parent use case.

These are based from reference [3].

In the previous banking example, there might be a use case called “Pay Bills”. This can be generalized to “Pay by Credit Card”, “Pay by Bank Balance” etc.

## 3.2. What You Should Be Doing

You should try to think about all 5 of the different relationships that have been covered and include as many of each instance as you can when creating your Use Case models at Level 5:

* Generalisation of an actor
* Generalisation of a Use Case
* Include
* Extend
* Association

This will allow you to create complete and advanced Use Case models to use in your projects. 

## 4. References

[1] Creately. Use Case Diagram Relationships Explained with Examples. <https://creately.com/blog/diagrams/use-case-diagram-relationships/>.

[2] Stack Overflow. What's is the difference between include and extend in use case diagram? <https://stackoverflow.com/questions/1696927/whats-is-the-difference-between-include-and-extend-in-use-case-diagram>.

[3] Visual Paradigm. What is Use Case Diagram? <https://www.visual-paradigm.com/guide/uml-unified-modeling-language/what-is-use-case-diagram/>.

