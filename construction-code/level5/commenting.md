# Code Commenting - Level 5

## 1. Table of Contents
- [2. Introduction](#2-introduction)
- [3. Documentation](#3-documentation)
  - [3.1. Documentation Comments](#31-documentation-comments)
    - [3.1.1. In-line Documentation](#311-in-line-documentation---source-code)
    - [3.1.2. Header Block Documentation](#312-header-block-documentation---source-code)
    - [3.1.3. API Documentation](#313-api-documentation)
    - [3.1.4. Organisational Styling Mention](#314-organisational-styling-mention)
  - [3.2. Bad commenting example](#32-an-example-of-bad-code-commenting)
  - [3.3. Clarification Comments](#33-clarification-comments)
  - [3.4. Bad practices](#34-bad-practices-not-to-follow)
- [4. Coding Standards](#4-coding-standards)
  - [4.1. Effective Coding Standards](#41-effective-coding-standards)
    - [4.1.1. Coding Standards based on Language](#411-coding-standards-based-on-language)
  - [4.2. Automate the Process](#42-automate-the-process)
- [5. References](#5-references)

## 2. Introduction

The question most people ask is "Why do we need code comments anyway?"

Code commenting is a very simple way to let someone know what your code is meant to be doing, even if their background in code is weak. Good comments make for easy reading and easy understanding for those who are perhaps not as tech savvy as yourself. Code commenting also explains why you wrote something. At Level 4, the expectation is that you will write basis code comments as a minimum measure to help a reader understand your code.

## 3. Documentation
### 3.1. Documentation Comments
These are meant for anyone who is likely to consume your source code, but they aren't likely to read through it in any real depth. If you are building something such as a <b>Library</b> or <b>Framework</b> that you would expect other developers to be using, then you need some form of documentation alongside that, with which comments help the basis of understanding.

#### 3.1.1. In-line Documentation - Source Code
This is the most common type of source code commenting. Do not do line by line code comments, unless you are doing API documentation, as this makes your code unreadable and is just too excessive. You want to tell the reader what your code does, but they don't need a running commentary all the time. You want to guide them through, not pull them through the grass as you are doing so. 
  
<b>e.g. provided via the Lodash.js documentation found [here](https://lodash.com/)</b>  
```java
// Load the full build.  
var _ = require('lodash');  
// Load the core build.  
var _ = require('lodash/core');  
// Load the FP build for immutable auto-curried iteratee-first data-last methods.  
var fp = require('lodash/fp');  
   
// Load method categories.  
var array = require('lodash/array');  
var object = require('lodash/fp/object');  
   
// Cherry-pick methods for smaller browserify/rollup/webpack bundles.  
var at = require('lodash/at');  
var curryN = require('lodash/fp/curryN');  
```
  
Each comment tells someone reading the documentation here what each line of code is doing. Any questions they have are answered as they are reading through.

<b>e.g. Source Code commenting</b>  
```java
//checks to see if there's a comment. If so, returns a thank you message.  
   
function sourceCodeComment () {  
  var comment = document.getElementbyID("Code Comment").value;   
  if (comment != null && comment != '') {   
        return console.log("Thank you for your comment.")  
}  
```
  
It might seem like this style of commenting is not necessary when the variable names make it obvious what the code is doing, but you need to maintain the mindset, where not everyone who might read the code necessarily has the same level as you, and so these easy to understand code comments that are situated above the code sections are worthwhile to consider including into your own work.

#### 3.1.2. Header Block Documentation - Source Code
This style of code commenting is useful in source code for simple explanations of what to expect in that file. For e.g.  
```java
//=============================================================================  
// rpg_scenes.js v1.6.2  
//=============================================================================  
   
//=============================================================================  
   
/**  
 * The Superclass of all scenes within the game.  
 *   
 * @class Scene_Base  
 * @constructor   
 * @extends Stage  
 */  
function Scene_Base() {  
    this.initialize.apply(this, arguments);  
}  
```
  
This is a good example of good use of header block commenting. Do not, however, provide a comprehensive list of dates on which the file was altered and new versions have been published. This sort of thing is recorded here on Git, so you don't need to worry about that aspect when considering version control within your comments.

#### 3.1.3. API Documentation
API documentation is a technical content deliverable, containing instructions about how to effectively use and integrate with an API. API description formats like the OpenAPI/Swagger Specification have automated the documentation process, making it easier for teams to generate and maintain them. More information regarding this style of Documentation will be discussed further in Level 6.

#### 3.1.4. Organisational styling mention 
If you’re in the trenches day in and day out, writing code and pushing to GitHub, your organization may have a style guide for comments they want you to follow. If they don’t, however, or you are on your own, keeping this stuff in mind will not only make your job easier in the future, but will also help out anyone who comes after you, too.

### 3.2. An example of bad code commenting
Let's look at the following example.  
  
```java
// Start the services  
StartServices();  
```
  
Can you tell why this is bad? It simply states what the code already tells you based on the function / method name that was provided. When writing code comments you need to tell the reader of your code <b>Why</b> this code is doing what it does.  
It is also important to format your comments with <b>Readability</b> in mind. This means that you should;
* Tab them appropriately
* Make them brief
* Keep them relevant
* Use them liberally, but not to excess
* Leave spaces where necessary

## 3.3. Clarification Comments
These style of comments are intended for anyone, this can include yourself if you need to leave a project for a while and want to return later. You might also need these comments if your plan is to refactor, maintain or extend upon your existing codebase.  
There are times when — after a lot of thought and experimentation — it turns out that the seemingly naive solution to a problem is actually the best. In those scenarios it is almost inevitable that some other coder will come around thinking they are much smarter than you are and start messing with the code, only to discover that your way was the best way all along.  
  
Here is a good example  
```java
/* don't use the global isFinite() because it returns true for null values*/ Number.isFinite(value) 
```
  
### 3.4. Bad practices not to follow
There will be times when you'll find coding frustrating and might decide to vent your frustrations in the form of comments in your source code that you might accidentally forget to remove (this has happened to me, but thankfully I saw it before my submission). 
An example is  
```java
/* This code sucks, you know it and I know it.  Move on and call me an idiot later. */  
```
  
It may seem funny at the time, or might help you vent your frustrations, but don't do this. 

## 4. Coding Standards
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

### 4.1. Effective Coding Standards
Why exactly do we need coding standards, and what benefits do they offer?  
There is a direct relationship between <b>coding standards</b> and <b>software maintainability</b>. There is no doubt that <b>source code</b> that adheres to good standards is simply more readable and reflects harmony, but there is another side to coding standards which is sometimes overlooked at the expense of too much attention to the aesthetics.
  
Effective coding technqiues focus more on techniques that highlight problems and make bugs stand-out and visible to everyone.
  
Effective coding standards are;  
* short, simple and concise
  * they do not attempt to cover and processify everything
  * leave plenty of room for developers to exercsie their own creativity
* strike the right balance between formatting issues and issues that 'make the wrong code look wrong'
* black and white instead of vague suggestions or recommendations

#### 4.1.1. Coding Standards based on Language
Coding Standards differ between programming languages, links to these standards are provided for you below;  
* [Java](../codingstandards/java.md)

* [C Programming](../codingstandards/c.md) which covers:
  * C#
  * C++
  
* [Web Development](../codingstandards/webdev.md) which covers:
  * Node.js
  * PHP
  
### 4.2. Automate the Process
Once you have developed effectvie coding standards and are maming use of them, you should learn how to <b>automate the process</b>.  
Automating the process of checking source code's adherence to standards, it will allow you to save a lot of time in perr reviews and alow you to catch everything that humans might miss. 
  
If you are starting fresh and looking for coding standards, start by searching online for well-known standards for your programming language. Start small and remember that there is more than one right way to style the code. There might already be a standard available from the language creators. Your coding standards should check for both style issues and design problems. Once you have standards, make sure that they are adopted by the team and automated. However, code that deviates from standards shouldn’t be considered erroneous. It should simply be marked as out of compliance and deviations must be reviewed and fixed.

There is an abundance of style checking tools available for all major programming languages.
The example image below shows the Checkstyle scan that is used for Java projects.  
![](https://codeahoy.com/img/checkstyle-intellij.png)



## 5. References 
[Elegant Themes: How to comment your code like a pro](https://www.elegantthemes.com/blog/wordpress/how-to-comment-your-code-like-a-pro-best-practices-and-good-habits)  
[Submain: 4 reasons we need code comments](https://blog.submain.com/4-reasons-need-code-comments/)  
[Freecodecamp: Putting comments in code: The good, the bad, and the ugly](https://www.freecodecamp.org/news/code-comments-the-good-the-bad-and-the-ugly-be9cc65fbf83/)  
[Codeahoy: Effective Coding Standards](https://codeahoy.com/2016/05/22/effective-coding-standards/#:~:text=Coding%20standards%20are%20a%20set,big%20software%20companies%20have%20them.)
