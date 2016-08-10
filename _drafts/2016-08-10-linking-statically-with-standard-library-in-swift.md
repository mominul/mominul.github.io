---
layout: post
published: false
title: Linking statically with Standard Library in Swift
---
It is possible to link [statically](https://en.wikipedia.org/wiki/Static_library) with Standard library aka **stdlib** in Swift. There is a flag named `-static-stdlib` in the compiler that allows us to do it.

The compiler always compiles our code dynamically linked with standard library as we can see in this example: