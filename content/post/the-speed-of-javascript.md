---
title: "The Speed of Javascript"
date: 2021-09-01T11:45:16-06:00
draft: false
tags:
    - javscript
    - jquery
    - JSRender
---

I still have difficulty comprehending the speed at which Javascript runs in the browser. Part of the speed is due to the processors that our computers are running. A more significant amount of the improvement though is the capabilities of the [Javascript engines](https://en.wikipedia.org/wiki/JavaScript_engine) that are being used in browsers as well as the advent of [JIT](https://en.wikipedia.org/wiki/Just-in-time_compilation) in those engines. 

It has dramatically changed not only what you can do in a web-based application but how you do it. It is such a stark change from how we used to write apps that I even have difficulty trying to describe the differences. 

I am working on a web-based application at the moment that reads a series of JSON files, stores the data in some class files and then builds UI elements and renders HTML using JQuery and JSRender in the browser. I am loading a library, JQuery, which is then used by a second library, JSRender, to do all of this UI building. I doubt that either library would have run in browsers when I was first building apps. We used to avoid Javascript because of speed and cross-platform issues and now it is all I need to code an entire application.

It just staggers the imagination really. 