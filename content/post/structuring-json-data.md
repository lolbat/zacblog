---
title: "Structuring JSON data"
date: 2021-09-22T12:26:18-06:00
draft: false
tags:
    - json
    - jsonpath
    - csv
    - jsrender
---

My new project has a lot of text data that is available in a `.csv` and spreadsheet files but not in any more useful format. I took the `.csv` data I had an created a sqllite `.db` file so I could use it to generate some queries to create a `.json` file which I will use to display the data but also to create the menu system.

The original data is the modding documentation for a game. It has been produced in a bit of an ad-hoc manner by the developers and so the structure of it is *odd*. None of this is problematic in and of itself but it does mean that there are categories of modding commands that have sub-categories and some that don't. I can't imagine that this is going to be a serious problem but I will have to create some conditional code in the JSRender templates that I build. In order to make that easier to do I created a structured `.json` file that has some meta-data about the categories so I can test and access that to make it easier to build menu.

There is a top-level node that has the name for the document, the version and then a holder for all of the data.

```json
{
	"docName": "CoE 5 Modding Commands",
	"version": 5.06,
	"categories": []
}
```
Each category has its own object in the `category` array.

```json
{
    "name": "Weapons",
    "hasSubCategories": true,
    "subcategoryList": ["Basic", "Chained", "Effects", "Special Attribute", "Start"],
    "data": []
}
```
I created a `hasSubCategories` key that stores a boolean so I could test that in my template and also denormalized the subcategory names so I could iterate over them without having to access all of the objects in the `data` key. The content in each `data` key is going to vary wildly and so anything I can do to make it easier to process the menus and then let the users navigate to the data the want will make the app work better.

The same file will be used to display the data on each individual command but I will be using the [jsonpath library](https://goessner.net/articles/JsonPath/) to access the data. I will add some data attributes to the menu system and then read those when the user clicks on a menu item to display the commands available. Jsonpath will not initially give me any functionality that I can't get with standard object access but it will let me build in search features at a later date.
