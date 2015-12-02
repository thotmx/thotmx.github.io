---
title: Create a new Dolphin action in KDE 4
date: 2015-11-27 14:22 UTC
tags: kde
---

### Context

  * I hate repetitive tasks.
  * I have to stamp a some PDF's invoices, in order to fit our local tax office's requirements.
  * I need to run a command every month in order to accomplish this task.
  * I'm a KDE 4 user.

### Problem

  I needed to find a simple solution to make it easier.

### Solution 

Create the file **~/.kde4/share/kde4/services/ServiceMenus/.desktop** and add this content: 

```
[Desktop Entry]
Type=Service
ServiceTypes=KonqPopupMenu/Plugin
MimeType=application/pdf
Name=Stamp Digital Ocean Tax ID
Actions=StampDigitalOceanTaxID;
X-KDE-StartupNotify=false
X-KDE-Priority=TopLevel

[Desktop Action StampDigitalOceanTaxID]
Name=Stamp Digital Ocean Tax ID
Exec=pdftk %F stamp /data/digital_ocean/tax_id_digital_ocean.pdf output digital_ocean.pdf
```

This file, add a new action when you press right click over a PDF file. The option will be "Stamp Digital Ocean Tax ID" and execute the command on the last line.

And that's it
