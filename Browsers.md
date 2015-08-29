---
layout: page
title: Browsers
permalink: /browsers/
banner: banner_php.jpg
order: 4
---

This is an overview of our browser support policy. This policy can be overridden on a per-project basis, but as a whole these are the browsers that we explicitly support and develop for.

### Internet Explorer 7 and older, Opera, various other browsers

Internet Explorer 7 was last updated on October 4, 2007 and is 8 years out of date as of this writing. We do not support or develop for Internet Explorer 7 unless a client explicitly requests it. Even in such a case, the design will be simplified to match the limited functionality of IE7 and certain specs such as flexbox or pseudo elements cannot be used which greatly extends development time.

### Internet Explorer 8

We offer limited support for IE8 - we will style a site roughly (~80% match) to match the layout of the evergreen browsers but the site will not be a pixel-perfect match and it is up to the developer's judgement what 80% means for the site. Functionality will be significantly limited and layout will be different when compared to IE9 or newer as IE8 does not have the ability to update itself which means that important specs such as flexbox will not work.

### Internet Explorer - 9, 10, 11

IE 9 and up is supported and tested for in our development work. While we find a minority of visitors to our clients' site use IE, we will test and match the site just as well as Chrome, Firefox or Safari.

### Chrome, Firefox, Safari on desktop - latest release

Chrome, Firefox, and Safari possess 90% of the global browser market share. We develop on and test these browsers first. Since these are auto-updating evergreen browsers, we support the latest version of each as a non-updating configuration is extremely rare. 

### Chrome, Safari on mobile

On mobile devices we test for Chrome & Safari on multiple iOS devices, back to iOS7 and Chrome on Android devices. We test on tablets & mobile phones using our in-office device lab. 

### JavaScript

99% of the Internet has JavaScript turned on and on our clients' sites the figure is closer to 100%. Therefore, we develop features using JavaScript with no explicit fallback. We use jQuery and will often CDN it in from Google - a feature which speeds up your site significantly but might be blocked by certain older antivirus' or legacy configurations. These are highly unpredictable and are therefore not developed for.