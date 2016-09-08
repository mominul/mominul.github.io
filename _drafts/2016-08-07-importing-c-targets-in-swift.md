---
layout: post
title: Importing C targets in Swift
subtitle: A lowlevel approach on importing C targets in Swift
---
[Swift](https://swift.org/), the revolutionary programming language from [Apple](http://www.apple.com/) has created new traditions in programming. As we all know, Swift can interoperate with [ObjectiveC](https://en.wikipedia.org/wiki/Objective-C) and [C](https://en.wikipedia.org/wiki/C_(programming_language)) language seamlessly. On macOS we can use this feature by [bridging](https://developer.apple.com/library/ios/documentation/Swift/Conceptual/BuildingCocoaApps/MixandMatch.html#//apple_ref/doc/uid/TP40014216-CH10-ID122) our sources with Xcode. But as the Swift evolution proposal [SE-0038](https://github.com/apple/swift-evolution/blob/master/proposals/0038-swiftpm-c-language-targets.md) has been accepted, we can also import C targets (C, ObjectiveC) easily with [Swift Package Manager](https://swift.org/package-manager/) and Ankit Agarwal has written a nice [blog post](https://ankit.im/swift/2016/05/21/creating-objc-cpp-packages-with-swift-package-manager/) on this.

### How actually Swift imports our codes?
Actually this magic task is done by the compiler. Like Swift, its compiler is also amazing and inherits a great [architecture](https://swift.org/compiler-stdlib/#compiler-architecture). But this great(to C coders) work is done by the thing named [Clang importer](https://github.com/apple/swift/tree/master/lib/ClangImporter) which is one of the major components of the compiler.

Clang importer actually maps our C codes as modules and imports them as regular Swift API. It uses the [module](http://clang.llvm.org/docs/Modules.html) feature from Clang.
