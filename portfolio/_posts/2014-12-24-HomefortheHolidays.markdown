---
layout: post
category: portfolio
title: Homes for the Holidays
img: "/images/HolidayHomesApp.jpg"
tools: Angular, Twitter Bootstrap, & Angular Google Maps
app: "https://holidayhome.firebaseapp.com/#/"
github: "https://github.com/SondaSengupta/HomefortheHolidays"
excerpt: "This is a site where people can share their favorite Christmas home displays. The markers are prepopulated with data from the Nashville Lights Competition."
date: 2014-12-25
---

![image](/images/HolidayHomesApp.jpg)

## About the App
The inspiration of this website came from a very practical problem. One of the few traditions in my family during winter is to go out and see the Christmas lights. However, if you've done it with your own family, it can be a pretty hit or miss endeavor. You might go into a whole neighborhood drawn by the beautiful lights of one home only to find the rest of the suburb doesn't share the same festive spirit.

Thus, my Nashville Software School Mid-Capstone project was a site that people could share festive homes in their neighborhood. Without logging in, you can view homes by geolocation or entering a street address. As a logged in user, you can enter and edit these home markers.

As of this moment, the markers have been prepopulated with data from the annual Nashville Lights Competition winners.

### Features
- Ability to view homes on map by geolocation or entering a street address without needing to log in.
- You can preview a home's picture, street address, and notes by clicking on its marker which brings up its infobox.
- If you are logged in, you can add comments into the Fireside Chat section.
- The member's map has the ability to edit information directly from a marker's infobox. Members can also view all homes in the database as a table.
- Log In/ Log out/ Forget Password is fully functional through Firebase.

![Maps Page](/images/HolidayHomesMap.jpg)

## About the Process
There were a few major hurdles in the creation of this site. First, the Google Maps API and Angular didn't play well together the first time around, since the map did not automatically refresh when changing views. I was able to fix this by using Angular Google Maps, an API specifically designed for the two built by some really clever people. Second, Google Maps took a really long time to load, especially with the addition of more markers. This is an ongoing issue, and the only half-baked solution I had so far was to increase user awareness by adding a loading bar.

Overall, I've learned quite a bit in this site's creation. Google Maps has a tremendous amount of features in its API and I barely scratched the surface. I had a lot of fun exploring and implementing these tricks.

## Links
-[Click Here](https://holidayhome.firebaseapp.com/#/) to go to the site.

-[Click Here](https://github.com/SondaSengupta/HomefortheHolidays) to view the code on Github.

-Learn more about [AngularJS](https://angularjs.org/)

-Learn more about [Twitter Bootstrap](http://getbootstrap.com/)

-Learn more about [Angular Google Maps](https://angular-ui.github.io/angular-google-maps/#!/)

-Learn more about [Angular Smooth Scrolling](http://ngmodules.org/modules/smoothScroll)

-Learn more about [Nashville Holiday Lights Contest](http://www.nashville.gov/Public-Works/News-and-Events/Holiday-Lights-Contest.aspx)
