# urxvt terminal emulator

Install urxvt:
```
sudo pacman -S urxvt-unicode
```

Make `~/.Xresources` file with some basic options:
```
URxvt*scrollBar: false
URxvt*background: Black
URxvt*foreground: White
URxvt.font: xft:monospace:size=8
```

Reload it with xrdb (you still have to open a new terminal):
```
xrdb ~/.Xresources 
```
