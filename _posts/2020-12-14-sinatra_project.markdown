---
layout: post
title:      "Sinatra Project"
date:       2020-12-14 09:33:31 -0500
permalink:  sinatra_project
---


This project, like the last, was pretty easy once I got the hang of it.

**However**

I can't say that the entire Sinatra module didn't give me actual anxiety attacks. 

Working full time as a glorified receptionist at a hospital in NYC during a global pandemic, we were short staffed and I *for sure* had a lot on my plate. This project was the absolute last thing on my mind.

When I finally came around to doing this project, I was stuck on what kind of application I actually wanted to build. I thought about the database that I use at work. We log in, we pull up patient information and provider clinic/on-call information. While we don't have the accessibility to necessarily create a new doctor or a new patient (this is usually done by administrators), who says the user in *my* project can't be an administrator?

And since it's my project I decided to make the best of it with the little time that I had.

Installing the Corneal gem was SO helpful in creating my folders. It save me so much time, and it even created a nice blue color scheme to go with my Grey Sloan Memorial Hospital logo that I implemented on the login page.

This application allows a user to log into the database, and they are welcomed by the homepage which displays a link to the available providers, and a link to edit user login information (which is validated by ActiveRecord).

When the available providers are displayed, the user has the option to choose an existing provider or create a new one. Creating a new provider will render a form with inputs that are validated by ActiveRecord and then saves that provider to the database. The application will then redirect the user to a page that displays that providers information such as name, specialty, clinic days, clinic location, and on call days. This page also includes a link that brings the user to a page that displays a list of that provider's patients. 

This patients page will give the user an option to either choose an existing patient, or create a new patient that belongs to that provider. I found that understanding the concept of has_many and belongs_to was fairly simple, however getting my routes to work properly using the foreign keys and ActiveRecord methods was pretty tricky. One of the most challenging parts of this project was trying to figure out how to ensure a patient's *doctor_id* was the correct one. Nonetheless, once I got the hang of it everything was smooth sailing! 

In the pages that display a patient's or a provider's information, there is an link to edit the information. That link contains a form to edit which will be validated by ActiveRecord. It also contains a button to delete this patient or doctor. Something I had a hard time with was trying to figure out how to delete a doctor's patients from the database when that doctor was being deleted. Turns out you can use ActiveRecord methods to obtain an array of patients, iterate over that array and delete each patient. Like this

```

    delete '/doctors/:id' do
        #deletes this doctor
        @doctor = Doctor.find(params[:id])
        @doctor.patients.each do |patient|
            patient.destroy #deletes this doctor's patients
        end
        @doctor.destroy 
        redirect to "/doctors"
    end

```


The easiest part of this project, in my opinion, was implementing validations and authorizations. The entire time I was doing this project, I kept thinking back to my CLI project  and saying to myself "I can't believe I wrote out all those methods". Using rack, ActiveRecord, and Sinatra showed me how nice it is to inherit from code that has been written already.

