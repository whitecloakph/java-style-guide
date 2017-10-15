# WC Java Style Guide

## Inspiration

This style-guide is somewhat of a mash-up between the existing Java language style guides. The language guidance is drawn from the following:

+ [The Official raywenderlich.com Java Style Guide](https://github.com/raywenderlich/java-style-guide)
+ [Android contributors style guide](https://source.android.com/source/code-style.html)
+ [Google Java Style Guide](https://google-styleguide.googlecode.com/svn/trunk/javaguide.html)

## Table of Contents

- [Naming](#naming)
  + [Packages](#packages)
  + [Classes & Interfaces](#classes--interfaces)
  + [Methods](#methods)
  + [Fields](#fields)
  + [Variables & Parameters](#variables--parameters)
  + [Misc](#misc)

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
XMLHTTPRequest
String URL
findPostByID
```

__Not Preferred__:

```java
XmlHttpRequest
String url
findPostById
```
