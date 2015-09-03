# `NSLog()`ing

## Objectives

1. Recognize the usefulness of `NSLog()`
2. Distinguish `NSLog()` as a function.
3. Use the string literal to define a text value.
4. Use string formatting with `NSLog()`.

## The Developer's Multi-tool

The `NSLog()` function that you just used to print out "Hello, World!" in the previous lab is a developer's tool that sends a string to the debug console.

We call it a developer's tool because in mobile development, the end user of the application only ever interacts with the program through views, and never interacts with the debugger or the terminal; however `NSLog()` has a diverse range of uses during development, and like what a #2 Philips-head screwdriver is to tinkering, `NSLog()` has universal applications that makes it belong in any and every toolkit. As a developer, there will never be a time when you **won't** benefit from having `NSLog()` at the ready.

### Funky Function

As a "function" (and not a method), `NSLog()` is unusual within Objective-C programming. Being a *function*, it is something that the system itself does. Most operations in Objective-C are performed by *methods*, which we'll discuss soon. For now, recognize that `NSLog()` is more a part of the C-language that Objective-C is built on top of rather than of Objective-C itself.

The simplest way to distinguish a function is by the use of parentheses `(` `)` to contain its *arguments*. The arguments (also "parameters") are the values or variables submitted to the function for it to use. In the case of `NSLog()`, it takes a formatted string as its argument, which it then sends to the debug console to be printed out.

### The String Literal

In programming, a "string" is a data structure that is used to represent text. This document that you're reading is considered a string. If you've heard of [ASCII](https://en.wikipedia.org/wiki/ASCII) or [UTF-8](https://en.wikipedia.org/wiki/UTF-8), those are different standards of interpreting binary values into textual characters that humans can understand.

In our code, we can create a string to send to an `NSLog()` by using the string literal (`@""`). This "string literal" is a syntax which tells the compiler to interpret the code within its opening and closing characters *as a text value*.

```objc
NSLog(@"Hello, World!");
```
This will print: `Hello, World!`, the text value defined by the string literal.

### String Formatting (Interpolation)

The `NSLog()` function actually accepts what is called a "format string". The `@"Hello, World!"` string is simply interpreted it as a format string without any formatting to be performed.

String formatting (or "interpolation") is the process of assembling a string from other values or variables. If you've ever written (or received) a form letter, it is this process at work: defining a template letter with placeholders for fields to be filled in with specific information at a later time.

![](https://curriculum-content.s3.amazonaws.com/ios/ios-objc-fundamentals-unit/form_letter.png)  
—*A form letter.*, from [openoffice.org](https://wiki.openoffice.org/wiki/File:WG11-11.png), [CC BY 3.0](http://creativecommons.org/licenses/by/3.0/)

In the terms of formatting a string, the "format string" is the template, the "format specifiers" are the placeholders, and the "format arguments" are the actual pieces of information (like names and addresses) that are used to fill in the placeholders according to the template. An "interpolated string" is a resulting string that is the combination of the format string's template and the values submitted through the format argument.

### Format Specifiers

There are actually quite a large number of valid format specifiers, but most of them have rare or obscure uses. The single most commonly used format specifier in Objective-C is `%@`, and this what is used for format arguments that are strings.

So, to print out "Hello, World!" using string formatting, we could write out an `NSLog()` like this:

```objc
NSLog(@"%@, %@!", @"Hello", @"World");
```
This will also print: `Hello, World!`.

The format specifiers are used as placeholders for the format arguments `@"Hello"` and `@"World"`, while the format string, which serves as the template, defines what punctuation should accompany the format arguments once they're brought together.

### Format Arguments

The format arguments are listed (separated by commas `,`) after the format string in corresponding order to the format specifier to which they're attributed. If we were to invert the order of the format arguments, it would invert their order in the interpolated string:

```objc
NSLog(@"%@, %@!", @"World", @"Hello");
```
This will print: `World, Hello!`.

There is no theoretical limit to the number of format specifiers and format arguments that a single format string can be associated with. Because of the syntax of it in Objective-C, however, formatting many arguments at once gets difficult to maintain, so you'll rarely see cases where more than a handful of format arguments are used at once.

Those are the very basics of using `NSLog()` with string interpolation!

```objc
NSLog(@"%@", @"(づ｡◕‿‿◕｡)づ");
```
