# ecryptfs-recover

Because ecryptfs is broken and nobody seems to care

```
# get the passphrase
$ ecryptfs-unwrap-passphrase .ecryptfs/user/.ecryptfs/wrapped-passphrase

# add it to the user session keyring
$ ecryptfs-add-passphrase --fnek

# mount it, enable filename encryption, fnek sig is the second one from the previous step
$ mount -t ecryptfs .ecryptfs/user/.Private  /path/to/mounting/point
```

