---
title: "Firefox and Fedora's system wide crypto policy"
---

Using Fedora 35 I had to retrieve some medical documentation for my father but Firefox refused to connect to the hospital site.  
The error was about the connection not being secure with this error:  
"SSL_ERROR_UNSUPPORTED_SIGNATURE_ALGORITHM".  
I did this stuff also on Ubuntu sometime ago with no issues whatsoever.  

I thought the hospital site was broken but then I tried to connect with my Android phone with Firefox *and it connected securely*.  
Then I have downloaded Chrome on Fedora *and it connected securely*.  

Then searching online I have found some french Fedora user encountering the same problem:  
https://forums.fedora-fr.org/viewtopic.php?id=73081  
I'm italian so I used google translator to read it.  

They refered to this article in Fedora documentation:  
https://fedoraproject.org/wiki/Changes/StrongCryptoSettings2  

Apparently Firefox was just obbeying Fedora's "strict" system wide crypto policy.  

Fortunately you can use this console command:  
`sudo update-crypto-policies --set LEGACY`  
and restart the system to be able to connect again to these sites.  

To revert this setting:  
`sudo update-crypto-policies --set DEFAULT`  

Don't really know if Fedora's policies are too strict or if that server is just badly configured.  
What I know is that:  
- Now it works  
- Once connected it uses TLS 1.2 and Fedora should refuse TLS inferior or equal to 1.1 with the stricter policy, so something doesn't add up.  

What I think:  
- Chrome probably doesn't care about system wide crypto policy... or maybe it is a Firefox bug.
