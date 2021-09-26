---
title: "Shut it down!"
date: 2021-09-26T09:05:28-06:00
draft: false
tags:
    - jsrender
    - bootstrap
    - jquery
    - json
    - jsonpath
    - conquestofelysium
---
Sometimes you just have to say [Shut it down!][youtube] and move on.

I spent the better part of the week working on creating a browser for the modding commands for Conquest of Elysium 5. I had the data for the commands built into a nested JSON file. I built a template for JSRender that took the data and created a collapsible tree menu that let you browse the command structure and then view individual commands. And I was just starting to work on pinning individual commands to a sidebar when I looked at it and realised that no-one would want to use it. 

**Shut it down!**

So I scrapped it all and started over.

It wasn't a total loss. I did manage to learn quite a few new things. 

### New things

**JSONPath**

I did manage to not only learn the [JSONPath library](https://goessner.net/articles/JsonPath/) but I built a small test file that would let me work out the pathing structure to get the data that I wanted. 

```javascript
// we need the subcategory data to get the correct command data
let xpathString = `$.categories[?(@.catname=='${category}')].commandData.subcategories[?(@.subcategory=='${subcategory}')].commands[?(@.name=='${commandName}')]`; 

objResult  = jsonPath(jsonDocumentData, xpathString);
```

It looks like a mess but I was using it to take the structure data from the tree menu and then pull out the individual JSON object for a specific command. The JSON data was structured to make a good tree menu but that didn't make it easy to parse traditionally. The JSONPath library made that a lot easier to do. 

**JSRender**

While I am familiar with JSRender, this code required me to figure out how to pass data from one content to another inside the same template. When you use a `{{for}}` tag in JSRender to iterate over a subsection of the JSON code it create a new content and so if you need to access a key value within that tag you need to pass the data to the new context.

```javascript
{{for subcategories ~topCategory=parentCategory}}
```

Something that is very handy when you are working on a tree menu. 

**Bootstrap**

I am learning a lot more about grid and flex layout using [Bootstrap](https://getbootstrap.com/). The structure of this scrapped implementation and the new one require sidebar that fill that browser as well as columns that fit in a system where the rendered HTML content isn't know in advance. I have also been using many more of the Bootstrap classes to do positioning. I'm even starting to figure out how to predefine how the layout breaks in a responsive layout. 

So while it was a bit of a PITA to realise at the last minute that the code wouldn't be usable, it was fun to learn some new tricks and expand my understanding of some of the tools I am already using.

[youtube]: "https://www.youtube.com/watch?v=CJ8cjlEMLR0" "30 Rock Shut it down compilation"