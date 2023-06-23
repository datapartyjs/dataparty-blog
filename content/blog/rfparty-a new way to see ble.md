---
author: null
date: 2022-10-13
title: "Rfparty - a new way to see BLE"
description: 'foo bar'
image: rfparty-images/rfparty-splash-1280.png
tags: ['rfparty', 'app', 'privacy']
categories: [
  'rfparty'
]
---

Today, Millions of IoT devices emit wireless BLE advertisements. 

[Rfparty](https://play.google.com/store/apps/details?id=xyz.dataparty.rfparty) is an app for exploring your wireless world. Built for educators, developers, cybersecurity specialist and the privacy minded to audit these BLE signals.


## Is BLE Private?

BLE has become a major part of many people's digital experience, but are these devices built with reasonable privacy in mind? Today there is no way for consumers to know for sure, other than to read the media- and if recent headlines are a barometer, the state of BLE privacy is rather questionable.  

{{<picture src="rfparty-images/nyt-headline-large.png" type="png" alt="NYT-I Used Apple AirTags, Tiles and a GPS Tracker to Watch My Husband’s Every Move" caption="NYT 2022 - I Used Apple AirTags, Tiles and a GPS Tracker to Watch My Husband..." class="float-left" link="https://www.nytimes.com/2022/02/11/technology/airtags-gps-surveillance.html">}}
</a>



While BLE has strong protections against eavesdropping and man-in-the-middle attacks, BLE retains one significant security challenge: how do users connect to their devices?

The most common solution that BLE devices employ is to send out public broadcasts, which announces the devices existence. This way, the owner can "scan" for these public transmissions, and pair to establish a secure connection. A challenge for device privacy is, that many devices never stop sending out these public beacons. In fact, many BLE products work on entirely broadcast protocols, allowing anyone to learn about the user and their devices by simply listening to these unencrypted transmissions.

Today, low-cost tracking devices use these simple BLE advertisements, combined with vast user ID bases, to create an Always-On corporate surveillance network. This is great for the folks searching for their keys... but what data will their helpful scanning friends provide to these large corporations?

{{<picture src="rfparty-images/apple-devices.png" type="png" alt="rfparty querying nearby apple devices" caption="rfparty querying nearby apple devices" class="float-right">}}

## OEMs to the rescue?

When these devices are abused, can we really rely on the [OEMs to provide adequate tools](https://www.cnet.com/tech/mobile/is-your-android-being-tracked-by-an-airtag-heres-how-to-find-out/) to detect their devices?

Today, Apple only provides comprehensive "always-on" privacy safeguards to Apple customers. However, their solutions for Android users are leaving many cyber security experts wanting better from the IoT industry. Other tracking device OEMs also face similar challenges in providing tracking protection for the general population.

# _"It's pretty terrible"_ {align=center}


So far Apple's Android solution has earned a rare [_"It's pretty terrible"_ from macworld](https://www.macworld.com/article/559337/airtag-tracker-detect-android-app.html). Meanwhile the [Washington Post reached an alarming conclusion](https://www.washingtonpost.com/technology/2022/03/31/airtags-stalking/):

_"Our test with a baby stroller finds it’s still too easy to stalk people with AirTags, Tiles and Samsung SmartTags — and no single company can fix it alone"_




## Trackers not the only privacy challenge

{{<picture src="rfparty-images/kiro-spd-radio.png" type="png" alt="KIRO - Seattle police have a wireless network that can track your every move" caption="KIRO - Seattle police have a wireless network that can track your every move" link="https://www.kiro7.com/news/seattle-police-have-wireless-network-can-track-you/246051198/" class="float-left">}}


Ok, we get it, literal tracking devices are pretty good at tracking things! But the thing consumers don't know, is that every BLE device has the potential to be tracked just like an AirTag.

Governments around the world have already installed industrial wireless tracking solutions throughout their cities to do just this legally and otherwise. In the case of [Seattle](https://www.kiro7.com/news/seattle-police-have-wireless-network-can-track-you/246051198/), it is done so illegally.


# How can rfparty help?


Auditing your BLE devices is the first step to understanding how to improve BLE security. rfparty scans for public BLE advertisements and displays them on a map. A line is drawn between the location where a device was first seen and links to where it was most recently seen.

In this demonstration, rfparty is used to audit the BLE behavior of a GoPro action camera. The app is left running in the background while the tester walks around a park. It was found that the GoPro sent beacons both when powered on and  when powered off. This enabled the rfparty app to partially reconstruct the portion of the user's journey where the user's movements may have been trackable via BLE.

{{<youtube "kDboDShA8do" >}}

Today rfparty supports a robust set of queries and is stable enough for the BLE curious to peer into these unseen systems. We hope to continuously improve the tool and bring more features to close the skills gap needed to audit wireless systems.

## Getting rfparty

rfparty is currently available for Android:

  * Android - [Google Play Store](https://play.google.com/store/apps/details?id=xyz.dataparty.rfparty).
  * Open Source version on [github](https://github.com/datapartyjs/rfparty-xyz).


{{< rawhtml >}}
<!-- Begin Mailchimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/classic-071822.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{clear:left; font:14px Helvetica,Arial,sans-serif; }
	/* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
    <form action="https://xyz.us21.list-manage.com/subscribe/post?u=7cfbc2e5276396fb5f543a2ed&amp;id=5ea825f5ee&amp;f_id=007bc2e1f0" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_self">
        <div id="mc_embed_signup_scroll">
  <h2>Mailing List</h2>
        
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

{{<picture src="google-play-badge.png" link="https://play.google.com/store/apps/details?id=xyz.dataparty.rfparty">}}
