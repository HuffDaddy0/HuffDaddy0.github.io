---
layout: post
title:      "'An HTMLCollection is like an Array, but not an Array'"
date:       2020-11-21 21:18:28 +0000
permalink:  an_htmlcollection_is_like_an_array_but_not_an_array
---



Do you remember seeing that in the Javascript lessons here on Learn? I do. I remember seeing it, noting it, and moving on. Until, in my Javascript-Rails project, I ran into a situation where an HTML collection is NOT an array! I was baffled. I had a bunch of cards, all with an h4 tag that I wanted to add an event listener. Easy Right? Grab them all, iterate them, add a click listener to each. Done. 

Not quite.


```
let htmlCollection = document.querySelectorAll('h4')    /=> HTMLCollection[., ., ., ., .,]

//Tip: Any time you use .querySelectorAll() You're going to end up with one of these HTML Collections

htmlCollection.map(element => element.addEventListener("click", function(){
................
}         /=> Error: htmlCollection.map is not a function.
```

WHAT!? So i go back and check my spelling. I couldnt have spelled map wrong right?
Nope.
WHAT!? Look at it. It's an array. ALL ARRAYS CAN BE MAPPED!!!
Maybe it's just a weird bug lets try again.

```
/=> Error: htmlCollection.map is not a function
```

Ok, so apparently the .map function disappeared right? Well, no. Code doesn't work like that. Then it hit me:
While I may be looking at something that LOOKS like an array, has indexes like an array, can be deconstructed like an array, etc... I'm not looking at an array.
I'm looking at an HTMLCollection.

Try for yourself, open up the console on this page and grab a collection using querySelectorAll. Any elemtn will work, even if you just get one you've still got an HTMLCollection in front of you.
Now inspect it in your console. See all of those EXTRA attributes??? I couldn't tell you what they all mean, but they're there right? How can an array hold all of that info, in that format? Well, it can't, and this isnt an array. It's an HTMLCollection.
What this means, for you the reader, is that you just lost all of you favorite iterating methods (.find(), .map(), .filter(), etc.) So how do you work with this thing?
You have a few options:
1. Bringing back the for loop!
```
for(let i=0; i < htmlCollection.length; i++){
     //work with each element here
}
```
But that's oldschool right? An personally, I'm not fond of for loops. They're SO repetitive. Imagine writing a new for loop every time you have to work with an HTMLcollection. LAME.
2. force it into an array.
I found this excellent method that can be used on the Array global object:
```
Array.from(htmlCollection)   /=>   [ . , . , . , . , . ]
```
Can you guess what it does? If you guessed it creates an array from your given input then you guessed correctly.
Try it on the HTMLCollection you grabbed in your console. Now, try to map your new array. It should work exactly as you would expect.
So what exactly did this method do for us? Well, when you passed in an HTMLCollection it said "I see an array here, and I also see the other attributes of an HTMLCollection. They must just want the array."

And that's exactly what it gives us.

That means NO messy for loops! Personally, I give that a thumbs up.





