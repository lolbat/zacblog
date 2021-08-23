---
title: "Using JSON"
date: 2021-08-23T10:12:57-06:00
draft: false
tags:
    - JSON
    - XML
    - Lingo
---

The problem of serializing data and then importing it back into your application is very, very old. I remember [Andy White][awhitelink] and a few others discussing approaches to this in Director twenty years ago. Andy came up with some code that could do it in Lingo and then XML became a thing[^1] and we all started using XML for serializing data. Andy, being Andy, came out with a better, and faster, XML parser than Macromedia did. And he did it before they released their official code. Always an amazing coder.

Javascript has support for its own native format to do this, [JSON][jsonlink], which is much [better than XML][xmlcomp].  Having had to work with XML and even XSLTs I can attest to the ease of use that JSON provides.

![pretty JSON display](/JSONOutput.jpg)

What I really like is that you can still store values in their native format so you don't need to post-process your data to convert it into something that is easier to code with. This was always a bit of a PITA with XML and 'DIY' solutions. I don't want to have to convert a value to a `boolean` or an `int` before I test it. The application that I am working on is for a game and it has hundreds of individual entries that all need to be stored and potentially edited to correct errors. 

Currently that data is stored in a spreadsheet \(why don't people use databases?\) so my current task is to create a workflow to take all of that data and format it into JSON files. Now I could do a simple straight export of the data and create a flat object but I want to compartmentalize some of the data so that it is stored in semantically logical arrays. 

```json
{ "name": "Dwarf Prince",
   "stats": {
   "activation": 4,
   "move": 5,
   "fight": 3,
   "shoot": 0,
   "defence": 11,
   "combatDice": 2,
   "health": 2,
   "points": 165
    },
   "hero":  true,
   "spellcaster": 0,
   "magic": true,
   "min": 1,
   "max": 1,
   "equipment": "Hand Weapon, Shield, Heavy Armour",
   "special": "Command (1), Champion, Shielding (1), Magic Items"
 }
 ```
It all looks 'flat' when you view it as a text blob.

I want to be able to access data in logical units in my code and then have that code inform me of its purpose when I come back to it at a later date.  I think this

```javascript
armyUnit.stats.move
```
is a much better way to approach code as well as the underlying data. Maybe I have just had to go back to too many five year old projects but I want to write code in a way that helps me, or someone else, understand it.

I am still working on how to format the JSON and so this isn't a final format. I may move some of the data into another list but that might also depend on how it will be used and displayed in the app. Some of the data is just there as a reminder for the end-user of the app and so it can stay in a comma delineated string. 

Now I just need a way to process all of this data. 

[^1]: I told you I was old

[awhitelink]: https://twitter.com/pixeltrix ("Beware! Twitter!")
[jsonlink]: https://en.wikipedia.org/wiki/JSON ("Isn't wikipedia great")
[xmlcomp]: https://www.w3schools.com/js/js_json_xml.asp ("A succinct explanation")

