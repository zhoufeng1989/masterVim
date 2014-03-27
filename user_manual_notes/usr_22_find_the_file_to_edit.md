**the file browser**

Vim has a plugin that makes it possible to edit a directory, you can browser
files in directory.

**current directory**

`:cd` change the current directory 
`:pwd` print current directory 
`:lcd` change the current directory only in the current window.

For a window where `:lcd` has been used a different current directory is
remembered. Using `:cd` or `:lcd` in other windows will not change it.

**find a file**

Vim use the `path` option to find the file.

In path, use commas to separate directory names: `:set path=.,/usr/local/include,/usr/include`
To search relative to the directory of the current file, use: `:set path=.`
To search in the current directory use an empty string between two commas: `:set path=,,`

**buffer list**

Vim uses the term buffer to describe a file being edited.Actually, a buffer is a
copy of the file that you edit.

hide buffer to edit another file without save the current one: `:hide edit anoter.txt`

buffer status:

+   active: appear in a window, text loaded.
+   hidden: not in a window, text loaded.
+   inactive: not in a window, not text loaded.

list buffers: `:buffers` or `:ls`, buffer flag in buffer list:

+   u   buffer is unlisted
+   %   current buffer
+   #   alternate buffer
+   a   buffer is loaded and displayed
+   h   buffer is loaded but hidden
+   =   buffer is read-only
+   -   buffer is not modifiable,the `modifable` option is off.
+   \+  buffer has been modified

edit a buffer: `:buffer 2`  
edit a buffer with name or part of name: `:buffer name`   
edit a buffer in new window: `:sbuffer 3` , also works with name or part of name.   

using buffer list:

+   :bnext  go to next buffer
+   :bprevious  go to previous buffer
+   :bfirst go to the first buffer
+   :blast  go to the last buffer

remove a buffer from list: `bdelete 3` also works with name or part of name. the
deleted buffers will show with command `:buffers!`.
