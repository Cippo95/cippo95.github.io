---
title: "Fedora has bad rendering in LibreOffice Writer"
---

LibreOffice Writer from Fedora's repositories renders characters differently from the standard Writer.  
![Writer issue](/docs/assets/image/writer-issue.png)  
> On the left Flatpak Flathub version on the right Fedora's  
 
I think it is worse (notice the blur under the letters).  
I recommend to use the Flatpak version from FlatHub or the community version from official LibreOffice site.  

I'm not the only one having seen this:  
<https://www.reddit.com/r/Fedora/comments/wkgxt6/blurry_fonts_in_libreoffice_writer_only_in_fedora/>  

In that post there's also a possible explanation, this patch could be the culprit:  
<https://src.fedoraproject.org/rpms/libreoffice/blob/f36/f/0001-tdf-144862-use-resolution-independent-positions-for-.patch/>  

From my tests it seems only a problem only with Writer.
