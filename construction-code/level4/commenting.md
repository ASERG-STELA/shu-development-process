# Code Commenting - Level 4

## 1. Table of Contents

- [Code Commenting - Level 4](#code-commenting---level-4)
  - [1. Table of Contents](#1-table-of-contents)
  - [2. Introduction](#2-introduction)
  - [3. Header Block Documentation](#3-header-block-documentation)
  - [4. In-line Documentation](#4-in-line-documentation)
  - [5. Clarification Comments](#5-clarification-comments)
  - [6. Bad practices not to follow](#6-bad-practices-not-to-follow)
  - [7. References](#7-references)

## 2. Introduction

The question most people ask is "Why do we need code comments anyway?"

Code commenting is a very simple way to let someone know what your code is meant to be doing, even if their background in code is weak. Good comments make for easy reading and easy understanding for those who are perhaps not as tech savvy as yourself. Code commenting also explains why you wrote something. At Level 4, the expectation is that you will write basis code comments as a minimum measure to help a reader understand your code.

These are meant for anyone who is likely to consume your source code, but they aren't likely to read through it in any real depth. Code comments are also used by different tools for automatic generation of documentation.
If you are building something such as a **Library** or **Framework** that you would expect other developers to be using, then you need some form of documentation alongside that, with which comments help the basis of understanding.

It is worth mentioning that several organisations, and open source projects, define specific code style guidelines that must be adhered to.
If they don’t, however, or you are on your own, keeping this stuff in mind will not only make your job easier in the future, but will also help out anyone who comes after you, too.

## 3. Header Block Documentation

This style of code commenting is useful in source code for simple explanations of what to expect in that file. For example,  

```javascript
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

This is a good example of good use of header block commenting. Do not, however, provide a comprehensive list of dates on which the file was altered and new versions have been published. This sort of thing is recorded by your version control system (e.g., git), so you don't need to worry about that aspect when considering version control within your comments.

## 4. In-line Documentation

This is the most common type of source code commenting. Do not do line by line code comments, unless you are doing API documentation, as this makes your code unreadable and is just too excessive. You want to tell the reader what your code does, but they don't need a running commentary all the time. You want to guide them through, not pull them through the grass as you are doing so.

Example provided via the Lodash.js documentation found [here](https://lodash.com/).

```javascript
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
  
Each comment tells someone reading the code what each line is doing. Any questions they have are answered as they are reading through.

Another very common strategy is to document what a function does, such as the following example:

```javascript
// Checks to see if there's a comment. If so, returns a thank you message.  
function sourceCodeComment () {  
  var comment = document.getElementbyID("Code Comment").value;   
  if (comment != null && comment != '') {   
        return console.log("Thank you for your comment.")  
}  
```

It might seem like this style of commenting is not necessary when the variable names make it obvious what the code is doing, but you need to maintain the mindset, where not everyone who might read the code necessarily has the same level as you, and so these easy to understand code comments that are situated above the code sections are worthwhile to consider including into your own work.

## 5. Clarification Comments

These style of comments are intended for anyone, this can include yourself if you need to leave a project for a while and want to return later. You might also need these comments if your plan is to refactor, maintain or extend upon your existing codebase.  
There are times when - after a lot of thought and experimentation - it turns out that the seemingly naive solution to a problem is actually the best. In those scenarios it is almost inevitable that some other coder will come around thinking they are much smarter than you are and start messing with the code, only to discover that your way was the best way all along.  

Here is a good example,

```java
/* don't use the global isFinite() because it returns true for null values*/
Number.isFinite(value)  
```

## 6. Bad practices not to follow

There will be times when you'll find coding frustrating and might decide to vent your frustrations in the form of comments in your source code that you might accidentally forget to remove (this has happened to me, but thankfully I saw it before my submission).

An example is  

```java
/* This code sucks, you know it and I know it.  Move on and call me an idiot later. */  
```

It may seem funny at the time, or might help you vent your frustrations, but don't do this.

Another example of code commenting is presented below

```java
// Start the services  
StartServices();  
```

Can you tell why this is bad? It simply states what the code already tells you based on the function/method name that was provided. When writing code comments you need to tell the reader of your code **Why** this code is doing what it does when it is not possible or easy to infer this by the code itselft.

It is also important to format your comments with **readability** in mind. This means that you should;

- Tab them appropriately
- Make them brief
- Keep them relevant
- Use them liberally, but not to excess
- Leave spaces where necessary

## 7. References

- [Elegant Themes: How to comment your code like a pro](https://www.elegantthemes.com/blog/wordpress/how-to-comment-your-code-like-a-pro-best-practices-and-good-habits)  
- [Submain: 4 reasons we need code comments](https://blog.submain.com/4-reasons-need-code-comments/)  
- [Freecodecamp: Putting comments in code: The good, the bad, and the ugly](https://www.freecodecamp.org/news/code-comments-the-good-the-bad-and-the-ugly-be9cc65fbf83/)
