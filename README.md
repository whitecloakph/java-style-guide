# WC Java Style Guide

## Inspiration

This style-guide is somewhat of a mash-up between the existing Java language style guides. The language guidance is drawn from the following:

+ [The Official raywenderlich.com Java Style Guide](https://github.com/raywenderlich/java-style-guide)
+ [Google Java Style Guide](https://google-styleguide.googlecode.com/svn/trunk/javaguide.html)

## Table of Contents

- [Naming](#naming)
  + [Packages](#packages)
  + [Classes & Interfaces](#classes--interfaces)
  + [Methods](#methods)
  + [Fields](#fields)
  + [Variables & Parameters](#variables--parameters)
  + [Misc](#misc)
- [Declarations](#declarations)
  + [Access Level Modifiers](#access-level-modifiers)
  + [Fields & Variables](#fields--variables)
  + [Classes](#classes)
  + [Enum Classes](#enum-classes)
- [Spacing](#spacing)
  + [Indentation](#indentation)
  + [Line Length](#line-length)
  + [Vertical Spacing](#vertical-spacing)
- [Getters & Setters](#getters--setters)
- [Brace Style](#brace-style)
- [Switch Statements](#switch-statements)
- [Annotations](#annotations)
- [Testing](#spacing)
  + [Test Classes](#test-classes)
  + [Test Methods](#test-methods)
- [Language](#language)

## Naming

On the whole, naming should follow Java standards.

### Packages

Package names are all __lower-case__, multiple words concatenated together, without hypens or underscores:

__Preferred__:

```java
com.whitecloak.mypackage
```

__Not Preferred__:

```java
com.whitecloak.my_package
```

### Classes & Interfaces

Written in __UpperCamelCase__. For example `MyClass`. 

### Methods

Written in __lowerCamelCase__. For example `myMethod`.

### Fields

Written in __lowerCamelCase__.

Static fields should be written in __uppercase__, with an underscore separating
words:

```java
public static final int MY_FIELD = 1;
```

### Variables & Parameters

Written in __lowerCamelCase__.

Single character values to be avoided except for temporary looping variables.

### Misc

In code, acronyms should be treated as words. For example:

__Preferred:__

```java
XmlHttpRequest
String url
findPostById
```

__Not Preferred__:

```java
XMLHTTPRequest
String URL
findPostByID
```

## Declarations

### Access Level Modifiers

Access level modifiers should be explicitly defined for classes, methods and
member variables.

### Fields & Variables

Prefer single declaration per line.

__Preferred:__

```java
String username;
String twitterHandle;
```

__Not Preferred:__

```java
String username, twitterHandle;
```

### Classes

Exactly one class per source file, although inner classes are encouraged where
scoping appropriate.

### Enum Classes

Enum classes should be avoided where possible, due to a large memory overhead.
Static constants are preferred. See http://developer.android.com/training/articles/memory.html#Overhead
for further details.

Enum classes without methods may be formatted without line-breaks, as follows:

```java
private enum CompassDirection { EAST, NORTH, WEST, SOUTH }
```

## Spacing

### Indentation

Indentation is using spaces - never tabs.

#### Blocks

Indentation for blocks uses 4 spaces

__Preferred:__

```java
for (int i = 0; i < 10; i++) {
    Log.i(TAG, "index=" + i);
}
```

__Not Preferred:__

```java
for (int i = 0; i < 10; i++) {
    Log.i(TAG, "index=" + i);
}
```

#### Line Wraps

Indentation for line wraps should use 8 spaces.

__Preferred:__

```java
CoolUiWidget widget =
        someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

__Not Preferred:__

```java
CoolUiWidget widget =
     omeIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

### Line Length

Lines should be no longer than 100 characters long.

### Vertical Spacing

There should be exactly one blank line between methods to aid in visual clarity 
and organization. Whitespace within methods should separate functionality, but 
having too many sections in a method often means you should refactor into
several methods.

## Getters & Setters

For external access to fields in classes, getters and setters are preferred to
direct access of the fields. Fields should rarely be `public`.

However, it is encouraged to use the field directly when accessing internally
(i.e. from inside the class). This is a performance optimization recommended
by Google: http://developer.android.com/training/articles/perf-tips.html#GettersSetters

## Brace Style

Only trailing closing-braces are awarded their own line. All others appear the
same line as preceding code:

__Preferred:__

```java
class MyClass {
    void doSomething() {
        if (someTest) {
            // ...
        } else {
            // ...
        }
    }
}
```

__Not Preferred:__

```java
class MyClass
{
    void doSomething()
    {
        if (someTest)
        {
        // ...
        }
        else
        {
        // ...
        }
  }
}
```

Conditional statements are always required to be enclosed with braces,
irrespective of the number of lines required.

__Preferred:__

```java
if (someTest) {
    doSomething();
}
if (someTest) { doSomethingElse(); }
```

__Not Preferred:__

```java
if (someTest)
    doSomething();
if (someTest) doSomethingElse();
```

## Switch Statements

Switch statements fall-through by default, but this can be unintuitive. If you
require this behavior, comment it.

Alway include the `default` case.

__Preferred:__

```java
switch (anInput) {
    case 1:
        doSomethingForCaseOne();
        // fall through
    case 2:
        doSomethingForCaseOneOrTwo();
        break;
    case 3:
        doSomethingForCaseOneOrThree();
        break;
    default:
        break;
}
```

__Not Preferred:__

```java
switch (anInput) {
    case 1:
        doSomethingForCaseOne();
    case 2:
        doSomethingForCaseOneOrTwo();
        break;
    case 3:
        doSomethingForCaseOneOrThree();
        break;
}
```

## Annotations

Standard annotations should be used - in particular `@Override`. This should
appear the line before the function declaration.

__Preferred:__

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
}
```

__Not Preferred:__

```java
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
}
```

## Testing

### Test Classes

Test classes are named starting with the name of the class they are testing, and ending with Test. For example, `MyClassTest` or `MyUtilTest`.

### Test Methods

Underscores may appear in JUnit test method names to separate logical components of the name, with each component written in __lowerCamelCase__. 

Test methods should follow the pattern __methodUnderTest_shouldExpectedBehavior_whenStateUnderTest__.

Example:

```java
@Test
public void method_shouldThrowException_whenAgeLessThan18() { }

@Test
public void method_shouldFailToWithdrawMoney_forInvalidAccount() { }

@Test
public void method_shouldFailToAdmit_ifMandatoryFieldsAreMissing() { }
```

## Language

Use US English spelling.

__Preferred:__

```java
String color = "red";
```

__Not Preferred:__

```java
String colour = "red";
```
