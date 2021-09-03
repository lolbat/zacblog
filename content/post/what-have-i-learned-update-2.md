---
title: "What Have I Learned - Update 2"
date: 2021-09-03T09:49:51-06:00
draft: false
tags:
    - jsrender
    - jsview
    - oop
    - node
---

Well it has been a busy week. Lets have a look back at all of the new things I have 'learned'[^1] in order to get my web application up and running. 

#### JSRender and JSView

So the biggest thing for me was learning to integrate [JSRender and JSView](https://www.jsviews.com) into my web application. I can't get over how well they work and also how easy they were to use. I am not really stressing either library but I took the HTML creation for a fairly complex display and turned it into a template and took the code needed to create it into one line.
```javascript
this.template.link(unitRenderElement, unitData);
```
The library is very fast. On my TODO list is a task to simplify one of the renderings I am doing since I have made it less effective than it could be. This is because I am iterating over an array instead of just sending the entire array to the template. 

The real magic was getting JSView to work. I needed to do some reworking of my code (a slight tweak really) to allow me to render the content using the `.link` method instead of the `.render` method. The template was tweaked to change the coding for the elements that the render engine was creating and I then just needed to make changes observable to have the new values displayed in the views.
```javascript
$.observable(thisUnit).setProperty("productCost", newCost);
```
I have to go back into the template and 'hook up' all of the items that will need to be observable but the hard work has been done. And by 'hard work' I mean linking up some libraries. Someone else did the real difficult work. 

Both of these libraries have dramatically changed the application. The code I am writing is a lot less complex as well as lower in quantity. I was able to delete about 100 lines of code that I had written previously to track data changes and display them. It was not pretty code and it is good that it was replaced. 

#### Javascript Classes

As I alluded to in a previous post, I have been working on taking functionality in the application and encapsulating it into a series of classes. I have a model and view class to store and display the data I am working with. I have another class to manage access to all of the data available and two more to deal with access to specialised data that is restricted based on some in-application definitions.

When I first learned to code using objects I was put into a situation where I was required to encapsulate a lot of functionality and data due to the restrictions of the development environment that I was using. It was a necessary requirement but I also think that it made my code better. So I am quite happy that I have been able to bring this coding style to Javascript development with classes.

#### Node

I don't think that I have really scratched the surface of Node but I have a better understanding of what it can do for me as a developer and also how to use some basic features of it. I wrote some tools to parse the JSON data that I am using into specialised formats based on the type of data in the file. One of the helpful [Miller][millerlink] developers provided me with some command line options to do the things I needed to do to the data right in the command line but the string was as long as my arm (as these things sometimes are) and it really isn't a feasible option for me given my issues with reading. So I built some Javscript code that uses Node to read files in, process them and then read them out again. Huzzah.

I am looking forward to learning some more about Node and how to use it to build more of my own tools. 

#### Shell scripting

Given the number of grey hairs I have you would assume that I was already experienced in shell scripting but aside from writing some `.bat` files to load Quake maps a long, long time ago I have really not had a need to use shell scripts. Since I have a large number of csv files that need to be converted into JSON files I wrote a shell script to do that very thing. I reads in the directory of .csv files and then create a new filepath for the results and sends the csv filenames and new filepaths to a node library to do the conversion. Huzzah again. 

#### Up next

So I have a fair bit of code to write to fill out the features for the initial release of my web application. Once that is ready to go I need to figure out a tool to build the web application with just the files I need so [webpack](https://webpack.js.org) or something like that.  I am also going to look into learning some more git command line options since it is a bit of a PITA to load Github Desktop every time I jsut need to push files to Github. 

[millerlink]:https://github.com/johnkerl/miller

[^1]: Obviously I have scratched the surface of a lot of things but I have learned some of the APIs and information available.