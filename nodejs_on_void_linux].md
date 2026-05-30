# **node js** in void linux.


## Installation:

Pretty straightforward compared to windows

```bash
sudo xbps-install -S nodejs
```


Now, you have `npm` and `node` installed. Great. But you don't wanna type:

```bash
sudo npm install -g something
```

for a living right?

## Setup of package managers: 

Instead of `sudo`, fix npm's permissions once:
```bash

# Create a directory for user-global packages
mkdir ~/.npm-global

npm config set prefix ~/.npm-global

# Add to your shell profile (~/.bashrc or ~/.zshrc)
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.bashrc

# Reload and install normally (no sudo!)
source ~/.bashrc

npm install -g pnpm

```

Finally, remember to install pnpm. Once npm is set up

## Why install pnpm:

Cuz it saves disk space.

You would otherwise end up downloading packages for each project separately. pnpm stores the packages in a global directory and hard links them every project.

Essentially, 10 projects would end up sharing a single global package, instead of 10 projects having duplicates of a package in their folders.

Good bye `npm install`

**once** pnpm is installed, make sure to run `pnpm setup`, so it's global directory (the place where all the modules will be installed) will be set in ~/.bashrc.