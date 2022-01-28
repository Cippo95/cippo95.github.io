---
title: 'Firefox and the "Failed to load module" Twitch issue
---

Firefox has a really annoying issue with Twitch, the famous **"Failed to load module"**.  
It seems to be a problem only on Linux systems which is interesting.  
Usually hard refreshing the page (CTRL+F5) a lot of times fixes it for a while, it seems a caching problem.  

One way to fix this for good is to enable "DNS over HTTPS" in Firefox settings... but I really don't understand why it fixes it.  

Today I have discovered another way to fix this looking at bugzilla:  
<https://bugzilla.mozilla.org/show_bug.cgi?id=1640212>  

Setting "network.http.rcwn.enabled" to **false** in about:config seems to work great.  

RCWN seems a way Firefox decides if use the local cache or redownload content.  
To me it seems more reasonable that the problem is here, maybe on Windows it works fine while on Linux systems it doesn't.
