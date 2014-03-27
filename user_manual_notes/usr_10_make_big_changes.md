**record and replay changes**

1.  The `q{register}` command starts recording keystrokes into the register
named {register}. The register name must be between a and z.
2.  Type your commands.
3.  To finish recording, press q (without any extra character).  You can now execute the macro by typing the command "@{register}".

You can now execute the macro by typing the command "@{register}".
The "@a" command can be preceded by a count, which will cause the macro to
be executed that number of times.
use "@@" to repeat last "@{register}" command.

substitute

:[range]s[ubstitute]/{pattern}/{string}/[flags] [count]

flags:

+   c
confirm each substitution

+   e
When the search pattern fails, do not issue an error message and, in particular, continue in maps as if no error occurred.  This is most useful to prevent the "No match" error from breaking a mapping.

+   g
Replace all occurrences in the line.  Without this argument, replacement occurs only for the first occurrence in each line.

+   i
ignore case for the pattern.

+   n
report the number of matches, do not actually substitute.

If the {pattern} for the substitute command is empty, the command uses the
pattern from the last substitute or ":global" command.  If there is none, but
there is a previous search pattern, that one is used.  With the [r] flag, the
command uses the pattern from the last substitute, ":global", or search
command.

If the {string} is omitted the substitute is done as if it's empty.  Thus the
matched pattern is deleted.  The separator after {pattern} can also be left
out then.  Example: >
	:%s/TESTING
This deletes "TESTING" from all lines, but only one per line.

[range]read other_file
read range lines from other_file into current file

[range]write other_file
write range lines to other_file

[range]write >>other_file
append range lines to other_file

[range]m[ove] {address}
Move the lines given by [range] to below the line given by {address}.
