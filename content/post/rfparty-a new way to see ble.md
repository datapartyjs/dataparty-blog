---
author: null
date: 2022-10-08
title: "Rfparty - a new way to see BLE"
description: 'foo bar'
image: rfparty-images/rfparty-splash-1280.png
tags: ['rfparty']
categories: [
  'rfparty'
]
---

[Rfparty](https://play.google.com/store/apps/details?id=xyz.dataparty.rfparty) is an app for exploring your wireless world.

Today, Millions of IoT devices emit wireless BLE signals. Built for educators, developers, cybersecurity specialist and the privacy minded to audit these BLE signals.



## Is BLE Private?

BLE has become a major part of many people's digital experience. But are these devices built with reasonable privacy? Today, there's no way for consumers to know for sure, other than to read the media. And if recent headlines are a barometer, the state of BLE privacy is questionable.  

{{<picture src="rfparty-images/nyt-headline-large.png" type="png" alt="NYT-I Used Apple AirTags, Tiles and a GPS Tracker to Watch My Husband’s Every Move" caption="NYT 2022 - I Used Apple AirTags, Tiles and a GPS Tracker to Watch My Husband..." class="float-left" link="https://www.nytimes.com/2022/02/11/technology/airtags-gps-surveillance.html">}}
</a>



While BLE has strong protections against ease dropping and man-in-the-middle attacks, BLE retains one significant security challenge. How do users connect to their devices?

The most common solution that BLE devices employ, is to send out public broadcasts, announcing the devices existence. This way, the owner can "scan" for these public transmissions, and pair to establish a secure connection. A challenge for device privacy is, that many devices never stop sending out these public beacons. In fact, many BLE products work on entirely broadcast protocols, allowing anyone to learn about the user and their devices by simply listening to these unencrypted transmissions.

Today, low cost tracking devices use these simple BLE advertisements, combined with vast user bases to create an always on corporate surveillance network. This is great for the folks searching for their keys... but what data will their helpful scanning friends provide to these large corporations?

{{<picture src="rfparty-images/apple-devices.png" type="png" alt="rfparty querying nearby apple devices" caption="rfparty querying nearby apple devices" class="float-right">}}

## OEMs to the rescue?

When these devices are abused, can we really rely on the [OEMs to provide adequate tools](https://www.cnet.com/tech/mobile/is-your-android-being-tracked-by-an-airtag-heres-how-to-find-out/) to detect their devices?

Today, Apple only provides comprehensive "always-on" privacy safeguards to Apple customers. Their solutions for Android users however are leaving many cyber security experts wanting better from the IoT industry. Other tracking device OEMs also face similar challenges in providing tracking protection for the general population.

# _"It's pretty terrible"_ {align=center}


So far Apple's Android solution has earned a rare [_"It's pretty terrible"_ from macworld](https://www.macworld.com/article/559337/airtag-tracker-detect-android-app.html). Meanwhile the [Washington Post reached an alarm conclusion](https://www.washingtonpost.com/technology/2022/03/31/airtags-stalking/):

_"Our test with a baby stroller finds it’s still too easy to stalk people with AirTags, Tiles and Samsung SmartTags — and no single company can fix it alone"_




## Trackers not the only privacy challenge

{{<picture src="rfparty-images/kiro-spd-radio.png" type="png" alt="KIRO - Seattle police have a wireless network that can track your every move" caption="KIRO - Seattle police have a wireless network that can track your every move" link="https://www.kiro7.com/news/seattle-police-have-wireless-network-can-track-you/246051198/" class="float-left">}}


Ok, we get it, literal tracking devices are pretty good at tracking things! But the thing consumers don't know, is that every BLE device has the potential to be tracked just like an AirTag.

In cities all over the world governments have already installed industrial wireless tracking solutions to do just this. Legally and in the case of [Seattle](https://www.kiro7.com/news/seattle-police-have-wireless-network-can-track-you/246051198/), illegally.


# How can rfparty help?


Auditing your BLE devices is the first step to understanding how to improve BLE security. Rfparty scans for public BLE advertisements and displays them on a map. A line is drawn between the locations where a device was first seen linking to where it was most recently seen.

In this demonstration, rfparty is used to audit the BLE behavior of a GoPro action camera. The app is left running in the background while the tester walks around a park. It was found that the GoPro sent beacons both when powered on, but also when visibly powered off. This enabled the rfparty app to partially reconstruct the portion of the user's journey where the user's movements may have been trackable via BLE.

{{<youtube "bDwpsSFVAN8" >}}

Today rfparty supports a robust set of queries and is stable enough to the BLE curious to peer into these unseen systems. We hope to continuously improve the tool and bring more features to close the skills gap needed to audit wireless systems.

## Getting rfparty

Rfparty is currently available for Android:

  * Android - [Google Play Store](https://play.google.com/store/apps/details?id=xyz.dataparty.rfparty).
  * Open Source version on [github](https://github.com/datapartyjs/rfparty-xyz).


{{<picture src="google-play-badge.png" link="https://play.google.com/store/apps/details?id=xyz.dataparty.rfparty">}}

