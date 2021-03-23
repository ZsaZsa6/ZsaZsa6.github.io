---
layout: post
title:      "JavaScript As Art"
date:       2021-03-23 23:43:43 +0000
permalink:  javascript_as_art
---


JavaScript is much different than any of the other languages I have learned, but as a compiled language, it obviously has similarities to the other languages.
The syntax of JavaScript initially gave me problems but after practicing outside the Flatiron curriculum, I could identify syntax errors quickly. 
Building the basic API portion of the project went well, but once I added in the comments, I had to figure out how to combine the comments with the proper fast. During that process, I also needed to calculate the number of hours for the fast. 
I used a class method within the Fast model for this:
```
def calculate_hours
        final_time = self.active ? Time.now.to_time : self.updated_at.to_time
        fast_seconds = final_time - self.created_at.to_time
        fast_minutes = fast_seconds/60      
        fast_hours = (fast_minutes/60).floor
        fast_left_minutes = fast_minutes - (fast_hours * 60)
        return { hours: fast_hours, minutes: fast_left_minutes.floor }
    end
```

I then had to combine that return in a way that I could access the hours and minutes and still have the other fast attributes available. 
```
def index
        fasts = Fast.all
        new_fast_array = fasts.map do |fast|
            fast.calculate_hours.merge!(fast: fast)
        end
        render json: new_fast_array, include: 
        [comments: {only: [:fast_id, :content, :id]}]
end
```

    

The front-end was much more challenging and took a lot of fine-tuning. Being able to have the comments under the fast and making sure the correct buttons showed up at the correct time, made me really think about what I was doing to the DOM and just how to lay each function and each component out properly. This did take a little trial and error on my part.

I titled this blog post, “JavaScript as art” because although JavaScript has a specific syntax, the development of a project can be done a multitude of ways. 
Some students that I observed added items directly to their index.html file and built off of that. I put very little in my index.html file but chose to create elements in my js files. 
I saw videos where adapters were used and fetches were created right in the file, but I chose to have my fetches in one file and classes for Fasts and Comments. I called the fetch within my classes and used constructors to define those things that I would be using within that class. 
So, although there are some rules to JavaScript, it’s much like a work of art, each project will depend on the artist for the final project. 

The chart Class gave me quite a bit of headache. I used the JSCharting library but understanding how to put the data into the chart was very difficult. I reached out to fellow students but none had used that particular library. I finally went to my son for help and he was able to help me get the data to display in the graph. 
My original design was supposed to show the fasting and feasting hours but even after working with the graph for days, I could not get that to happen. The documentation on the website wasn’t very helpful in actually applying the data correctly. I did, however, figure out how to get the graph to only display 24 hours. I would like to figure out how to make the chart more clearly with both the fasting and feasting times and to stack them on top of each other. 

This project was definitely a learning experience for me and I do feel much more confident in my abilities in JavaScript. I am excited to move on to React and Redux and turn in my final project in Flatiron. 

