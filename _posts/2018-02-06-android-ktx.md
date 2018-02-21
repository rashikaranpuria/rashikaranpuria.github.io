---
layout: post
title: 'Android KTX'
subtitle: 'A new library by Android, that you need to try today'
date: 2018-02-06
categories: webapp
cover: '/assets/img/Androidktx.png'
tags: android kotlin
---

It is amazing how much improved our Android development process has been, after **Kotlin** was announced as the official language for Android development. From people at Android, improving Android Studio to make it easier for us developers, to use Kotlin on our favorite IDE, to people at Kotlin making **Anko** library, to ease out the bulky operations in Android development even further with functions and extensions that simplify the time consuming things.

And now android has released a preview of another mind blowing library on which a lot of [amazing people](https://github.com/android/android-ktx/graphs/contributors) are working to make our lives a lot easier. The library in spotlight is [Android Kotlin extensions](https://github.com/android/android-ktx). Android KTX is still in preview but it is open for us to try and give our feedback to the contributors because they are working hard to make it a lot better. The aim of Android KTX is to make Android development with Kotlin a lot more concise, simple and idiomatic. So that you don't have a stupid excuse to not use Kotlin for Android development any more **:D**, just kidding **:P**, or may be not.
Android KTX provides extension functions for working with Android firmware classes and more. They currently cover some of the most used classes in Android like **Views, Canvas, Animator, Shared Preferences, Database, utils**, etc.

To get started with using the library add google as repository in your project's build.gradle:
```java
repositories {
    google()
}
```
and add a dependency for library in your app's build.gradle:

```java
dependencies {
	// Android KTX
    implementation 'androidx.core:core-ktx:0.1'
}
```
They have also provided some simple examples that show how much Android KTX improves the development process by simplifying operations and hence saving our time. For eg, when converting a string into a URI.
with Kotlin:
```java
val uri = Uri.parse(mUriString)
```
and with Android KTX:
```java
val uri = mUriString.toUri()
```
Using Shared preferences, we needed apply() or commit() like below:
```java
sharedPreferences.edit()
    .putInt("key", intVal)
    .apply()
```
but with KTX, it is as simple as this:
```java
 sharedPreferences.edit {
    putInt("key", intVal)
}
```

Have you tried to trigger an action in a view's pre draw listener?
In Kotlin:
```java
view.viewTreeObserver.addOnPreDrawListener(
    object : ViewTreeObserver.OnPreDrawListener {
        override fun onPreDraw(): Boolean {
            viewTreeObserver.removeOnPreDrawListener(this)
            actionToBeTriggered()
            return true
        }
    })
```
But with KTX, oh my god!
```java
view.doOnPreDraw {
     actionToBeTriggered()
}
```
The above one is simply amazing!

There are a lot of other things that Android KTX has to offer, and even though it is a preview but we all can work to help them get a step closer to a stable version, so that we can start using this nice library in our production code. Try out this library, submit issues, suggest features and if possible contribute. Here is the link (https://github.com/android/android-ktx/)

They also plan to create Kotlin extensions for **support library** and **architecture components** soon. Architecture components is the one I am waiting for the most.

This library shows that people at Android have enormous plans for Kotlin. I have said it before and I am saying it again that it is high time for you to start using Kotlin in your production apps. I started a long time ago and I haven't had a complaint since.
If you are looking to learn Kotlin better and finding more complex use cases, here is a book that you should definitely try out.
[![Kotlin Cookbook](/assets/img/book_cover.png)](https://goo.gl/da3Exi){:target="_blank"}

Comment your views and share this post with friends who don't know about **Android KTX** or the [book](https://goo.gl/da3Exi){:target="_blank"} above.
