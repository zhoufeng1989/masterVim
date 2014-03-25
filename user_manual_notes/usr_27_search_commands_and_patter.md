**ignore case**

```
" ignorecase
:set ignorecase

" Override the 'ignorecase' option if the search pattern contains upper case characters.  
" Only used when the search pattern is typed and 'ignorecase' option is on.
:set ignorecase smartcase

" overrules the 'ignorecase' and 'smartcase' option
" \c case-sensitive
" \C case-insensitive
" only matches word
\Cword 

" match WORD, word, Word and etc.
\cword
```

**offset**

By default, the search command leaves the cursor positioned on the beginning
of the pattern. You can tell Vim to leave it some other place by specifying
an offset. For the forward search command "/", the offset is specified by
appending a slash (/) and the offset. If offset is positive, the cursor moves down that many lines; if negative, it moves up.


```
/default/2
```

character offsets

```
" e offset indicates an offset from the end of the match, the cursor will on two characters behind this word
/default/e-2

" b offset indicates an offset from the begin of the match
/default/b+2
```

**the search pattern may be a regular expression**

**match a line break**

\_x	Where "x" is any of the characters classes: The character class with end-of-line added

```
" match line break
/the\nword

" match line break or space
/the\_sword

" match any amout of write space
/the\_s\+word
```
