---
title: "Writing My First Swift App"
date: 2020-01-24T17:44:57+02:00
draft: false
categories:
- "Development"
tags: 
- "Swift"
- "IOS development"
- "Xcode first steps"
description: "Writing My First Swift App"
author: "Alex Trandafir"
keywords:
- swift
- xcode
- development
- ios development
- xcode first steps

---

<p>{{< le "I played a lot in the meantime with some of the concepts below (with swift, Kotlin and Java). I did change my mind on a lot of topics but decided to let the article as-is." >}}</p>

<!-- wp:paragraph -->
<p>This post is not intended to be a tutorial on how to write your first app. It's merely my experience and maybe a general guideline on what to expect if you're trying to do this for the first time. If you already wrote an IOS app this post is probably not for you. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I've always considered that, in order to become better at something, you need to explore the surroundings. IT has a lot of sub-fields and, for a developer, the simplest way to explore is to play around with a new language.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I come from a Java background, working mainly with enterprise, distributed applications. I've always been interested in frontend development, it has a way to make you feel empowered every time you can actually see your progress. I've played around with web development before (Angular and Vue) and Android (still Java based, back when Kotlin wasn't a thing yet) and I figured I ought to try Swift and IOS development. I did play with XCode before, but on an Objective-C project, so Swift was an entire new subject to me.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Get acquainted with the tooling</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>One of the first things to do when starting out with a new language is to do a bit of research regarding the tooling available for it. As a developer when I say tooling I mostly refer to your editor (IDE) because that's where you'll be spending most of your time. For IOS the choice is simple: Xcode. Tooling doesn't mean just the IDE. but for starters that's all I needed to worry about.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>"Xcode ninja" is surely in someone's CV somewhere because Xcode is almost like a skill on its own. Simulators, organizer, certificates, console, debugger, library, navigation are all things related to XCode that one must learn one's way around. I had to Google even the most trivial aspects to learn my way around Xcode which felt more like a barrier at first. Worry not, it's easy to get the hang of it once the basics are well understood. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Structure</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The thing about moving to an entire new ecosystem is that you also need to learn how everything glues together. In the case of frontend apps there has to be a place where the visuals are linked to your models and actually enable you to do some logic. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://developer.apple.com/library/archive/documentation/General/Conceptual/Devpedia-CocoaApp/Storyboard.html">Storyboards</a> and auto-layout are the current standard (starting with IOS 13 we also have <a href="https://developer.apple.com/xcode/swiftui/">SwiftUI</a>, my experience below is prior to SwiftUI, so I'll just ignore it for now). There's no point in doing a history about how it all got here but it's important to know it's not the only way of achieving this. When searching on how to do stuff, you need to know what to filter out and get the results you actually need. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Application lifecycle</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In software, everything has a lifecycle. The lifecycle dictates the behaviour of the component and it needs to be understood in order to get the most out of it. The life cycle refers to your software's ability to respond to system events. Apple <a href="https://developer.apple.com/documentation/uikit/app_and_environment/managing_your_app_s_life_cycle">provides</a> a decent documentation on this, however it's not necessarily useful, especially when you're starting to play around with an app (depends what we're trying to accomplish). They are especially useful when playing around with deep linking though (called <a href="https://developer.apple.com/documentation/uikit/inter-process_communication/allowing_apps_and_websites_to_link_to_your_content/handling_universal_links">universal links</a> now), so depending on the project it might be useful. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Application lifecycle is one of the most important aspects in programming. However, an analogy might help here, when you're learning to drive a car you're not really concerned on how the combustion engine actually works. It just works. Same here, if you're just starting to play around with it, you'll eventually learn about it and apply best practices and whatnot.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>View controller lifecycle</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>I've already mentioned storyboards. They are (or were?) the standard way of designing the user interface. The view controller's <a href="https://developer.apple.com/library/archive/referencelibrary/GettingStarted/DevelopiOSAppsSwift/WorkWithViewControllers.html">lifecycle</a> is something you'll bump into a lot, so make sure to at least have a look at it before diving into your first app. Practice is key here, it always is. The gist of it is in the following picture:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><img class="wp-image-61" style="width: 400px;" src="https://indiespun.files.wordpress.com/2020/01/wwvc_vclife_2x.png" alt="undefined"></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Swift </h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Getting to the actual point here, I've had a love hate experience with Swift. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Optionals.</strong> Coming from Java 7 and the world of "null" it was pretty complicated to wrap my head around Optionals. Theory is nice and all but once you start actually using <a href="https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html">optionals</a> you realise it introduces a lot of grey area. This is where I'm sure I did most of my mistakes, I had to force unwrap a lot of Optionals and that looks like an antipattern to me. It might be easy to read but at what cost? {{< le "Changed my mind, I like them now :D" >}} </p> 
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Error handling</strong>. If you read the first paragraph on Wikipedia of <a href="https://en.wikipedia.org/wiki/Swift_(programming_language)">Swift</a>, it's clear the language does a lot of stuff. And that's nice but also a problem. Classic try-catch blocks are available (but a bit different, they're actually do-try-catch blocks), throwing "functions" is a weird functional thing that you would expect from a "multi-paradigm programming language", but the thing that took me by surprise was the existence of "try?", which will make the function return an Optional. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://docs.swift.org/swift-book/LanguageGuide/Extensions.html">Extensions</a></strong> are cool. Being able to extend a class from the SDK (or any other source) opens a wide array of possibilities. It's a great way to get rid of the "Utils" classes that were used everywhere and looked really ugly. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Callbacks</strong> are ugly af. I've used them a dozen times, I still have no clue on the syntax. I had to Google each and every time in order to make things work. The weird thing is that you'll find numerous ways to accomplish <strong>asynchronous</strong> activities, delegates being the second candidate (and it appears there are actually even more). If you're a beginner with Swift, as I am, expect to have a pretty difficult time with this. </p>

<p>These are obviously not all the features of swift. There are plently of resources online explaning things. These are just the features I've stumbled upon the most and the ones that I had enough time and practice to opinionate about.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Google is ambiguous</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Well not Google per se, they're not to blame for this. The thing with Swift is that it gets yearly updates, and sometimes these updates break things. Whenever you're upgrading your Swift version you'll notice there are a lot of changes in the way the SDK works. XCode is extremely valuable here, as it helps you a lot with your syntax, but it sometimes feels like "the Swift people" are not sure what they're doing. A lot of classes are renamed in new versions and the <a href="https://en.wikipedia.org/wiki/Syntactic_sugar">syntactic sugar</a>'s sweetness is altered. This will make Google ambiguous at times, you might end up Googling something that will not work with your current Swift version or that will need major alterations. One way to improve your searches is to add the swift version at the end of your query. You still need to pay attention and keep this in mind.  </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p> The biggest problem with constant Swift breaking changes are the dependencies you'll end up using. You'll need to make sure they are maintained with every new Swift version. This takes us to the next topic</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Package managers </h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>You will most likely need some sort of third party library to help you accomplish your goal. The <em>raw</em> way to use a library is to download it, put it in your repo somewhere and link your project to it. And that's perfectly fine but it will eventually make things a bit too messy and verbose. Enter package managers. Apple didn't provide an official package manager until recently (<a href="https://swift.org/package-manager/">Swift Package Manager</a>), so <a href="https://cocoapods.org/">Cocoapods</a> became the de-facto package manager for everything Xcode related. The problem with it is that is alters your project, it's pretty easy to use though. Starting with XCode 11, <a href="https://itnext.io/replacing-cocoapods-with-swift-package-manager-fa37d67294c3">SPM</a> can now be used for IOS Applications as well so maybe it's worth looking into it. I would expect it has better integration with the whole ecosystem, but didn't manage to play around with it.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>IOS update - update everything</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Upgrading XCcode uses as much as <strong>20GB space</strong> on your disk. Whenever there is a new IOS version, you'll also have to download a new version of XCode. I use a 2015 MacBook Pro, one of the cheapest Pros I could've bought at that point, which had an 128GB SDD. This will not get you far, and I always ran out of disk space. I recently upgraded to a 512GB SSD and life is much better now, but it was a major problem for me whenever there was an update. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Conclusions</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>I'm a total beginner with this. The best way to learn is to play around with it. I was talking about  <a href="/blog/posts/my-first-post/">Mount Stupid</a> in an earlier post, I think I'm still climbing it. I'm not sure if there is a leap to take here as I don't see myself investing a lot of time into IOS development, but it's nice to have an idea of how you can accomplish certain things in a totally foreign ecosystem. As I said in the beginning, this is not a "tutorial", it is not a "best practice" article nor a guide for newbies. It's merely my experience and my thoughts about it at this point and some general advices on what to expect if you're just starting to play around with IOS development. </p>
<!-- /wp:paragraph -->


<!-- wp:heading -->
<h2>Cool resources</h2>
<!-- /wp:heading -->
<p>The internet is full of resources. Here's what I've found most useful:</p>

* https://github.com/matteocrippa/awesome-swift
