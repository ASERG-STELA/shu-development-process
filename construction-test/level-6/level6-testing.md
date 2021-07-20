# Testing - Level 6 <!-- omit in toc -->

## 1. Introduction

Testing is a vital part of software development, and at Level 6, you will need to know how to conduct effective testing. At this level, you will be exposed to 3 different types of software testing, and it will be nice to see you use a tool or framework to automate as much of it as possible:

- Unit Testing
- Integration Testing
- User Acceptance Testing

This document will provide you with some information and resourses for you to look at to learn how to automate your tests, and what is expected at this level. We will also cover User Acceptance Testing (UAT) in more detail than what was previously explained in Level 5, as well as an in-depth look at evaluation techniques (a type of UAT). For some guidance on unit testing, integration testing, and some basic information on UAT, please re-visit the Level 5 testing guidelines [here](../level-5/level5-testing.md).

## 2. Table of Contents

- [1. Introduction](#1-introduction)
- [2. Table of Contents](#2-table-of-contents)
- [3. User Acceptance Testing/Evaluation](#3-user-acceptance-testingevaluation)
  - [3.1. Types of Evaluation](#31-types-of-evaluation)
    - [Lab-based studies](#lab-based-studies)
    - [SUS Survey](#sus-survey)
    - [Diaries and Logs](#diaries-and-logs)
    - [Observational Studies](#observational-studies)
    - [Focus Groups and Interviews](#focus-groups-and-interviews)
    - [Analytical Evaluations](#analytical-evaluations)
    - ["Guerilla" Usability Testing](#guerilla-usability-testing)
  - [3.2. Choosing a Method](#32-choosing-a-method)
  - [3.3. Ethics](#33-ethics)
- [4. Automating Tests](#4-automating-tests)
- [5. What is Expected](#5-what-is-expected)
- [6. Tools](#6-tools)
  - [Unit/Integration Testing](#unitintegration-testing)
  - [User Acceptance Testing](#user-acceptance-testing)
  - [Code Coverage](#code-coverage)

## 3. User Acceptance Testing/Evaluation

At Level 6, you will be exposed to UAT more so than in previous levels. You will likely have to do some form of UAT for your Final Year Project and CSSD modules (and perhaps others). This UAT will likely be User Interface (UI) evaluation to evaluate your systems **usability goals** and **user experience goals**.

Some examples of usability goals include:

- Effective to use
- Efficient to use
- Safe to use
- Easy to learn

Some examples of user experience goals include:

- Satisfying
- Engaging
- Helpful
- Enjoyable

You will also want to think about what methods you think would be appropriate to evaluate your system, quantitative or qualitative.

Quantitative methods involve a comparison of measured data. This is best for usability evaluation as you can measure statistics such as time taken to complete a task, or number of clicks.

Qualitative methods involve watching users interact with your system. This can be used for both usability and user experience evaluation.

### 3.1. Types of Evaluation

There are many types of evaluation for many different types of systems, including:

- Lab-based studies
- SUS Survey
- Diaries and logs
- Observational studies
- Focus groups and interviews
- Analytical Evaluations
- "Guerilla" usability testing

#### Lab-based studies

Lab-based studies are (loosly) based on methods from experimental psychology. It uses (semi-) formal experimental design and can be used for quantitative or qualitative evaluation.

It requires a constrained environment and can involve professional analysts, which is something you probably won't have access to at university. The question also needs to be asked: Is this representative of the real world?

The process involves 5 steps:

1. Choose your research question - can be very defined e,g, How quickly can users buy a ticket to London? or less defined e.g. Do users understand the interface?
2. Decide what to measure - quantitative mesures e.g. time taken, or qualitative measures e.g. user feedback.
3. Create procedures:
   - Recruit participants
   - Consent forms and initial interviews/questionnaires
   - Instructions
   - Experiment plan
   - Post-study interview/questionnaire
4. Run the study - Gather data from participants for analysis. Ensure to follow the procedures from previous step.
5. Analyse the results:
   - Examine the data
   - Look for key points/statistics
   - Try to find examples
   - Gather useful quotations to illustrate
   - Try to match across participants
   - Graphs would be useful for quantitative analysis

Problems:

- Not real-world – no context
- Overly structured
- can be intimidating
- How we expect users to act – not how they actually act

#### SUS Survey

This is a quick and reliable way to measure the usability of your system, and is a method that will be easy to do for yourselves as university students.

It consists of a 10 item questionnaire with five response options for respondents; from Strongly agree to Strongly disagree. It allows you to evaluate a wide variety of products and services, including hardware, software, mobile devices, websites and applications. It also fits well with an Agile approach, and is an attitudinal (subjective) approach.

The 10 questions are:

1. I think that I would like to use this system frequently.
2. I found the system unnecessarily complex.
3. I thought the system was easy to use.
4. I think that I would need the support of a technical person to be able to use this system.
5. I found the various functions in this system were well integrated.
6. I thought there was too much inconsistency in this system.
7. I would imagine that most people would learn to use this system very quickly.
8. I found the system very cumbersome to use.
9. I felt very confident using the system.
10. I needed to learn a lot of things before I could get going with this system.

The participant’s scores for each question are converted to a new number, added together and then multiplied by 2.5 to convert the original scores of 0-40 to 0-100.  Though the scores are 0-100, these are not percentages and should be considered only in terms of their percentile ranking.

A SUS score above a 68 would be considered above average and anything below 68 is below average, however the best way to interpret your results involves “normalizing” the scores to produce a percentile ranking.

#### Diaries and Logs

This one is simple and self explanitory:

- Ask users to document usage of the system
- Good for alpha and beta releases
- Small number of users
- Need to carefully choose users

#### Observational Studies

This method involves watching users interact with the system instead of making them document their views. This can be done in a lab or in the real world, however difficulty arises of not interfering as this could change the observed result. You may need to record a video for future reference and you can compare results to system log data.

Observational studies can be difficult due to:

- Observing without interfering
- Participants’ schedules
- Interruptions
- Understanding the domain
- Need help – from people or technology

They are usually done using 2 methods:

- Video recording
- Shadowing users

Both of these involve following ethical practices which can affect users. You will need consent from all users to undertake this type of study, which will involve drafting up a participant information sheet and consent form (more on ethics later).

#### Focus Groups and Interviews

Like diaries and logs, interviews and focus groups are pretty self explanitory. An interview is a discussion with one participant, which can be done in real-world context and can be less intimidating than lab-based test. Interviewees often have no formal tasks to perform and can be structured or unstructured. If conducted 'in the wild', you could also ask participants for demonstrations.

A focus group is similar, but is a moderated discussion with multiple participants at once, lead by a facilitator. It is a method used to learn more about users and the participants should be representative.

#### Analytical Evaluations

This type of evaluation is probably the one you are least likely to do at university. It involves using expert evaluators rather than actual users. The study takes place in a lab rather than 'in the wild'.

This can be good for a number of reasons, the main reason being that you get expert feedback on your system from people who know what to look for. The downside is that they are often not an accurate representation of real users, and are likely not to use your system in real life and will just see it as part of their job.

#### "Guerilla" Usability Testing

This type of testing is used to perform a quick usability test in the real world. It involves simply going into a public space, and approaching users (or incentivise them to approach you) to get them to use your system while you observe and ask them questions. This is very effective from as little as 5 participants (as after this point, the participants will usually be repeating things previous participants have said).

This type of testing is good as you can access a wide range of users, and can be very effective and cheap. It is particularly useful for apps as it is easily portable. However, as with Analytical Evaluations, you are also unlikely to do this type of evaluation, as you will not encounter many occasions where you can go out and show your product to users, especially due to COVID-19.

There are also other types of evaluation that you are unlikely to do at university, including 'Wizard of Oz' and 'Heuristic Evaluation' as they involve expert evaluators (heuristic) and a 'wizard' in the case of 'Wizard of Oz' (to fake system responses).

### 3.2. Choosing a Method

Choosing a method can be daunting as there are so many. But it depends on a number of factors:

- How easily can you access users?
- How developed is the system?
- How complex are the tasks?
- How important is context?
- Is it possible to simulate context?
- **What do you want to know?**

The final point in particular is probably the most significant. It can be a specific performance question such as "Is method A faster than method B?" or a more general question such as "Do users enjoy using the system?".

### 3.3. Ethics

With any type of UAT/evaluation, you will have to consider the ethics of your studies, and get ethical approval for your study from the university. This involves submitting an ethical approval form, either a University Research Ethics Committee 1 (UREC1) or UREC-2. There are higher UREC levels, although anything above UREC2 involves the use and storage of personal information, which is not something you want to deal with at university. Most will involve creating a UREC2 (low risk with human participants) form.

You will also need to create a 'Participant Information Sheet' (letting participants know what the study is for and how their data will be used) and a 'Participant Consent Form' (allowing participants to give written consent to taking part in the study). Although this might be considered 'boring', it is vital that you do this if you are showing your product off to anybody for UAT purposes, you do not want to be going to court over GDPR breaches.

## 4. Automating Tests

At Level 6, it will be nice to see you automate as many of your tests as possible. The easiest way to do this is through a tool using Continuous Integration (CI). CI is the practice of automating the integration of code changes from multiple contributors into a single software project. It allows developers to frequently merge code changes into a central repository where builds and tests then run. Automated tools are often used to assert the new code’s correctness before integration.

CI is often used to run some automated unit and integration tests before/during a branch merge on Github. This is very useful as errors that could compromise the code will get found, and the merge will be stopped before it has taken place. There are many tools that use CI including [Github](https://github.com/features/actions), [Gitlab](https://about.gitlab.com/), [Jenkins](https://www.jenkins.io/), and more.

More documentation on CI as well as other DevOps practices can be found in both the [Level 5 Delivery](../../deployment-delivery/level-5/level-5-delivery-guidelines.md) and [Level 6 Delivery](../../deployment-delivery/level-6/level-6-delivery-guidelines.md) guidelines. You can also find how to implement a CI pipeline in Github using Github Actions [here](../../planning/version-control/tools/level-5-github-actions.md).So visit these documents for more information.

For automating user acceptance tests, we recommend you use a tool called [Selenium](https://www.selenium.dev/). This a great, portable framework for testing web applications. Automating UAT is not essential at Level 6, but it would be nice to see depending on the module (such as CSSD or your Final Year Project).

## 5. What is Expected

At Level 6, we are expecting the following:

- Unit testing: Should be programmed and integrated with build (CI).
- Integration testing: Should be programmed and integrated with build. CI practice is recommended.
- User acceptance testing: Nice to be automated using a tool such as Selenium.
- Code coverage: Nice to see depending on the module. See more on code coverage [here](../../construction-code/code-review/level-6/level-6-code-review-guidelines.md).

## 6. Tools

There are a wide range of testing tools and frameworks out there for you to utilise on your projects. Some have already been covered at [Level 5](../level-5/level5-testing.md). This document will not show you how to use all of these tools, but we can provide you with links to the official documentation of tools we recommend:

### Unit/Integration Testing

- [MSTest:](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-mstest)
- [NUnit:](https://docs.nunit.org/articles/nunit/intro.html)
- [xUnit:](https://xunit.net)
- [JUnit:](https://junit.org/junit5/docs/current/user-guide)
- [PyTest:](https://docs.pytest.org/en/6.2.x/)

### User Acceptance Testing

- [Selenium](https://www.selenium.dev/)
- [Capybara](https://github.com/teamcapybara/capybara)
- [Cucumber](https://cucumber.io/)

### Code Coverage

- Java: Atlassian Clover, Cobertura, JaCoCo
- Javascript: istanbul, Blanket.js
- PHP: PHPUnit
- Python: Coverage.py
- C#: Visual Studio Code coverage, ReSharper's dotCover
