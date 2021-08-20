---
title: "Building a Page"
date: 2021-08-20T10:59:46-06:00
draft: false
tags:
    - codekit
    - coldfusion
    - php
    - javascript
---

I don't know about how it works now but when [ColdFusion][cfwiki] was stilled owned by Allaire I really enjoyed using the language and the coding tools. Macromedia purchased Allaire in 2001 and it was all downhill for the language at that point. I was sadly done using CFML before Adobe came into the picture but I can't imagine that they made anything better.

There were any number of things that I liked about working in ColdFusion but the one thing that really made an impact was your ability to compartmentalise code into external files and either include them directly or make calls to them. It let you build very clean and simple pages. Program logic was easily split off from display code and a CFML page could be quite small.

I think for me that the most important thing was that this made pages easier to understand and easier to work with. I could find a small include and work on that and not have to worry about wading through 100+ lines of HTML. And since the companies that I worked at used code versioning systems it also meant that I didn't need to halt work on a section of the website just to make a small change to one component. 

I am one of those [people that don't like php][phplink]. For most of the usual reasons. When I stopped working in CFML I effectively stopped doing web development because of the choice of languages that were available at the time. Ruby came onto the scene just as I was leaving it so it offered no succor for my language related pain.

I did use php from time to time but mostly just so I could use php includes to create smaller html components that I then controlled using Javascript. Now I know that I could use [ES6 Modules][es6] and that might be something that I look at in the future as I continue to expand my Javascript skills. 

What I am currently using, and will for the foreseeable future as it rocks my world so much, is [CodeKit][codekitlink] for the Mac. ES6 Modules will certainly help to make my code cleaner but CodeKit helps keep the entire project cleaner. I can build HTML components and import them into the `.kit` files that CodeKit uses. Currently I have files for my css and js includes as well as my navbar, footer and any text that is in an HTML page. I also break the HTML in my files down into logical components and then create separate files for them.  For a large HTML file this can be a godsend since it can take a large amount of HTML and make it much simpler to work with.

```lang-html
    <div class="container">

      <div class="row align-items-start">
      
        <!-- @import '/components/column1_index_comp.html' -->
        
        <!-- @import '/components/column1a_index_comp.html' -->
        
        <!-- @import '/components/column2_index_comp.html' -->
        
        <!-- @import '/components/column3_index_comp.html' -->
      
      </div> <!-- row -->
    
    </div> <!-- container -->
```
It also meant that when I wanted to move some of the columns into a different order and break them into distinct columns that I again didn't have to wade through a huge HTML file.

I am restarting an old project and one of the first things I am doing is using CodeKit to break the HTML files into more manageable pieces. It is an absolute joy to do and I suspect that it will also make the project easier to work with.

[cfwiki]: https://en.wikipedia.org/wiki/Adobe_ColdFusion "A wiki article about ColdFusion"
[phplink]: https://www.jesuisundev.com/en/why-developers-hate-php/ "I am not alone"
[es6]: https://exploringjs.com/es6/ch_modules.html "Look a lot of verbiage!"
[codekitlink]: https://codekitapp.com "I loves it soooo much!"