---
layout: post
title:      "Makeup CLI"
date:       2020-10-11 18:50:17 +0000
permalink:  makeup_cli
---


I'll start off by saying this project was nothing short of challenging. In the same light, I had *so much* fun building this CLI. 

Going through the labs of Object Orientation, I constantly felt like I had no idea what was going on. I just could not grab the concept of anything I was trying to learn. I became really discouraged seeing how behind I was, and I was really dreading this project.
Going into project week I mostly just took the time to research what API's were because to be frank, I had no clue. I didn't know what a get request was, I didn't know what the terms 'requre' and 'require relative' meant, I didn't even know how to use an API. **Thankfully**, my cohort mates love to post resources in Slack, so big shoutout to them.

When it came time to actually build this CLI, once I got my environment file set up and my API set up, it was a wrap. Building out those classes and methods was like second nature to me. Fixing my own errors really helped me understand how everything comes together through relation. 

Although it's not the most beautiful or most unique thing in the world, it made me realize how much knowledge I've gained on Ruby Object Orientation.

My CLI uses a basic Makeup API to display information about products to the user and present them with the option to buy the product at a specified link. 
The user has the option of searching makeup products by brand, or by searching them all at once. 
Because of this I did find it kind of challenging to keep my code **DRY**, but it was nothing that a little instance variable or interpolation couldn't fix. 
Another challenge I ran into was formatting the list of colors from the JSON element into an array to display in the more info section. For whatever reason, whenever I would iterate over the elements and call on colors, it would always return the array of colors!! It was so frustrating. I usually don't like to ask for help, but at this point I needed some guidance. I swallowed my pride and went to office hours. Once I got the code working the way it needed to, it was like a weight lifted off my shoulders! So if anyone reading this post is also like me, *please please please* swallow your pride and **go to office hours**!!!

This is the code that tripped me up. I tried everything I could to get colors pushed into an array that .join could be called on, but nothing worked until I went to office hours.

```
makeup.each do |m| 
            a = Makeup.new(name: m["name"], brand: m["brand"], price: m["price"], description: m["description"], website: m["product_link"], rating: m["rating"], product: m["product_type"])
            m["product_colors"].each do |color|
                a.colors << color["colour_name"]
            end
        end
```

All this to say, I learned so much with this project and that's the whole reason why I had fun doing it. Granted, I found myself working on this project (willingly) until about 5am every morning for the past week, but it wasn't because of deadlines or pressure, it was because I was having fun learning while coding.

