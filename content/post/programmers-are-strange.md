---
title: "Programmers Are Strange"
date: 2021-09-08T15:16:12-06:00
draft: false
tags:
    - javascript
---
It is sometimes odd to be a coder. Perfectly acceptable code gets changed into 'leaner', 'more precise' code after hours of tweaking and reading docs. 

I spent a part of the day trying to figure out the best way to streamline some code I had.

```javascript
let commanderTest = true;
if (item.restrictions["commander"] ) {
  commanderTest = characterTypes.commander;
}
```
So the code checks to see if the item we are processing has a restriction and if the unit we are attaching the item to has that quality. The code assumes that the unit passes the test and then it looks to see if there is a restriction and if so if the unit has that character type. It is pretty simple and it is three lines of code.

I couldn't leave it like this though. I pondered it while I was doing errands this morning and then finally replaced it with a ternary operator.

```javascript
let commanderTest = (item.restrictions["commander"] ? characterTypes.commander : true);
```
The really crazy thing is I normally hate code like this. I think ternary operators are an especially pronounced example of code structures that tend to be unreadable. And yet here I am using one. 

I could understand doing this if the application had to process through a lot of data but in this instance it has to test, perhaps, twenty items. The code doesn't need to be this focused. And yet here I am doing it.

Programmers are strange.
