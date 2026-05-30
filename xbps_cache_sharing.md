## Why Install over the internet what has already been installed?


In computer A, you installed 1GB worth of packages using `xbps-install`. Great.

But utterly foolish is it, to install the 1GB package in computer B (if it is void linux too) over the internet. Why?

Because you can share the xbps packages installed in computer A with computer B using USB pendrive.

Let's go over the steps shall we?


### Insert the pendrive in computer A

The commands below are just ritual. If you know what you are doing, then do what you want.

```bash

lsblk
>>> so that you know where the USB is. Eg: /dev/sdb1
 
# this makes /mnt the path to access the contents of your usb
sudo mount /dev/sdb1 /mnt


# this scoops all the .xbps files in the cache and dumps it in void repo
cp /var/cache/xbps/*.xbps /mnt/void-repo


# Let's index the folder
cd /mnt/void-repo
sudo xbps-rindex -a *.xbps

# Finally, unmount the pendrive safely
sudo umount /mnt

```

Remove the pendrive from computer A


### Insert pendrive in computer B

```bash

# the typical mounting process

sudo mount /dev/sdb1 /mnt

cd /mnt/void-repo

# Now, all we have to do is install the packages from within the repository
sudo xbps-install -R ./ <whatever you want>

```

Fin
