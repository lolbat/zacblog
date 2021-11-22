---
title: "Classes"
date: 2021-11-22T11:32:32-07:00
draft: false
tags:
    - javascript
    - class
---

If I never have to work with a database again it will be a joy.

I don't dislike them so much as I am just *#@&^ing* tired of dealing with them.

So when I started [a document viewer for Conquest of Elysium](https://coe5alamanc.netlify.app) I decided to avoid a database and just store the data locally. This not only simplifies the hosting situation but it means that people can update the content using much simpler tools and even do it offline. Currently the data and the web app are in different repositories but I hope to rectify that soon. 

In its initial instance, the app loaded a large number of JSON files and then let the user browse. Those files were then used to render tables which were displayed using [Datatables](https://www.datatables.net). Nothing complicated but I really didn't like how the code was structured. Either did eslint but that is another story. I was planning to replace Datatables with [SlickGrid](http://slickgrid.net) but I had already built the data structure for the documents and it would have required a total rewrite since SlickGrid has a much different way of rendering data.  That is still in the cards but it will require removing the rendering code since SlickGrid can use the JSON files directly and without JSRender I don't need jQuery so there would be a lot of code to pull out and replace.

### The Problems

The code to load the JSON files was in the `core.js` file and it required there to be several variables floating around without any reference to what they were or where they were used. It also meant that the class file I had to manage the data was passively receiving the data. Not necessarily an issue but the structure felt wrong. My original intent was to encapsulate the code to load the JSON files but in the end it was just easier to put all of that code into the data class.

I also started to generate .html files for display. These were created because they had a lot of lists and also had text content that didn't necessarily fit into a structured data format. 

So I decided to rewrite the app so that it loaded all of the data, JSON and .html, externally but only did so when the user requested it. The idea is that eventually there will be a lot of data and it didn't seem right to have the user wait to load it all if they only really wanted to view a single document.

### Classes

I was using a class for the data management in the initial version but this new version does two new things. First, it subsumed all of the data loading into the class and secondly, it loads its own class to help display dialogs to the user. Since the main code never needs to display a dialog it doesn't load that class and is effectively ignorant of it. 

Classes in Javascript seem to be a work in progress. The main issue with them is `this.`. It is contextual so if your class has code that does an asynchronous load of some external data then you have to work around the fact that `this.` will mean different things inside and outside your async calls. 

This code will generate an error when you run it. 

```javascript
  $.get(filePath)             
  .done(function( data ) {
    this.storeDataResult(data);
  })
```
In terms of the call to the jQuery `.get` method, `this.` is a reference to the document window and not the class that the code is running in. So in order to have this work correctly you have to store a reference to the correct scope for `this.` before calling the method.

This code will work.

```javascript
let me = this;

$.get(filePath) 
  .done(function( data ) {
    me.storeDataResult(data);
  })
```
And it has the added bonus of letting me use `me.` in code again.

### Documentation

This is a minor issue but it is made more problematic by two issues. Javascript documentation online hasn't caught up with the changes in Javascript and so it is difficult to find docs that talk about using classes in the manner that I am using them. As well, a lot of online technical documentation is frankly no good. It is good on the technical side but when it comes to explaining how to use things it often falls down. I could find a lot of instances of Javascript class docs that don't really deal with "real world" examples of using classes. 

So you can find out how to declare them or how to subclass them (as an aside, why the %^&* are programmers so fixated with subclassing?) but not how to use them in an app and import them correctly. Or how to deal with contextual referencing in classes.

It also doesn't help that there is a lot of crap content online and that search engines seem to think that a nine year old StackOverflow thread is more relevant than a six month old blog post. That is an entirely different rant though.

### tunnel.push(light)

So in the end I did get it working. The classes are imported correctly and the behaviours I wanted encapsulated are, in fact, encapsulated. The main code of the app is so very much cleaner and easier to follow. And I learned many new things. Which is really the point of all of this. 

My next tangent is going to be building some command line Node tools to read and parse binary data. That is going to be a lot of fun. 