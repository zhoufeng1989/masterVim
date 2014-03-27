**making corrections**

|   keys    |   action  
|:----------|:----------
|<CTRL-W>   |delete word
|<CTRL-U>   |delete line
|<HOME>     |to start of line
|<S/C-Left> |one word left
|<S/C-Right>|one word right
|<END>      |to end of the line
|<CTRL-V>   |insert literally
|<CTRL-C>   |quit insert mode,go back to normal mode
|<CTRL-H>   |delete the character before the cursor
|<DEL>      |delete the character under cursor

**show match**

`:set showmatch`
when you type a ), the matched ( will be showed .

**completion**

`<CTRL-P>` and `<CTRL-N>`

by default, it searches:
+   current file
+   files in other windows
+   other loaded files(hidden buffers)
+   files not loaded(inactive buffers)
+   tag files
+   all files #included by the current file

completing specific items

+   <CTRL-X> <CTRL-F>       
filename in the current directory

+   <CTRL-X> <CTRL-L>       
whole line

+   <CTRL-X> <CTRL-D>       
macro definitions

+   <CTRL-X> <CTRL-I>       
current and included files

+   <CTRL-X> <CTRL-K>       
words from a dictionary

+   <CTRL-X> <CTRL-T>       
words from a thesaurus 

+   <CTRL-X> <CTRL-]>       
TAGS

+   <CTRL-X> <CTRL-V>       
Vim command line

+   <CTRL-X> <CTRL-O>       
source code


**repeat insert**

+   <CTRL-A>   
insert previously inserted text

+   <CTRL-@>   
insert previously inserted text and stop insert

**copy from another line**
+   <CTRL-Y>    
insert the character above the cursor

+   <CTRL-E>    
insert the character below the cursor

**insert a register**
+   <CTRL-R>   
insert the contents of a register 

**abbrevations**

Vim enables you to type an abbreviation and then will automatically expand it for you.
Only whole words are checked for abbreviations.

`:iabbrev abbrev full-to-expand`

It is possible to define an abbreviation that results in multiple words.

```
:iabbrev #b /****************************************
:iabbrev #e <Space>****************************************/
```

use `abbrevation` to fix typing mistakes
`:abbrevate teh the`
