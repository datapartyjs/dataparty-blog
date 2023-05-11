---
author: "nullagent"
date: 2023-05-11
title: "State of Party"
description: 'Roadmap for 2023'
image: "dataparty-thumb-cropped.png"
tags: ['linux', 'privacy', 'dataparty']
categories: [
  'roadmap',
  'dataparty'
]
---

Today billions of people lead double lives. One, grounded in their physical existance. And another, contained within the harddrives of countless corporate clouds. Lifetime's of content and metadata are being shoveled into networks hostile to free expression and privacy.

Your data is destined to be stored on servers you do not own. To be crunched and combed over for corporate gain, government survailence and exploited by cyber criminals for ill gotten profits.

## Contrast

The current state of affairs stands in stark contrast to the early internet computer enthusiasts fell in love with. The internet was founded largely on the concept of decentralized services run by researchers and hobbyist. Over time corporations realized centralizing the internet made them a lot of money. Now, we are the product online. Despite the massive danger this poses its very hard to run our own services. Frequently there are no good options available to the average person.

_"Ubisoft has confirmed it is closing down multiplayer servers for 15 games…"([gamesradar, 2022](https://www.gamesradar.com/ubisoft-is-turning-off-multiplayer-servers-for-these-15-games/))_

We watch helplessly as [our favorite video games shutdown _(gamernet)_](https://gamerant.com/games-shut-down-servers-2022/) when corporate servers go offline. We are told to keep trusting companies, after they have lost [private data for entire countries _(cnet)_](https://www.cnet.com/news/privacy/equifaxs-hack-one-year-later-a-look-back-at-how-it-happened-and-whats-changed/). We get no say when excentric billionaires buy our favorite services. Even email servers have become so hard to operate [IT experts are giving up after 20 years](https://cfenollosa.com/blog/after-self-hosting-my-email-for-twenty-three-years-i-have-thrown-in-the-towel-the-oligopoly-has-won.html).

How can _this_ be the future?


## A better way…

It's clear. We need apps to be less centralized and less corporate. But how can small teams make decentralized services?

We've started building the solution!

### Welcome to the party

We're a collective of black hackers.

We love ethical hacking, video games, Hip Hop and cinema! We plan to release technology and experiences that combine these core loves.

Throughout 2023 we'll be building many apps based around [@dataparty/api](https://datapartyjs.github.io/dataparty-api/_). These apps will range from video games, social services, IoT platforms and secure file storage. We'll also be releasing various experiences which blur the line between art and technology.

{{<picture src="dataparty-2023-timeline.svg" type="svg" class="float-left" alt="dataparty 2023 roadmap" caption="dataparty 2023 roadmap" link="/images/dataparty-2023-timeline.svg">}}


### Collective Philosophy

Each of our applications will pioneer what we see as the best ways to build privacy preserving software. We believe in open sourcing very early because building in the open is the best way to ensure our fans can trust our applications. We'll communicate the stability and quality of our applications with the following labels:

  - proof of concept
  - expiremental
  - stable


### No VC

We aim to make all of our applications accessible, core to this vision is a rejection of toxic VC. [Venture Capital has consistently failed to support diverse teams like ours](https://techcrunch.com/2023/01/06/black-founders-still-raised-just-1-of-all-vc-funds-in-2022/).

Our applications will be made available under a "pay what you want" approach. We'll open source all our apps & services with few exceptions. We believe this will reward learning about technology as you can always download and run our code for free!

### Community

Follow our open source approach by joining our community on [ko-fi](https://ko-fi.com/dataparty) and [discord](https://discord.gg/JrYQ3f4Pxz)!

We believe in developing in the open and learning with our community. Technology thrives when its creatione is open, empathetic and responsible!



### Developers, developers, developers, developers


At the heart of our approach is a new way to build RESTful solutions based on expressjs which enables microservices to be run everywhere. We call this approach a `party` that way your users can party on their data!


{{<picture src="dataparty-overview-full.svg" type="svg" class="float-left" alt="dataparty api overview" caption="dataparty api overview" link="https://datapartyjs.github.io/dataparty-api">}}

Dataparty services can run in your browser, cordova apps, server, embedded device or desktop apps. Dataparty fits into any environment nodejs or html5 does. We support a pluggable approach which enables app makers to select the level of decentralization they prefer. Dataparty services can be built for [Web2.0 style](https://github.com/datapartyjs/dataparty-api/blob/master/examples/test-service-node-host.js) centralized cloud hosting environments and deliver high availability just like any expressjs solution. Web3.0 developers can build systems which work primarily in a [peer-to-peer](https://datapartyjs.github.io/dataparty-api/tutorial-peer-to-peer.html) mode. Embedded engineers can build solutions which run [entirely on the edge](https://datapartyjs.github.io/dataparty-api/tutorial-local-party.html). Need a mixture of all of these approaches? No problem, you can mix and match to build hybrid Web2.0/Web3.0 services exactly how you'd like!

Since dataparty also runs in the browser it means that developers can now easily use a single codebase to support all platforms their apps run in. This begins to blur the lines between frontend developers and backend developers.

### DBs

Dataparty doesn't stop at the microserves and comms layer. At its heart is ORM that can be extended to support any [document based database](https://datapartyjs.github.io/dataparty-api/#database-selection), like MongoDB or IndedexedDb. Queries written for one DB can typically run be unmodified in any other DB. This enables queries to be quickly moved from running in the backend to the frontend or vice versa.

### Comms

We've supported many types of [communications approaches](https://datapartyjs.github.io/dataparty-api/module-Comms.html). Of course we support the workhorses of Web2.0 [HTTP](https://datapartyjs.github.io/dataparty-api/module-Comms.RestComms.html)+[Websockets](https://datapartyjs.github.io/dataparty-api/module-Comms.WebsocketComms.html) we all know and love, but we don't stop their. For embedded engineers we support [BLE](https://datapartyjs.github.io/dataparty-api/module-Comms.BLEPeerClient.html). For Web3.0 applications we support WebRTC. And for the privacy away we support [i2p](https://datapartyjs.github.io/dataparty-api/module-Comms.I2pSocketComms.html) (tor coming soon!).

### End-to-End Encryption

Building end-to-end encryption into your applications has never been easier than with [@dataparty/crypto](https://github.com/datapartyjs/dataparty-crypto/tree/master#datapartycrypto).

## Support

Excited about building a better internet? [Buy us a coffee](https://ko-fi.com/dataparty) or give a follow:

 * https://ko-fi.com/dataparty
 * https://github.com/datapartyjs
 * https://dataparty.xyz
 * https://twitter.com/datapartydao
 * Join our discord https://discord.gg/JrYQ3f4Pxz


## Mailing List

{{< rawhtml >}}
<!-- Begin Mailchimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/classic-071822.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{clear:left; font:14px Helvetica,Arial,sans-serif; 
    max-width: 75%;
  }
	/* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
    <form action="https://xyz.us21.list-manage.com/subscribe/post?u=7cfbc2e5276396fb5f543a2ed&amp;id=5ea825f5ee&amp;f_id=007bc2e1f0" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_self">
        <div id="mc_embed_signup_scroll"></div>
        
  <div class="indicates-required"><span class="asterisk">*</span> indicates required</div>
    
  <div class="mc-field-group">
    <label for="mce-EMAIL">Email Address  <span class="asterisk">*</span>
  </label>
    <input type="email" value="" name="EMAIL" class="required email" id="mce-EMAIL" required>
    <span id="mce-EMAIL-HELPERTEXT" class="helper_text"></span>
  </div>

  <div id="mce-responses" class="clear foot">
    <div class="response" id="mce-error-response" style="display:none"></div>
    <div class="response" id="mce-success-response" style="display:none"></div>
  </div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->

  <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_7cfbc2e5276396fb5f543a2ed_5ea825f5ee" tabindex="-1" value=""></div>
      <div class="optionalParent">
          <div class="clear foot">
              <input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button">
          </div>
      </div>
  </div>

</form>
</div>
<!--End mc_embed_signup-->
{{< /rawhtml >}}
