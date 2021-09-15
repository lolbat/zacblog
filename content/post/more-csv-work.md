---
title: "More csv work"
date: 2021-08-27T09:12:43-06:00
draft: false
tags:
    - csv
    - json
    - node
    - miller
    - CSVTOJSON
---

I finally managed to finish my csv to JSON workflow. I originally tried using[Miller][millerlink] to export my csv to JSON but it didn't provide all of the options that I needed. I managed to find a node library called [csvtojson][csvlink] that had all of the tools I needed. It also lets you edit the header names to create [nested JSON data][nestedlink] in a way that I needed as well. I will be keeping Miller handy though as I will have more csv work to do in the future.

The library can be used in node but it can also be run as a command line tool and that is how I am currently using it. Despite being able to do nested data I wrote my own node code to do that processing for me. Most of the files I want to process have quite a few fields that need to be nested and I don't want to modify the spreadsheet headers since those will ultimately be public facing and the nesting format is easy to understand but would be a PITA in a spreadsheet.

The node tool I wrote turned out to be surprisingly easy to build. Node is not a difficult as I thought. I have two sets of key/value pairs that I want to put into a nested array and then delete the original keys. As well, I have a replacer function that write out the boolean and integer values in the file without the double quotes. I am doing this to make it simpler to use the data in my web application. 

So now all I do is export the data from my spreadsheet and then call the csvtojson library and pipe the results to my node tool which then exports the final file. Once the first version of the web app is ready for public testing I will go back and create a bash shell script to process all the csv files and then copy them to the deployment directory.

 I have two other JSON files that I create but since they are singletons I am using the nested feature in csvtojson to create those and then running another process to strip the quotes from the booleans and integer. 

[millerlink]:https://github.com/johnkerl/miller
[csvlink]:https://github.com/Keyang/node-csvtojson
[nestedlink]:https://github.com/Keyang/node-csvtojson#nested-json-structure