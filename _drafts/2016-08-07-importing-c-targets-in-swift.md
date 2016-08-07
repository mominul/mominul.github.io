---
layout: post
published: false
title: Importing C targets in Swift
subtitle: A lowlevel approach
---
[Swift](https://swift.org/), the revolutionary programming language from [Apple](http://www.apple.com/) has created new traditions in programming. As we all know, Swift can interoperate with [ObjectiveC](https://en.wikipedia.org/wiki/Objective-C) and [C](https://en.wikipedia.org/wiki/C_(programming_language)) language seamlessly. On macOS we can use this feature by [bridging](https://developer.apple.com/library/ios/documentation/Swift/Conceptual/BuildingCocoaApps/MixandMatch.html#//apple_ref/doc/uid/TP40014216-CH10-ID122) our sources with Xcode. But as Swift evolution proposal [SE-0038](https://github.com/apple/swift-evolution/blob/master/proposals/0038-swiftpm-c-language-targets.md) has been accepted, we can also import C targets (C, ObjectiveC) easily with [Swift Package Manager](https://swift.org/package-manager/). Ankit Agarwal has written a [blog post](https://ankit.im/swift/2016/05/21/creating-objc-cpp-packages-with-swift-package-manager/) on this.

The [Rust](https://www.rust-lang.org) language can also interoperate with C and other languages by    using [Foreign Function Interface](https://doc.rust-lang.org/book/ffi.html) feature. But with Swift, we can do it more