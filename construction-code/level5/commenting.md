# Code Commenting - Level 5

## 1. Table of Contents
- [2. Introduction](#2-introduction)
- [3. Coding Standards](#3-coding-standards)
  - [3.1. Effective Coding Standards](#31-effective-coding-standards)
  - [3.2. Coding Standards based on Language](#32-coding-standards-based-on-language)
  - [3.3. Automate the Process](#33-automate-the-process)
- [4. References](#4-references)

## 2. Introduction

The question most people ask is "Why do we need code comments anyway?"

Code commenting is a very simple way to let someone know what your code is meant to be doing, even if their background in code is weak. Good comments make for easy reading and easy understanding for those who are perhaps not as tech savvy as yourself. Code commenting also explains why you wrote something. At Level 4, the expectation is that you will write basis code comments as a minimum measure to help a reader understand your code.

These are meant for anyone who is likely to consume your source code, but they aren't likely to read through it in any real depth. Code comments are also used by different tools for automatic generation of documentation.
If you are building something such as a **Library** or **Framework** that you would expect other developers to be using, then you need some form of documentation alongside that, with which comments help the basis of understanding.

It is worth mentioning that several organisations, and open source projects, define specific code style guidelines that must be adhered to.
If they don’t, however, or you are on your own, keeping this stuff in mind will not only make your job easier in the future, but will also help out anyone who comes after you, too.

More information on basic code commenting can be found in the Level 4 Code Commenting Document found [here](../level4/commenting.md).

## 3. Coding Standards
When creating your code comments, it is advised that your commenting follows a relevant coding standard. Coding standards are a set of guidelines, best practices, programming styles and conventions that developers adhere to when writing source code for a project. All big software companies have them.  
An example of some guidelines, taken from the <b>Linux kernel coding style</b>  

a. Tabs are 8 characters, and thus indentations are also 8 characters.  
  
b. The limit on the length of lines is 80 columns and this is a strongly preferred limit.  
  
c. The preferred form for allocating a zeroed array is the following:  

```java
p = kcalloc(n, sizeof(...), ...);  
```
*Both forms check for overflow on the allocation size n * sizeof(…), and return NULL if that occurred.*  
  
A few examples of good coding standards are;  
* No more than one statement per line
* Line length should not exceed 80 or 100 characters
* Test class must start with the name of the class they are testing followed by 'test'.  
e.g. <b>ServerConfigurationTest</b>  
* One character variable names should only be used in loops or for temporary variables  
It is important to remember there is a grey area when considering acceptable coding standards and those set out as personal opinion rather than standards that are considered to be good.

### 3.1. Effective Coding Standards
Why exactly do we need coding standards, and what benefits do they offer?  
There is a direct relationship between <b>coding standards</b> and <b>software maintainability</b>. There is no doubt that <b>source code</b> that adheres to good standards is simply more readable and reflects harmony, but there is another side to coding standards which is sometimes overlooked at the expense of too much attention to the aesthetics.
  
Effective coding technqiues focus more on techniques that highlight problems and make bugs stand-out and visible to everyone.
  
Effective coding standards are;  
* short, simple and concise
  * they do not attempt to cover and processify everything
  * leave plenty of room for developers to exercsie their own creativity
* strike the right balance between formatting issues and issues that 'make the wrong code look wrong'
* black and white instead of vague suggestions or recommendations

### 3.2. Coding Standards based on Language
Coding Standards differ between programming languages, links to these standards are provided for you below;  
* [Java](../codingstandards/java.md)

* [C Programming](../codingstandards/c.md) which covers:
  * C#
  * C++
  
* [Web Development](../codingstandards/webdev.md) which covers:
  * Node.js
  * PHP
  
### 3.3. Automate the Process
Once you have developed effectvie coding standards and are maming use of them, you should learn how to <b>automate the process</b>.  
Automating the process of checking source code's adherence to standards, it will allow you to save a lot of time in perr reviews and alow you to catch everything that humans might miss. 
  
If you are starting fresh and looking for coding standards, start by searching online for well-known standards for your programming language. Start small and remember that there is more than one right way to style the code. There might already be a standard available from the language creators. Your coding standards should check for both style issues and design problems. Once you have standards, make sure that they are adopted by the team and automated. However, code that deviates from standards shouldn’t be considered erroneous. It should simply be marked as out of compliance and deviations must be reviewed and fixed.

There is an abundance of style checking tools available for all major programming languages.
The example image below shows the Checkstyle scan that is used for Java projects.  
![](https://codeahoy.com/img/checkstyle-intellij.png)



## 4. References 
[Codeahoy: Effective Coding Standards](https://codeahoy.com/2016/05/22/effective-coding-standards/#:~:text=Coding%20standards%20are%20a%20set,big%20software%20companies%20have%20them.)
