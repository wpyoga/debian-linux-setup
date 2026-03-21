`
```
xf_set() { xfconf-query -c xsettings -p "$1" -n -t "$2" -s "$3" ; }

xf_set /Net/ThemeName string "Adwaita"
xf_set /Net/IconThemeName string "HighContrast"

xf_set /Xft/Antialias int 1
xf_set /Xft/DPI int 96
xf_set /Xft/Hinting int 1
#xf_set /Xft/HintStyle string "hintfull"
xf_set /Xft/HintStyle string "hintslight"
xf_set /Xft/RGBA string "rgb"

xf_set /Gtk/CanChangeAccels bool false
xf_set /Gtk/FontName string "Liberation Sans 10.5"
xf_set /Gtk/MonospaceFontName string "Noto Sans Mono 10"

while IFS= read -r LINE; do
  grep -qs -xF "$LINE" ~/.config/gtk-3.0/gtk.css || echo "$LINE" >> ~/.config/gtk-3.0/gtk.css
done <<"EOF"
* { outline-width: 2px; }
EOF

kill `pidof xfwm4`

exit
```

