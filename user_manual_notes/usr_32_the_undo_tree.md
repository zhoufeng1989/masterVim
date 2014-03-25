**undo up to a file write**

+   earlier

```
" go to older text state {count} times
:earlier {count}

" go to older text state abote {N} seconds/minutes/hours/days before.
:earlier {N}s/{N}m/{N}h/{N}d

" go to older text state {N} file writes before
" When changes were made since the last write ":earlier 1f" will revert the text to the state when it was written.  
" Otherwise it will go to the write before that.
:earlier {N}f
```

+   later

go forward with later command

**jump around the tree**

:undolist  
list the leafs in the tree of changes, the number column is the change number

:undo {N}   
jump to after change number {N}

:echo undotree()  
show the undo tree
