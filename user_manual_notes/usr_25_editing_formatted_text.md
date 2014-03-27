**breaking lines**

+   `textwith` option:
If you set the 'textwidth' option, Vim automatically inserts line breaks when
insert.

+   `wrap` option:

This option changes how text is displayed.  It doesn't change the text in the buffer.
When on, lines longer than the width of the window will wrap and displaying
continues on the next line.  When off lines will not wrap and only part of long
lines will be displayed.  When the cursor is moved to a part that is not shown,
the screen will scroll horizontally.


**format text**

+   `gq` operator: format a range of lines

`gq` works with visual mode,motion and text object.

`gqap` format a paragraph

`gggqG` format file

**align text**

+   [range]center [width]
Center lines in [range] between [width] columns (default 'textwidth' or 80 when 'textwidth' is 0).

+   [range]right [width]
Right-align lines in [range] at [width] columns (default 'textwidth' or 80 when 'textwidth' is 0).

+   [range]left [indent]
Left-align lines in [range].  Sets the indent in the lines to [indent] (default 0).  

+   filter the text through an external program

```
:%!fmt
```


**indents and tabs**

+   'autoindent' option       
Copy indent from current line when starting a new line 

+   'shiftwidth' option         
use '>' to indent, the amount of indenet added is specified with 'shiftwidth' option

+   'softtabstop' option     
Number of spaces that a `<Tab>` counts for while performing editing operations, like inserting a `<Tab>` or using <BS>.  

+   'tabstop' option and retab
'tabstop' option defines number of spaces that a <Tab> in the file counts for.  

`:[range]ret[ab][!] [new_tabstop]` replace all sequences of white-space containing a <Tab> with new strings of white-space using the new tabstop value given.  If you do not specify a new tabstop size or it is zero, Vim uses the current value of 'tabstop'.


**deal with long lines**

|             |
|:------------|:---------------------------------------------
|    zh       |    scroll right
|    4zh      |    scroll four characters right
|    zH       |    scroll half a window width right
|    ze       |    scroll right to put the cursor at the end
|    zl       |    scroll left
|    4zl      |    scroll four characters left
|    zL       |    scroll half a window width left
|    zs       |    scroll left to put the cursor at the start

|        |
|:-------|:--------------------------------------------------
|   g0   | to first visible character in this line
|   g^   | to first non-blank visible character in this line
|   gm   | to middle of this line
|   g$   | to last visible character in this line

+   'linebreak' option

If on Vim will wrap long lines at a character in 'breakat' rather than at the last character that fits on the screen.

+   move by visual line

To move only one screen line, use the `gj` and `gk` commands.

join one paragraph into one line

paragraph seperate with empth line: `g/./,/^$/join`

paragraph seperate with blank line: `g/\S/,/^\s*$/join`


**edit tables**

when edit table ,try 

```
set virtualedit=all
```

Virtual editing means that the cursor can be positioned where there is
no actual character.  This can be halfway into a tab or beyond the end
of the line.  Useful for selecting a rectangle in Visual mode and editing a table.
