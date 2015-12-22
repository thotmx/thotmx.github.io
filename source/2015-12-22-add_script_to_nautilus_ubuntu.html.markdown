---
title: add_script_to_nautilus_ubuntu
date: 2015-12-22 05:33 UTC
tags: ubuntu, nautilus
---

In [my previous post](2015/11/27/create-a-new-dolphin-action-in-kde-4.html), in order to avoid a repetitive task I had to create a new action in Dolphin.

But now, for jobs reasons, I'm an Ubuntu user. So I should replicate the same behavior in Nautilus.

Create a file with the name of the action on this path `~/.local/share/nautilus/scripts`

Paste this script

```script
#!/bin/bash

for line in $NAUTILUS_SCRIPT_SELECTED_FILE_PATHS; do
  if [[ "$line" = "" || "$line" = " " ]]; then
    exit
  else
    filename = $(basename $line)
    pdftk $line stamp /data/digital_ocean/tax_id_digital_ocean.pdf output digital_ocean.pdf
  fi
done

exit0
```

Restart nautilus

Done!

Now, you are going to have an Script submenu with the new action on your right click menu. 
