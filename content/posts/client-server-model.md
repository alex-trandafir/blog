---
title: "Client Server Model"
date: 2020-01-28T22:20:55+02:00
draft: false
series: "tech_in_laymans"
categories:
- "Tech in Laymans"
tags: 
- "Web technologies"
description: "About the client server model in simpler words"
author: "Alex Trandafir"
keywords:
- client server model
- tech terms in simple words
---

<!-- wp:paragraph -->
<p>An analogy might do the trick: Imagine going to the bakery in order to buy a bread. You'll have a client (you) buying (requesting?) the bread and a seller (server) giving you the bread. The internet is basically composed of gazillions of such transactions, each client requesting different types of bread and each bakery having its own recipe. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The trick here is that sometimes the baker would also like to buy some bread. Sometimes from other bakeries, but sometimes even from himself. In the diagram below you'll notice that I've marked server as a client as well. This can get tricky once you go into more complex models, the thing to remember is that a baker can also be a client once it buys something else. Server sells, client buys. Sellers also buy.</p>
<!-- /wp:paragraph -->

{{< figure src="https://res.cloudinary.com/livebashco/image/upload/v1580239386/Screenshot_2020-01-28_at_21.22.27_hiqvyj.png" title="Server client examples" >}}

<!-- wp:paragraph -->
<p>The most basic example would be trying to Google something. You'll open up your browser (the client) and hit "www.google.com" in the address bar. The browser will resolve the address of "google.com" to a specific address (IP) and go to that address in order to give you the information you asked for (in this case being the classical google.com homepage). Google's servers will respond with the requested information and your browser will be able to interpret it and display it nicely.</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://res.cloudinary.com/livebashco/image/upload/v1580240458/Screenshot_2020-01-28_at_21.40.51_i00wje.png","type":"rich","providerNameSlug":""} -->
<figure class="wp-block-embed is-type-rich"><div class="wp-block-embed__wrapper">
<img src ="https://res.cloudinary.com/livebashco/image/upload/v1580240458/Screenshot_2020-01-28_at_21.40.51_i00wje.png"/>
</div></figure>
<!-- /wp:embed -->

{{< series tech_in_laymans >}}
