---
title: "Firefox fonts getting cutted off"
---

**UPDATE: I'm not seeing this issue anymore, maybe it was fixed. If you still have this continue to read.**

With default settings Firefox's fonts on some site get strangely cutted off.  
I can notice this on Facebook post's titles, or very often on cookie policies.  

The issue is that it seems that Firefox searches for Window's fonts like Arial, Helvetica, Time New Roman, Times and Courier New.  
It doesn't find them and then tries to use compatible fonts failing.  

The fix is to use some good font to replace what Firefox searches for.
You can do it creating a file in .config/fontconfig named fonts.conf.

Here is my current one: 

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
<match>
  <test name="family"><string>Arial</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Liberation Sans</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Helvetica</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Liberation Sans</string>
    </edit>
  </match>
    <match>
    <test name="family"><string>Times New Roman</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Liberation Serif</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Times</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Liberation Serif</string>
    </edit>
  </match>
  <match>
    <test name="family"><string>Courier New</string></test>
    <edit name="family" mode="assign" binding="strong">
      <string>Liberation Mono</string>
    </edit>
  </match>
</fontconfig>
```
