---
title: "Health-Check External Disk"
description: "Hard disk health is measured using S.M.A.R.T. (if available) and bad blocks scan."
excerpt: "Hard disk health is measured using S.M.A.R.T. (if available) and bad blocks scan."
categories: [Administration]
tags: [NAS, QNAP, SMART, USB, bad blocks]
---

0. Hard disk and docking station need to support S.M.A.R.T.

0. For S.M.A.R.T., `smartmontools` is needed.

0. On (QNAP) NAS, install [Entware.]("https://github.com/Entware/entware")

0. ssh on NAS.

0. Install `smartmontools`: `opkg install smartmontools`.

0. Connected the external device.

0. run dmesg to see `dev` address of the external device. Output will look something like this:

```bash
sd 13:0:0:0: [sdi] Spinning up disk...
[798870.006728] sd 13:0:0:0: Attached scsi generic sg8 type 0
[798871.003044] ............ready
[798882.053671] sd 13:0:0:0: [sdi] 3907029168 512-byte logical blocks: (2.00 TB/1.81 TiB)
[798882.058613] sd 13:0:0:0: [sdi] Write Protect is off
```     
    Here, the device address is `/dev/sdi`.
    
0. Get S.M.A.R.T. error log: `# smartctl /dev/sdi -l error`.

0. Start a short self test: `# smartctl /dev/sdi -t short`.

0. Start a long self test: `# smartctl /dev/sdi -t long`.

0. Run bad blocks scan: `badblocks -n /dev/sdi`.
**Tip:** use `tmux` (`opkg install tmux`) to keep process alive after exiting the terminal.
