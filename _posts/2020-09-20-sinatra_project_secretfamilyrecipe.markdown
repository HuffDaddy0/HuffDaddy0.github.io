---
layout: post
title:      "Sinatra Project: SecretFamilyRecipe"
date:       2020-09-20 19:13:22 +0000
permalink:  sinatra_project_secretfamilyrecipe
---


I LOVED creating this Sinatra project. For the very first time I was able to take these months of hard work and create something meaningful and useful to my family and I. Now, don't get me wrong, the CLI project was fantastic and I think it really sparked something in me. However, this is something I can share with those closest to me. I couldn't tell any of my support group "Hey guys! Set up a local environment on your computer, go to my github, clone and fork my repo, and then in your terminal type bin/run!" I would have recieved blank stares in response to that. Their minds would have gone "Set up a what? Go to myd what? Do what and what to what???? I dont have any forks, just cookies... maybe... and i dont think I'll be at an airport any time soon." Needless to say, it would never happen.
However, with this project I now have something that, with a little bit of extra work, I can slap on a free hosting site and say "go to www.my_project_url.com." Short and simple, and something that anyone who's ever used the internet can do.
I would say that this project tested my ActiveRecord knowledge more than anything. I constantly kept returning to the ActiveRecord labs and lessons to refresh myself on things, especially setting up relationships efficiently. Why have a recipe belong to a user and a family when it can just belong to a family through user? One thing that I was sure I was being proactive about was my use of the SQL table ":families." I knew that active record uses pluralization to determine a number of different things regarding to relationships. In order to be proactive I thought "ActiveRecord is taking the table name and stripping off the "s" at the end in order to find a Model that builds objects from that table." By that thinking, I didnt want to confuse ActiveRecord with the singular `family` instead it needed to be `familie.` Right?
**Wrong.** Turns out the folks who developed ActiveRecord were kind enough to take that into consideration. Active record DOES NOT just strip the s off of whatever you use for your table name. In most cases that is all it has to do, however there is an entire library in ActiveRecord dedicated to irregular pluralizations. `Families` included. As far as readability of code, that's an awesome thing. While I may have spent a good two hours before I finally realized the issue, I learned a valuable lesson: 
>Have faith in your fellow developers. 
Especially developers of a major component like active record. They foresaw this, and while I may have wasted time because of it I'm sure there are countless others who've benefitted immensely from that library. It also showed me to think ahead as far as ease of use goes. My experience showed me that active record was stripping off an "s." (I had never used an irregular plural like this in a table before.) If I had been someone picking up active record for the first time, I would simply type it like it was english. Like it should be. And if it weren't for that library I'm sure countless people would have wasted countless more than my two hours trying to figure out why `families` wasnt the table for the Family model.
Another issue I ran into was determining when a method needed to be a helper method (belonging to a controller), and when it needed to belong to a model. My recipe's were created with attributes like `prep_minutes` and `prep_hours` so in order to find the total prep time I needed a method `#total_prep_time`. Without really considering WHAT this method was going to do and WHO it was going to do it to I placed them in my recipe helpers. What do you think was returned when I tried to call:
```
def total_prep_time
   "#{self.prep_minutes} : #{self.prep_minutes}"
end
```
on an instance of a recipe, when it was DEFINED in the controller.
```
No method error: no method 'total_prep_time' found for object <RecipeController>
```
OOPS! "Lets just copy and paste that over into the Recipe model!"
`01 : 30`
YES!
The moral is it matters where things are defined. You can't find a `prep_minutes` from something whos attributes are `:params, :session`. Going forward I will always be considering WHAT a method will do and WHO it will do it to.

In conclusion, this project was very important. It really helped solidify a few of the things that I didn't fully retain from the lessons. That's just how I work though. Sometimes I have to make the mistakes in order to prevent making them in the future, and every project I do solidifies the idea that errors are your friend. Every single error I've run into in the last few months has been like a little mentor that only exists long enough for me to learn a lesson, big or small.
I cannot wait to continue into rails. My next project is going to be huge for me: My own personal business website. I am a contractor in my local area doing home remodeling. I believe that rails will be the perfect framework to build my own application on.
