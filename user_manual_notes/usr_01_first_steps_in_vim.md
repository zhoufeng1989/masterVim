显示当前Vim模式 :set showmode


word movement

use a numeric prefix to move past multiple words/WORDS.



match a parenthesis

"%" command moves to the matching paren,if the cursor is not on a useful
character, it will search forward to find one and then moves to its matching
paren.

match pairs are defined with 'matchpairs' option

move to a specific line

+   [count]H
to line [count] from top (Home) of window (default: first line on the window) on the first non-blank

+   M
to middle line of window, on the first non-blank character.

+   [count]L
to line [count] from bottom of window(default:Last line on the window) on the
first non-blank character.

show where you are

+   <CTRL-g>
+   set nu[mber]
+   set ruler

scrolling around

+   <CTRL-U>/<CTRL-B>
scroll up(content backward) half a screen/full screen of text.

+   <CTRL-D>/<CTRL-F>
scroll down(content forward) half a screen/full screen of text.

+   <CTRL-E>
scroll up one line at a time

+   <CTRL-Y>
scroll down one line at a time

+   zz
puts the cursor at center of window

+   z.
same as zz, but put the cursor at first non-blank character in the line

+   zb
puts the cursor at bottom of window

+   z-
same as zb, but put the cursor at first non-blank character in the line

+   zt
puts the cursor at top of window

+   z<CR>
same as zt, but put the cursor at first non-blank character in the line

+   z{height}<CR>
make window {height} lines tall.

search

set ignorecase:search string case-nosensitive

set hlsearch: highlight matched string

set nowrapscan: stops at the end/start of the file

jumps in file

+   <CTRL-O>/<CTRL-I>
jumps to older/newer cursor position in jump list

+   marks

`{mark} go to mark
'{mark} go to the begining of the line containing the mark.
m{mark} set mark
:marks show marks list
'a - 'z		lowercase marks, valid within one file
'A - 'Z		uppercase marks, also called file marks, valid between files
'0 - '9		numbered marks, set from .viminfo file
