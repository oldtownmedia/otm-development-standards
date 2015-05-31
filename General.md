---
layout: page
title: General 
permalink: /general/
banner: banner_general.jpg
order: 3
---

## Compiling

```html
 -- source maps
 -- js
 	-- linting
 -- naming
 ```
 
## Performance

### Tools to find performance issues

There are several publicly available tools to help find performance issues or bottlenecks. We use several to identify potential issues - below is a comprehensive list of the best tools to analyze performance.

[Pingdom](http://tools.pingdom.com/fpt/)<br>
[GTMetrix](http://gtmetrix.com/)<br>
[Webpage Test](http://www.webpagetest.org/)<br>
[Google Page Speed Insights](http://developers.google.com/speed/pagespeed/insights/)

### Compressing images

No amount of CSS & JS performance will make a dent in a slow-performing site if you have too many or too-large of images. Therefore, any images that can be compressed be reduced as much as possible. This can take place locally or with an external tool like TinyPNG.

[TinyPNG](https://tinypng.com/)

### Concatenation

CSS & JS files should be compressed & contacted to serve as few files as possible in production. It's easiest to run this concatenation on the production site so that you can still test without concatenation and identify any potential issues. 

### Caching


