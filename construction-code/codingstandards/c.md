# C Programming Coding Standards
Coding Standards (Coding Conventions) serve the following purposes:
* They create a consistent look to the code, so that readers can focus on content, not layout
* They enable readers to understand the code more quickly by making assumptions based on the previous experience
* They facilitate copying, changing, and maintaining the code
* They demonstrate C# and C++ best practices

## 1. Table of Contents
- [2. C#](#2-c)
   - [2.1. Naming Conventions](#21-naming-conventions)
      - [2.1.1. Casing](#211-casing)
      - [2.1.2. The `using` directive](#212-the-using-directive)
      - [2.1.3. Using `static` type](#213-using-static-type)
      - [2.1.4. Example that does not include the `using` directive](#214-example-that-does-not-include-the-using-directive)
   - [2.2. Layout Conventions](#22-layout-conventions)
   - [2.3. Commenting Conventions](#23-commenting-conventions)
   - [2.4. Language Guidelines](#24-language-guidelines)
      - [2.4.1. String Data Type](#241-string-data-type)
      - [2.4.2 Implicitly Typed Local Variables](#242-implicitly-typed-local-variables)
      - [2.4.3. Unsigned Data Type](#243-unsigned-data-type)
      - [2.4.4. Arrays](#244-arrays)
      - [2.4.5. Delegates](#245-delegates)
      - [2.4.6. Try-Catch and Using statements in Exception Handling](#246-try-catch-and-using-statements-in-exception-handling)
      - [2.4.7. && and || Operators](#247-and-and-or-operators)
      - [2.4.8. New Operator](#248-new-operator)
      - [2.4.9. Event Handling](#249-event-handling)
      - [2.4.10. `Static` Members](#2410-static-members)
      - [2.4.11. LINQ Queries](#2411-linq-queries)
- [3. C++](#3-c)
- [4. References](#4-references)


## 2. C#

### 2.1. Naming Conventions
#### 2.1.1. Casing
Every language has it's own casing standards, many organisations or teams also may have their own standards.  
There are 3 casings generally accepted by C# standards.
* `PascalCase` - This is for class names, file names, namespace names, ALL method names, and public member names.
* `camelCase` - This is used for member names that are not publically accessible.
* `UPPER_CASE` - You might also think of this as "upper snake case", this is only used for constants.  
  
There are some exceptions though, which are known as "Pascal_snake_case" or "snake_case" which are sometimes used in "Unit Testing". A descriptive method name such as <b>Should_return_2_when_adding_1_and_1</b> is much easier to read, which is why it is generally preferred to use snake casing when doing unit tests.  
<b>Event Handlers</b> (a type of method) often include an underscore to seperate the target from the action. A classic example is <b>Page_Load</b> in ASP.NET, but this is *not* Pascal_snake_case. E.g. in <b>InputControl_Init</b>, the <b>InputControl</b> is the target andf <b>Init</b> is the event.  
  
When casing your `private` member variables, it is best practice to use camelCase for this, as this always refers to the class scope. An example is provided below.
```csharp
public class Person
{
    private string firstName;

    public void SayHello()
    {
        Console.WriteLine($"Hello, {this.firstName}!");
    }
}
```
Here the <b>Person</b> class has a private member variable <b>firstName</b>, which is only accessible from inside the class. The <b>SayHello</b> method is available to any consumer of this class. It accesses the <b>firstName</b> variable through `this` which refers to the *current* instance of the class <b>Person</b>.  
Another common approach is to prepend the member name with an underscore(_). Here is the same example again using this convention.
```csharp
public class Person
{
    private string _firstName;

    public void SayHello(string firstName = null) 
    { 
        Console.WriteLine($"Hello, {firstName ?? _firstName}!");
    }
}
```
Using the underscore allows us to omit `this` when we use the variable. In the example, the method parameter has the same base name as a class member. Therefore, if we use underscore in all member variables, we can avoid accidentally taking the wrong variable.

#### 2.1.2. The `using` directive
The `using` directive has 3 uses:
* To allow the use of types in a namespace so that they do not have to qualify the use of a type in that namespace:
```csharp
using System.Text;
```
* To allow you to access `static` members and nested types of a type without having to qualify the access with the type name
```csharp
using static System.Math;
```
* To create an alias for a namespace or a type. This is called a *using alias directive* 
```csharp
using Project = PC.MyCompany.Project;
```
The `using` keyword is also used to create *using statements*, which help to ensure that [IDisposable](https://docs.microsoft.com/en-us/dotnet/api/system.idisposable?view=net-5.0) objects such as files and fonts are handled correctly.

#### 2.1.3. Using `static` type
You can access `static` members of a type without having to qualify the access with the type name:
```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

#### 2.1.4. Example that does not include the `using` directive
In short examples that do not include `using` directives, use namespace qualifications. If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace. Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.

```csharp
var currentPerformanceCounterCategory = new System.Diagnostics.
    PerformanceCounterCategory();
```
You do not have to change the names of objects that were created by using Visual Studio designer tools to make them fit other guidelines.


### 2.2. Layout Conventions
Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.
* Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).
* Write only one statement per line.
* Write only one declaration per line.
* If continuation lines are not indented automatically, indent them one tab stop (four spaces).
* Add at least one blank line between method definitions and property definitions.
* Use parentheses to make clauses in an expression apparent, as shown in the following code.
```csharp
if ((val1 > val2) && (val1 > val3))
{
    // Take appropriate action.
}
```

### 2.3. Commenting Conventions
* Place the comment on a separate line, not at the end of a line of code.
* Begin comment text with an uppercase letter.
* End comment text with a period.
* Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.
* Do not create formatted blocks of asterisks around comments.

```csharp
// The following declaration creates a query. It does not run
// the query.
```

### 2.4. Language Guidelines
The following sections describe practices that the C# team follows to prepare code examples and samples.

#### 2.4.1. String Data Type
Use String interpolation to concatenate short strings, as shown below:
```csharp
string displayName = $"{nameList[n].LastName}, {nameList[n].FirstName}";
```
To append strings in loops, especially when you are working with large amounts of text, use a `StringBuilder` object:
```csharp
var phrase = "lalalalalalalalalalalalalalalalalalalalalalalalalalalalalala";
var manyPhrases = new StringBuilder();
for (var i = 0; i < 10000; i++)
{
    manyPhrases.Append(phrase);
}
//Console.WriteLine("tra" + manyPhrases);
```

#### 2.4.2. Implicitly Typed Local Variables
Local variables can be declared without giving an explicit type. The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement. The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET class library.
```csharp
// i is compiled as an int
var i = 5;

// s is compiled as a string
var s = "Hello";

// a is compiled as int[]
var a = new[] { 0, 1, 2 };

// expr is compiled as IEnumerable<Customer>
// or perhaps IQueryable<Customer>
var expr =
    from c in customers
    where c.City == "London"
    select c;

// anon is compiled as an anonymous type
var anon = new { Name = "Terry", Age = 34 };

// list is compiled as List<int>
var list = new List<int>();
```
More information on Implicit typing [here](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables).  
Use implicit typing for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.
```csharp
// When the type of a variable is clear from the context, use var
// in the declaration.
var var1 = "This is clearly a string.";
var var2 = 27;
```
Do not use `var` when the type is not apparant from the right side of the assignment.
```csharp
// When the type of a variable is not clear from the context, use an
// explicit type. You generally don't assume the type clear from a method name.
// A variable type is considered clear if it's a new operator or an explicit cast.
int var3 = Convert.ToInt32(Console.ReadLine());
int var4 = ExampleClass.ResultSoFar();
```
Do not rely on the variable name to specify the type of the variable, it might not be correct.
```csharp
// Naming the following variable inputInt is misleading.
// It is a string.
var inputInt = Console.ReadLine();
Console.WriteLine(inputInt);
```
You should avoid the use of `var` in place of `dynamic`. The `dynamic` type indicates that use of the variable and references to its members bypass compile-time type checking. Instead, these operations are resolved at run time. The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM). More information on this can be found [here](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/reference-types).  
Use implicit typing to determine the type of the loop variable in `for` loops. An example is shwon below.
```csharp
var phrase = "lalalalalalalalalalalalalalalalalalalalalalalalalalalalalala";
var manyPhrases = new StringBuilder();
for (var i = 0; i < 10000; i++)
{
    manyPhrases.Append(phrase);
}
//Console.WriteLine("tra" + manyPhrases);
```
Do not use implicit typing to determine the type of the loop variable in `foreach` loops. An example is shown below.
```csharp
foreach (char ch in laugh)
{
    if (ch == 'h')
        Console.Write("H");
    else
        Console.Write(ch);
}
Console.WriteLine();
```
#### 2.4.3 Unsigned Data Type
You should use `int` rather than unsigned types. The use of `int` is common throughout C#, and it is easier to interact with other libraries when youn use `int`.

#### 2.4.4. Arrays
Use the concise syntax when you initialise arrays on the declaration line.
```csharp
// Preferred syntax. Note that you cannot use var here instead of string[].
string[] vowels1 = { "a", "e", "i", "o", "u" };

// If you use explicit instantiation, you can use var.
var vowels2 = new string[] { "a", "e", "i", "o", "u" };

// If you specify an array size, you must initialize the elements one at a time.
var vowels3 = new string[5];
vowels3[0] = "a";
vowels3[1] = "e";
// And so on.
```

#### 2.4.5. Delegates
Use the concise syntax to create instances of a delegate type.
```csharp
// First, in class Program, define the delegate type and a method that
// has a matching signature.

// Define the type.
public delegate void Del(string message);

// Define a method that has a matching signature.
public static void DelMethod(string str)
{
    Console.WriteLine("DelMethod argument: {0}", str);
}
```
```csharp
// In the Main method, create an instance of Del.

// Preferred: Create an instance of Del by using condensed syntax.
Del exampleDel2 = DelMethod;

// The following declaration uses the full syntax.
Del exampleDel1 = new Del(DelMethod);
```

#### 2.4.6. Try-Catch and Using statements in Exception Handling
Use a `try-catch` statement for most exception handling. Exception handling is responding to exceptions when a computer program runs. An exception occurs when an unexpected event happens that requires special processing. Exception handling attempts to gracefully handle these situations so that a program (or worse, an entire system) does not crash.
```csharp
static string GetValueFromArray(string[] array, int index)
{
    try
    {
        return array[index];
    }
    catch (System.IndexOutOfRangeException ex)
    {
        Console.WriteLine("Index is out of range: {0}", index);
        throw;
    }
}
```
You can simplify your code by using the C# `using` statement. If you have a `try-finally` statement in which the only code is the `finally` block is a call to the "Dispose" method, use a `using` statement instead. IDisposable is an interface used to get rid of unmanaged resources.
```csharp
// This try-finally statement only calls Dispose in the finally block.
Font font1 = new Font("Arial", 10.0f);
try
{
    byte charset = font1.GdiCharSet;
}
finally
{
    if (font1 != null)
    {
        ((IDisposable)font1).Dispose();
    }
}

// You can do the same thing with a using statement.
using (Font font2 = new Font("Arial", 10.0f))
{
    byte charset = font2.GdiCharSet;
}
```

#### 2.4.7. And and Or Operators
* And == `&&`
* Or == `||`  
To avoid exceptions and increase performance by skipping unnecessary comparisons, use `&&` instead of `&` and `||` instead of `|` when you perform comparisons, as shown in the following example.
```csharp
Console.Write("Enter a dividend: ");
var dividend = Convert.ToInt32(Console.ReadLine());

Console.Write("Enter a divisor: ");
var divisor = Convert.ToInt32(Console.ReadLine());

// If the divisor is 0, the second clause in the following condition
// causes a run-time error. The && operator short circuits when the
// first expression is false. That is, it does not evaluate the
// second expression. The & operator evaluates both, and causes
// a run-time error when divisor is 0.
if ((divisor != 0) && (dividend / divisor > 0))
{
    Console.WriteLine("Quotient: {0}", dividend / divisor);
}
else
{
    Console.WriteLine("Attempted division by 0 ends up here.");
}
```

#### 2.4.8. New Operator
Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.
```csharp
var instance1 = new ExampleClass();
```
Which is equivalent to.
```csharp
ExampleClass instance2 = new ExampleClass();
```
You can use object initialisers to simplify the process of object creation.
```csharp
// Object initializer.
var instance3 = new ExampleClass { Name = "Desktop", ID = 37414,
    Location = "Redmond", Age = 2.3 };

// Default constructor and assignment statements.
var instance4 = new ExampleClass();
instance4.Name = "Desktop";
instance4.ID = 37414;
instance4.Location = "Redmond";
instance4.Age = 2.3;
```

#### 2.4.9. Event Handling
If you are defining an event handler that you do not need to remove later, use a `lambda` expression.
```csharp
public Form2()
{
    // You can use a lambda expression to define an event handler.
    this.Click += (s, e) =>
        {
            MessageBox.Show(
                ((MouseEventArgs)e).Location.ToString());
        };
}
```
```csharp
// Using a lambda expression shortens the following traditional definition.
public Form1()
{
    this.Click += new EventHandler(Form1_Click);
}

void Form1_Click(object sender, EventArgs e)
{
    MessageBox.Show(((MouseEventArgs)e).Location.ToString());
}
```

#### 2.4.10 `Static` Members
Use the static modifier to declare a `static` member, which belongs to the type itself rather than to a specific object. The `static` modifier can be used to declare `static` classes. In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors. The `static` modifier can't be used with indexers or finalizers.  
Call `static` members by using the class name: `ClassName.StaticMember`. This practice makes code more readable by making static access clear. Do not qualify a static member defined in a base class with the name of a derived class. While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.
More information can be found [here](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/static).  

#### 2.4.11. LINQ Queries
LINQ (Language Integrated Query) is uniform query syntax in C# and VB.NET to retrieve data from different sources and formats. It is integrated in C# or VB, thereby eliminating the mismatch between programming languages and databases, as well as providing a single querying interface for different types of data sources.  
Use meaningful names for query variables, such as.
```csharp
var seattleCustomers = from customer in customers
                       where customer.City == "Seattle"
                       select customer.Name;
```
Use aliases to make sure that property names of anonymous types are correctly capitalised, using `Pascal` casing. (See [Naming Conventions](#21-naming-conventions)).
```csharp
var localDistributors =
    from customer in customers
    join distributor in distributors on customer.City equals distributor.City
    select new { Customer = customer, Distributor = distributor };
```
Rename properties when the property names in the result would be ambiguous. for example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of the customer and `ID` is the ID of the distributor.
```csharp
var localDistributors2 =
    from customer in customers
    join distributor in distributors on customer.City equals distributor.City
    select new { CustomerName = customer.Name, DistributorID = distributor.ID };
```
Use implicit typing in the declaration of query variables and range variables.
```csharp
var seattleCustomers = from customer in customers
                       where customer.City == "Seattle"
                       select customer.Name;
```
Align query clauses under the `from` clause, as shown in the examples above.  
Use `where` clases before other query clauses to ensure that later clauses operate on the reduced, filtered set of data.
```csharp
var seattleCustomers2 = from customer in customers
                        where customer.City == "Seattle"
                        orderby customer.Name
                        select customer;
```
Use multiple `from` clauses instead of a `join` clause to access inner collections. For example, a collection of `Student` objects might each contain a collection of test scores. When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.
```csharp
// Use a compound from to access the inner sequence within each element.
var scoreQuery = from student in students
                 from score in student.Scores
                 where score > 90
                 select new { Last = student.LastName, score };
```

## 3. C++
The C++ Guidelines document provided by Bjarne Stroustrup and Herb Sutter is a fantastic tool to use for your needs, this has been linked in the references titled "C++ Core Guidelines". Important information for the document may be added here at a later date but for now please refer to this document for assistance on writing more efficient and maintainable C++ Code.



## 4. References
[Submain 9 C# Coding Standards Developers Need To Get Started](https://blog.submain.com/coding-standards-c-developers-need/)  
[Microsoft C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions#naming-conventions)  
[Microsoft Secure Coding Guidelines](https://docs.microsoft.com/en-us/dotnet/standard/security/secure-coding-guidelines)  
[C++ Core Guidelines](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)
