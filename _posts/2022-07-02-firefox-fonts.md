---
title: "Firefox fonts getting cutted off"
---

With default settings Firefox's fonts on some site get strangely cutted off.  
I can notice this on Facebook post's titles, or very often on cookie policies.  

![Fonts issue](/docs/assets/image/fontscutted.png)

It seems that Firefox searches for some Windows's font and then tries to use compatible fonts.
This seems to lead to bad results for some reason.

Creating a file in .config/fontconfig named fonts.conf that forces "good replacements" seems the way to go.

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
