---
title: "Javascript OOP Is Odd"
date: 2021-09-02T09:24:11-06:00
draft: false
tags:
    - oop
    - javascript
    - director
    - lingo
---

I am by no means an expert in OOP. I know how to use it and I know some of the concepts but I couldn't tell you anything about polymorphism or abstraction but I know that I use them. Way back in the olden days when I was writing Director code in Lingo I wrote my projects almost exclusively using objects. In fact I doubt that I could have written a project without using objects of some type since it became a fundamental of my coding style and my workflow. 

I suspect that this is one of the, many, reasons why I found php to be such a PITA to work with. I am not sure how it works now but at the time any sort of class structure in php was non-existent. Or at least the php-gurus that I worked with didn't seem to know or use it. Cold Fusion was similarly OOP deficient but it had many, many systems for encapsulating code in a manner that was similar to how you would encapsulate functionality in OOP classes.

OOP in Javascript appears to be, in my partially informed, opinion a bit of a dog's breakfast. First off, there are 'objects' in Javascript that are really just property lists. 

```javascript
const car = {type:"Fiat", model:"500", color:"white"};
```

I am not sure why these are referred to as 'objects' as they certainly not from my perspective. Where I think they become more of a standard object is the use of  `prototype` but the entire process seems pointlessly complicated which is usually a hallmark of features added to a language on an ad-hoc basis. 

Classes were added to Javascript in ES6 and they are certainly a step closer to the OOP coding that I am used to. The main problem is that classes in Javascript have no way to refer to themselves. The bane of classes in Javascript is the `this` keyword. It is always relative to the context of the current code execution and so if you try to access code outside of the current classes context then `this` suddenly points to a different reference and you can't access your properties or methods any longer.

Javascript doesn't have a means to provide the class a reference to itself so that it can always access its own properties. In [Lingo](https://en.wikipedia.org/wiki/Lingo_(programming_language)) we had:

```
on new me, <arguements>
```

When the object was instanced it was provided with a reference to itself and as a coder you then used that to refer to the object and its properties. 

Javascript classes are in their relative infancy compared to methods like `prototype` and objects and so it makes sense that they are slightly limited. Currently they work best when all of their functionality is encapsulated and the code doesn't need to do any asynchronous operations. Those will definitely mess you up when you try to access class properties. 

My current project uses quite a few Javascript classes but mostly as ways to encapsulate operations on the UI or the underlying data. Despite them not being as robust and flexible as other classes systems I have used in the past I find their availability very useful since it allows me to work in a system that I am more comfortable using. 

I still think they are f*&king odd though.