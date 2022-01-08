---
title: "Templating"
date: 2022-01-08T12:15:39-07:00
draft: false
tags:
    - javascript
---

Sometimes you do things that you are inordinately proud of despite their real lack of complexity.

![Handlebars abound](/template.jpg)

For one of my earlier projects I used JSRender as a templating system. The data I wanted to render was fairly complex and I also needed to integrate it with a view controller so JSRender was an easy choice.

My current project doesn't require the level of complexity that JSRender provides so I went out looking for a simpler templating system. There are quite a few that potentially fit the bill but they all included features I didn't need. So I [followed some advice](https://jonsuh.com/blog/javascript-templating-without-a-library/) I found online and built my own. 

I built a series of templates using the `template` tag and then iterated over the data and used the `replace` method and some RegExp values to do the work. It doesn't do much other than the exact things I need for this project but its also 3K without being minified and it is also simple to use.

```javascript
let shipHTML = shipRender.renderHTML(this.shipTemplate, thisShip);
```

I know it isn't that big of a deal but it just makes me happy every time I see the templates and the code. 