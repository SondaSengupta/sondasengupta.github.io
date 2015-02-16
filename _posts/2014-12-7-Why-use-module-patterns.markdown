---
layout: post
title: Why use Module Patterns?
img: "/images/modulefloortile.jpg"
excerpt: "I like to think that module patterns is the next level to coding for a beginner. You are not merely content anymore to have working code. You want cleaner, more efficient code."
date: 2014-12-7
---
In the beginning, when I was first learning Javascript a wee month ago, I knew nothing about modules. It was more important that I just get the code working. When you are starting out with your first language, you tend to mishmash things together and cross your fingers hoping it will do what you had in mind. With trial and error, the mistakes become less and the code starts to do more of what you want, and more importantly, you start to understand how it all works.

Then you become more discerning. It’s not enough just to get the code onto your file, but you develop a particular way that you want it written so its easier to read, easier to debug, and more efficient to use.

I like to think that module patterns is the next level to coding for a beginner. You are not merely content anymore to have working code. You want cleaner, more efficient code.

Module patterns are tried and true methods to write cleaner, more efficient code. A module pattern is a particular type of design pattern that breaks up code into segments called modules in which each module is given a particular overall task. For example, in the very common MVC module, you separate your database and its data rules (Model) from the user interface (View) and the logic behind your app (Controller).

This has many particular benefits. For one, this is great organization for a large team, who can break a large project into modules and assign people to each task. Because your code organization follows a well known convention, it becomes easier for future developers to maintain your project. It is much easier finding and editing your small module instead of the nightmare of sifting through lines and lines of spaghetti code that is intertwined to all parts of the project. On top of this, the code is localized so it does not clutter up the global namespace and your variables will not interfere with another developer’s variables.

Not only are module patterns great for large teams, but you will see them used extensively in API creation. Perhaps you have created a library, but you don’t want users to accidentally interfere with variables and functions that make the library’s innards. Module patterns allow you to set up private and public spaces so that only the variables and functions you specify will be able to be accessed.

For the individual, module patterns allow for cleaner looking code that is easier to read and easier to come back to when the project becomes a memory. There are some really great resources out there to learn more about design patterns in general, and specifically module patterns to Javascript. When you are ready to take your code to the next step, be sure to check them out.

<!---image provided by Alvi-Man at
 http://www.morguefile.com/archive/display/630598 --->
