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


---

Extra resources for the reverse operation:

https://superuser.com/questions/616182/how-to-mount-local-directory-to-remote-like-sshfs?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa

```
Host $HOSTNAME
    RequestTTY yes
    ProxyCommand ncat -l -p 34567 -e /usr/lib/sftp-server & nc %h %p
    RemoteForward 34568 localhost:34567
    RemoteCommand sshfs localhost:$MY_DIR $MPOINT -o directport=34568; /bin/bash -li; fusermount -u $MPOINT
```