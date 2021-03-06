=========
TMUX Tips
=========

Plugins
-------

- tpm            : tmux plugin manager;
- tmux-open      : open highlighted selection directly from tmux copy mode;
- tmux-copycat   : enhance tmux search;
- tmux-yank      : copy to system clipboard;
- tmux-sensible  : basic tmux setting sensible for everyone;
- tmux-continuum : continuous saving of tmux environment and automatic restore when tmux is started;
- tmux-resurrect : persists tmux environment across system restarts;
- tmux-themepack : thems;

Tools
-----

- tmuxp  : tmux session manager, which can be used to start sessions based on yaml definition;
- xpanes : conduct concurrent ops with multiple panes, e.g., xpanes -c "ssh root@{}" host1 host2

Scripts
--------

- Create panels from shell

  ::

    tmux new-window -n sshlogins
    for IP in 11 12 13; do
      tmux split-window "ssh root@192.168.10.${IP}"
      tmux select-layout tiled
    done

Shortcuts
----------

+----------------------------------------+-----------------------------------------------+
|Action                                  |  Shortcuts                                    |
+========================================+===============================================+
|Help                                    |  ^b ? (q to exit)                             |
+----------------------------------------+-----------------------------------------------+
|List keys/commands                      |  tmux list-keys/list-commands                 |
+----------------------------------------+-----------------------------------------------+
|Reattach a detached session             |  tmux attach                                  |
+----------------------------------------+-----------------------------------------------+
|Re-attach an attached session           |  tmux attach -d (redraw tmux display to max)  |
+----------------------------------------+-----------------------------------------------+
|Detach from current session             |  ^b d OR ^b :detach                           |
+----------------------------------------+-----------------------------------------------+
|Assign a new name to a session          |  ^b $ OR tmux new-session -s <name>           |
+----------------------------------------+-----------------------------------------------+
|Rename a window                         |  ^b ,                                         |
+----------------------------------------+-----------------------------------------------+
|List windows                            |  ^b w                                         |
+----------------------------------------+-----------------------------------------------+
|Go to window                            |  ^b <num.>                                    |
|                                        |  ^b '<num. ge 10 >                            |
+----------------------------------------+-----------------------------------------------+
|Go to next window                       |  ^b n                                         |
+----------------------------------------+-----------------------------------------------+
|Go to previous window                   |  ^b p                                         |
+----------------------------------------+-----------------------------------------------+
|List session                            |  ^b s OR tmux ls                              |
+----------------------------------------+-----------------------------------------------+
|Create a new window                     |  ^b c                                         |
+----------------------------------------+-----------------------------------------------+
|Exit current window                     |  ^d                                           |
+----------------------------------------+-----------------------------------------------+
|Split window/pane horizontally          |  ^b "                                         |
+----------------------------------------+-----------------------------------------------+
|Split window/pane vertically            |  ^b %                                         |
+----------------------------------------+-----------------------------------------------+
|Change pane layout                      |  ^b space                                     |
+----------------------------------------+-----------------------------------------------+
|Use horzion/vertical layout             |  ^b M 1/2                                     |
+----------------------------------------+-----------------------------------------------+
|Switch to other pane                    |  ^b o OR ^b q <num.>                          |
+----------------------------------------+-----------------------------------------------+
|Kill the current pane                   |  ^b x                                         |
+----------------------------------------+-----------------------------------------------+
|Move the current pane out as a window   |  ^b !                                         |
+----------------------------------------+-----------------------------------------------+
|Swap panes                              |  ^b ^o                                        |
+----------------------------------------+-----------------------------------------------+
|Swap current pane with previous/next    |  ^b {/}                                       |
+----------------------------------------+-----------------------------------------------+
|Show pane index                         |  ^b q                                         |
+----------------------------------------+-----------------------------------------------+
|Toggle zoom-state of current pane       |  ^b z                                         |
+----------------------------------------+-----------------------------------------------+
|Copy mode/Scroll up/down                |  ^b [ + Up/Down/PgUp/PgDown(q to exit)        |
+----------------------------------------+-----------------------------------------------+
|Copy                                    |  ^b [ + space -> move cursor -> Enter         |
+----------------------------------------+-----------------------------------------------+
|Paster                                  |  ^b ]                                         |
+----------------------------------------+-----------------------------------------------+
|Search in copy mode                     |  ^s                                           |
+----------------------------------------+-----------------------------------------------+
|Resize pane                             |  ^b Alt + Up/Down/Left/Right                  |
+----------------------------------------+-----------------------------------------------+
|Enable/disable mouse                    |  ^b: set-option [-g] mouse on/off             |
+----------------------------------------+-----------------------------------------------+
|Tmux in another tmux                    |  ^b ^b + <keys>                               |
+----------------------------------------+-----------------------------------------------+
|switch client                           |  ^b (/)                                       |
+----------------------------------------+-----------------------------------------------+
|Choose tree                             |  ^b s                                         |
+----------------------------------------+-----------------------------------------------+
|vi mode                                 |  ^b: set-option [-g] mode-keys vi             |
+----------------------------------------+-----------------------------------------------+
|Move window/pane                        |  - ^b: move-window -s <src> -t <dst>          |
|(src/dst format as:                     |  - ^b: move-pane -s <src> -t <dst>            |
|[session name]:[windows id][.]<pane id>)|  - ^b: join-pane -s <src> -t <dst>            |
|                                        |  - ^b m + ^b: move/join-window/pane -s <src>  |
|                                        |  - ^b: move-window -r                         |
+----------------------------------------+-----------------------------------------------+
|Shortcut for moving a window            |  ^b .                                         |
+----------------------------------------+-----------------------------------------------+
|Run same commands on all panes          |  ^b: set-option [-g] synchronize-panes on/off |
+----------------------------------------+-----------------------------------------------+
|Backup/restore sessions(tmux-rescurrect)|  ^b ^s -> save ; ^b ^r -> restore             |
+----------------------------------------+-----------------------------------------------+
|Automatic rename panel                  |  - ^b: set-optiong -g allow-rename on/off     |
|                                        |  - ^b: set-optiong -g automatic-rename on/off |
+----------------------------------------+-----------------------------------------------+
|Show global options                     |  ^b: show-optionts -g                         |
+----------------------------------------+-----------------------------------------------+
|Show global options about window        |  ^b: show-options -g -w                       |
+----------------------------------------+-----------------------------------------------+
|Create a new session                    |  ^b: new -s <session name>                    |
+----------------------------------------+-----------------------------------------------+
|Set border color                        |  - ^b: set -g pane-active-border-bg default   |
|                                        |  - ^b: set -g pane-active-border-fg colour208 |
+----------------------------------------+-----------------------------------------------+
|Display information                     |  ^b: display-message -p '#{pane_width}'       |
+----------------------------------------+-----------------------------------------------+
