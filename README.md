# Software Development Process <!-- omit in toc -->

- [1. Introduction](#1-introduction)
- [2. The Reference Process](#2-the-reference-process)
- [3. Level-based view](#3-level-based-view)
  - [3.1. Level 4](#31-level-4)
  - [3.2. Level 5](#32-level-5)
  - [3.3. Level 6](#33-level-6)
- [4. Process-based view](#4-process-based-view)
  - [4.1. Communication](#41-communication)
  - [4.2. Planning](#42-planning)
  - [4.3. Modelling - Analysis](#43-modelling---analysis)
  - [4.4. Modelling - Design](#44-modelling---design)
  - [4.5. Construction - Code](#45-construction---code)
  - [4.6. Construction - Test](#46-construction---test)
  - [4.7. Deployment - Delivery](#47-deployment---delivery)
  - [4.8. Deployment - Support and Feedback](#48-deployment---support-and-feedback)
- [5. Tools view](#5-tools-view)
- [6. Development Team](#6-development-team)

## 1. Introduction

We are creating a software development process that can be followed by students at all levels as they work on both individual and group
assessments.
We're doing this because we want our students to use good practice, to undersatnd the software lifecycle and to become familiar with industry-standard tools.

## 2. The Reference Process

The SHU development process follows the generic process framework described by Pressman and Maxim [REF], which comprises five methodological stages: communication, planning, modelling, construction and deployment. These main stages encompass a set of support steps: analysis and design related to modelling; code and test related to construction; and delivery, support and feedback for deployment.

![Reference Process](./Process.png)

Each level of study has an specific set of guidelines, techniques and tools with appropriate depthness for the level.

The different stages are presented below, with links for their respective guidelines and can be viewed in two ways:

- Click [here](#3-level-based-view) for a level-based view of the guidelines ([L4](#31-level-4), [L5](#32-level-5), [L6](#33-level-6)).
- Click [here](#4-process-based-view) for a process-based view of the guidelines.

Rembember, these stages are simply used for helping organising and presenting the process, and should not be interpreted as a strict order.
In fact, each student is free to navigate over the stages as he/she sees fit.

A description of each phase is presented below.

- The **communication** phase is dedicated to understanding the objectives of stakeholders, and for the design and collection of requirements that help identify the expected software functionalities and quality attributes.
- The **Planning** phase is responsible for defining the scope of the project, the resources needed, the risks involved, a work schedule, and the resulting products.
- The **Modelling** phase is divided into analysis and design steps.
  - The **Analysis** is focused on the definition/formalisation of requirements, using artefacts like user stories and use cases.
  - The **Design** step is focused on the modelling of the solution. It usually involves decision around architecture, data structure, user-interface, classes, algorithms, etc.
- The **Construction** phase involves the implementation of the structures modeled in the design phase. For this purpose, **code** and **tests** are conducted.
- The **Deployment** involves the steps of **delivery** and **support and feedback**.
  - **Delivery** is focused activities associated with the ongoing DevOps practices.
  - **Support and feedback** step is driven by monitoring and maintenance activities. This step also contains guidance regarding assessment, reports and presentations. We also consider evaluation, reporting and reflection as part of this last step.

## 3. Level-based view

### 3.1. Level 4

- Planning
  - [Git version control](planning/version-control/level_4_git_instructions.md)
- Modelling - Analysis
  - [User stories](modelling-analysis/level4/user-stories.md)
- Construction - Code
  - Code commenting
  
### 3.2. Level 5

- Planning
  - [Git version control](planning/version-control/level_5_git_instructions.md)
- Modelling - Analysis
  - [User stories](modelling-analysis/level5/user-stories.md)
  - [MoSCoW prioritisation method](modelling-analysis/level5/moscow_prioritisation_method.md)
- Modelling - Design
  - UML Class diagrams
- Construction - Code
  - Code commenting

### 3.3. Level 6

- Planning
  - [Git version control](planning/version-control/level_6_git_instructions.md)
- Modelling - Analysis
  - [User stories](modelling-analysis/level6/user-stories.md)
- Modelling - Design
  - UML Class diagrams
- Construction - Code
  - Code commenting

## 4. Process-based view

### 4.1. Communication

- [**Communication guidelines**](communication/README.md)

### 4.2. Planning

- [**Planning guidelines**](planning/README.md)

### 4.3. Modelling - Analysis

- [**Analysis guidelines**](modelling-analysis/README.md)

### 4.4. Modelling - Design

- [**Design guidelines**](modelling-design/README.md)

### 4.5. Construction - Code

- [**Code guidelines**](construction-code/README.md)

### 4.6. Construction - Test

- [**Tests guidelines**](construction-test/README.md)

### 4.7. Deployment - Delivery

- [**Delivery guidelines**](deployment-delivery/README.md)

### 4.8. Deployment - Support and Feedback

- [**Support and feedback guidelines**](deployment-support-feedback/README.md)

## 5. Tools view

- **Project Planning:** Trello, MS Project, MS Excel
- **Communication:** Team, Slack
- **Version Control:** Git, CVS or similar
- **Design:** STARUML, Visio or similar
- **Coding:** Visual Studio/ Intelli J  or similar
- **Unit Testing:** Junit/Nunit or similar. Coverage tools
- **Code Review:** SonarQube
- **Integration Testing:** Azure DevOps or similar
- **User Acceptance Testing:** Selenium
- **Deployment/Release:** Azure DevOps or similar

## 6. Development Team

- Carlos Da Silva
- Soumya Basu
- Chris Bates
- James Harmson
- Brian Davis
