---
title: "I heart Codekit"
date: 2021-11-26T15:43:47-07:00
draft: false
tags:
    - CodeKit
---

![Building a page with imports](/codeKit.jpg)

The sign of a good tool is that it enables you to work in ways that you hadn't thought of. I am a big fan of  [CodeKit](https://codekitapp.com). It lets me work with a number of command line technologies through a GUI interface and it makes it easy to not only use them but also to put in exceptions to those apps and your build process for occasions when you have files that you don't want or don't need to minify or lint. It is the main reason why I have not needed tools like [vite](https://vitejs.dev) and [parcel](https://parceljs.org). CodeKit does it already and in the case of Parcel it does it without objecting to the JSRender templates I use.

One of my favourite features in CodeKit are [kit files](https://codekitapp.com/help/kit/). The CodeKit website describes them as:
> Kit adds two things to HTML: **imports** and **variables**. CodeKit compiles Kit files into HTML, so Kit is ideal for static sites.

This is a dramatic over-simplification. 

The current project I am working on is an attempt to take an old HTML and Javascript SPA and make it responsive. Not so much that you can use it on your phone but enough that it will work comfortably on a tablet. It is a very data intense application. The underlying code, both HTML and Javascript, is very good but the main index.html file has 921 lines of code. Trying to work through that and build responsive, grid-based code around it would be a nightmare.

That is where the `.kit` files come in. As you can see in the image above, I broke the structure of the page into several logical sections and made each of those its own `.kit` file. Several of those sections were still very large so they had their own `.kit` files that build out a single HTMl component that is imported into the main page.

It is now easy as pie to build some HTML and CSS code around those imports and move sections of the code into columns as they are built. I wouldn't want to even think of doing that with 921 lines of HTML code. In fact, I have had to do that very thing in the past and it was a nightmare. 

And I am only scratching the surface of what you can do with them. I could certainly do this with other tools but it is just do darned easy with CodeKit. 