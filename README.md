# Software Development Process <!-- omit in toc -->

- [1. Introduction](#1-introduction)
- [2. The Reference Process](#2-the-reference-process)
- [3. Level-based view](#3-level-based-view)
  - [3.1. Level 4](#31-level-4)
  - [3.2. Level 5](#32-level-5)
  - [3.3. Level 6](#33-level-6)
- [4. Process-based view](#4-process-based-view)
  - [4.1. Initiation](#41-initiation)
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

The SHU development process is based on the generic process framework described by Pressman and Maxim [REF], and comprises five methodological stages: initiation, planning, modelling, construction and deployment. These main stages encompass a set of support steps: analysis and design related to modelling; code and test related to construction; and delivery, support and feedback for deployment.

![Reference Process](./Process.png)

Each level of study has an specific set of guidelines, techniques and tools with appropriate depthness for the level.

The different stages are presented below, with links for their respective guidelines and can be viewed in two ways:

- Click [here](#3-level-based-view) for a level-based view of the guidelines ([L4](#31-level-4), [L5](#32-level-5), [L6](#33-level-6)).
- Click [here](#4-process-based-view) for a process-based view of the guidelines.

Rembember, these stages are simply used for helping organising and presenting the process, and should not be interpreted as a strict order.
In fact, each student is free to navigate over the stages as he/she sees fit.

A description of each phase is presented below.

- The **Initiation** phase is dedicated to understanding the objectives of stakeholders, and for the design and collection of requirements that help identify the expected software functionalities and quality attributes.
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

- Initiation
  - [Initiation Guidelines](initiation/level4/level4-initiation.md)
- Planning
  - [Git Version Control](planning/version-control/level_4_git_instructions.md)
  - [Project Management](planning/project-management/level-4/level_4_management_guidelines.md)
  - [Team Communication](planning/team-communication/level-4/level_4_team_communication_guidelines.md)
- Modelling - Analysis
  - [User Stories](modelling-analysis/level4/level-4-user-stories.md)
  - [Use Case Diagrams](modelling-analysis/level4/level_4_use_case_guidance.md)
- Modelling - Design
  - [Class, Entity Relationship and Sequence Diagrams](modelling-design/level4/level4-design.md)
- Construction - Code
  - [Code Commenting](construction-code/level4/level4-code-commenting.md)
- Deployment - Delivery
  - [Delivery Guidelines](deployment-delivery/level-4/level_4_delivery_guidelines.md)
- Deployment - Support - Feedback
  - [Support - Feedback Guidelines](deployment-support-feedback/level-4/level_4_feedback_guidelines.md)
  
### 3.2. Level 5

- Planning
  - [Git Version Control](planning/version-control/level_5_git_instructions.md)
  - [Project Management](planning/project-management/level-5/level_5_management_guidelines.md)
  - [Team Communication](planning/team-communication/level-5/level_5_team_communication_guidelines.md)
- Modelling - Analysis
  - [User Stories](modelling-analysis/level5/level-5-user-stories.md)
  - [MoSCoW Prioritisation Method](modelling-analysis/level5/moscow_prioritisation_method.md)
- Modelling - Design
  - [UML Class Diagrams]()
- Construction - Code
  - [Code Commenting](construction-code/level5/level5-code-commenting.md)
- Deployment - Delivery
  - [Delivery](deployment-delivery/level-5/level-5-delivery-guidelines.md)

### 3.3. Level 6

- Planning
  - [Git Version Control](planning/version-control/level_6_git_instructions.md)
  - [Project Management](planning/project-management/level-6/level_6_management_guidelines.md)
  - [Team Communication](planning/team-communication/level-6/level_6_team_communication_guidelines.md)
- Modelling - Analysis
  - [User Stories](modelling-analysis/level6/level-6-user-stories.md)
- Modelling - Design
  - [UML Class Diagrams]()
- Construction - Code
  - [Code Commenting](construction-code/level6/level6-code-commenting.md)

## 4. Process-based view

### 4.1. Initiation

- [**Initiation guidelines**](initiation/README.md)

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

- [**Project Planning:**](planning/project-management/tools/project_management_tools.md) Trello, MS Project, MS Excel
- **Team Communication:** Team, Slack
- **Version Control ([L4](/planning/version-control/tools/level_4_git_tools.md)):** Git, CVS or similar
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
