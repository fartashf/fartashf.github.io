---
layout: post
title: My tmux Cheat-sheet
comments: True
---

The moment I heard about `tmux`, I knew that all the trouble of working with 
`screen` was over. The most stupid thing about `screen` is that `ctrl-a`, such 
a frequently used combination, is replaced. Some of the most beautiful things 
about `tmux` before listing my cheat-sheet:

- Easy to name windows, and move them.
- Panes
- VIM mode in copy mode.

~~~
http://tmuxcheatsheet.com/ 
tmux new -s <name>
C-b ?: show help
C-b d: detach
tmux ls
tmux a -t <name>
C-b c: new window
C-b ,: rename window
C-b &: kill window
C-b l: change to last window
C-b n: change to next window
C-b p: change to prev window
C-b 0-9: change by window number
C-b s: list sessions
C-b $: rename session
C-b w: list windows
C-b %: split horizontally
C-b “: split vertically
C-b hjkl: move to panes
C-b q: show pane numbers
C-b o: move to next pane
C-b z: toggle pane zoom
C-b space: toggle pane layout
C-b {}: move the current pane
C-b x: kill pane
C-b !: convert pane into a window
C-b ;: change to last pane
C-b t: show time
C-b [: start copy mode
  space: start selection
  Escape: clear selection
  Enter: copy selection or exit copy mode
C-b ]: paste
C-b (): move between sessions
C-b s: show all sessions

restore tmux session
http://superuser.com/a/615716

:resize-pane -D/-L/-U/-R 20
~~~
