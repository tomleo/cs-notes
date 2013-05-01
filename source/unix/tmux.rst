TMUX NOTES
==========

Start tmux session::
   tmux new-session -s <name>
   tmux new -s <name>

Detatch session::
   Ctrl-b d

List existing tmux sessions::
   tmux list-sessions
   tmux ls

start tmux session::
   tmux attach -t <name>

kill session (while in the session::
   exit

kill session::
   tmux kill-session -t <name>

new window::
   PRE c

rename window::
   PRE ,

next/previous window::
   PRE n
   PRE p

n window::
   PRE n

find window::
   PRE f

list windows::
   PRE w

close window::
   PRE &

split pane verticle::
   PRE %

split pane horizontal::
   PRE "

switch pane::
   PRE o
   PRE <left|right|top|down arrow>

close pane::
   exit
   PRE x

LEFT off @ 1.5 Working with Panes - tmux book
---------------------------------------------

::

    Ctrl-b c Create new window
    Ctrl-b d Detach current client
    Ctrl-b l Move to previously selected window
    Ctrl-b n Move to the next window
    Ctrl-b p Move to the previous window
    Ctrl-b & Kill the current window
    Ctrl-b , Rename the current window
    Ctrl-b % Split the current window into two panes
    Ctrl-b q Show pane numbers (used to switch between panes)
    Ctrl-b o Switch to the next pane
    Ctrl-b ? List all keybindings

