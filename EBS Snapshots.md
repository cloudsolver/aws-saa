EBS Snapshots allow you to take a backup of your volume. Any point in time backup.

### EBS Snapshot Archive
Move a snapshot to an `archive tier` is 75% cheaper.
Restoration can take some time 24 to 72hrs for restoring the archive.
### Recycle Bin 
A Recycle Bin for EBS Snapshots prevents accidental deletes.
- #Q How can you recover snapshots after an accidental deletion? By setting up rules to retain deleted snapshots.
- Retention from 1 day up to 1 year is possible.

### Fast Snapshot Restore (FSR)
- Force full initialization of snapshot to have no latency on the first use.
- #usecase . Faster boot times will speed up  VDI environments and allow  Auto Scaling Groups to come online and start processing traffic more quickly, even for large and/or custom AMIs. 
- The trade off is price for performance.
