**repeat with visual mode**

*gv*       
Start Visual mode with the same area as the previous area and the same mode.

**add and subtract**

+   [count]CTRL-A			
Add [count] to the number or alphabetic character at or after the cursor.  

+   [count]CTRL-X          
Subtract [count] to the number or alphabetic character at or after the cursor.   

**make a change in many files**

+   argdo {cmd}, excute {cmd} for each file in the  argument list

```
" print the argument list
:args   

" define {arglist} as the new argument list and edit the first one
:args {arglist} 

" It works like doing this 
" :rewind 
" :{cmd} 
" :next 
" :{cmd}
" :argdo %s/\<x_cnt\>/x_counter/ge | update
:argdo {cmd}
```

+   windo {cmd}, execute {cmd} in each window

```
"  It works like doing this: CTRL-W t :{cmd} CTRL-W w :{cmd} etc.                               
"  This only operates in the current tab page.
:windo {cmd}
```
    

+   bufdo {cmd} execute {cmd} in each buffer in the buffer list.

```
"  It works like doing this:                   
"     :bfirst                                 
"     :{cmd}                                  
"     :bnext                                  
"     :{cmd}                                  
"     etc.                                    
:bufdo {cmd}
```

+   windo {cmd} execute {cmd} in the current window of each tab page. 

```
"  It works like doing this: >     
"  	:tabfirst               
"  	:{cmd}                  
"  	:tabnext                
"  	:{cmd}                  
"  	etc.                    
:tabdo {cmd}
```

**using VIM from a shell script**

```
#  -e for ex mode
#  -s for silent mode
#  change.vim vim commands file
#  use vim in ex mode
vim -e -s file < change.vim

#  -s here is for script without -e option
#  use vim in normal mode
vim -s script file

#  read from stdin
ls | vim -

#  record typed keys, -W overwriten existed file
vim -w script file ```
```
