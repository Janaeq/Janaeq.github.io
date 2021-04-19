---
layout: post
title:      "Building a JavaScript app using a Rails API"
date:       2021-04-19 23:20:59 +0000
permalink:  building_a_javascript_app_using_a_rails_api
---


For my fourth project, I decided to make an application that organizes my tiktok likes into specific categories. As a user that spends countless hours of the night on the app, I like way more videos than I'll ever admit. Because of this, whenever I go back to try and find a video that I liked a few days ago I'd have to scroll so much to find it.

With an app that can organize my favorite videos into categories, I'll have a smaller subset of videos to look through and I can find the video I'm looking for much faster! 

I wanted to make the app as simple as possible. 
    1. Create a category
    2. Add videos to that category
 
#### Creating the API with Rails

My application has two models: Category, and Videos.
These models are related through a has_many/belongs_to relationship. A category has many videos, and a video belongs to a category. I used the active_model_serializers gem to generate my JSON in an object-oriented manner, so that a Category object would have an array of videos that belong to that category. 

In order to get information from the tiktok video link that the user provided (thumbnail and embed code) I needed to use Oembed, which is basically just a format for allowing an embedded representation of a URL on third party sites. In my application controller, I had to call on Oembed to retrieve the thumbnail and embed code and call on these methods in the videos_controller to add it to the video object in the backend before sending it to the frontend as a complete JSON object. Without this, I would just have a pretty much useless URL.

Once I got that all set up, my API was ready to use in my frontend!

#### Using JavaScript

Since the beginning of the JavaScript module, I felt confused! It was like a whole new language (literally), and I had such a hard time understanding. Through countless hours of googling and youtube searches, [Programming with Mosh](https://www.youtube.com/user/programmingwithmosh) helped out a TON!
I was a bit behind in the course, and when I started my project I had not done the "OOJS" lesson. I later found out that this was a huge mistake, because this was an essential requirement of my project. I later went back and completed those lessons. With the help of project build videos, I was able to get a good start on my project and create a responsive and functioning SPA!

Though I need more practice with JavaScript, this project really taught me a lot, I accomplished my one goal of making it super simple! I even created a popup like window for the embedded video to play! The only issue though, is that the embedded video only plays upon document load. Since this is a single page application, when you click on the thumbnail to play the video, the content of the embedded code shows up, but unfortunately the video doesn't play. I googled the issue, and a potential solution was to use jQuery to load the single div that contained the embedded code! However, since my application is running from file:/// instead of http:///, CORS has blocked jQuery from loading the popup div. 

Once my application is deployed, it'll have an http:/// url and the video should load just fine!





