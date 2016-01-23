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

In the event of large changes to a production site, the full site should also be pulled to the development server or local to stage the changes and test for issues. Site should not be pushed back to production until client testing has completed.


### WordPress File Organization

Most of our functionality falls into either mu-plugins and themes. There is a distinct and important separation of functionality between the two. Essentially, themes should be completely interchangeable with each other and standalone from backend functionality on the site. You should be able to swap out themes with one another without losing custom post types, admin modifications, etc.

Here are the main reasons why we hold to this separation:

1. Makes themes entirely interchangeable - we or a client can change the theme out without losing any data of functionality.
2. Speeds up development time with separate concerns - keeps front-end in the theme and back-end in plugin.
3. Re-theming sites or existing clients is significantly easier
4. Allows us to organize plugin functionality into swappable chunks and trade them between projects with no consequences.


### Testing

Testing is split into several different types for organization.

#### Content

Content testing is one of the most important parts of our workflow. In [evans](https://github.com/oldtownmedia/evans) we have a test content suite that allows you to spin up a lot of test content and test a site with disparate content types and length. Spin up several pages of each cpt of content and visually test the consequences on the front-end.

#### Device

All sites should be tested on multiple real devices to ensure maximum compatibility. Use several real devices to actually test every page on the site you're building. Laptops, tablets, and phones of multiple OS' should be used.

#### Browser

Similar to testing on multiple devices, multiple browsers in each OS should be used. See Browsers for support & testing requirements. 

#### Automated

We use [scutinizer](https://scrutinizer-ci.com/githube) to evaluate all new site code & run unit tests. Scrutinizer points out several issues with code that the human eye has a hard time seeing such as duplicate code blocks, missing references, etc.

 
### Performance

#### Tools to find performance issues

There are several publicly available tools to help find performance issues or bottlenecks. We use several to identify potential issues - below is a short list of the best tools to analyze performance.

[Pingdom](http://tools.pingdom.com/fpt/)<br>
[Webpage Test](http://www.webpagetest.org/)<br>
[Google Page Speed Insights](http://developers.google.com/speed/pagespeed/insights/)

#### Compressing images

No amount of CSS & JS performance will make a dent in a slow-performing site if you have too many or too-large of images. Therefore, any images that can be compressed be reduced as much as possible. This can take place locally or with an external tool like TinyPNG.

[TinyPNG](https://tinypng.com/)<br>
[Compressor.io](https://compressor.io/)

#### Resource counts

Resources should be reduced to the smallest size possible. JS & CSS should be concatenated (if HTTP1/1), images should be sprited if possible, icons should be converted to SVGs, and images loaded in conditionally with media queries where possible.


#### Concatenation

CSS & JS files should be compressed & concatenated to serve as few files as possible in production. It's easiest to run this concatenation on immediately before production so that you can still test without concatenation and identify any potential issues. 