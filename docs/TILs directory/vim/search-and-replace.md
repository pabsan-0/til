---
title: search and replace
date: "2023-04-25"
tags:
    - vim
---


# vim / search and replace

Search and replace utilities.

- `y` yank pastes to the `"` register by default. 
- `Ctrl+R "` retrieve text at `"` register
- `.` repeat previous command

--- 

### Search selected text
```
v             # visual mode and select text
y             # yank selection, will go into " register by default
/             # open search
Ctrl+R  "     # paste from " register
<enter>       # profit
```

### Replace using motions
```
/foo <enter>   # search for your match   
cgn            # change operator `c` then `gn` motion    
bar <esc>      # write text then escape
.              # press to repeat operation as many as desired    
```

### Replace using regex
```
:%s/foo/bar/g  # easy regex
```
<br> 


!!! Future
    - `:%`: motion `(1,$)` 
    - `c`: change operator
    - `gn`: motion
    

