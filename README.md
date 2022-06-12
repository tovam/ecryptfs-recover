# ecryptfs-recover

Because ecryptfs is broken and nobody seems to care

```
USER=user

# go to the /home directory
$ cd /path/to/home

# get the passphrase (potential permissions problems if different uids)
$ ecryptfs-unwrap-passphrase .ecryptfs/$USER/.ecryptfs/wrapped-passphrase

# add it to the user session keyring
$ ecryptfs-add-passphrase --fnek

# mount it, passphrase is the passphrase's passphrase, enable filename encryption, fnek sig is the second one from the previous step
$ mount -t ecryptfs .ecryptfs/$USER/.Private /path/to/mounting/point
```

