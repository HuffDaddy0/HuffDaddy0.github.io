---
layout: post
title:      "Big-O and why it's important"
date:       2021-02-15 02:24:47 +0000
permalink:  big-o_and_why_its_important
---


Have you ever thought about measuring performance of a function? How would you go about doing that? Would you measure it in milliseconds? What if a function on takes .00000000000000001 second? That would round to 0 milliseconds. So how much time did it take?

This is one of the issues that big-o notation answers. Big-O notation is a way to convey the time-complexity of an algorithm. That is, how much time an algorithm takes in regards to the number of inputs that are given to the function. 

There are many different time complexities that an algorithm can take but some common complexities are:
1. Constant - O(1) - These algorithms take roughly the same amount of time regardless of the number of inputs given.
2. Linear - O(n) - These algorithms increase in time is directly proportional to the number of inputs given
3. Quadratic - O(n^2) - These algorithms get exponentially slower as more inputs are given
4. Logarithmic O(logn) - These algorithms time complexity increases logarithmicly as more inputs are given. (A logarithmic solution is always preferred over any solution other than constant)

Big O notation seeks to answer the question of how long an algorithm would take when you reach absurdly large numbers, like those close to infinity. Since so many factors influence the time an algorithm takes to run on a given computer, this abstraction to a mathematical equation allows us to visualize the performance comparatively to another logarithm and choose which best suits our needs.

Big O Notation is also not exact. Since we are using it to evaluate the time an algorithm takes when given a near infinite number of inputs on something something like O(n + 2). Now consider if n was 1 billion. 1,000,000,000 + 2. Does the 2 make any significant difference when compared to 1 billion? It doesnt! So we just drop it! 
Developer math is fun math :)
