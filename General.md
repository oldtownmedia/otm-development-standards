---
layout: page
title: General 
permalink: /general/
banner: banner_general.jpg
order: 4
---

### Development Cycle

#### Local development

Initial site development should be done on a local machine using Vagrant or MAMP as a local server. This allows us to build and test the site  without waiting for any pushes/ftp or Internet connection.


#### Staging server

After the full site is developed the files & database should be pushed to our development server. This server allows us to fully test a site, optimize, and add content. The site lives here until we are ready to push it to production.


#### Production changes

In the event of large changes to a production site, the full site should also be pulled to the development server to stage the changes and test for issues. Site should not be pushed back to production until client testing has completed.

 
### Performance

#### Tools to find performance issues

There are several publicly available tools to help find performance issues or bottlenecks. We use several to identify potential issues - below is a comprehensive list of the best tools to analyze performance.

[Pingdom](http://tools.pingdom.com/fpt/)<br>
[Webpage Test](http://www.webpagetest.org/)<br>
[Google Page Speed Insights](http://developers.google.com/speed/pagespeed/insights/)

#### Compressing images

No amount of CSS & JS performance will make a dent in a slow-performing site if you have too many or too-large of images. Therefore, any images that can be compressed be reduced as much as possible. This can take place locally or with an external tool like TinyPNG.

[TinyPNG](https://tinypng.com/)<br>
[Compressor.io](https://compressor.io/)

#### Resource counts

Resources should be reduced to as little as possible. JS & CSS should be concatenated, images should be sprited if possible, icons should be converted to SVGs, and images loaded in conditionally with media queries where possible.


#### Concatenation

CSS & JS files should be compressed & contacted to serve as few files as possible in production. It's easiest to run this concatenation on the production site so that you can still test without concatenation and identify any potential issues. 


