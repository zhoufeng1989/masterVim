##motion##

commands move the cursor position. 

**left-right motions**

+   h               to left
+   l               to right
+   0               to the first character of the line
+   ^               to the first non-blank character of the line
+   $               To the end of the line. When a count is given also go [count - 1] lines downward
+   g_              To the last non-blank character of the line and [count - 1] lines downward 
+   |               To screen column [count] in the current line.
+   f{char}			To [count]'th occurrence of {char} to the right.
+   F{char}			To the [count]'th occurrence of {char} to the left.
+   t{char}			Till before [count]'th occurrence of {char} to the right.  The cursor is placed on the character left of {char} .
+   T{char}			Till after [count]'th occurrence of {char} to the left.  The cursor is placed on the character right of {char} .
+   ;			    Repeat latest f, t, F or T [count] times.
+   ,			    Repeat latest f, t, F or T in opposite direction [count] times.


**up-down motions**

+   k			    [count] lines upward .
+   j               [count] lines downward.
+   -               [count] lines upward, on the first non-blank character.
+   \+              [count] lines downward, on the first non-blank character.
+   G			    Goto line [count], default last line, on the first non-blank character.
+   gg			    Goto line [count], default first line, on the first non-blank character.
+   :[range]		Set the cursor on the last line number in [range].  [range] can also be just one line number, e.g., ":1" or ":'m".
+   {count}%		Go to {count} percentage in the file, on the first non-blank in the line .  To compute the new line number this formula is used: ({count} * number-of-lines + 99) / 100



**word motions**

+   [count]w/W
move cursor to the start of the next word/WORD.

+   [count]b/B
move cursor to the start of the word/WORD which begins before the current cursor position.

+   [count]e/E
move cursor to the end of the word/WORD which ends after the current cursor position.

+   [count]ge/gE
move cursor to the end of the word/WORD which ends before the current cursor position.

word and WORD

A word consists of a sequence of letters, digits and underscores, or a
sequence of other non-blank characters, separated with white space (spaces,
tabs, <EOL>).  This can be changed with the 'iskeyword' option.  An empty line
is also considered to be a word.

A WORD consists of a sequence of non-blank characters, separated with white
space.  An empty line is also considered to be a WORD.




##operator##

commands to delete or change text.

+   c	change, cc changes a whole line
+   d	delete
+   y	yank into register (does not change the text)
+   ~	swap case (only if 'tildeop' is set)
+   g~	swap case
+   gu	make lowercase
+   gU	make uppercase
+   !	filter through an external program
+   =	filter through 'equalprg' or C-indenting if empty
+   gq	text formatting
+   g?	ROT13 encoding
+   >	shift right
+   <	shift left
+   zf	define a fold
+   g@      call function set with the 'operatorfunc' option

The motion commands can be used after an operator command, to have the command operate on the text that was moved over.  That is the text between the cursor
position before and after the motion.

If the motion includes a count and the operator also had a count before it, the two counts are multiplied.  For example: "2d3w" deletes six words.

```
[count]motion[count]operator
```

**operator linewise or characterwise**

The operator either affects whole lines, or the characters between the start
and end position.  Generally, motions that move between lines affect lines
(are linewise), and motions that move within a line affect characters (are
characterwise).  

When a motion is not of the type you would like to use, you can force another
type by using "v", "V" or CTRL-V just after the operator.

**change text**

change operator: c

some shortcuts:

+   x(dl)
+   X(dh)
+   D(d$)
+   C(c$)
+   s(cl)
+   S(cc)

replace character under cursor: r
enter replace mode: R

repeating a change

command "." repeat last change. Works for all changes you make, except for the "u" (undo), CTRL-R (redo) and commands that start with a colon (:).

**moving text**

+   ["x]p   
Put the text [from register x] after the cursor [count] times.
+   ["x]P			
Put the text [from register x] before the cursor [count] times.  
+   xp
swap two characters

**copy text**
+   ["x]y{motion}		
rank {motion} text [into register x].
+   ["x]yy			
Yank [count] lines [into register x].


**visual mode**

select characters : v
select lines: SHIFT-V
select blocks: CTRL-V

go to other end of highlight text: o
in vusual mode, go to the other corner in the same line: O


**operator and text object**

Operator-text object is very similar to operator-motion, but instead of operating on the text
between the cursor position before and after a movement command, the text
object is used as a whole. It doesn't matter where in the object the cursor was.

some text objects

+   aw/aW/as/ap
a word/WORD/sentence/paragraph

+   a[/a]
a [] block

+   a(/a)
a () block

+   a{/a}
a {} block

+   a</a>
a <> block

+   a"/a'/a`
a quoted string

+   iw/iW/is/ip
inner word/WORD/sentence/paragraph

+   i[/i]
inner [] block

+   i(/i)
inner () block

+   i{/i}
inner {} block

+   i</i>
inner <> block

+   i"/i'/i`
inner quoted string

When used after an operator:
For non-block objects:
	For the "a" commands: The operator applies to the object and the white
	space after the object.  If there is no white space after the object
	or when the cursor was in the white space before the object, the white
	space before the object is included.
	For the "inner" commands: If the cursor was on the object, the
	operator applies to the object.  If the cursor was on white space, the
	operator applies to the white space.
For a block object:
	The operator applies to the block where the cursor is in, or the block
	on which the cursor is on one of the braces.  For the "inner" commands
	the surrounding braces are excluded.  For the "a" commands, the braces
	are included.
