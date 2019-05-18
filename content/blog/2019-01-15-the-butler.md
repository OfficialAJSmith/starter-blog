---
title: 'This weeks progress  '
date: 2019-05-17T04:00:00.000Z
image: /images/this-weeks-events-header.png
tags:
  - JavaScript
  - Netlify
  - Udacity
published: true
---
  Here is my _first_ post and a week in review progress. This was brought about because of a group known as Let's Code. A few peers and myself decided to work on communication while passing on some information we learned.  

- - -

<!-- excerpt -->

  This week I started off by working on a mobile first website for my private Minecraft server. It was pretty easy to get most of the work done to make it mobile ready. But one thing I overlooked and over thought for that matter was the hamburger menu. While it's only a few lines of code I still got stumped on a glitch with the menu not opening and closing. Here's the code if your curious.    

```
(function() {

	var hamburger = {
		navToggle: document.querySelector('#hamburg'),
        nav: document.querySelector('#ull'),

		doToggle: function(e) {
			e.preventDefault();
			
			this.nav.classList.toggle('active');
		}
	};
    hamburger.nav.addEventListener('click', function(e) { hamburger.doToggle(e); });
	hamburger.navToggle.addEventListener('click', function(e) { hamburger.doToggle(e); });

}());
```

  The second thing I worked on was a [Udacity](https://www.udacity.com/) class I am taking for some review of JavaScript. So far I am really enjoying the structure and quizzes at the end of each little section. Each lesson plan is about 2 hours worth of studying and working on exercises. I'm on the second lesson which covers strings, variables, escaping strings such as `\n`(next line),`\t`(tabs) and some others. 

   And last but not the least thing I worked on was setting up this blog page and learning how to break it and mess around with different features built into the CMS. For now I am just using MarkDown because its a good thing to know when using Git.
