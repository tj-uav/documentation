---
description: To perform an action upon boot
---

# Run script on startup

sudo crontab -e

At the bottom of the crontab file, type:

@reboot sudo /global/path/to/file

