# WC Java Style Guide

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
public static final int THE_FIELD = 1;
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
