---
layout: post
title:      "Rails Project"
date:       2021-02-21 05:24:41 +0000
permalink:  rails_project
---


My project is a dog walking application that allows users to sign up, log in, and create walks for dogs listed under their profile. The users can also leave comments on walkers that they have used, and these comments can be viewed by any logged in user.
I think the most complex part of this project was implementing nested forms and ensuring that the views were different based on the params that were passed in. It was as if once I thought I got the hang of it, another error came up that I had to spend hours figuring out. Thankfully, going over the labs time and time again allowed me to really understand nested forms and showing different views. 
I was also a bit iffy about the relationships between my objects. It always amazes me how active record helpers really makes relationships super simple. For example, my users are not directly related to walks because they're not the ones involved in the walk. Their dogs are. So rather than implementing a ` user id` in my walk table, I created a has_many relationship in my user model that relates the user and the walk through the user's dog `has_many :scheduled_walks, through: :dogs, source: :walks`
One thing that I get very nervous about is keeping my code DRY. As I move on with each project, it seems that it becomes easier to do this. The use of partials and helpers really eased my anxiety about this. So rather than having a huge view file with if-else statements all over the place, it's much nicer to have a simple view that renders partials so that your code is a lot cleaner.

About omniauth - I was not a huge fan of how simple the lab was for this. I felt like this was something that needed so much more explanation. However, when I actually included it in my program I was shocked at how easy using the Google Oauth was! It was something I was dreading! So when I got it to actually work, I was in awe! The fact that it can take my name from google was actually shocking. This is definitely something I intend to use in almost every one of my future applications.
