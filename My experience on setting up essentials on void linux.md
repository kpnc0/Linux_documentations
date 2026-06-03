# void linux essentials 2026-05-30

Once **void linux** is set up, it's time to `xbps-install` and `flatpak` your way into production.

## Act 1: basic commands


* `sudo poweroff`
* `sudo zzz`
* `sudo gparted` [partition software]
* `free -h` RAM usage.
* `top` (such a simple command to view processor and RAM use)
* `sudo xbps-install <software>`

There are various commands out there, and most will be memorised with practice.


## Act 2: essential programs xbps-install

* Install `shotcut` video editor
* Install `neovim` program editor (actually
* Install `ghostwriter` markdown editor
* Install `git` and `github-cli` (we know why)
* No need to install `falkon` or `lynx`

* Install `flatpak` for advanced apps.
* `sudo xbps-install -Su` for a system update

## Know what packages you installed

```bash
xbps-query -m

```
The above command tells you what packages you installed, case you got amnesia.




