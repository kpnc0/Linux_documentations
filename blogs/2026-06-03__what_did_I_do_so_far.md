## So, I decided to replace windows 8 with void linux.

I don't really know what got to me, but one day, while travelling back home, I got the urge to remove windows and install **void linux** into my laptop.

On the way, I purchased a 8GB pendrive for a suspiciously cheap price (turns out to be a fake when I tried using it)

I end up having to perform a tedious process of clearing my USB pendrives of it's contents and flashing it with a tiny-core iso.

### Why tiny-core you may **ask**?
* Because my mind still believe I could easily change the OS of a system, let alone boot into it via USB. I downloaded a 20MB iso just to check if the process wor**worked**.

Now, I noticed I had an old PC that was presumed "dead" by me. My initial theory was that the HDD was wearing out, or that the CPU fried up.

I booted into the PC with tinycore, and voila, it booted perfectly.

* My old PC was not dead like I thought.
* I possibly revived a hardware that would've been lying dead.

As I saw tinycore boot perfectly, I decided to escalate, and install the void linux iso.

### The old PC had problems

I could boot successfully into the PC, via USB. However, the boot took waay too long, giving me errors of a drive corruption (sr0 Error, and I didn't really know what sr0 even mean)

I used Deepseek for querying and debugging the issues. But that happened later. 

When the PC **finally** booted into void linux, I realized I couldn't access the harddrive, giving me the error of **Bad superblocks**. 
* I hypothesized that my hard drive was **failing**.

I decided to revisit the PC later.

### Of the laptop:
The USB boot happened without much **problems**, and now, I had to manually set up the partitions here.

* I decided to query Deepseek about this. And let me tell you, it saved quite some time for me.
* One thing I learnt was that I didn't really have to wipe out my whole HDD, or even C://. 
* As a matter of fact, I just had to wipe out windows_recovery partition (~20gb) to **convert to ext4** and make it the root/ of my OS. And a tiny 200MB already allocated space for the bootloader.

***Side yap***
The thing was, I had planned to shrink the C:// partition, but I got ntfs error, and for me to recover it using windows diagnostics.
That I did, and my windows was officially stuck on repairing C:// drive. Following that, I decided to remove the windows boot option altogether by **renaming** the bootloader files, **later**.


My joy was endless after watching my laptop boot to void linux without an USB. 

### Back to my old PC: 

Now, here's my situation:

* 2GB RAM
* Old processor
* 500GB HDD
* Intel graphics card

* Hard drive presumed **dead**
* USB boot taking way longer than user due to a huge chain of errors (sr0 errors)


And this old beast ran windows 8 (The OS idles at around 1.1GB RAM). 

Firstly, I had to manually try fixing the situation of driver errors. Without mountable drives, I couldn't possibly **flash** the bootloader to my computer.

* Deepseek queried: sr0 meant optical drives, so I had to disconnect HDD and optical drive to get rid of  the errors.
* I manually disconnected the required. The USB boot happened **instantly**.
* I reconnected the HDD port. And behold: the hard drive mounted successfully in void linux. I could access the files that otherwise would've been lost forever.
* Following that, I **converted** the old PC's C:// drive into root. And totally wiped out windows.
* My PC was finally up and running. This happened on 2026-05-25, a day after flashing my laptop.


## functionality setup

I had:
* A functioning void_linux_musl laptop
* A functioning void_linux_musl PC

I set them up side by side.

***Side yap***
My laptop was old, really old. 6GB ram, celeronR perhaps. It gave me a lot of tech discipline.

### xbps-install

I had used deepseek to suggest me commands, and I would type it, not knowing what it did. But eventually, on repeated use, I figured out what the commands **meant**.

I had figured out how to use gparted. ntfs-3g for ntfs file system support.

xbps-install was the first commands I memorized.

* Since the day of setting up, 2026-05-26, I used xbps-install a lot, to set up git, nodejs and the classic developer kits.
* The developer kit installation was quite straightforward, and pretty **lightweight**.
* I figured out how to share packages offline via pendrive. `sudo xbps-install -R ./ <package-name>`. I documented various processes in my github, so check it out:
* My experience the whole week till today involved trying out torrenting, custom compiling open source **rust** repository to run on musl (theorzr/portablemc). All of it documented in github.
* Learnt that I was on `musl`, and `gilbc` was more compatible with most apps for linux. But now, I like the minimalism of musl. My life would involve compiling against musl from source, and mostly **shipping** great code.
* I also got comfortable with **hardware**, also figured out that even a small kick to my PC CPU will cause a **disconnect** of my HDD. So, I would have to disconnect and reconnect the HDD. Apparently, the problem was **not** that my HDD was failing, but it was **certainly** connection issues. Another issue might be RAM getting physically moved.


