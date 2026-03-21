`
```
# customize terminal

xfconf-query -c xfce4-terminal -p /color-background -n -t string -s "#222"
xfconf-query -c xfce4-terminal -p /color-cursor -n -t string -s "#777"
xfconf-query -c xfce4-terminal -p /color-palette -n -t string -s "#000;#f66;#7e7;#fe8;#49f;#f7f;#3ee;#ddd;#666;#faa;#afa;#ffa;#6bf;#faf;#7ff;#fff;"
xfconf-query -c xfce4-terminal -p /misc-cursor-blinks -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-default-geometry -n -t string -s "96x32"
xfconf-query -c xfce4-terminal -p /misc-menubar-default -n -t bool -s false
xfconf-query -c xfce4-terminal -p /misc-copy-on-select -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-slim-tabs -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-new-tab-adjacent -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-show-unsafe-paste-dialog -n -t bool -s false
xfconf-query -c xfce4-terminal -p /scrolling-unlimited -n -t bool -s true
xfconf-query -c xfce4-terminal -p /font-name -n -t string -s "DejaVu Sans Mono 10.5"

exit
```

