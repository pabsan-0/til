---
title: comment multiple lines
date: "2023-05-11"
tags:
    - ssh
---

# ssh / command on arrival

When sshing to a LAN device, you can run commands on arrival with:

```
ssh user@192.168.21.28 -t -o RemoteCommand="ls; bash"
```

There is a lot more options to it, see:

- `man ssh`  
- `man ssh_config`  
- `man ssh_config 5` 