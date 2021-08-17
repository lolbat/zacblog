---
title: "Deploying"
date: 2021-08-17T15:29:15-06:00
draft: false
---

So it works locally. Now how do we get it to Github?

My first problem is that the repository is private. I need to make it public so that Github Pages will allow me to host it using the free plan that I am using. 

Hugo defaults to building all of your static content into the `/public` directory and Github pages, which assumes that you are using [Jekyll][jk] wants to find everything in the `/doc` directory. Not a problem but my first build was into the `/public` directory so I need to use the `publishDir` configuration directive and change the location.

I assume that it is a caching issue but this causes me no end of problems as the files get posted to Github and the site created but the server isn't looking in the `/docs` directory even when I build into it. 

I do manage to get that resolved but it involves me fussing with a Pages setting in Github and pushing new content far too many times. My hope is that this is all now resolved and I can use the blog without any issues.

I am using the directory that Github wants to use to make my life easier and the folks at Hugo think that the best solution is to [deploy using a Github Action][deploy] which seems overkill for a blog with some static html pages. Maybe one day I will get there

[jk]: https://jekyllrb.com "Another static site generator" 
[deploy]: https://gohugo.io/hosting-and-deployment/hosting-on-github/ "Holy heck!"
