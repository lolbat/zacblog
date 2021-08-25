---
title: "Using Node to build CLI tools"
date: 2021-08-25T15:46:55-06:00
draft: false
tags:
    - node
    - json
    - miller
    - javascript
---
So I have been working with various command line tools and apps to try to build a workflow to let me take csv data that I export from a spreadsheet and turn it into JSON. This actually isn't too difficult and there are a lot of tools, like [Miller][millerlink], that will let you take csv and monkey with it. It has a **lot** of options but many of them seem to be tools to work with CSV, or similar, data and not a lot of them seem to be options for JSON. 

One thing that I need to do is to take the JSON that results from my csv export and then 'massage' it a bit to create a more logical structure for the data. I was hoping that I could do this in Miller but even i fit had the options I need I have to work with quite a few key names and I don't want to have to do that in the command line. Frankly I am not that good a typist and I have a slight reading disability. The command line is not my friend.

Quite a while ago I wrote some Javascript code to do some data modelling. It was simple code and I just needed it to run and spit out the results. I have [node][nodelink] installed and so I ran the files in the Terminal using node.

I don't really have a lot of experience with node and so when I ran into a wall looking for existing tools for my workflow I decided to look into writing some Javascript code to do the work for me. Node has a quick method for creating command line tools but since I only really need this code for this specific project I decided to skip them and use node as a means of running my Vanilla JS code.

I was decidedly easy to incorporate the node file system code and within a few minutes I had a tool that would run from the command line, take a file name and then reformat the JSON code into a new format for me. 

The scariest thing is that this code ran correctly the first time. I can't recall the last time that happened. 

So now I can use miller to create the JSON files and then pipe the results to my Javascript code to finish the processing. 

[millerlink]:https://github.com/johnkerl/miller
[nodelink]: https://nodejs.dev