+++
date = '2020-08-11T10:25:17-04:00'
draft = false
title = 'Recover Synology rsync backup jobs'
+++

I recently upgraded a very old Netgear ReadyNAS device to a new Synology DS-420+ at a remote location.  

The main use of the old ReadyNAS was an a rsync target for backing up my main Synology rack station.  I have about 2.5TB of rsync’d files.  I wanted to reuse the existing rsync files to avoid the several months necessary to build a new  backup.  

I thought I could just repoint the existing Hyper Backup jobs on the Synology rack station.  This did not work as I couldn’t reset the name of the share where the files were to be backed up to.  I also tried building new jobs using the targets of the copied files but this would error out because HyperBackup would report that files already existed in the target directories.

To work around these issues what I was able to do was create new rsync single copy backup jobs in HyperBackup with the same source as the existing jobs but pointing to new backup locations.  I then started the backup jobs.  I then canceled them shortly after they started. Once fully canceled I copied the old rsync files into the new backup locations.  I set the file ownership of these files to the same account used to run the rsync.  Once I did this I could restart the HyperBackup jobs and they detected the existence of the files.  This saved months of rerunning HyperBackup to fully rebuild the backup images.
