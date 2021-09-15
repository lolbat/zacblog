---
title: "A New Project"
date: 2021-09-15T16:29:40-06:00
draft: false
tags:
    - electron
    - codemirror
---

So my current project is coming to a close and I am on the lookout for a new one to start working on. My current obsession is a game called [Conquest of Elysium 5](http://www.illwinter.com/coe5/index.html) and it has a modding system that is simple enough that even an old coot like myself can partake. 

The code for the mods is created in a single text file and all of the images used are in `.tga` format and stored at the same directory level. There are also some additional graphics for displaying banners in the Steam store and in the app when you load the mod. Finally there is a single text file to make the mod publicly visible in the Steam Workshop.

So my next project is going to be a mode editor for the game. I will use [electron](https://www.electronjs.org) to do the cross-platform development and implement the [CodeMirror](https://codemirror.net/6/) to display the code and also enable a build process so that coders can make it easier to write a mod and then build it for release.

### Ta Dah!

![a comp](/zacblog/comp.jpeg)

So this is what I imagine an initial version would look like. It is taken from a screenshot for the [Atom code editor](https://github.com/atom/atom) and I have added some code from the *War in Heaven* mod as well as my idea of what a project directory structure would look like. 

#### Goals

##### Includes
So my basic idea is to create a code editor that will create a standard project directory that a coder could then use to help organize their work. Currently all of the data for a mod is in a single text file and for a large mod that can be hundreds of lines of code. The aforementioned *War in Heaven* mod has 302 lines of code and I suspect that it is not the largest. This is clearly an accident waiting to happen and so the first thing I want to do is create an include system in the app so that it can let you write out code in smaller parts and then include them in a main file. Then when you build the mod it would create a single file from all of the includes. So instead of 75 lines of new rituals in your mod you could have a `main.c5s` file that had a single line
```javascript
@include rituals.c5s
```
This would entail one or two editor specific file extensions to make it easy to distinguish between the editor's files and the file you need to include with the mod.
##### Directory structure
To keep everything simple the editor would also use a build directory to write out all of the files for the final version of the mod. This way any structure that the editor uses won't cause problems when creating the mod for delivery. So in the comp above you can see that there is are `src`, `build` and `img` directories but when you do a build all of the content would be copied over to the build directory. So your organization doesn't impact on the build and the requirements for the build don't impact any structure you want to put on your code and assets.
##### Autocompletion
The game's mod system includes commands such as `destroyterr`, `noportalreq` and `nonearby1req`. They are all lowercase and they are all typos waiting to happen. CodeMirror makes it easy to add autocompletion and I also want to see if it is possible to add parameter completion as well so the editor will know that `flymode` requires a number and that number is from a table of possible values.
#### Is that all?
Well for the moment it is.
There are a lot of things that could make this a nonviable project. The game's authors could say no or the mod writers themselves could just shrug and not think it was worth the effort. I am going to be posting a link to this blog post on the Steam Community forum to get some feedback from people but I will probably start building the basic structure of the app in the next few days.
 

