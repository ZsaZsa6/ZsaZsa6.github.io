---
layout: post
title:      "Working it out!!"
date:       2020-07-01 14:24:12 +0000
permalink:  working_it_out
---

Well, at least this time I didn't have that coding freeze going on!! I knew what I wanted to build and I knew that I wanted to build it from scratch!! I didn't want to try to figure out what I needed and didn't need from Corneal. 

But working through this module had taken me FIVE MONTHS!! Not because I didn't understand it, but because my life became crazy! Extra responsibilities, very limited time to work on coding and emotional stress to the max!!

All through this module, I felt like I wasn't getting it. Putting together erb tags just seemed to befuddle me!! Tux and the Rake console just never seemed to work for me!! I watched video after video, and I could understand what the instructor was talking about but I still didn't feel confident...

REWIND!! I am an obsessive list maker!! My poor Echo Show has more lists than should be humanly possible!! I have an Evernote app that I use like crazy, a Swipes app that has too many entries and pieces of paper scribbled with little lists for the day. The whiteboard on the side of my refrigerator is always full. From the size and flavors of cake I need to make to the orders on Amazon that I need to put in, it's a mess. 

I didn't hope to create an app like Evernote, but I do have dreams of making something that others like me could use to add another way of keeping track of all the To-dos of life!! 

So I knew I wanted to create an app for lists. It seemed redundant because there are sooo many out there, but I wanted something that I could relate to and get excited about. 

So I created Ronda's Sinatra Lists.

It's not super pretty. It's not Evernote, but it's a start!!

Routes have been a struggle for me, but when I started on this app, it seemed to all come together!! I finally understood that "get" was getting data from the user and "post" was putting that information into a refined format for the user to see. TA-DA!!

Forms suddenly made sense and I could even understand interpolating erb tags. What is this magic? 

I have to give MAD PROPS to Micah Shute!! His videos were a HUGE help to me!! The way he explained code made total sense to me!! Watching him and seeing how sometimes his code failed to do what he wanted and then seeing him solve the issue really gave me confidence. 


So WHAT DID I BUILD!?!

I built a website using a Sinatra framework that allows a user to sign up for an account and create lists. Each account has a username, an email address, a name and a password. Each list has a category, a title and content. 

Not super happy with the way the content is displayed right now but it meets the standards. My perfectionist self wants to expand but my time limits laugh at me!! This would be the area that I would expand.

I found a happy piece of code to verify that the email address was present and also was in the correct format.

```
validates :email, presence: true, :format => {:with => /\w+@\w+\.\w+/}
```

Making the user and list models was relatively simple since the list relationship was simply that it belongs_to a user. The user model needed a validation of a unique username and also that there was a username as this is the way that the user would login in the future. 
Also a secure password was essential so I just used the BCrypt function of has_secure_password as that seemed to be the simplest way. 

Getting the routes and views working was quite easy after watching some videos. I was able to use some rather simple code for this. 

I used the destroy method to delete a user's list and session.clear to delete the session when a user logs out.

Helper methods weren't as clearly explained in the curriculum as I would've like but I was able to Google some other sites that gave me some great explanations and some happy lines of code that I then used in my application controller.


```
self.helpers do

        def current_user
        @user ||= User.find_by(id: session[:user_id])
        end

        def logged_in?
            !!current_user
        end

        def authenticate
            redirect '/login' if !logged_in?
        end

        def authorize(list)
            authenticate
            redirect '/lists' if list.user != current_user
        end
    end
```

These helped me to be able to be sure that a user couldn't jump onto some other user's lists and manipulate them. I used these throughout my routes to make sure the lists were secured from other user's editing or deleting efforts.


All in all, I am happy with my website. It's functional and has all the required aspects and a few little extras. I plan to continue to work with it and make it better as I have time. 


