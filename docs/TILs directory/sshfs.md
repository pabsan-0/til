---
title: sshfs
date: "2023-05-11"
tags:
    - ssh
---

# sshfs

Mount a LAN location on your computer. On the *receiving* machine, run:

```
$ mkdir mount_point 
$ sshfs user@192.168.21.28:/home/user/shared_location $PWD/mount_point
```

When finished, unmount with:
```
umount $PWD/mount_point
```

There is probably something better, but you can see the mountpoints via `df -s`. 

