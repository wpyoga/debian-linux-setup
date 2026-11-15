`
```
# customize terminal

xf_term() { xfconf-query -c xfce4-terminal -p "$1" -n -t "$2" -s "$3" ; }

BLACK=444
BLACK_HI=DDD
RED=E55
RED_HI=C22
GREEN=191
GREEN_HI=2B2
YELLOW=946000
YELLOW_HI=B93
BLUE=65A5ED
BLUE_HI=2676CC
MAGENTA=8543A0
MAGENTA_HI=9947BA
CYAN=167D91
CYAN_HI=008AA5
WHITE=BBB
WHITE_HI=FFF


# uncomment for light mode terminal
xfconf-query -c xfce4-terminal -p /color-background -n -t string -s '#f7f7f7'
xfconf-query -c xfce4-terminal -p /color-foreground -n -t string -s '#222'
#xfconf-query -c xfce4-terminal -p /color-palette -s '#383A42;#B83228;#387A38;#946400;#285CB8;#852084;#006A94;#777A83;#696C77;#E45649;#50A14F;#C18401;#4078F2;#A626A4;#0184BC;#383A42'
#xfconf-query -c xfce4-terminal -p /color-palette -s '#343A40;#E45A60;#357A36;#946000;#65A5ED;#8543A0;#167D91;#E8EDF2;#555E68;#C93642;#278B3C;#AD7600;#2676CC;#9947BA;#008AA5;#FFFFFF'
#xfconf-query -c xfce4-terminal -p /color-palette -s '#343A40;#E45A60;#357A36;#946000;#65A5ED;#8543A0;#167D91;#B8BDC2;#555E68;#C93642;#278B3C;#AD7600;#2676CC;#9947BA;#008AA5;#FFFFFF'
#xfconf-query -c xfce4-terminal -p /color-palette -s '#343A40;#E45A60;#357A36;#946000;#65A5ED;#8543A0;#167D91;#B8BDC2;#A5AEA8;#C93642;#278B3C;#AD7600;#2676CC;#9947BA;#008AA5;#FFFFFF'

xfconf-query -c xfce4-terminal -p /color-palette -s "#$BLACK;#$RED;#$GREEN;#$YELLOW;#$BLUE;#$MAGENTA;#$CYAN;#$WHITE;#$BLACK_HI;#$RED_HI;#$GREEN_HI;#$YELLOW_HI;#$BLUE_HI;#$MAGENTA_HI;#$CYAN_HI;#$WHITE_HI"

# uncomment for standard terminal with dark background
#xfconf-query -c xfce4-terminal -p /color-background -n -t string -s "#222"
#xfconf-query -c xfce4-terminal -p /color-cursor -n -t string -s "#777"
#xfconf-query -c xfce4-terminal -p /color-palette -n -t string -s "#000;#f66;#7e7;#fe8;#49f;#f7f;#3ee;#ddd;#666;#faa;#afa;#ffa;#6bf;#faf;#7ff;#fff;"

xfconf-query -c xfce4-terminal -p /misc-cursor-blinks -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-default-geometry -n -t string -s "96x32"
xfconf-query -c xfce4-terminal -p /misc-menubar-default -n -t bool -s false
xfconf-query -c xfce4-terminal -p /misc-copy-on-select -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-slim-tabs -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-new-tab-adjacent -n -t bool -s true
xfconf-query -c xfce4-terminal -p /misc-show-unsafe-paste-dialog -n -t bool -s false
xfconf-query -c xfce4-terminal -p /scrolling-unlimited -n -t bool -s true
#xfconf-query -c xfce4-terminal -p /font-name -n -t string -s "DejaVu Sans Mono 10.5"
xfconf-query -c xfce4-terminal -p /font-name -n -t string -s "Noto Mono 10.5"

grep -qs -F "LS_COLORS=" ~/.bashrc || tee -a ~/.bashrc <<"EOF"
case "$TERM" in
  xterm-color|*-256color) export LS_COLORS="${LS_COLORS}:di=38;2;23;74;156:ln=38;2;0;208;224:tw=38;2;23;59;12;48;2;57;255;20";;
esac
EOF

exit
```

