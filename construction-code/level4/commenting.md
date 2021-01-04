# Code Commenting - Level 4

## 1. Table of Contents
- [Code Commenting - Level 4](#code-commenting---level-4)
  - [1. Table of Contents](#1-table-of-contents)
  - [2. Introduction](#2-introduction)
  - [3. Documentation Comments](#3-documentation-comments)
    - [3.1. In-line Documentation - Source Code](#31-in-line-documentation---source-code)
    - [3.2. Header Block Documentation - Source Code](#32-header-block-documentation---source-code)
    - [3.3. Organisational styling mention](#33-organisational-styling-mention)
  - [4. Clarification Comments](#4-clarification-comments)
  - [5. Bad practices not to follow](#5-bad-practices-not-to-follow)
  - [4. References](#4-references)

## 2. Introduction

The question most people ask is "Why do we need code comments anyway?"

Code commenting is a very simple way to let someone know what your code is meant to be doing, even if their background in code is weak. Good comments make for easy reading and easy understanding for those who are perhaps not as tech savvy as yourself. Code commenting also explains why you wrote something. At Level 4, the expectation is that you will write basis code comments as a minimum measure to help a reader understand your code.

## 3. Documentation Comments

Code commenting are meant for anyone who is likely to consume your source code, but they aren't likely to read through it in any real depth. If you are building something such as a **Library** or **Framework** that you would expect other developers to be using, then you need some form of documentation alongside that, with which comments help the basis of understanding.

### 3.1. In-line Documentation - Source Code

This is the most common type of source code commenting. Do not do line by line code comments, unless you are doing API documentation, as this makes your code unreadable and is just too excessive. You want to tell the reader what your code does, but they don't need a running commentary all the time. You want to guide them through, not pull them through the grass as you are doing so.

**e.g. provided via the Lodash.js documentation found [here](https://lodash.com/)**

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

**e.g. Source Code commenting**

```java
//checks to see if there's a comment. If so, returns a thank you message.
function sourceCodeComment () {  
  var comment = document.getElementbyID("Code Comment").value;   
  if (comment != null && comment != '') {   
        return console.log("Thank you for your comment.")  
}  
```

It might seem like this style of commenting is not necessary when the variable names make it obvious what the code is doing, but you need to maintain the mindset, where not everyone who might read the code necessarily has the same level as you, and so these easy to understand code comments that are situated above the code sections are worthwhile to consider including into your own work.

### 3.2. Header Block Documentation - Source Code

This style of code commenting is useful in source code for simple explanations of what to expect in that file. For e.g.,

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

### 3.3. Organisational styling mention

If you’re in the trenches day in and day out, writing code and pushing to GitHub, your organization may have a style guide for comments they want you to follow. If they don’t, however, or you are on your own, keeping this stuff in mind will not only make your job easier in the future, but will also help out anyone who comes after you, too.

## 4. Clarification Comments

These style of comments are intended for anyone, this can include yourself if you need to leave a project for a while and want to return later. You might also need these comments if your plan is to refactor, maintain or extend upon your existing codebase.  
There are times when - after a lot of thought and experimentation - it turns out that the seemingly naive solution to a problem is actually the best. In those scenarios it is almost inevitable that some other coder will come around thinking they are much smarter than you are and start messing with the code, only to discover that your way was the best way all along.  
  
Here is a good example  
```java
/* don't use the global isFinite() because it returns true for null values*/ Number.isFinite(value)  
```

## 5. Bad practices not to follow

Let's look at the following example.  
```java
// Start the services  
StartServices();  
```

Can you tell why this is bad? It simply states what the code already tells you based on the function/method name that was provided. When writing code comments you need to tell the reader of your code **Why** this code is doing what it does.  
It is also important to format your comments with **Readability** in mind. This means that you should;

- Tab them appropriately
- Make them brief
- Keep them relevant
- Use them liberally, but not to excess
- Leave spaces where necessary

There will be times when you'll find coding frustrating and might decide to vent your frustrations in the form of comments in your source code that you might accidentally forget to remove (this has happened to me, but thankfully I saw it before my submission).

An example is  
```java
/* This code sucks, you know it and I know it.  Move on and call me an idiot later. */  
```
  
It may seem funny at the time, or might help you vent your frustrations, but don't do this.

## 4. References 
[Elegant Themes: How to comment your code like a pro](https://www.elegantthemes.com/blog/wordpress/how-to-comment-your-code-like-a-pro-best-practices-and-good-habits)  
[Submain: 4 reasons we need code comments](https://blog.submain.com/4-reasons-need-code-comments/)  
[Freecodecamp: Putting comments in code: The good, the bad, and the ugly](https://www.freecodecamp.org/news/code-comments-the-good-the-bad-and-the-ugly-be9cc65fbf83/)
