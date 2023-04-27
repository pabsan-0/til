---
title: complete
date: "2023-04-27"
tags:
    - ubuntu
---

# complete

A simple tool to handle shell autocompletion. 

```
complete -f my-program      # Autocomplete files in current dir
complete -d my-program      # Autocomplete directories

complete -W "foo bar" -E    # Autocomplete custom words when shell is empty 
                            # Word separation ruled by $IFS

```


Here's a more advanced example of a custom function for autocompletion. You'd typically source this script. 

- From an empty prompt, tabbing will autocomplete for `tmuxinator start -p`
- After that, it will scan the current dir for the `*.yml` glob
- Completion is stopped after 4 words in the prompt

```
#!/bin/bash
# Autocompletes for tmuxinator start -p *.yml

_complete_tmuxinator_ls(){
      # echo $COMP_WORDS

      if [ ${COMP_WORDS[COMP_CWORD-1]} == "tmuxinator" ]
      then 
          COMPREPLY=("start")
      elif [ ${COMP_WORDS[COMP_CWORD-1]} == "start" ]
      then 
          COMPREPLY=("-p")
      elif [ $COMP_CWORD -lt 4 ]
      then
          COMPREPLY=($(ls -1 | grep -- "^${COMP_WORDS[COMP_CWORD]}.*.yml")) #2> /dev/null))
      else
          : 
      fi
      return 0
}

complete -W "tmuxinator" -E 
complete -F _complete_tmuxinator_ls tmuxinator
```