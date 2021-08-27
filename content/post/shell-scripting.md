---
title: "Shell Scripting"
date: 2021-08-27T11:49:01-06:00
draft: false
tags:
    - csv
    - json
    - csvtojson
    - node
    - bash
    - table tool
---
So I didn't wait to get other work done and went ahead and built the shell script to automate converting all of my csv files. I did a few stackoverflow searches to find some information about getting filenames into a shell script and then iterating over them. I also had to look up how to determine the filename without the extension as I had to create a new .json filename for the output file. The script itself is wildly simple

```shell
#!/bin/sh

csvfiles=`ls *.csv`

for eachfile in $csvfiles
do
   noext=${eachfile%%.*}
   echo "./json/raw/$noext.json"
   node /usr/local/lib/node_modules/csvtojson/bin/csvtojson ./$eachfile > ./json/raw/$noext.json
done
```
The kicker in writing this was determining that I had to use `node` to call the csvtojson library and also that I needed to provide the full path to the binary file. 

So this shell script will get a list of al the .csv files in the directory and then send the filename and the new json path to csvtojson to get it to convert and output it. 

#### Table Tool

I also decided to ditch a spreadsheet app for editing my files and downloaded [Table Tool][ttlink] to do my edits. I will still need the spreadsheet application to create the initial files since the data I am working with is coming from a third-party Excel sheet. Once I have it in .csv format though I will just be using Table Tool for any edits I need to do.

[ttlink]:https://github.com/jakob/TableTool
 