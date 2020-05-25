---
toc: false
layout: post
description: When you moved Microsoft Edge from Google Chrome but you can't cast to any chromecast.
categories: [how-to, browser, softwares]
title: How to cast to Chromcast in Microsoft Edge
image: images/th/chromecast-edge-th.png
---
# When you see the words coming earlier than voices.

This has to work spontaneously, but it doesn't work in most scenarios. Make sure your Chromecast supported device and the device you are cast to are on the same network, and if possible, test Chromecast using Google Chrome. Enable the following flags after making sure they work with Google Chrome.

Go to `edge://flags/#cast-media-route-provider` and `edge://flags/#load-media-router-component-extension` then change to enabled from default. 

So this is how it suppose to look;

![Both are enabled](/images/chromecast-edge-screenshot.jpg)

Then it should work.