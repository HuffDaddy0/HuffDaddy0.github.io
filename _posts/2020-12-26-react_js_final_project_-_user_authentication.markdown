---
layout: post
title:      "React.js Final Project - User Authentication"
date:       2020-12-26 22:46:29 +0000
permalink:  react_js_final_project_-_user_authentication
---


For my React project I wanted to stretch what we've learned and implement user authentication into an application containing seperate front and back ends. While this sounds fairly straightforward in theory it is a bit more complicated in practice. First, while rails has a very good authentication system through ActiveRecord and bcrypt, you won't be able to use it if you load your rails backend as an api. Creating an api-only backend will disable rails sessions (and in turn disable cookies from being passed between the browser and server.) Without this cookie, there is the possibility of being logged in on the backend but not on the front, and vice-versa.
It took a while to get set up, but the basics are this:
1. When a user signs up, the user is created in the database. This information is then saved to the rails session, and sent to the frontend to be saved into the redux store. Now, the user is logged in in both front and back end.
2. When a user is logs in, a POST fetch request is made to the backend. At this point the User controller searches the database for a matching email, and then once one is found it checks the password given against the salted-hashed version stored by bcrypt. (I used the .authenticate method for this.) If the passwords match the database sends the users information back to the front end and the user information is stored into the redux store.
3. Everytime the app component is mounted, I send a check to the backend to see if anyone is signed in there. This means that when every time the application is loaded it is looking at the cookie data to determine if someone was previously logged in on this browser. If so, the backend sends that user back to the front and stores it in the redux store. This is how a user statys logged in even after closing the application through the use of cookies.
4. Logout is the simplest action to create here, it does two things. First, it send a delete request to the sessions controller. The controller then clears the session data associated with the current user. When this is successful, it sends a response to the front-end, which in turn clears the redux store of any user related information.

When I started this I though it would be a very straightforward process. In hindsight, it is easier than it initially seemed. The tricky part is keeping track of the information being passed around, and where and how it was stored. I used helper methods in my rails backend to check things like is_logged_in? and did the same on the frontend. 

