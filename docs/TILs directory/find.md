---
title: find
date: "2023-06-12"
tags:
    - find
    - bash
    - ubuntu
---

# find

Find is an essential linux command. Here's some templates 

- Finding different types of files
  
```
find . -type f      # files
find . -type l      # symlinks
find . -name *.png  # images by extension

```

- Running commands

```
find . -name *.txt -exec rm {} \;                 # the \; is needed
find . -name *.txt -exec cp {} ../my/other/dir \; # copy files over there
find . -name *.png -exec rm ../other/dir/{} \;    # remove redundant files elsewhere
```

- Time fetching

```
find . -name *.txt -newermt 2002-5-5
find . -name *.txt -newermt @1686554460
```

[more on time here](https://stackoverflow.com/a/57964862)