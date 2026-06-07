## I need to manage my stress.

I realized that my CPU had a nice little GPU sitting in it.

I've only been conscious about the RAM, HDD and the processors. But never thought that I should activate my GPU in void musl xfce.

When I saw the nice little GPU sitting down there, taking up my SATA3 plug's space, I decided to activate it.

## Step 1 is to check if the system can even see the drive

```bash
lspci | grep VGA
```

when I ran that command, I realized that there was:
VGA compatible controller: Intel Corporation 4 Series Chipset Integrated Graphics Controller (rev 03)

Sweet. Integrated graphics controller.

Since it is intel, I need to install the intel drives.

```bash
sudo xbps-install -S mesa-dri xf86-video-intel
```

Turns out, in my PC, the mesa-dri was already installed. Guess it is time to simply reboot.

## Confusion.

When I rebooted, I literally saw that my wallpaper changed. That was one clue. Another thing was that when I rebooted the first time, my screen was not recieving input. I had to reboot again.
Something did change.

I installed `glxinfo` and `xrandr` for further checking.
