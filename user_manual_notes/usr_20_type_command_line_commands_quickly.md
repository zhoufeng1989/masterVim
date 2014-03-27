**keys to move around in the command line**

|   keys        |   move
|:--------------|:--------------------------
|   <Left>      |   one character left
|   <Right>     |   one character right
|   <S/C-Left>  |   one word left
|   <S/C-Right> |   on word right
|   <CTRL-B>    |   to begin of command line
|   <CTRL-E>    |   to end of command line
|   <CTRL-W>    |   delete word forward
|   <CTRL-U>    |   delete form cursor to begin
|   <Insert>    |   replace character under cursor
| <CTRL-C>/<ESC>|   cancle command line

**command line completion**

`<tab>` to complete the command line in context sensitive way,`<tab>` again to go through through the list, `<CTRL-P>` to go through in another direction.

when there are many matches, `<CTRL-D>` to show matched list, `<CTRL-L>` commands completes the word to the longest unambiguous string.

**command line history**

`<Up>` key to recall an older command line, `<Down>` then takes you back to newer commands.

list history:
the `:` commands history: `:history`    
the `/` and `?` commands history : `history /`

`<CTRL-P>` will work like `<Up>,` except that it doesn't matter what you already
typed. Similarly for `<CTRL-N>` and `<Down>`.

**command line window**

open command line window with command `q:`,then you are in Normal mode.edit one
line and press `<Enter>` to execute it. the old history is not changed, but append
new entry in histroy list.


