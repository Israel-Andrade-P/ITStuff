# Vim Cheat Sheet 🧠⚡

---

## NORMAL MODE

### Movements & Navigation
```vim
gg            " go to top of file
G             " go to bottom of file
<number>G     " jump to specific line

w             " move forward by word
b             " move backward by word
e             " move to end of word
0             " beginning of line
$             " end of line

M             " move cursor to middle of screen

Ctrl+d        " scroll down half page
Ctrl+u        " scroll up half page
Ctrl+f        " forward one screen
Ctrl+b        " backward one screen

%             " jump to matching pair {}, (), []
```
### Text Editing
```
x             " delete character under cursor
u             " undo

dw            " delete word
dd            " delete line
diw           " delete inner word
dip           " delete inner paragraph
dap           " delete a paragraph

yw            " yank word
yy            " yank line
yiw           " yank inner word
yip           " yank inner paragraph
ggVGy         " yank entire file

ciw           " change inner word
cip           " change inner paragraph

ci"           " change inside quotes
ci( / cib     " change inside parentheses
ci{ / ciB     " change inside curly braces

gUiw          " uppercase inner word
gui"          " lowercase inside quotes
gUap          " uppercase paragraph

yi(           " yank inside parentheses
vi{           " select inside curly braces
=ip           " auto-indent paragraph

J             " join line with next (adds space)
gJ            " join line with next (no space)
```
### Search, Macros & Registers
```
*             " search word under cursorO
n             " next match
N             " previous match

.             " repeat last command

"<reg>p       " paste from register
"<reg>y       " yank into register

qh            " start recording macro into register h
@h            " replay macro from register h

/word         " search for word

g-            " go backward in undo tree
g+            " go forward in undo tree
```
## COMMAND MODE
```
:             " enter command mode
:q            " quit
:wq           " save and quit
:q!           " quit without saving
:x            " save and quit
ZZ            " save and quit

:r file       " read file into current buffer
:w file       " write to new file

:!command     " run shell command from Vim

:e file       " open file in new buffer
:enew         " create empty buffer

:bn           " next buffer
:bp           " previous buffer
:bd           " delete buffer
:badd file    " add buffer without switching

:%s/old/new/g     " find and replace
:%s/old/new/gc    " replace with confirmation

:split file   " horizontal split
:vsplit file  " vertical split
Ctrl+w w      " switch between splits

:set number       " show line numbers
:set nonumber    " hide line numbers

:reg          " view registers
:<number>     " jump to line number
```
## INSERT MODE
```
i             " insert before cursor
a             " insert after cursor
A             " insert at end of line

o             " new line below
O             " new line above
```
## VISUAL MODE
```
v             " visual mode
V             " visual line mode

c             " change selection

>             " indent selection
<             " outdent selection
=             " auto-indent

gu            " lowercase selection
gU            " uppercase selection

vaw           " select around word
viw           " select inner word

:sort ui      " sort selection alphabetically

t<char>       " move before character
f<char>       " move to character

:s/old/new    " replace in selection (supports regex) Regex note: characters like (, [, { must be escaped with \.
```
## REPLACE MODE
```
R             " enter replace mode
```

## GENERAL
```
vim +<line> file            # open file at line
vim -O file1 file2          # open files in horizontal splits
```

