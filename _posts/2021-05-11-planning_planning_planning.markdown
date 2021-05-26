---
layout: post
title:      "Planning, Planning, Planning"
date:       2021-05-11 18:59:35 -0400
permalink:  planning_planning_planning
---

**A good plan brings a better result and a better process**

Cakes take a lot of planning. People who don't make and  decorate cakes, don't often realize how much planning actually goes into that beautiful end result!! You can try to just "wing it" but that often results in disaster!!

Before I ever start baking, I have to figure out how many cups of frosting and cake batter I need to make, and how much of each ingredient I need to have. I always make out a diagram of what sizes, shapes and colors of cake and frosting I need for each cake. I plan out the design of each cake and make sure I have the structural support I will need to pull off that design. I make sure I have the beautiful little final touches available, and make sure I have all the equipment I need for the actual baking and decorating. 
After getting everything designed, listed and calculated, it's time to go shopping!! Cake making starts with a plan, well before the oven is ever turned on!

### A good piece of software takes a lot of planning

I have tried "winging it" when making a cake and I have had several "caketastrophes"!!

When I began my first project, I had an idea of what I wanted it to look like, but because I didn't even KNOW really how to plan for it, I forced myself to JUST START CODING!! I have learned, over time, better planning equals a better process and a better project. 

To plan for this React/Redux project, I discovered Figma and drew out (in very basic form) what I wanted each part of this app to look like. As I began to start building, I constantly went back to my framework, sometimes finding that some of my planning would not be coming to fruition during the time I had for this project.

 I also learned that sometimes a simple ingredient that I would normally use, needed to be switched out for things to continue on smoothly.  Just as baking soda and baking soda are not interchangeable, ` ==  ` and `===` do not work exactly the same. When comparing an id from JavaScript to the id of a JSON object, which comes through as a string.  `===` stands for "exactly the same", while `==`  compares their meaning.  
 
 For instance, in this piece of code: 
 ```
 game: state.games.games.find((game) => game.username === match.params.username)
```
 
 The match works correctly with `===` because both are strings.
 
In this piece of code a line before the line that sends the warning will allow things to continue to move along,


```
const mapStateToProps = (state, {match}) => {  
  return {
    // eslint-disable-next-line 
    challenge: state.challenges.list.find((challenge) => challenge.id == match.params.id),
    
    loading: state.challenges.loading,
  };
};
```

 
  
 
 
 Although React will throw a little warning upon hitting that comparison, the show will go on and that warning can be avoided by adding `// eslint-disable-next-line ` above the line where the comparison is used. 



Ruby and Rails is like baking bread--there are some major rules. You must follow them or your product will simply not work. 

JavaScript and React --- you still gotta know the rules but you can cook, bake, sweet, savory, just make sure you know what each ingredient is doing and how you need to use it!! Don't forget how to use JSX and always look to your DevTools to help you see what data is coming through, what actions are happening and what type of data is being returned so you can properly manage it.

After all the planning, you gotta do a tiny bit of trial and error, especially when you are icing the cake!! CSS is like the icing on the cake, the prettifying of the project.  I used Tailwind in my project and although the inline CSS looked a little messy, it allowed me to change each element individually. 








