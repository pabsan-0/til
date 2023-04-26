---
title: comment multiple lines
date: "2023-04-26"
tags:
    - vim
---

# vim / comment multiple lines

A few multicursor-like operations, but not quite, that can be done in vim

- `Ctrl+V`: block visual mode (square selection)
- `:%s/^/# /` regex

--- 

### Uncomment a line:
```
hjkl        # Place cursor on target characters
Ctrl+V      # for visual block then span the rows
x
```

### Comment a line using inputs:

```
hjkl           # Place cursor on target characters
Ctrl+V jjjj    # for visual block then span the rows
I              # Insert mode  (i would only place a single char)
#              # write text to insert (will appear on current line)
<esc>          # after a moment will fill multicursor
```

### Comment a line using regex:
```
hjkl           # Place cursor on target characters
Ctrl+V jjjj    # for visual block then span the rows
:%s/^/# /      # substitute linestart (not selection start) for comment
```