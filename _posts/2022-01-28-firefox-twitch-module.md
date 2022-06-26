---
title: "Firefox on Linux and the 'Failed to load module' Twitch issue"
---

Firefox on Linux has an annoying issue with Twitch: it fails to load the page correctly with error **"Failed to load module"**.  
Usually hard refreshing the page (CTRL+F5) fixes it for a while, it seems a caching problem.  

Historically enabling "DNS over HTTPS" fixes it but I really don't understand why.  

Today I have discovered another way to fix this looking at bugzilla:  
<https://bugzilla.mozilla.org/show_bug.cgi?id=1640212>  

Setting "network.http.rcwn.enabled" to **false** in about:config works great for me.  

RCWN seems a way for Firefox to decide if using local cache or redownload content.  
It seems more reasonable that the issue is here but it is interesting that it shows only on Linux.  

In the same bugzilla page it seems that also enabling "network.dns.disableIPv6" solves the problem.  
I have tested it and I have still encountered the issue but becomes more rare.  
