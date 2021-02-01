# Level 4 Delivery Guidelines

## 1. Abstract

This document will serve to provide Level 4 students with the knowledge of one of the most important aspects of the software development lifecycle. The Delivery of the product.
At Level 4, you will only need to have the knowledge of how to run and compile your code, to ensure that it is functioning correctly at the point of delivery (submission deadline).
I will walk through some basic examples of how to compile your code in Visual Studio 2019 and IntelliJ IDEA, as well as some basic information on what the compiler actually does.

## 2. Table of Contents

- [1. Abstract](#1-abstract)
- [2. Table of Contents](#2-table-of-contents)
- [3. What Is A Compiler](#3-what-is-a-compiler)
  - [3.1. How Does A Compiler Work](#31-how-does-a-compiler-work)
- [4. How To Compile In Visual Studio 2019](#4-how-to-compile-in-visual-studio-2019)
- [5. How To Compile In IntelliJ IDEA](#5-how-to-compile-in-intellij-idea) 
- [6. References](#6-references)
  
## 3. What Is A Compiler

A Compiler, is a piece of computer software that translates (compiles) source code written in a high-level language (e.g., C++) into a set of machine-language instructions that can be understood by a digital computer’s CPU. 
They are very large programs, with error-checking and other abilities. Some compilers translate high-level language into an intermediate assembly language, which is then translated (assembled) into machine code by an assembly program or assembler. This is the case with C++. Other compilers generate machine language directly
(reference [1]). Compilers are built in to many IDE's, such as Visual Studio 2019 and IntelliJ IDEA. 

## 3.1. How Does A Compiler Work

As previosuly mentioned, the compilation process converts high-level source code to a low-level machine code that can be executed by the target machine.
The compilation process consists of several phases:

1. Lexical analysis
2. Syntax analysis
3. Semantic analysis
4. Intermediate code generation
5. Optimisation
6. Code generation

### Lexical Analysis

The first stage of the compilation process is lexical analysis. During this phase, the compiler splits source code into fragments called lexemes. A lexeme is an abstract unit of a specific language’s lexical system. In the C++ code:
String greeting = "hello";

There are 5 lexemes:

1. String
2. greeting
3. =
4. “hello”
5. ;

After splitting code into lexemes, a sequence of tokens is created.

### Syntax Analysis

In this phase, the compiler uses a sequence of tokens generated in the first stage, to check the grammatic structure of the source code and its syntax correctness. Meanwhile, any syntax errors result in a compilation error, and the compiler informs the developer about them. It essencially does 2 things:

1. It checks source code for any syntax error.
2. It generates an abstract syntax tree that the next stage uses.

### Sementic Analysis

In this stage, the compiler uses an abstract syntax tree to detect any semantic errors, for example:

* Assigning the wrong type to a variable
* Declaring variables with the same name in the same scope
* Using an undeclared variable
* Using language’s keyword as a variable name

### Intermediate Code Generation

During the compilation process, a compiler can generate one or more intermediate code forms.
Intermediate code has 2 forms of representation:

1. High-Level – similar to the source language. In this form, we can easily boost the performance of source code. However, it’s less preferred for enhancing the performance of the target machine.
2. Low-Level – close to the machine’s machine code. It’s preferred for making machine-related optimizations.

### Optimisation

In the optimisation phase, the compiler uses a variety of ways to enhance the efficiency of the code. This can be done by:

* Function inlining – replacing the function call with its body.
* Dead code elimination – compiler gets rid of code that is never executed, or if executed, its returned result isn’t used.
* Loop fusion – executing, in one loop, operations from the adjacent loops that have the same iteration conditions.
* Instruction combining – instructions realising similar operations are combined into one; for example, x = x + 10; x = x – 7; could be replaced with x = x + 3;

### Code Generation

Finally, the compiler converts the optimised intermediate code to the machine code dedicated to the target machine. The final code should have the same meaning as source code and be efficient in terms of memory and CPU resource usage.

These are based from reference [2].

## 4. How To Compile In Visual Studio 2019

I will now walkthrough how to compile your code in Visual Studio 2019. You will need to do this each time you want to run your programs, likely to be written in C# at this level. It is very simple to do.
I have prepared a simple 'Hello World' application, written in C# to use as an example program for a console application, as well as an example of a windows forms application (the process is the same).

Lets start witht the **console application:**

![Simple hello world console application](/deployment-delivery/images/c_sharp_console_app.PNG)

This is just a simple 'Hello World' application that we will compile. To compile, simply click the green arrow at the top of the IDE next to your project name or press F10:

![Compile hello world console application](/deployment-delivery/images/compile_c_sharp.PNG)

Your program should now be running and a console window should appear:

![Compiled hello world console application](/deployment-delivery/images/compiled_c_sharp.PNG)

If you have any errors in your program that the compiler has spotted, this window should appear. Always click **No** as you do not want to run the program anyway as it will run the last build without the recent changes you have made: 

![Build errors in project](/deployment-delivery/images/build_errors.PNG)

You can see details on the errors in your program in the error list window at the bottom of the IDE:

![Viewing errors](/deployment-delivery/images/error_list.PNG)

It is a similar process with **Windows Forms** applications, here is a windows forms application I had laying around on my machine:

![Windows Forms application](/deployment-delivery/images/c_sharp_forms_app.PNG)

To compile, we once again go to the top of the IDE and click the green arrow next to **Start** or F10:

![Compile Windows Forms application](/deployment-delivery/images/compile_forms.PNG)

The program will now compile and open a forms application:

![Compiled Windows Forms application](/deployment-delivery/images/compiled_forms.PNG)

Any errors during compilation will once again bring up the build errors pop up, and you can view these errors in the **Error list**.

## 5. How To Compile In IntelliJ IDEA.

Compiling in IntelliJ IDEA is very similar to that of Visual Studio 2019. You will be using IntelliJ for Java development.
I have prepared a similar 'Hello World' application to that written in C++, this time, written in Java, so that I can use the IntelliJ compiler:

![Example Java application](/deployment-delivery/images/java_app.PNG)

To compile, there are 2 ways. Click the green arrow on either:

The **nav bar:**

![Compile Java application on navbar](/deployment-delivery/images/run_navbar.PNG)

The **line of code** where the function starts:

![Compile Java application on line of code](/deployment-delivery/images/run_code_line.PNG)

If the compilation is successful, you should get an output in the console window:

![Successful compile of Java application](/deployment-delivery/images/compiled_java.PNG)

If the compilation is not successful and there are build errors, the application will not compile and the errors can be shown in the **build output**:

![Build errors in Java application](/deployment-delivery/images/java_error.PNG)

## 6. References 

[1] Britannica. Compiler. <https://www.britannica.com/technology/compiler>.

[2] Baeldung. How Compilers Work. <https://www.baeldung.com/cs/how-compilers-work>.
