# disksize-increasing


1. Check current filesystem size of /dev/vda1:
lsblk

2. If you see the block device is larger than the partition, you will need to grow the primary partition of your Droplet:
growpart /dev/vda 1 (space between vda and 1 is intended)

3. Grow the filesystem on the partition:
resize2fs /dev/vda1 

4. Re-check the filesystem size to ensure it is filling the disk:
df -h
