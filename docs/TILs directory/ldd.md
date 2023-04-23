---
title: ldd
tags:
    - apt
    - c
    - ubuntu
    - apt-file
    - ldd
---


# ldd

Get runtime dependencies of C programs

Imagine you've been developing an app in your PC, which has lots of things installed. When writing instructions, what dependencies do you really need?


```
$ ldd ./main.o
        libgstreamer-1.0.so.0 => /lib/x86_64-linux-gnu/libgstreamer-1.0.so.0 (0x00007f375de2b000)
        ...
```

Then you can find how to get those with the `apt-file` tool.
```
$ apt-file search libgstreamer-1.0.so.0
libgstreamer1.0-0: /usr/lib/x86_64-linux-gnu/libgstreamer-1.0.so.0
libgstreamer1.0-0: /usr/lib/x86_64-linux-gnu/libgstreamer-1.0.so.0.2001.0
libgstreamer1.0-0: /usr/lib/x86_64-linux-gnu/libgstreamer-1.0.so.0.2003.0
libgstreamer1.0-dev: /usr/share/gdb/auto-load/usr/lib/x86_64-linux-gnu/libgstreamer-1.0.so.0.2001.0-gdb.py
libgstreamer1.0-dev: /usr/share/gdb/auto-load/usr/lib/x86_64-linux-gnu/libgstreamer-1.0.so.0.2003.0-gdb.py
```


<!-- 

Can you find this through the navigation bar ?

-->