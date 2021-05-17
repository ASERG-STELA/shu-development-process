# Level 4 Code Review Guidelines

## 1. Abstract

This document will provide Level 4 students with the knowledge to conduct good quality code/peer reviews for your software projects.

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. What Is Code Reviewing](#3-what-is-code-reviewing)
  - [3.1. Why is it Important](#31-why-is-it-important)
- [4. Types of Code Review](#4-types-of-code-review)
  - [4.1. The Email Thread](#41-the-email-thread)
  - [4.2. Pair Programming](#42-pair-programming)
  - [4.3. Over-the-Shoulder](#43-over-the-shoulder)
  - [4.4. Tool-Assisted](#44-tool-assisted)
- [5. How to Conduct a Good Code Review](#5-how-to-conduct-a-good-code-review)
- [6. What is Expected](#6-what-is-expected)
- [7. References](#7-references)

## 3. What Is Code Reviewing

Code review, sometimes called peer code review, is a quality assurance activity where one or more programmers will check some source code from another developer for any mistakes. This activity has been proven to accelerate and streamline the software development process. 

The argument might be made that there is no need to do code reviews if you employ comprehensive manual or automated Unit Testing, however, testing will only check if the program is functioning correctly, not that the programs' features are what they are supposed to be. This needs the human intervention in which a piece of software cannot determine.

## 3.1. Why is it Important

As previously mentioned, code reviews allow developers to spot mistakes in each others code. These mistakes could be anything from syntactic and compiler errors, to merge conflicts when you are looking to merge different branches in your Github repositories. 

Other developers in your team may be more likely to spot mistakes on your code than you are. You may need a fresh set of eyes of someone who has not seen your code before. Other than the obvious reason why it is important; to make sure a program is functioning correctly, it is also important for ensuring the code matches what is required by the client, which a software testing tool will not be able to tell you.

## 4. Types of Code Review

There are a few different ways you can conduct a code review, there is not really any right or wrong way to do it, as long as you determine if there are any mistakes in the code, and rectify them. Here are four common approaches, but you may find your own approach to be the best for you:

* The Email Thread
* Pair Programming
* Over-the-Shoulder
* Tool-Assisted

## 4.1. The Email Thread

This approach is simple. If you are struggling with something, or would like some code reviewing before pushing the changes to Github, you can email the changed file to your colleagues for them to review when their workflow permits. 
Although known as 'The Email Thread', you can swap email for any communication software that allows for file sharing, such as Discord, Microsoft Teams, Zoom or Google Drive.

This approach can be more flexible than the other techniques, an email thread of code reviews can quickly get complicated, and it depends on the workloads of your colleagues. If they are busy with other tasks and don't have the time straight away to review your code, it may get forgotten about, leaving you to either do the work yourself or having to use one of the other techniques.

## 4.2. Pair Programming

Pair programming is a key part of the Extreme Programming (XP) methodology. It involves two developers working side-by-side on a piece of code together, checking each others work as they go. This technique essentially integrates code reviews directly into development as it is ongoing, which will save time over waiting for someone to review the code after you have completed its development.

However, as both developers will be too 'close' to their code (and may be more bias), other code review methods might provide more objectivity. It can also use more resources and personnel than other techniques.

## 4.3. Over-the-Shoulder

This is a more comfortable form of pair programming. This technique involves a colleague shadowing a developer while they review the code for you, whilst at the same time, you explain what the code does, and why it is needed. This is possibly the easiest and most intuitive way to perform code reviews, as it is lightweight and often quite informal. However, this lightweightness can be too light if it lacks proper documentation (so make sure to write comments or notes on something!). 

## 4.4. Tool-Assisted

Tool assisted is arguably the most efficient of the four techniques. In this method, code is reviewed using software-based code review tools, with some of the most popular being:

* [SonarQube](https://www.sonarqube.org/)
* [Review Board](https://www.reviewboard.org/)
* [Github](https://github.com/features/code-review/)
* [Crucible](https://www.atlassian.com/software/crucible)
* [UpSource](https://www.jetbrains.com/upsource/)

There is no 'best tool', so try some out, and use whatever is most comfortable for you. Using a tool will assist with the following tasks:

* Organising and displaying the updated files in a change.
* Facilitate a conversation between reviewers and developers.
* Assess the efficacy of the code review process with metrics.

## 5. How to Conduct a Good Code Review

Here are 9 code review best practices, that you should try to use when undertaking your code reviews (reference [3]):

1. Know What to Look for in a Code Review (e.g. structure, style, logic, performance, test coverage, design, readability (and maintainability), functionality)

2. Build and Test — Before Review (make sure the code compiles before review)

3. Don't Review Code for Longer Than 60 Minutes

4. Check No More Than 400 Lines at a Time

5. Give Feedback That Helps (Not Hurts)

6. Communicate Goals and Expectations

7. Include Everyone in the Code Review Process

8. Foster a Positive Culture

9. Automate to Save Time (not essential, would be nice to see at Level 6)

## 6. What is Expected

At Level 4, you are not expected to use a code review tool. Instead, you should focus on manual code reviews, using one or more of the other three techniques listed above. Then end goal is to ensure there are no bugs in your code, minimise your chances of having issues, confirm the code adhears to guidelines and increase the efficiency of it. It is also important to make sure the new code is actually an improvement over the old code base. 

For more information on how to conduct code reviews, look at references [1] and [2].

## 7. References

[1] SmartBear. What is Code Review?. <https://smartbear.com/learn/code-review/what-is-code-review/>.

[2] Kinsta. 12 Best Code Review Tools for Developers (2021 Edition). <https://kinsta.com/blog/code-review-tools/>.

[3] Perforce. 9 Code Review Best Practices. <https://www.perforce.com/blog/qac/9-best-practices-for-code-review>.
