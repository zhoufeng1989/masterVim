**suspend and resume**

`<CTRL-Z>` or `:suspend` to suspend vim, and fg to resume.

**execute shell command**

`:!{command}`

**getting back to some file**

`:oldfiles` list files you edited recently without exiting Vim, then if you
would like to eidt the second file, you type: `:e #<2`

`:browser oldfiles` is another way to do it in a simpler way.

**sessions**

a Vim session contaions all the information about what you are editing.

create a session file:`:mksession vimbook.vim`

later if you want to restore this session,use: `:source vimbook.vim`.

to start Vim and restore a specific session, use: `vim -S vimbook.vim`

what session will store depends on `sessionoptions`.

another way to use session is to create a windwo layout and reuse it.

**views**

a view store properties for one window only.

store the view for the current window: `:mkview`, get the view back:`:loadview`

you can switch between views, you can store up to ten views for the same file
this way, on unnumbered and nine numbered 1 to 9.

the second way to use views is by storing the view in a file with a name and
restore it with `:source view.vim`
