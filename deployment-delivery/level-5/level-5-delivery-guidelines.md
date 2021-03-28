# Level 5 Delivery Guidelines

## 1. Abstract

This document will serve to provide Level 5 students with instructions on what you need to do for arguably the most important phase of the software development lifecycle. The Delivery of the product. At Level 5, along with submitting the README file located [here](../README-Template.md), some flavour of DevOps would also be nice depending on the module.  

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. DevOps](#3-devops)
  - [3.1. What is DevOps](#31-what-is-devops)
  - [3.2. Continuous Integration](#32-continuous-integration)
  - [3.3. Continuous Delivery and Deployment](#33-continuous-delivery-and-deployment)
- [4. What is Expected](#4-what-is-expected) 
- [5. Tools](#5-tools)
- [6. References](#6-references)

## 3. DevOps

At Level 5, some flavour of DevOps would be good to implement depending on the module. GSDP would be an ideal module to implement some DevOps practices.

## 3.1. What is DevOps

DevOps (Development Operations) is a set of practices that works to automate and integrate the processes between software development and IT teams, so they can build, test, and release software faster and more reliably (reference [1]).
You may not think this is very applicable to you as students, but it is a good idea to learn some form of DevOps before you start your first development job after university, as companies will more than likely have some form of IT team that developers like yourselves will need to work with.

DevOps is not a thing, such as a piece of software or programming language, it is a culture; a set of practices to help improve software development enabling for rapid software release. It is made up of 8 main practices, which can be seen from this diagram:

![DevOps diagram](../images/devops-diagram.png)
*Fig. 1: DevOps practices. Retrieved from reference [2]*

This diagram shows the primary DevOps practices, as well as some popular tools that are often used during each phase. Throughout each phase, teams collaborate and communicate to maintain alignment, velocity, and quality. 
At this Level you should already be familiar with **Plan**, **Code** and **Build**. In this document, we will pay particular attention to **Release** and **Deployment**. These two phases are often called **Continuous Integration** and **Continuous Delivery/Deployment** (CI/CD). We will now go into detail about these two phases. The CI/CD pipeline is one of the best practices for DevOps teams to implement, for delivering code changes more frequently and reliably.

## 3.2. Continuous Integration

Continuous Integration (CI) is the practice of automating the integration of code changes from multiple contributors into a single software project. 
It allows developers to frequently merge code changes into a central repository where builds and tests then run. Automated tools are often used to assert the new code’s correctness before integration. At Level 5, using automated tools is not expected, but would be nice if you have the ability.

As you can probably guess, the backbone of a good CI pipeline/workflow is good version control management. Version control is also supplemented with other checks like automated code quality tests, and syntax style review tools. In Git (which you should be familiar with at this level), a CI pipeline can be implimented using an **Action**. I will demonstrate how to implement a Github Action later in the document.

CI is a valuable and well-established practice in modern, high performance software engineering organizations, therefore it is a good practice to learn, before you go out into the working world (reference [3]). You can set up a CI pipeline in Github using Github Actions. We have provided guidance for this, which can be seen [here]().

## 3.3. Continuous Delivery and Deployment

Coninuous Delivery (CD) is slightly different, but goes hand in hand with Continuous Integration. Continuous Delivery is essentially an extension of Continuous Integration since it automatically deploys all code changes to a testing and/or production environment after the build stage. 
This means that on top of automated testing, you have an automated release process where you can deploy your application any time. 

In theory, with CD, you can decide to release daily, weekly, fortnightly, or whatever suits your business/user requirements. It is best practice to release as soon as possible, releasing in small, managable batches that are easy to troubleshoot if any problems arise.

Continuous Deployment goes one step further than Continuous Delivery. With this practice, every change that passes all stages of your production pipeline is released to your customers. There's no human intervention, and only a failed test will prevent a new change to be deployed to production (reference [4]). This is not expected at Level 5.

## 4. What is Expected

At Level 5, DevOps is not expected to be seen in all of your projects. In some modules such as GSDP however, it would be nice to see some basic DevOps such as a Continuous Integration pipeline. This can be done using a Github Action. You can follow the guidance [here]() to set one up. 
It is essential that you maintain good version control management in your GSDP module, and it would be nice to see a Github Action implemented for some basic automated testing. Manual communication should still be of high importance on this module, and during any of your other group projects.

Code should be pushed and merged in small batches frequently if you are following DevOps practices. If this is done in conjunction with automated tests in a CI workflow, you will impress your clients and your module leaders, and importantly, make for good quality code and releases.  

As well as this; as with Level 4, you should also complete and upload the README file located [here](../README-Template.md) with your submission. This README goes into a little more detail than the one provided for Level 4, so make sure you fill out all sections appropriately. 

## 5. Tools

There are many tools that can be used to set up a basic DevOps pipeline. We have already talked about Github Actions, you can follow a walkthrough of this [here]().
Some other tools that are good for deployment can be seen below, they don't just have to be used for a DevOps pipeline:

### Gitlab
Download/info: https://about.gitlab.com/stages-devops-lifecycle/

### Gitea
Download/information: https://gitea.io/en-us/

### Codeship
Download/information: https://www.cloudbees.com/products/codeship

### Jenkins
Download/information: https://www.jenkins.io/

## 6. References

[1] Atlassian. DevOps: Breaking the Development-Operations barrier. <https://www.atlassian.com/devops>.

[2] Medium. How to Become an DevOps Engineer in 2020. <https://medium.com/swlh/how-to-become-an-devops-engineer-in-2020-80b8740d5a52>. By Shane Shown.

[3] Atlassian. What is Continuous Integration?. <https://www.atlassian.com/continuous-delivery/continuous-integration>. 

[4] Atlassian. Continuous integration vs. continuous delivery vs. continuous deployment. <https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment>.

