# Web Development Coding Standards <!-- omit in toc -->

## 1. Table of Contents

- [1. Table of Contents](#1-table-of-contents)
- [2. PHP](#2-php)
  - [2.1. Coding Practices](#21-coding-practices)
    - [2.1.1. Files](#211-files)
    - [2.1.2. Lines](#212-lines)
    - [2.1.3. Indenting](#213-indenting)
    - [2.1.4. Keywords and Types](#214-keywords-and-types)
    - [2.1.5. Declare Statements, Namespace and Import Statements](#215-declare-statements-namespace-and-import-statements)
    - [2.1.6. Classes, Properties and Methods](#216-classes-properties-and-methods)
      - [2.1.6.1. Extends and Implements](#2161-extends-and-implements)
      - [2.1.6.2. Traits](#2162-traits)
      - [2.1.6.3. Properties and Constants](#2163-properties-and-constants)
      - [2.1.6.4. Methods and Functions](#2164-methods-and-functions)
      - [2.1.6.5. Method and Function Arguments](#2165-method-and-function-arguments)
      - [2.1.6.6. `abstract`, `final` and `static`](#2166-abstract-final-and-static)
      - [2.1.6.7. Method and Function Calls](#2167-method-and-function-calls)
    - [2.1.7. Control Structures](#217-control-structures)
      - [2.1.7.1. `If`, `elseif`, `else`](#2171-if-elseif-else)
      - [2.1.7.2. Switch and Case](#2172-switch-and-case)
      - [2.1.7.3. While and Do While](#2173-while-and-do-while)
      - [2.1.7.4. `for`, `foreach`, `try`, `catch` and `finally`](#2174-for-foreach-try-catch-and-finally)
    - [2.1.8. Operators](#218-operators)
    - [2.1.9. Closures](#219-closures)
    - [2.1.10. Anonymous Classes](#2110-anonymous-classes)
- [3. Node.js](#3-nodejs)
- [4. References](#4-references)

## 2. PHP

PHP is a vast language that allows coders of all levels the ability to produce code not only quickly, but efficiently. However, while advancing through the language, we often forget the basics that we first learnt, or are still currently learning, (or overlooked) in favour of shortcuts and/or bad habits. Work found here comes from the **PSR-12: Extended Coding Style** documentation.

### 2.1. Coding Practices

To help combat this common issue, this section is aimed at reminding coders of the basic coding practices within PHP.

#### 2.1.1. Files

All PHP files MUST use the Unix LF (linefeed) line ending only.  
All PHP files MUST end with a non-blank line, terminated with a single LF.  
The closing `?>` tag must be omitted from files containing only PHP.

#### 2.1.2. Lines

There MUST NOT be a hard limit on line length.  
The soft limit on line length MUST be 120 characters.  
Lines SHOULD NOT be longer than 80 characters; lines longer than that SHOULD be split into multiple subsequent lines of no more than 80 characters each.  
There MUST NOT be trailing whitespace at the end of lines.  
Blank lines MAY be added to improve readability and to indicate related blocks of code except where explicitly forbidden.  
There MUST NOT be more than one statement per line.

#### 2.1.3. Indenting

Code MUST use an indent of 4 spaces for each indent level, and MUST NOT use tabs for indenting.

#### 2.1.4. Keywords and Types

All PHP [keywords](https://www.php.net/manual/en/reserved.keywords.php) and [types](http://php.net/manual/en/reserved.other-reserved-words.php) MUST be in lower case.  
Any new types and keywords added to future PHP versions MUST be in lower case.  
Short form of type keywords MUST be used i.e. `bool` instead of `boolean`, `int` instead of `integer` etc.

#### 2.1.5. Declare Statements, Namespace and Import Statements

The header of a PHP file may consist of a number of different blocks. If present, each of the blocks below MUST be separated by a single blank line, and MUST NOT contain a blank line. Each block MUST be in the order listed below, although blocks that are not relevant may be omitted.

1 - Opening `<?php` tag.  
2 - File-level docblock.  
3 - One or more declare statements.  
4 - The namespace declaration of the file.  
5 - One or more class-based `use` import statements.  
6 - One or more function-based `use` import statements.  
7 - One or more constant-based `use` import statements.  
8 - The remainder of the code in the file.  

When a file contains a mix of HTML and PHP, any of the above sections may still be used. If so, they MUST be present at the top of the file, even if the remainder of the code consists of a closing PHP tag and then a mixture of HTML and PHP.

When the opening <?php tag is on the first line of the file, it MUST be on its own line with no other statements unless it is a file containing markup outside of PHP opening and closing tags.

Import statements MUST never begin with a leading backslash as they must always be fully qualified.

The following example illustrates a complete list of all blocks:

```php
<?php

/**
 * This file contains an example of coding styles.
 */

declare(strict_types=1);

namespace Vendor\Package;

use Vendor\Package\{ClassA as A, ClassB, ClassC as C};
use Vendor\Package\SomeNamespace\ClassD as D;
use Vendor\Package\AnotherNamespace\ClassE as E;

use function Vendor\Package\{functionA, functionB, functionC};
use function Another\Vendor\functionD;

use const Vendor\Package\{CONSTANT_A, CONSTANT_B, CONSTANT_C};
use const Another\Vendor\CONSTANT_D;

/**
 * FooBar is an example class.
 */
class FooBar
{
    // ... additional PHP code ...
}
```

Compound namespaces with a depth of more than two MUST NOT be used. Therefore the following is the maximum compounding depth.

```php
<?php

use Vendor\Package\SomeNamespace\{
    SubnamespaceOne\ClassA,
    SubnamespaceOne\ClassB,
    SubnamespaceTwo\ClassY,
    ClassZ,
};
```

And the following would not be allowed'

```php
<?php

use Vendor\Package\SomeNamespace\{
    SubnamespaceOne\AnotherNamespace\ClassA,
    SubnamespaceOne\ClassB,
    ClassZ,
};
```

Delcaring strict types in files containing markup outside PHP opening and closing tags, the declaration MUST be the first line of the file and include an opening PHP tag, the strict types declaration and closing tage, shown below.

```php
<?php declare(strict_types=1) ?>
<html>
<body>
    <?php
        // ... additional PHP code ...
    ?>
</body>
</html>
```

Dedclare statements MUST contain no spaces and MUST be exactly `declare(strict_types=1` (with an optional semi-colon terminator).  
You can declare block statements, but they MUST be defined as shown below.

```php
declare(ticks=1) {
    // some code
}
```

#### 2.1.6. Classes, Properties and Methods

When you are instantiating a new class, you need to make sure you add your parenthesis `()` even if you don't have any arguments, like so.

```php
new Foo();
```

##### 2.1.6.1. Extends and Implements

The `extends` and `implements` keywords need to be declared on the same line as the class name. Your opening brace needs to be on its own line, the closing brace for the also needs to be on the next line after the body. Opening braces need to be on their own line and MUST NOT be preceded or followed by a blank line. Closing braces MUST be on their own line and MUST NOT be preceded by a blank line.

```php
<?php

namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // constants, properties, methods
}
```

You can split your `interfaces` and `extends` across mutiple lines, where each subsequent line is indented once, but when doing this, the first item in the list MUST be on the next line, and there has to be only one interface on each line, shown below.

```php
<?php

namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    // constants, properties, methods
}
```

##### 2.1.6.2. Traits

The `use` keyword used inside the classes to implement traits MUST be declared on the next line after the opening brace. Each individual trait that is imported into a class has to be included one-per-line and each inclusion MUST have its own `use` import statement.

```php
<?php

namespace Vendor\Package;

use Vendor\Package\FirstTrait;
use Vendor\Package\SecondTrait;
use Vendor\Package\ThirdTrait;

class ClassName
{
    use FirstTrait;
    use SecondTrait;
    use ThirdTrait;
}
```

If your class has nothing after the `use` statement, then the class closing brace should be on the next line. Otherwise, there MUST be a blank space after the `use` import statement.

```php
<?php

namespace Vendor\Package;

use Vendor\Package\FirstTrait;

class ClassName
{
    use FirstTrait;

    private $property;
}
```

##### 2.1.6.3. Properties and Constants

Visibility MUST be declared on all properties and all constants if your project minimum version supports PHP 7.1 or later. The `var` keyword should not be used to declare a property. Don't declare more than one property per statement, and make sure property names are not prefixed with a single underscore which indicates `protected` and `private` visibility. An underscore prefix has no meaning otherwise. Make sure you have spaces between type declaration and property names.

```php
<?php

namespace Vendor\Package;

class ClassName
{
    public $foo = null;
    public static int $bar = 0;
}
```

##### 2.1.6.4. Methods and Functions

- Method
  - Method names must not be prefixed with a single underscore to indicate `protected` or `private` visibility.
  - Underscore prefix explicitly has no meaning.
  - Method names must not be declared with a space after the name.
  - The opening and closing braces should eb on thier own lines for increased visibility.
  - No spaces before or after the parenthesis.

```php
<?php

namespace Vendor\Package;

class ClassName
{
    public function fooBarBaz($arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
```

- Function
  - Function names must not be declared with a space after the name.
  - The opening and closing braces should eb on thier own lines for increased visibility.
  - No spaces before or after the parenthesis.

```php
<?php

function fooBarBaz($arg1, &$arg2, $arg3 = [])
{
    // function body
}
```

##### 2.1.6.5. Method and Function Arguments

In the argument list, there shouldn't be a space before each comma, and there needs to be one space after each comma. Method and function arguments with default values must go att the end of the argument list.

```php
<?php

namespace Vendor\Package;

class ClassName
{
    public function foo(int $arg1, &$arg2, $arg3 = [])
    {
        // method body
    }
}
```

Argument lists may be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list must be on the next line, and there must be only one argument per line.  When the argument list is split across multiple lines, the closing parenthesis and opening brace must be placed together on their own line with one space between them.

```php
<?php

namespace Vendor\Package;

class ClassName
{
    public function aVeryLongMethodName(
        ClassTypeHint $arg1,
        &$arg2,
        array $arg3 = []
    ) {
        // method body
    }
}
```

When you have a return type declaration present, there must be one space after the colon followed by the type declaration. The colon and declaration must be on the same line as the argument closing parenthesis with no spaces between the two characters.

```php
<?php

declare(strict_types=1);

namespace Vendor\Package;

class ReturnTypeVariations
{
    public function functionName(int $arg1, $arg2): string
    {
        return 'foo';
    }

    public function anotherFunction(
        string $foo,
        string $bar,
        int $baz
    ): string {
        return 'foo';
    }
}
```

In nullable type delcarations, there must not be a space between the question mark and the type.

```php
<?php

declare(strict_types=1);

namespace Vendor\Package;

class ReturnTypeVariations
{
    public function functionName(?string $arg1, ?int &$arg2): ?string
    {
        return 'foo';
    }
}
```

When using the reference operator `&` before an argument, there must not be a space after it, like in the previous example. There musn't be a space between the variadic three dot operator and the argument name.

```php
public function process(string $algorithm, ...$parts)
{
    // processing
}
```

When combining the reference operator and the variadic three dot operator, there mustn't be any space between the two of them.

```php
public function process(string $algorithm, &...$parts)
{
    // processing
}
```

##### 2.1.6.6. `abstract`, `final` and `static`

When present the `static` and `final` declarations must precede the visibility declaration. When present, the `static` declaration must come after the visibility declaration.

```php
<?php

namespace Vendor\Package;

abstract class ClassName
{
    protected static $foo;

    abstract protected function zim();

    final public static function bar()
    {
        // method body
    }
}
```

##### 2.1.6.7. Method and Function Calls

When making a method or function call, there must not be a space between the method or function name and the opening parenthesis, there must not be a space after the opening parenthesis, and there must not be a space before each comma, and there must not a space after each comma.

```php
<?php

bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);
```

Arguments lists **may** be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list must be only only one argument per line. A single argument being split across multiple lines (as might be the case with an anonymous function or array) does not constitute splitting the argument list itself.

```php
<?php

$foo->bar(
    $longArgument,
    $longerArgument,
    $muchLongerArgument
);
<?php

somefunction($foo, $bar, [
  // ...
], $baz);

$app->get('/hello/{name}', function ($name) use ($app) {
    return 'Hello ' . $app->escape($name);
});
```

#### 2.1.7. Control Structures

The general style rules for control structures are as follows:

- There must be one space after the control structure keyword
- There must not be a space after the opneing parenthesis
- There must not be a space before the closing parenthesis
- There must be one space between the closing parenthesis and the opening brace
- The structure body be indented once
- The body must be on the next line after the opening brace#
- The closing brace must be on the next line after the body  
The body of each structure must be enclosed by braces. This standardises how the structures look and reduces the likelihood of introducing errors as new line get added to the body.

##### 2.1.7.1. `If`, `elseif`, `else`

An `if` structure looks like the following. Note the placement of parentheses, spaces, and braces; and that `else` and `elseif` are on the same line as the closing brace from the earlier body.

```php
<?php

if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body;
}
```

The keyword `elseif` should be used instead of `else if` so that all control keywords look like single words. You can split your expressions in parenthesis across multiple lines, where each subsequent line is indented a least once. When doing so, the first condition must be on the next line. Your closing parenthesis and opening brace must be placed together on their own line with one space between them. `Boolean` operators between conditions must always be at the beginning or at the end of the line, not a mix of both.

```php
<?php

if (
    $expr1
    && $expr2
) {
    // if body
} elseif (
    $expr3
    && $expr4
) {
    // elseif body
}
```

##### 2.1.7.2. Switch and Case

A `switch` structure looks like the following. It is important to note the placement of parenthesis, spaces, and braces. The `case` statement must be indented once from `switch`, and the `break` keyword (or other terminating keywords) must be indented at the same level as the `case` body. There must not be a comment such as `// no break` when fall-through is intentional in a non-empty `case` body.

```php
<?php

switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Third case, return instead of break';
        return;
    default:
        echo 'Default case';
        break;
}
```

Expressions in parenthesis may be split across multiple lines, wherr each sunbsequent line in indented at least once. When doing so, the first condition must be on the next line. The closing parenthesis and opening brace must be placed together on their own line with one space between them. `Boolean` operators between conditions must always be at the beginning or at the end of the line, not a mix of both.

```php
<?php

switch (
    $expr1
    && $expr2
) {
    // structure body
}
```

##### 2.1.7.3. While and Do While

A `while` statement looks like the following;

```php
<?php

while ($expr) {
    // structure body
}
```

Expressions inside the parenthesis may be split across multiple lines, where each subsequent line is indented at least once. When doing so, the first condition must be on the next line. The closing parenthesis and opening brace must be placed together on their own line with one space between them. `Boolean` operators between conditions must always be at the beginning or at the end of the line, not a mix.

```php
<?php

while (
    $expr1
    && $expr2
) {
    // structure body
}
```

A `Do While` is similar, and looks like so;

```php
<?php

do {
    // structure body;
} while ($expr);
```

Expressions found in parenthesis may be split across multiple lines, where each subsequent line is indented at least once. The first condition must be on the next line. `Boolean` operators between conditions must always be at the beginning or at the end of the line, not a mix of both.

```php
<?php

do {
    // structure body;
} while (
    $expr1
    && $expr2
);
```

##### 2.1.7.4. `for`, `foreach`, `try`, `catch` and `finally`

A `for` statement looks like the following;

```php
<?php

for ($i = 0; $i < 10; $i++) {
    // for body
}
```

We can split the expressions along mutiple lines, where each subsequent line is indented at least once. When you do this, make sure that the first expression goes on the next line. The closing parenthesis and opening brace must be placed together on their own line with one space in between.  
The `foreach` is very similar in the way we write it, as seen below;

```php
<?php

foreach ($iterable as $key => $value) {
    // foreach body
}
```

A `try-catch-finally` block is used to catch errors. Remember no matter what, the `finally` block will always execute. It looks like the following;

```php
<?php

try {
    // try body
} catch (FirstThrowableType $e) {
    // catch body
} catch (OtherThrowableType | AnotherThrowableType $e) {
    // catch body
} finally {
    // finally body
}
```

#### 2.1.8. Operators

There are three operators that you would use;

- Unary  
The increment/decrement operators must not have any space between the perator and operand.

```php
$i++;
++$j;
```

Type casting operators must not have any space within the parentheses:

```php
$intValue = (int) $input;
```

- Binary  
All binary **arithmetic, comparison, assignment, bitwise, logical, string** and **type** operators must be preceded by and followed by at least one space.

```php
if ($a === $b) {
    $foo = $bar ?? $a ?? $b;
} elseif ($a > $b) {
    $foo = $a + $b * $c;
}
```

- Ternary  
The conditional operator, also known simply as the ternary operator, must be preceded and followed by at least one space around both the `?` and `:` characters.

```php
$variable = $foo ? 'foo' : 'bar';
```

When the middle operand of the conditional operator is omitted, the operator must follow the same style rules as other binary **comparison** operators.

```php
$variable = $foo ?: 'bar';
```

#### 2.1.9. Closures

Closures need to be declared with a space after the `function` keyword, and a space before and after the `use` keyword. The opening brace must go on the same line, and the closing must go on the next line following the body. Make sure that there is no space after the opening parenthesis of the argument or variable list, and there must not be a space before the closing parenthesis of the argument or variable list.  
In the argument and variable list, there must not be a space before each comma, and there must be one space before each comma, and one space after each comma. Closure arguments with default values must go at the end of the argument list. If a retunr type is present, make sure it follows the same rules as with normal functions and methods. If the `use` keyword is present, the colon must follow the `use` list closing parentheses with no spaces between the two characters.  
A closure list example is provided here;

```php
<?php

$closureWithArgs = function ($arg1, $arg2) {
    // body
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // body
};

$closureWithArgsVarsAndReturn = function ($arg1, $arg2) use ($var1, $var2): bool {
    // body
};
```

You can split lists across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list must be on the next line, and there must be only one argument or variable per line. When the ending list is split acorss multiple lines, the closing parenthesis and opening brace must be placed together on their own line with one space between them.  
The following are examples of closures with and without argument lists and variable lists split across multiple lines.

```php
<?php

$longArgs_noVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) {
   // body
};

$noArgs_longVars = function () use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // body
};

$longArgs_longVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // body
};

$longArgs_shortVars = function (
    $longArgument,
    $longerArgument,
    $muchLongerArgument
) use ($var1) {
   // body
};

$shortArgs_longVars = function ($arg) use (
    $longVar1,
    $longerVar2,
    $muchLongerVar3
) {
   // body
};
```

Note the formatting rules also apply when the closure is used directly in a function or method calls as an argument.

```php
<?php

$foo->bar(
    $arg1,
    function ($arg2) use ($var1) {
        // body
    },
    $arg3
);
```

#### 2.1.10. Anonymous Classes

Anonymous classes are the classes which are defined without any name. In PHP 7, we can define an anonymous class using keyword 'new class'. This class can replace a full class definition. These classes must follow the same guidelines and principles as closures in the above section.

```php
<?php

$instance = new class {};
```

The opening brace may be on the same line as the `class` keyword so long as the list of `implements` interfaces does not wrap. If the list of interfaces wraps the brace then must be placed on the line immediately following the last interface.

```php
<?php

// Brace on the same line
$instance = new class extends \Foo implements \HandleableInterface {
    // Class content
};

// Brace on the next line
$instance = new class extends \Foo implements
    \ArrayAccess,
    \Countable,
    \Serializable
{
    // Class content
};
```

## 3. Node.js

This section will be added later.

## 4. References

[PHP The Right Way](https://phptherightway.com/)  
[PHP PSR-12: Extended Coding Style](https://www.php-fig.org/psr/psr-12/)
[PHP Documentation in English](https://www.php.net/manual/en/)  
[PHP Design Patterns](https://designpatternsphp.readthedocs.io/)  
