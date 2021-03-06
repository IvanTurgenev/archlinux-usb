# tmux terminal multiplexer (instead of screen)

Tmux has Session-Window-Pane hierarchy.

Start your session: `tmux`
Split pane vertically: `Ctrl-b %`
Split pane horizontally: `Ctrl-b "`
Move between panes: `Ctrl-b [arrows]`
Closing panes: `Ctrl-d`
Create a new window: `Ctrl-b c`
Switching between windows: `Ctrl-b p`, `Ctrl-b n`, `Ctrl-b [number]`
Detach current session: `Ctrl-b d`
List sessions: `tmux ls`
Attach a session: `tmux attach -t [number]`
Create a named session: `tmux new -s [name of new session] `
Rename a session: `tmux rename-session -t [number] [name of new session]`
Attach a named session: `tmux attach -t [name of session]`
Available commands: `Ctrl-b ?`
Toggle fullscreen of a pane: `Ctrl-b z`
Resize pane in direction of [arrow]: `Ctrl-b Ctrl-[arrow]`
Rename the current window: `Ctrl-b ,`

Tmux can enter into copy mode where all current terminal output is available in pager.

Enter copy mode and scroll up for the output: `Ctrl-b PgUp`
Quit the copy mode: `q`

## Powerline status bar

Install powerline status bar:
```
sudo pacman -Syu powerline powerline-fonts
```

Add following to your `~/.tmux.conf`:
```
source /usr/lib/python3.7/site-packages/powerline/bindings/tmux/powerline.conf
```

## Custom colortheme

You can use a custom colortheme for tmux, for example the one from this link:
<https://github.com/seebi/tmux-colors-solarized/blob/master/tmuxcolors-256.conf>

To append it to your tmux configuration:
```
cat tmuxcolors-256.conf >> ~/.tmux.conf
```

## Problems with st

If you have problems with tmux and vim under st - for example exiting vim under tmux exits the current session as well, this is the solution. If you did not install st with make clean install, you must compile the st terminfo entry with the following command (within the st source folder):
```
tic -sx st.info
```

This will create `~/.terminfo` folder with relevant data.


