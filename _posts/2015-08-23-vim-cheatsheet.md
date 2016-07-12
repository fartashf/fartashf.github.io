---
layout: post
title: My VIM Cheat-sheet
comments: True
---

What I enjoy the most in VIM is how commands get combined to do complicated 
tasks. I don't need to hold multiple keys to do every single task, I can type 
letters as if I'm talking to the editor. Here are some beautiful examples 
before diving into my cheat-sheet:

- `ya(` Yank text Around ()
- `ctr-v 10j shift-i #### ESC` Visual block mode, select 10 lines below, insert 
  at the beginning, ####, done. And you've got a special comment section.

  * [Motions](#motions)
    * [Starters](#starters)
    * [Motions and Operators](#motions-and-operators)
    * [Left-Right Motions](#left-right-motions)
    * [Up-Down Motions](#up-down-motions)
    * [Word Motions](#word-motions)
    * [Text Object Motions](#text-object-motions)
    * [Text Object Selection](#text-object-selection)
    * [Marks](#marks)
    * [Jumps](#jumps)
    * [Various motions](#various-motions)
    * [Traversing text in Insert mode](#traversing-text-in-insert-mode)
  * [Folding](#folding)
    * [Starters](#starters-1)
    * [Long](#long)
  * [pymode keys](#pymode-keys)
  * [vim-unimpaired](#vim-unimpaired)
  * [Recording](#recording)
  * [Set Flags](#set-flags)
  * [Split](#split)
  * [Misc.](#misc)
    * [Making a list of numbers](#making-a-list-of-numbers)
    * [Enclose A Word](#enclose-a-word)
    * [Replace A Word With A Register](#replace-a-word-with-a-register)
    * [Mouse Copy](#mouse-copy)

# Motions

## Starters

~~~
ctrl-g shows where you are in a file
cursor history C-o and C-i
All the right moves http://vim.wikia.com/wiki/All_the_right_moves
H, M, L move cursor to top, middle or bottom of screen
h, l move left, right
k, j move up, down
0, _ move to beginning of line
$, g_ move to end of line
ctrl-u, ctrl-d move half page up and down

_ move to first non-blank character of the line
g_ move to last non-blank character of the line

Use g* or g# if you don't want to search for the exact word.
http://vim.wikia.com/wiki/VimTip7
use [( [{ [) [} to get to the closest opening and closing brackets or parentheses from inside them.
use [[ ]] to navigate between sections or {}

ci} ci( ci[ ci' change inside brackets 
vi} select inside brackets
ca} ca( ca' caw change around
s substitute char
S,cc substitute line
I insert at beginning
A insert at end
dt; delete until ;
J join lines
g- undo in time
g+ redo in time
C-6 switch between open buffers
f<c> jump to next <c>
F<c> jum to prev <c>
~~~

## Motions and Operators

~~~
c change
d delete
y yank
~ swap case
gu make lower case
gU make upper case
= filter through 'equalprg' or C-indenting
<> shift left/right
zf define a fold

v force the operator to work characterwise
V force the operator to work linewise
ctrl-v force the operator to work blockwise
~~~

## Left-Right Motions

~~~
h/l
0 to the first char of the line
^ to the first non-blank char of the line
$ to the last char
g_ to the last non-blank char
g0 when line wraps to the first char of the line
g^ when line wraps like ^
gm like 0 but half a screen-width to the right
g$ when line wraps
| to screen column in the cur line
f{char} to next occurrence of char
F{char} to prev occurrence of char
t T like f but before and after chars
; repeat last f F t T
, repeat last f F t T in opposite direction
~~~

## Up-Down Motions

~~~
k/j
gj
gk
- upwards on the first non-blank
+ downwards on the first non-blank
_ downwards on the first non-blank count-1 times
G got to line, default last line
gg go to line, default first line
{count}% go to percentage in file
~~~

## Word Motions

~~~
w words forward
W WORDS forward (to the next blank char)
e forward to the end of word
E forward to the end of WORD
b backwards
B backwards
ge backwards to the end of word
gE backwards
~~~

## Text Object Motions

~~~
( sentence backwards
) sentence forwards
{} paragraphs
~~~

## Text Object Selection

~~~
aw "a word"
iw "inner word"
aW "a WORD"
iW "inner WORD"
as "a sentence"
is "inner sentence"
ap "a paragraph"
ip
a[ a] "a [] block"
a( a) "a () block"
a< a> "a <> block"
a{ a} " a {} block"
a" a' a~ "a "'~ block"
~~~

## Marks

~~~
~ jump to the location
' jump to the first char of the line
m' m~ set the previous context mark
m{a-zA-Z} set a mark
'{a-z} ~{a-z} jump to mark
:marks
'[ ~[ '] ~] to the first or last char of the previously changed
'' ~~ to the last jump
'^ ~^ to the last insert
'. ~. to the last change
~~~

## Jumps

~~~
ctrl-o jump to older position
<tab> or ctrl-i jump to newer position
~~~

## Various motions

~~~
% find the next item in this line and jump to its match. Item can be ([{}]) /**/ #if ...
[] + ({[mM  got to next or prev item
H M L go to home, middle, last line of screen

~~~

## Traversing text in Insert mode

[http://stackoverflow.com/a/1737259](http://stackoverflow.com/a/1737259)


~~~
Ctrl-w change previous word and stay in insert mode
~~~

# Folding

## Starters

~~~
za toggle
zo open
zc close
zf'a create a fold from current line to mark a
~~~

## More

~~~
zx undo everything and recompute folds
zM close all folds
zR open all folds
zi toggle foldenable
zm fold more, subtract one from foldlevel
zr reduce folding add one to foldlevel

zO open all folds under cursor
zC close all folds under cursor

za toggle folding
zA toggle folding recursively
zo open one or count folds

zn Fold "none" reset foldenable and open all folds
zN Fold "normal" set foldenable and restores all folds

zj zk move between folds
[z ]z move to the start or end of the current fold
~~~

# pymode keys

~~~
[M ]M move between methods
[C ]C move between classes
ctrl-space completion
~~~

# vim-unimpaired

~~~
[l ]l :lprev :lnext
[q ]q :cprev :cnext
[b ]b :bprev :bnext
~~~

# Recording

~~~
q <letter> starts
q ends
@ <letter> replay
~~~

# Set Flags

~~~
:set            - shows vars different from defaults
:set all        - shows all values
:set foo?       - shows the value of foo
:set foo+=opt   - add opt to the value w/o changing others
:set foo-=opt   - remove opt from value
:set foo&       - reset foo to default value
:setlocal foo   - only the current buffer
~~~

# Split

[https://technotales.wordpress.com/2010/04/29/vim-splits-a-guide-to-doing-exactly-what-you-want/](https://technotales.wordpress.com/2010/04/29/vim-splits-a-guide-to-doing-exactly-what-you-want/)


~~~
:topleft new
window  horizontal  up      -->   :topleft    split
window  horizontal  down    -->   :botright   split
window  vertical    left    -->   :topleft    vsplit
window  vertical    right   -->   :botright   vsplit
buffer  horizontal  up      -->   :leftabove  split
buffer  horizontal  down    -->   :rightbelow split
buffer  vertical    left    -->   :leftabove  vsplit
buffer  vertical    right   -->   :rightbelow vsplit
~~~

# Misc.

## Making a list of numbers

[http://vim.wikia.com/wiki/Making_a_list_of_numbers](http://vim.wikia.com/wiki/Making_a_list_of_numbers)


~~~
:put =range(11,15)
:put =map(range(1,150), 'printf(''%04d'', v:val)')
:for i in range(1,10) | put ='192.168.0.'.i | endfor
~~~

## Enclose A Word

~~~
ciw(Ctrl+r")
~~~

## Replace A Word With A Register

In general, select with visual mode then use other commands to replace

[http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text ](http://vim.wikia.com/wiki/Replace_a_word_with_yanked_text )

~~~
viwp
~~~

## Mouse Copy

~~~
:set all&
:redraw!
:set cc=""
~~~

~~~
:set paste/nopaste
vim broken arrow keys -> :!reset
vim :diffthis similar to vimdiff
replace with newline \r
copy to clipboard: install vim-gnome

r: replace character
.: repeat last command
http://unix.stackexchange.com/questions/22590/block-editing-live-in-emacs-or-vim 
Start and end selection in positions outside the text
:set virtualedit=block
~~~
