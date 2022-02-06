---
title: 'Failure-Driven Unit Testing'
description: 'Some concrete adivces on how to efficiently do (Unit) testing.'
excerpt: 'Some concrete adivces on how to efficiently do (Unit) testing.'
categories: [Development]
tags: [testing, junit]


---
> Unit testing is as time consuming as it is time saving.

[TDD by the book](http://amzn.to/2v8haz8) is rarely applied in practice. Time is always short so test-driven development needs to give you an immediate benefit, otherwise it will never make it into your development routine. E.g., writing the test case before the actual class is just not intuitive. Furthermore, trying to cover all lines of your new class right from the beginning has basically zero efficiency, since you spend a lot of time testing things that will disappear on the next rapid-prototyping-iteration on the next morning.

## Do not just write random tests.

Start prototyping, use your app and only test if you run into problems (which usually happens immediately). Failures will tell you what to test, which is why every single test you write will fail first and will address a real world problem. Only one exception: Always test identity (`hashCode()` & `equals()`) right at the beginning. If identity calculation of your types is erroneous you are lost!
 
## Write this test now!

You found the bug, you could fix it and forget about it. Don't be lazy now. For two reasons: First, we don't want to see that bug again and want to make sure it stays dead. Write a test that ensures this, then fix it and never think about it again. Second, there is no point in time where it will be more easy to write a decent test case for this problem than now, since now you are perfectly aware of it. No need to think your way into it.
 
## If you have already some type hierarchy, start at the *bottom* of the type hierarchy, not the top.

This will save you some duplicate testing. If a type at the bottom has some failing tests, try to test the same thing for the super type and so on. Only if you cannot map the failure to the next type up the hierarchy, you need to find the problem right there.

## Test your way *down* the [Testing Pyramid](https://martinfowler.com/bliki/TestPyramid.html)

Start with Integration and UI tests. If one test fails, continue to write tests for the next, more concrete application layer. All the way down to most basic Unit tests, if necessary.

## Limitations?

This approach works best for obvious and immediate bugs. For example UI or behavioral bugs.  If your application does some number crunching or similar task that is hard or impossible to comprehend, you will probably not recognize a bug once you see it. Does that mean you cannot apply the failure-driven-testing model? Not at all. But bugs will not be recognized during prototyping or during first usage. Write top-level tests, that cover your algorithms at the most large-scale possible. If those tests fail, you have a starting point and know what to do.




*..work in progress..*