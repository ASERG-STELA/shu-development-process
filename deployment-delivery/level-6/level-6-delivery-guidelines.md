# Level 6 Delivery Guidelines

## 1. Abstract

This document will serve to provide Level 6 students with instructions on what you need to do for arguably the most important phase of the software development lifecycle. The Delivery of the product. At Level 6, along with submitting the README file located [here](../L6-README-Template.md), we expect DevOps culture to be adopted, especially for your Final Year Project, and CSSD modules.  

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. DevOps](#3-devops)
- [4. What is Expected](#4-what-is-expected)
- [5. Tools](#5-tools)
- [6. References](#6-references)

## 3. DevOps

If you have read through the [level 5](../level-5/level-5-delivery-guidelines.md) guidelines, you should now be familiar with what DevOps is, and the different phases involved within the culture. 
As a reminder, DevOps (Development Operations) is a set of practices that works to automate and integrate the processes between software development and IT teams, so they can build, test, and release software faster and more reliably (reference [1]). 
DevOps is an important aspect of software development to learn before you graduate university, and it will impress your interviewers for any graduate roles/schemes.

DevOps is made up of 8 main practices, which can be seen from this diagram:

![DevOps diagram](../images/devops-diagram.png)
*Fig. 1: DevOps practices. Retrieved from reference [2]*

## 4. What is Expected

At Level 6, we are expecting to see DevOps culture adopted for your larger projects, most notably your Final Year Project. It would also be nice to see in your CSSD module. We are expecting each phase to be implemented, other than the final stage; **Monitor**, as you are not expected to maintain these projects after submission (although it may be beneficial to you to maintain your Final Year Projects). A CI/CD pipeline should be adopted at the minimum.

We expect:

* **Plan**: Correct use of version control with branching and CI/CD adopted, good project management and team communication.
* **Code** and **Build**: Good quality code with comments, and with the designs and models you have created in mind.
* **Test**: Use of a tool would be nice such a JUnit/NUnit or Selenium, comprehensive Unit Testing and User Acceptance Testing where applicable. Should be done on develop branch.
* **Release**: Continuous Integration adopted, perhaps through the use of Github Actions. Code being merged in small batches frequently, with automated tests being run.
* **Deployment**: Continuous Delivery being used in FYP and CSSD if applicable, releasing as soon as possible, but could be a scheduled timeframe i.e. weekly.
* **Operate**: Not essential, however would be nice to see in Final Year Projects if applicable e.g. Kubernetes or Docker.

And remember, you should always fill in and submit a README file detailing the contents of your submission. This can be found [here](../L6-README-Template.md). You should do this along with any DevOps implementation, the details of this should be outlined in the README.

## 5. Tools

We recommend the tools below for integrating the full DevOps pipeline into your projects. We are not expecting all of these to be used, but some such as Junit/NUnit and Github Actions would be good to see:

### Testing

* JUnit/NUnit: 
  * JUnit: https://junit.org/junit5/
  * NUnit: https://nunit.org/
* Selenium: https://www.selenium.dev/

### Release

* Github Actions: https://github.com/features/actions
* Gitlab: https://about.gitlab.com/
* Gitea: https://gitea.io/en-us/
* Codeship: https://www.cloudbees.com/products/codeship
* Jenkins: https://www.jenkins.io/

### Deployment/Operate

* Docker: https://www.docker.com/
* Kubernetes: https://kubernetes.io/
* Azure: https://azure.microsoft.com/en-gb/ (free credit available from university)
* DC/OS: https://dcos.io/

## 6. References

[1] Atlassian. DevOps: Breaking the Development-Operations barrier. <https://www.atlassian.com/devops>.

[2] Medium. How to Become an DevOps Engineer in 2020. <https://medium.com/swlh/how-to-become-an-devops-engineer-in-2020-80b8740d5a52>. By Shane Shown.
