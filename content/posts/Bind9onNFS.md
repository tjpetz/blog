+++
date = '2020-04-05T10:26:49-04:00'
draft = false
title = 'Resolution on Bind9 on NFS'
+++

After a good bit of investigation and thinking… the problem with bind9 has nothing to do with bind9. The problem was a mismatch between UIDs between the Synology NAS server and the bind account on the pi. As I was using sec=sys for authentication all the authentication is based on UIDs. On the pi bind has a UID of 109. There was no account on my Synology NAS with a UIDs of 109. Hence the access was denied by the NFS server.

To continue using NFS for the root filesystem I will need to either run in an insecure configuration: you can map every single vid on the client to the admin account on the Synology and then grant full access to the files on the Synology. However that means every account on the pi would end up having full admin access over everything. Certainly not a very good idea. Or alternately I’d need to manage ALL accounts centrally on the Synology for all the pi’s. This seems like a bit of an overkill in complexity.

To avoid the complexity I’m going to use iSCSI for the root filesystem for each pi. I’ll probably use NFS for common shares such as home directories and where I want to share docker images.

This is a good concise guide for configuring iSCSI on a pi for booting: [https://www.domoticz.com/forum/viewtopic.php?t=28797](https://www.domoticz.com/forum/viewtopic.php?t=28797).  Note, it does assume some familiarity with iSCSI. Assuming you have that familiarity it’s a really good short guide.

I decided against using the script to switch between SD and iSCSI booting included in the article. For the few times I may need to revert to SD booting I’ll user a different SD or simply copy the cmdline.txt and config.txt files from their original configuration.
