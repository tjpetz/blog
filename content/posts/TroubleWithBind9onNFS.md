+++
date = '2020-03-29T10:29:24-04:00'
draft = false
title = 'Trouble with Bind9 on a Pi with NFS root'
categories = ["linux", "networking"]
+++

I got a new Raspberry Pi 4 as I’m looking to consolidate some of my old Pi’s and clean up my servers. To avoid issues with wearing out the SD cards I mount the root file system off an NFS NAS storage server.

Unfortunately I’ve hit a problem with installing Bind9 using the defaults when mounting root via NFS. When starting Bind9 I get the error

 named[5466]: working directory ‘/var/cache/bind’ is not writable

However, the /var/cache/bind directory is fully writable by the bind account.

Running a few test I verified that the exact same configuration works when the root filesystem is on the SD card. It seems this issue is related to the chroot that the bind9 runs in by default. If I edit /etc/defaults/bind9 and remove “-u bind” from OPTIONS then bind starts. However, its obviously running as root. I’d prefer to have it run as bind.

So far poking around at google hasn’t identified the specific issue. I’m pretty sure it’s somehow related to using chroot on an NFS mounted filesystem.

I’ll post an update if/when I figure out the issue. In the meantime if you hit the same problem you can always run as root 🙁