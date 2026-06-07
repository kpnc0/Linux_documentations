## I have 2GB RAM

And browsers treat your ram like their own **property**.

My PC would freeze without the swap memory, everytime the 2GB was used up. So, let's implement the swap file:

## Implementation of the swap memory out of an existing ext4.

Create swap file:
```bash
sudo fallocate -l 2G /swapfile
```

Secure and format:
```bash
# 2. Set secure permissions (Root read/write only)
sudo chmod 600 /swapfile

# 3. Format the file as swap space
sudo mkswap /swapfile
```


Activation of the swap file:
```bash
# 4. Activate swap
sudo swapon /swapfile

# 5. Verify it is working
swapon --show
free -h
```

Making it permanent (fstab):
```bash
# back up fstab:
sudo cp /etc/fstab /etc/fstab.bak

# Add a config line to fstab
echo '/swapfile none swap defaults 0 0' | sudo tee -a /etc/fstab
```

Done, now we have a 2GB swap file in case the RAM runs out.


## Now, to resize the swap file:

Turn off the swap file (IMPORTANT)
```bash
sudo swapoff /swapfile
```

Remove the old swapfile:
```bash
sudo rm /swapfile
```

Create a new swapfile of desired size:
```bash
sudo fallocate -l 6G /swapfile
```

Set the permissions:
```bash
sudo chmod 600 /swapfile
```

Activate the swapfile:
```bash
sudo mkswap /swapfile
sudo swapon /swapfile
```

Achivement unlocked: downloading RAM.

