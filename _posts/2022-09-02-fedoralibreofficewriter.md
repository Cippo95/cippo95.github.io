---
title: "Fedora bad rendering in LibreOffice writer"
---

LibreOffice Writer from Fedora's repositories renders characters differently from the standard Writer.  
I'm not the only one having seen this as you can see here:  
<https://www.reddit.com/r/Fedora/comments/wkgxt6/blurry_fonts_in_libreoffice_writer_only_in_fedora/>  

As you can see the way it renders is pretty bad.  
I have tested both the Flathub and community version from LibreOffice and they work fine and advice to use these versions. 

In the same Reddit post that I have linked there's also a possibile explanation that says that this patch could be the culprit:  
<https://src.fedoraproject.org/rpms/libreoffice/blob/f36/f/0001-tdf-144862-use-resolution-independent-positions-for-.patch/>  

From my tests it seems only a problem with Writer and not the other LibreOffice's apps.
