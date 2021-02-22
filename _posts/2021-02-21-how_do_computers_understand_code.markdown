---
layout: post
title:      "How do computers understand code?"
date:       2021-02-22 03:39:54 +0000
permalink:  how_do_computers_understand_code
---


After completing Flatiron's curriculum, I have found myself spending a lot of time wondering, 'What's next?'. The obvious answer is the career search; that's the next step in everyone's path. When I say;  "what's next?", though, I mean what do I LEARN next? Things are constantly changing in this world. Languages rise and fall. Frameworks have their days and are soon replaced. In a climate that's ever-changing, how do you decide what the next best thing is? Software engineering, as we all know, is a neverending path of learning. 

 I decided to step back to Computer Science. This is the very foundation of everything we do and it has always intrigued me. Sure, we're writing code, but how does a computer understand that? How does it know that

```
const string = "hello"
const otherString = "world"

return string.concat(otherString)
```

returns "hello world"? Furthermore, how does the computer remember "hello" and "world" in order to create "hello world"?

Well, the answer is not straightforward.

Below the code we write, are other layers of code. Our code is being run through lower level programs before and during it's run-time.
Higher level language are passed through lower level languages until everything is boiled down to ones and zeros.

Most people know, to some degree, that computers are just ones and zeros. However, Did you know that these ones and zeros are actually a language of themselves? What do you think these ones and zeros represent?
They actually represent the state of tiny switches inside of computers known as transistors. The computer you're reading this on has MILLIONS of them; so the ones and zeros actually represent the storage of electricity:
0 - the switch is off, or unpowered.
1 - the switch is on, or powered.

Think about it: What is the only physical input into a computer that it has to use to solve problems we as programmers give it? ELECTRICITY! It has to be plugged in or the battery has to be charged. Every single thing that a computer does is done by the storage, manipulation, and interpretation of electricity. As a former electrician, I find this implementation  fascinating.

Every combination of on and off switches is equivalent to a value like 12 or A.
