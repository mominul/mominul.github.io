---
layout: post
title: Linking statically with Standard Library in Swift
tags: [swift]
---
It is possible to link [statically](https://en.wikipedia.org/wiki/Static_library) with Standard library aka **stdlib** in Swift. There is a flag named `-static-stdlib` in the compiler that allows us to do it.

## Shared vs Static Libraries
There are some pros and cons in each of Shared and Static Libraries. Here a nice answer about those advantages and disadvantages in [StackOverflow](http://stackoverflow.com/a/2649430)

> ...
> There are advantages and disadvantages in each method.
>
> Shared libraries reduce the amount of code that is duplicated in each program that makes use of the library, keeping the binaries small. It also allows you to replace the shared object with one that is functionally equivalent, but may have added performance benefits without needing to recompile the program that makes use of it. Shared libraries will, however have a small additional cost for the execution of the functions as well as a run-time loading cost as all the symbols in the library need to be connected to the things they use. Additionally, shared libraries can be loaded into an application at run-time, which is the general mechanism for implementing binary plug-in systems.
>
>Static libraries increase the overall size of the binary, but it means that you don't need to carry along a copy of the library that is being used. As the code is connected at compile time there are not any additional run-time loading costs. The code is simply there.
> ...

So, if we use **dynamic linking**(*linking with shared library*) we can get:

* Reduced binary size
* There is a probability of [dependency hell](https://en.wikipedia.org/wiki/Dependency_hell)
* Need to think about libraries which we depend on

But with *static linking*:

* Binary size is big (usually binary size is equal to = actual binary size + size of linked libraries)
* No probability of **dependency hell**
* Portability
* No need to think about libraries which we depend on

## Example
Here we have a small code that calculates the sine angle of 45 degree.

```swift
import Glibc

// How about calculating sine of 45 degree?

let degree = 45.00
let convert = M_PI / 180

// Let's use sin function imported from Glibc
let result = sin( degree * convert )

print("The sine of \(degree) degrees is \(result)")
```

### Dynamic Linking
As usual swift compiler will compile our code dynamically linking with standard library 
