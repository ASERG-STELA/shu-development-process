# Testing - Level 4

## 1. Introduction
Unit Testing is a type of software testing where individual units or components of a software are tested. The purpose is to validate that each unit of the software code performs as expected. Unit Testing is done during the development (coding phase) of an application by the developers. Unit Tests isolate a section of code and verify its correctness. A unit may be an individual function, method, procedure, module, or object. At Level 4, the expectation is that you will at least do **manual testing** when you are conducting Unit Testing for your software.

## 2. Table of Contents
- [3. Unit Testing](#3-unit-testing)
  - [3.1. Benefits of Unit Testing](#31-benefits-of-unit-testing)
  - [3.2. What should you test?](#32-what-should-you-test)
  - [3.3. What shouldn't you test?](#33-what-shouldnt-you-test)
  - [3.4. Manual vs Automated](#34-manual-vs-automated)
    - [3.4.1. Manual Testing - Pros and Cons](#341-manual-testing---pros-and-cons)
    - [3.4.2. Automated Testing - Pros and Cons](#342-automated-testing---pros-and-cons)
  [4. References](4#-references)  

## 3. Unit Testing
In most cases, Unit testing are not an effective way to find bugs in your code. They are more effective in examining each unit within your code separately. When you run your application for real, all those units have to work together, and the whole is more complex and subtle than the sum of its independently-tested parts. Defects in an individual component may bear no relationship to the symptoms an end user would experience and report, since you aree designing the preconditions for your unit tests, they won't ever detect problems triggered by preconditions that you didn't anticipate. Unit tests can be effective at detecting in one instance though, and that is when you are re-factoring your code without meaning to change it's behaviour. In this case, tests can often tell you if the unit's behaviour has changed.

### 3.1. Benefits of Unit Testing
When we think about why we should be conducting Unit Tests, it is important to have an understanding as to why they are necessary, and the benefits of them.
* They prove your code actually works
* You get a low-level regression-test suite
* You can improve the design without breaking it
* It's more fun to code with them than without them
* They demonstrate concrete progress
* They are a form of sample code
* It forces you to plan before you code
* It reduces the cost of bugs
* It's even better than code inspections
* Unit tests make designs better

### 3.2. What should you test?
So now you know the benefits of conducting Unit testing, the next thing to think about is, what should you test? These include.
* Collections passed as parameter not changed in the method
* Algorithm Engines
* Utility methods
* Core business logic methods
* Simple DB queries checking predicates
* Services that are high-risk

### 3.3. What shouldn't you test?
We know what we should be testing, but how about what we shouldn't be?
* Constructors or properties (if they just return variables). Test them only if they contain validations.
* Configurations like constants, readonly fields, configs, enumerations, etc.
* Facades of just wrapping other frameworks or libraries
* Container service registrations
* Exception messages
* POCO classes — models, etc.
* .NET Core/Framework logic- like default parameters
* Private methods directly
* Complex SQL Queries (more than 3 joins or grouping, etc.). Better to test it with manual or some kind of system test against real DB.
* ASPNET.Core controller methods
* Complex multi-threading code (it is better to be tested with integration tests)
* Methods that call another public method

### 3.4. Manual vs Automated
In order to do unit testing, we write a section of code to test a specific function in software application. We can also isolate this function to test more rigorously which reveals unnecessary dependencies between the function being tested and other units so the dependencies can be eliminated. We can make use of [UnitTest Frameworks](https://www.guru99.com/test-automation-framework.html) to help develop automated test cases for unit testing. Unit testing is generally of two types. Although Unit testing is generally automated, it can also be done manually if this is preferred. There is no favoritism in terms of which is declared as the best, but automated is the preferred technique. 

|           Parameter           |                      Automation Testing                |                  Manual Testing                | 
|-------------------------------|--------------------------------------------------------|------------------------------------------------|
|  Definition                   | Uses automation to execute test cases  | Test cases are executed by a human tester and software |
|  Processing Time              | Significantly faster than a manual approach | Time-consuming and takes up human resources |
|  Exploratory Testing          | Does not allow random testing | Exploratory Testing is possible in Manual Testing |
|  Initial Investment           | II is higher in AT, though the ROI is better in the long run | II is comparatively lower. ROI is lower in the long run compared to AT                |
|  Reliability                  | Reliable method, as it is performed by tools and scripts. There is no testing fatigue | It is not accurate because of the possibility of human error|
|  UI Change                    | For even a trivial change the UI of the AUT, Automated Test Scripts need to be modified to work as expected                   | Small changes like change in id, class etc. of a button wouldn't thwart execution of a manual tester                |
|  Investment                   | Required for testing tools as well as automation engineers | Needed for human resources               |
|  Cost-Effective               | Not cost effective for low-volume regression | Not cost effective for high-volume regression          |
|  Test Report Visibility       | With automation testing, all stakeholders can login into the automation system and check test execution results                   | Manual Tests are usually recorded in an Excel or Word, and test results are not readily / readily available.                 |
|  Human Observation            | Automated testing does not involve human consideration. So it can never give assurance of user-friendliness and positive customer experience                   | The manual testing method allows human observation, which may be useful to offer user-friendly system.                |
|  Performance Testing          | Performance Tests like Load Testing, Stress Testing, Spike Testing, etc. have to be tested by an automation tool compulsorily               | Performance Testing is not feasible manually                |
|  Parallel Execution           | This testing can be executed on different operating platforms in parallel ad reduce test execution time                   | Manual tests can be executed in parallel but would need to increase your human resource which is expensive                     |
|  Batch Testing                | You can batch test multiple Test Scripts for nightly execution                   |                 |
|  Programming Knowledge        | It is a must in Automated Testing                   | No need for programming in Manual Testing                |
|  Set-up                       | Requires less complex test execution set up  | Needs to have a more straightforward test execution setup                 |
|  Engagement                   | Done by tools. It's accurate and never gets bored  | Repetitive Test Execution can get boring and error-prone                |
|  Ideal Approach               | Useful when frequently executing the same set of test cases     | Proves useful when the test case only needs to run once or twice.                 |
|  Build Verification Testing   | Useful for Build Verification Testing (BVT) | Executing the Build Verification Testing (BVT) is very difficult and time-consuming in manual testing                |
|  Deadlines                    | Zero-risks of missing out a pre-decided test | Has a higher risk of missing out the pre-decided test deadline                |
|  Framework                    | Uses frameworks like Data Drive, Keyword, Hybrid to accelerate the automation process    | Does not use frameworks but may use guidelines, checklists, stringent processes to draft certain test cases                |
|  Documentation                | Automated Tests acts as a document provides training value especially for automated unit test cases. A new developer can look into a unit test cases and understand the code base quickly                   | Manual Test cases provide no training value                |
|  Test Design                  | Enforce/drive Test Driven Development Design                   | Do not drive design into the coding process                |
|  Devops                       | 	Help in Build Verification Testing and are an integral part of DevOps Cycle                   | Defeats the automated build principle of DevOps                 |
|  When To Use?                 | Is suited for Regression Testing, Performance Testing, Load Testing or highly repeatable functional test cases                   | Is suitable for Exploratory, Usability and Adhoc Testing. It should also be used where the AUT changes frequently                |

#### 3.4.1. Manual Testing - Pros and Cons
* Pros
  * Get fast and accurate visual feedback
  * It is less expensive as you don't need to spend your budget fro the automation tools and process
  * Human judgment and intuition always benefit the manual element
  * While testing a small change, an automation test would require coding which could be time-consuming, while you could test manually on the fly
  
* Cons
  * Less reliable testing method because it's conducted by a human. Therefore, it is always prone to mistakes and errors
  * The manual testing process can't be recorded, so it is not possible to reuse the manual test
  * In this testing method, certain tasks are difficult to perform manually which may require an additional time of the software testing phase

#### 3.4.2. Automated Testing - Pros and Cons

* Pros
  * Automated testing helps you to find more bugs compare to a human tester
  * As most of the part of the testing process is automated, you can have a speedy and efficient process
  * Automation process can be recorded. This allows you to reuse and execute the same kind of testing operations
  * Automated testing is conducted using software tools, so it works without tiring and fatigue unlike humans in manual testing
  * It can easily increase productivity because it provides fast & accurate testing result
  * Automated testing support various applications
  * Testing coverage can be increased because of automation testing tool never forget to check even the smallest unit
  
* Cons
  * Without human element, it's difficult to get insight into visual aspects of your UI like colors, font, sizes, contrast or button sizes
  * The tools to run automation testing can be expensive, which may increase the cost of the testing project
  * Automation testing tool is not yet foolproof. Every automation tool has their limitations which reduces the scope of automation
  * Debugging the test script is another major issue in the automated testing. Test maintenance is costl* y

## 4. References
[Guru99: Unit Testing Tutorial](https://www.guru99.com/unit-testing-guide.html)  
[DZone Unit Testing Guidelines: What to Test and What Not To Test](https://dzone.com/articles/unit-testing-guidelines-what-to-test-and-what-not)  
[Guru99: Automated Testing vs Manual Testing](https://www.guru99.com/difference-automated-vs-manual-testing.html)   
