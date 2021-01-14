# Java Programming Coding Standards

## 1. Table of Contents
- [2. Code Conventions](#2-code-conventions)
   - [2.1. File Names](#21-file-names)
   - [2.2. File Organisation](#22-file-organisation)
   - [2.3. Indentation](#23-indentation)
   - [2.4. Comments](#24-comments)
   - [2.5. Declarations](#25-declarations)
   - [2.6. Statements](#26-statements)
   - [2.7. White Space](#27-white-space)
   - [2.8. Naming Conventions](#28-naming-conventions)
- [3. References](#3-references)

## 2. Code Conventions
Code conventions are important to programmers for a number of reasons;
* 80% of the lifetime cost of a piece of software goes to maintenance
* Hardly any software is maintained for it's whole life by the original author
* Code conventions improve the readability of the software, allowing engineers to understand new code more quickly and thoroughly
* If you ship your source code as a product, you need to make sure it is well packaged and clean as any other product you create

### 2.1. File Names
Java uses the following file suffixes;
* Java Source - `.java`
* Java bytecode - `.class`

There are also some common file names used which are;
* `GNUmakefile` - the preferred name for makefiles. We use `gnumake` to build our software
* `README` - the preferred name for the file that summarises the contents of a particular directory

### 2.2. File Organisation
#### Java Source Files
Each Java source file contains a single public class or interface. When private classes and interfaces are associated with a 
<b>public class</b>, you can put them in the same source as the public class. The public class should be the first interface in the file.  
Java source files have the foilowing ordering:
* Beginning comments
* Package and Import Statements
* Class and interface declarations  

#### Beginning Comments
All source files should begin with a c-style comment that lists the class name, version information, date, and copyright notice:
```java
/*
 * Classname
 * 
 * Version information
 *
 * Date
 * 
 * Copyright notice
 */
 ```
 
#### Package and Import Statements
The first non-comment line of most Java source files is a `package` statement. After that `import` statements can follow. For example: 
```java
package java.awt;

import java.awt.peer.CanvasPeer;
```

#### Class and Interface Declarations
The following table describes the parts of a class or interface declaration, in the order that they should appear.

|   	|   Part of Class / Interface Declaration	|   Notes	|   
|---	| ---                                    	|---	    |
|  1 	|   Class / Interface documentation comment (`/**...*/`) | Go to "Comments / Documentation Comments" for more information as to what should be here |  
|  2 	|  `class` or `interface` statement 	    |        	|   	
|  3 	|  Class/interface implementation comment (`/*...*/`), if necessary  | This comment should contain any class-wide or interface-wide information that wasn't appropriate for the class/interface documentation comment. |   	
|  4 	|  Class (`static`) variables  	| First the `public` class variables, then the `protected`, then package level (no access modifier), and then the `private`.    	|   	
|  5 	|  Instance variables  | First `public`, then `protected`,. then package level (no acces modifier), and then `private`.       	|   	
|  6 	|  Constructors   |        	|   	
|  7 	|  Methods 	 | These methods should be grouped by functionality rather than by scope or accessibility. For example, a private class method can be in between two public instance methods. The goal is to make reading and understanding the code easier.      	|   	

### 2.3. Indentation
The normal convention is to use <b>four</b> spaces as the unit for Indentation. The exact construction of the indentation (spaces vs tabs) is not specified. Tbas must be set exactly every <b>eight</b> spaces (not four).  

#### Line Length
Avoid lines longer than 80 characters, since they're not handled well by many terminals and tools.  
Note: Examples for use in documentation should have a shorter line length-generally no more than 70 characters.  

#### Wrapping Lines
When your expression won't fit on a single line,  break it according to these general principles:
* Break after a comma
* Break before an operator
* Prefer higher-level breaks to lower-level breaks
* Align the new line with the beginning of the expression at the same level on the previous line
* If the above rules lead to confusing code or to code that's squished uiup against the right margin, just indent 8 spaces instead

Here are some examples provided below:  

Here are some examples of breaking method calls:
```java
someMethod(longExpression1, longExpression2, longExpression3, 
        longExpression4, longExpression5);
 
var = someMethod1(longExpression1,
                someMethod2(longExpression2,
                        longExpression3));
```
Following are two examples of breaking an arithmetic expression. The first is preferred, since the break occurs outside the parenthesized expression, which is at a higher level.

```java
longName1 = longName2 * (longName3 + longName4 - longName5)
           + 4 * longname6; // PREFER

longName1 = longName2 * (longName3 + longName4
                       - longName5) + 4 * longname6; // AVOID
```
Following are two examples of indenting method declarations. The first is the conventional case. The second would shift the second and third lines to the far right if it used conventional indentation, so instead it indents only 8 spaces.
```java
//CONVENTIONAL INDENTATION
someMethod(int anArg, Object anotherArg, String yetAnotherArg,
           Object andStillAnother) {
    ...
}

//INDENT 8 SPACES TO AVOID VERY DEEP INDENTS
private static synchronized horkingLongMethodName(int anArg,
        Object anotherArg, String yetAnotherArg,
        Object andStillAnother) {
    ...
}
```
Line wrapping for if statements should generally use the 8-space rule, since conventional (4 space) indentation makes seeing the body difficult. For example:
```java
//DON'T USE THIS INDENTATION
if ((condition1 && condition2)
    || (condition3 && condition4)
    ||!(condition5 && condition6)) { //BAD WRAPS
    doSomethingAboutIt();            //MAKE THIS LINE EASY TO MISS
} 

//USE THIS INDENTATION INSTEAD
if ((condition1 && condition2)
        || (condition3 && condition4)
        ||!(condition5 && condition6)) {
    doSomethingAboutIt();
} 

//OR USE THIS
if ((condition1 && condition2) || (condition3 && condition4)
        ||!(condition5 && condition6)) {
    doSomethingAboutIt();
}
```
Here are three acceptable ways to format ternary expressions:
```java
alpha = (aLongBooleanExpression) ? beta : gamma;  

alpha = (aLongBooleanExpression) ? beta
                                 : gamma;  

alpha = (aLongBooleanExpression)
        ? beta 
        : gamma;
```


### 2.4. Comments
This section will show some examples of commenting. This has already been discussed in the [Commenting](../level5/commenting.md) file.
#### Block Comments
A block comment should be preceded by a blank line to set it apart from the rest of the code.
```java
/*
 * Here is a block comment.
 */
```
Indented block comment
```java
/*-
 * Here is a block comment with some very special
 * formatting that I want indent(1) to ignore.
 *
 *    one
 *        two
 *            three
 */
```

#### Single-Line Comments
```java
if (condition) {

    /* Handle the condition. */
    ...
}
```

#### Trailing Comments
```java
if (a == 2) {
    return TRUE;            /* special case */
} else {
    return isPrime(a);      /* works only for odd a */
}
```

#### End-of-line Comments
```java
if (foo > 1) {

    // Do a double-flip.
    ...
}
else {
    return false;          // Explain why here.
}
//if (bar > 1) {
//
//    // Do a triple-flip.
//    ...
//}
//else {
//    return false;
//}
```

#### Documentation Comments
```java
/**
 * The Example class provides ...
 */
public class Example { ...
```


### 2.5. Declarations
One kind of Java statement is a declaration statement, which is used to declare a variable by specifying its data type and name. ... Instead of defining a value over and over, a variable that has a value attached to it can be defined.
#### Number Per Line
```java
int level; // indentation level
int size;  // size of table
```
You can use spaces as shown above, or you can use tabs like so:
```java
int     level;          // indentation level
int     size;            // size of table
Object  currentEntry;    // currently selected table entry
```

#### Initialisation
Try to initialize local variables where they're declared. The only reason not to initialize a variable where it's declared is if the initial value depends on some computation occurring first.

#### Placement
Put declarations only at the beginning of blocks. (A block is any code surrounded by curly braces "{" and "}".) Don't wait to declare variables until their first use; it can confuse the unwary programmer and hamper code portability within the scope.

```java
void myMethod() {
    int int1 = 0;         // beginning of method block

    if (condition) {
        int int2 = 0;     // beginning of "if" block
        ...
    }
}
</blockquote>
```
An exception to this is within `for` loops, which in Java can be declared in the `for` statement:
```java
for (int i = 0; i < maxLoops; i++) { ... }
</blockquote>
```

DO NOT declare the same variable within the loop however:
```java
int count;
...
myMethod() {
    if (condition) {
        int count = 0;     // AVOID!
        ...
    }
    ...
}
```

#### Class and Interface Declarations
When coding Java classes and interfaces, the following formatting rules should be followed:
* No space between a method name and the parenthesis "(" startings its parameter list
* Open brace "{" appears at the end of the same line as the declaration statement
* Closing brace "}" starts a line by itself indented to match its corresponding opening statement, except when it is a `null` statement the "}" should appear immediately after the "{".

```java
class Sample extends Object {
    int ivar1;
    int ivar2;

    Sample(int i, int j) {
        ivar1 = i;
        ivar2 = j;
    }

    int emptyMethod() {}

    ...
}
```
* Methods are separated by a blank line

### 2.6. Statements
Java statements are instructions that tell the programming language what to do, like declaration and string statements. Basic statements define variables and initiate Java methods or start the execution of blocks of other statements. Assignment statements assign values to variables.

#### Simple Statements
Each line contains at most one statement:
```java
argv++;         // Correct
argc--;         // Correct  
argv++; argc--; // AVOID!
```

#### Compound Statements
Compound statements are statements that contain lists of statements enclosed in braces "`{ statements }`". See the following sections for examples.

* The enclosed statements should be indented one more level than the compound statement.
* The opening brace should be at the end of the line that begins the compound statement; the closing brace should begin a line and be indented to the beginning of the compound statement.
* Braces are used around all statements, even single statements, when they are part of a control structure, such as an `if-else` or `for` statement. This makes it easier to add statements without accidentally introducing bugs due to forgetting to add braces.

#### Return Statements
A `return` statement with a value should not use parenthesis unless they make the return value more obvious in some way:
```java
return;

return myDisk.size();

return (size ? size : defaultSize);
```

#### If, If-Else, If-Else-If Else Statements
The `if-else` class statement should have the following form:
```java
if (condition) {
    statements;
}

if (condition) {
    statements;
} else {
    statements;
}

if (condition) {
    statements;
} else if (condition) {
    statements;
} else {
    statements;
}
```
If statements alwyas use braces, avoid the following error-prone form:
```java
if (condition) //AVOID! THIS OMITS THE BRACES {}!
    statement;
```

#### For Statements
A `for` statement should have the following form:
```java
for (initialization; condition; update) {
    statements;
}
```
An empty `for` statement (one in which all the work is done in the initialisation, condition, and update clauses) should have the following form:
```java
for (initialization; condition; update);
```

#### While Statements
A `while` statement should have the following form:
```java
while (condition) {
    statements;
}
```
An empty `while` staement should have the following form:
```java
while (condition);
```

#### Do-While Statements
A `do-while` statement shopuld have the following form:
```java
do {
    statements;
} while (condition);
```

#### Switch Statements
A `switch` statement should have the following form:
```java
switch (condition) {
case ABC:
    statements;
    /* falls through */
case DEF:
    statements;
    break;
case XYZ:
    statements;
    break;
default:
    statements;
    break;
}
```
Every time a case falls through (doesn't include a `break` statement), add a comment where the `break` statement would normally be. This is shown in the preceding code example with the `/* falls through */` comment.

Every `switch` statement should include a default case. The `break` in the default case is redundant, but it prevents a fall-through error if later another case is added.

#### Try-Catch Statements
A `try-catch` statement shouyld have the following forrm:
```java
try {
    statements;
} catch (ExceptionClass e) {
     statements;
}
```
A `try-catch` statement may also be followed by `finally`, which executes regardless of whether or not the `try` block has completed successfully.
```java
try {
    statements;
} catch (ExceptionClass e) {
    statements;
} finally {
    statements;
}
```

### 2.7. White Space
#### Blank Lines
We use blank lines in code to improve readability, by setting off sections of code that are logically related. Two blank lines should always be used in the following circumstances:
* Between sections of a source file
* Between class and interface definitions

One blank line should always be used in the following circumstances
* Between methods
* Between the local variables in a method and its first statement
* Before a block or single-line comment
* Between logical sections inside a method to improve readability

#### Blank Spaces
Blank spaces should be used in the following circumstances:
* A keyword followed by a parenthesis should be seperated by a space:
```java
while (true) {
           ...
       }
```
Note that a blank space should not be used between a method name and its opening parenthesis. This helps to distinguish keywords from method calls.

* A blank space should appear after commas in argument lists.
* All binary operators except . should be separated from their operands by spaces. Blank spaces should never separate unary operators such as unary minus, increment ("++"), and decrement ("--") from their operands. 
```java
a += c + d;
    a = (a + b) / (c * d);
    
    while (d++ = s++) {
        n++;
    }
    printSize("size is " + foo + "\n");
```
* The expressions in a `for` statement should be seperated by blank spaces
* Casts should be followed by a blank space:
```java
myMethod((byte) aNum, (Object) x);
myMethod((int) (cp + 5), ((int) (i + 3)) 
                                  + 1);
```

### 2.8. Naming Conventions
Naming conventions make programs more understandable by making them easier to read. They can also give information about the function of the identifier-for example, whether it's a constant, package, or class-which can be helpful in understanding the code.

| Identifier Type | Rules for Naming | Examples |   
|---	            |---             	 |---    	|
| Packages        | The prefix of a unique package name is always written in all-lowercase ASCII letters and should be one of the top-level domain names, currently com, edu, gov, mil, net, org, or one of the English two-letter codes identifying countries as specified in ISO Standard 3166, 1981.  Subsequent components of the package name vary according to an organization's own internal naming conventions. Such conventions might specify that certain directory name components be division, department, project, machine, or login names.  | com.sun.eng   com.apple.quicktime.v2  edu.cmu.cs.bovik.cheese |
| Classes         | Class names should be nouns, in mixed case with the first letter of each internal word capitalized. Try to keep your class names simple and descriptive. Use whole words-avoid acronyms and abbreviations (unless the abbreviation is much more widely used than the long form, such as URL or HTML). | class Raster; <br> class ImageSprite;|
| Interfaces      | Interface names should be capitalised like class names. | interface RasterDelegate; |
| Methods         | Methods should be verbs, in mixed case with the first letter lowercase, with the first letter of each internal word capitalised.  | getBackground();  runFast();         |
| Variables       |  Except for variables, all instance, class, and class constants are in mixed case with a lowercase first letter. Internal words start with capital letters. Variable names should not start with underscore _ or dollar sign $ characters, even though both are allowed.Variable names should be short yet meaningful. The choice of a variable name should be mnemonic- that is, designed to indicate to the casual observer the intent of its use. One-character variable names should be avoided except for temporary "throwaway" variables. Common names for temporary variables are `i`, `j`, `k`, `m`, and `n` for integers; `c`, `d`, and `e` for characters. | int i; <br> float myWidth; <br> char c;   |
| Constants    | The names of variables declared class constants and of ANSI constants should be all uppercase with words separated by underscores ("_"). (ANSI constants should be avoided, for ease of debugging.)	 | static final int MIN_WIDTH = 4; <br> static final int MAX_WIDTH = 999; <br>  static final int GET_THE_CPU = 1; |


## 3. References
* [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
* [Oracle Sun Coding Standard](https://www.oracle.com/java/technologies/javase/codeconventions-contents.html)
* [Android Coding Standard (Mobile Development)](https://source.android.com/setup/contribute/code-style)
