+++
date = '2018-10-06T10:34:23-04:00'
draft = false
title = 'Upgraded NetworkBrowser to Xcode 10'
+++

I upgraded NetworkBrowser to Xcode 10.  The biggest change is in starting to internationalize the application.  With Xcode 10 there is a big focus on internationalization (this is a very good thing).  But with this focus comes some warnings for layout builder.  I found that I could resolve most of the issues after viewing this WWDC 2018 video [Creating Apps for a Global Audience](https://developer.apple.com/videos/play/wwdc2018/201/) and using the stacked layout view.

[Network Browser](https://github.com/tjpetz/NetworkBrowser)
