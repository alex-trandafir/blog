---
title: "Server sider rendered vs Single Page Application"
date: 2020-02-05T23:43:11+02:00
draft: false
category: tech_in_laymans
series: "tech_in_laymans"
categories:
- "Tech in Laymans"
tags: 
- single page application
- server side rendering
- web technologies
description: "A comparison between server side rendering and single page applications"
author: "Alex Trandafir"
keywords:
- single page applications
- single page application
- server side rendering
- web technologies
- tech terms in simple words
---

{{< le "In the past 2 years things have changed dramatically, server-side-rendering making a very vigurous comeback. Nevertheless the theory stands. The context doesn't. " >}}

{{< noobdisclaimer >}}

<!-- wp:paragraph -->
<p>Most modern websites are now "single page application" (<a href="https://en.wikipedia.org/wiki/Single-page_application">SPA</a>). That means they are "rendered" once by the client and then only updated when something is modified. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The biggest impact of performance when loading a website is the static data that is delivered with each website: html, css, images, fonts. In the SPA model these static resources are only sent once and then, with each new information the client gets from the server, it adjusts the html accordingly. </p>
<!-- /wp:paragraph -->

{{< figure src="https://res.cloudinary.com/livebashco/image/upload/w_1000/v1580244341/excalidraw-2020128181339_1_y1vycx.png" title="Server Side Rendered vs Single Page Application" alt="Server Side Rendered vs Single Page Application" >}}


<!-- wp:heading -->
<h2>Server side rendering</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>This concept has lost traction in the past 5-6 years, but technology tends to repeat itself (<a href="https://alligator.io/react/server-side-rendering/">React SSR</a>). Server side rendering means that the whole information is generated on the server and sent to the client "as is". The client will not have to run any kind of scripts, it will just "show" (render) the information from the server as it received it. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We can consider that an "application" is a piece of software that has an interface that someone can interact with. In the case of server side rendering you can think as the "application" lives only on the server and the client (usually a browser) is only used to display the interface. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Server side rendering has a great advantage SEO-wise. Crawlers will be able to get more information from server side rendered websites due to the fact that all data is provided by the server, thus not being dependent on actions performed by a user. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's take an example to better understand this. Imagine we have a list of Frequently Asked Questions (FAQs). When the user clicks one of those questions a section will appear below the question with the answer to the question. </p>
<!-- /wp:paragraph -->


{{< figure src="https://res.cloudinary.com/livebashco/image/upload/w_1000/v1580937518/excalidraw-2020128181339_xq8xdx.png" title="FAQs mockup" alt="FAQs mockup" >}}

<!-- wp:paragraph -->
<p>In the example above the server will return the whole web page in the case of server side rendering. That includes: questions header, question 1, question 2,  question 3, section of question 1, css, javascript, fonts. Due to <a href="https://www.codebyamir.com/blog/a-web-developers-guide-to-browser-caching">browser caching</a> some of these resources will not actually be retrieved again from the server, thus saving some load time and some web traffic, but that's an optimization perfomed by browsers. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Single page applications</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>You may have noticed I'm putting these two concepts on the opposite side of the spectrum. Yet only one has the word "application" in it. I mentioned before that the application "lives" on the server in the case of server side rendered. Single page applications use a different approach: the application lives both on the client and on the server.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>When first loading the application the server will provide more than just an html that needs to be displayed. It will also provide an "application" that will be run on the browser. This makes the initial load a lot heavier but the following actions are optimised to use as little resources as possible. The most common way of accomplishing this in complex applications (that need a backend service) is through <a href="https://www.smashingmagazine.com/2018/01/understanding-using-rest-api/">REST APIs</a>: client submits a request and the server responds with a thin data structure (usually <a href="https://www.w3schools.com/js/js_json_syntax.asp">json</a>). No html, css, javascript files are exchanged in the request, thus making things smoother.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Going back at the above example, after the client submits the request (clicks the first question) the server will only respond with the answer to the request, something like: </p>
<!-- /wp:paragraph -->

<!-- wp:syntaxhighlighter/code -->
<pre class="wp-block-syntaxhighlighter-code">{
   "question":{
      "title":"How to do something",
      "id":1,
      "article":"just start doing it Lorem ipsum dolor sit amet"
   }
}</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:paragraph -->
<p>The application will then parse the response and include it in the current page dynamically.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Implications</h2>
<!-- /wp:heading -->

* Search engine optimisation (SEO)
* Load times
* Development knowledge (frontend/backend)
* Infrastructure
* And more :) 

## Anything else?

There are actually a lot of other subjects that derive from this: dynamic content (different based on client - like facebook),  static content (same for everyone, like a landing page or this blog), lazy loading for resources (pulling dependencies only when they are needed thus minimizing initial load time for SPAs), server caching (all kinds of headers that tell the browser what to cache and for how long) etc. 

{{< series tech_in_laymans >}}

