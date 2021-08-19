---
title: "Getting Going"
date: 2021-08-17T13:12:51-06:00
draft: false
tags:
    - brew
    - git
    - hugo
---

You have to assume that any blog that involves using a command line tool and pushing content to a code control system will have a few hickups involved with getting it going. Such is the case with this blog. The Hugo docs seem to be based on the assumption taht you are going to get Github to render the static html pages. So their explanation of the process involves creating a Github Workflow Action. That seems to be a bit too far into the deep end for me at the moment.

So there were a lot of steps I needed to do to get this runnning

**\#1 uninstall brew**

While my Macbook is *very* new, I transfered a lot of files from my old iMac and part of that was a very old install of [brew][brew]. I tried to get it to update itself but that just threw a lot of errors. Better to start fresh.

**\#2 install xcode**
brew wants xCode. I assume that it requires it to do builds. Seems unlikely that brew would have gvc installed on its own.

**\#3 install git**
This step was actually quite easy as xCode installs git. I just tested to make sure that it was working.

**\#4 install Hugo**
With brew working this was an easy step. I am attempting to do as much as I can from the Terminal and so all of my Hugo work so far as been via the CLI. Oddly the [Hugo Quick Start instuctions][HQI] are run from a Mac. Maybe this isn't all that odd for people currently doing Javascript and web development but coming back into this field and seeing official docs using the Mac is a surprise. 

Like many, many quick start guides online, the Hugo Quick Start is written without a lot of emphasis on explaining the command line commands and options that are being presented. And they also seem to assume that you are copying commands and pasting them in. I doubt that anyone thinks that the average user is going to type in

```
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke

``` 
I did but I am a bit odd and I am also trying to force myself to not use any shortcuts. I have been spending a lot of time looking through various quick start guides online for various tools and libraries and they all seem a little too 'quick' for my tastes. So this isn't really a fault with the Hugo docs but a general trend. 

**\#5 write a post and test**

This is again a very simple step. It is odd having to use the command line to create a blog post but once you do that you can open the Markdown file into any editor and edit it. The oddity is using Markdown in the first place. This just wasn't a thing when I was was first building websites and applications. It is interesting just how widespread the format has become and I suspect that it being used in git has helped to popularise it. 

Hugo renders the pages quickly and pops open a server to display my new, very local, blog. Then it [gets a bit weird...][weird]

[brew]: https://brew.sh "Homebrew actually"
[HQI]: https://gohugo.io/getting-started/quick-start/ "Hugo Quick Start"
[weird]: {{< ref "deploying.md" >}} "Deploying the blog"