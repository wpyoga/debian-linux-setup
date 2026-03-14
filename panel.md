`
```
# convenience functions
panel_remove() { xfconf-query -c xfce4-panel -p "$1" -Rr ; }
panel_set() { xfconf-query -c xfce4-panel -p "$1" -n -t "$2" -s "$3" $4 ; }
panel_plugin() { panel_set /plugins/plugin-"$1" string "$2" ; PLUGINS="$PLUGINS $1" ; }
panel_plugin_opt() { panel_set /plugins/plugin-"$1"/"$2" "$3" "$4" $5 ; }
panel_separator() { panel_plugin "$1" separator ; panel_plugin_opt "$1" expand bool "$2" ; panel_plugin_opt "$1" style int "$3" ; }
panel_launcher() { panel_plugin "$1" launcher ; panel_plugin_opt "$1" items string "$2" -a ; }

# clean up first
rm -r ~/.config/xfce4/panel/

panel_remove /panels

panel_set /panels int 1 -a
panel_set /panels/dark-mode bool false
panel_set /panels/panel-1/icon-size int 24
panel_set /panels/panel-1/length int 100
panel_set /panels/panel-1/position string 'p=4;x=0;y=0'
panel_set /panels/panel-1/position-locked bool true
panel_set /panels/panel-1/size int 32

panel_remove /plugins
PLUGINS=

panel_plugin 1 whiskermenu
panel_plugin_opt 1 button-title string XFCE
panel_plugin_opt 1 hover-switch-category bool true
panel_plugin_opt 1 launcher-show-tooltip bool false
panel_plugin_opt 1 position-categories-alternate bool true
panel_plugin_opt 1 position-search-alternate bool true
panel_plugin_opt 1 show-button-title bool true

panel_separator 9 false 0

panel_launcher 11 xfce4-web-browser.desktop

panel_launcher 12 xfce4-terminal-emulator.desktop

panel_launcher 13 xfce4-file-manager.desktop

panel_plugin 14 directorymenu
panel_plugin_opt 14 base-directory string "$HOME"

panel_plugin 21 tasklist
panel_plugin_opt 21 flat-buttons bool false
panel_plugin_opt 21 grouping uint 0
panel_plugin_opt 21 middle-click uint 1
panel_plugin_opt 21 show-labels bool true
panel_plugin_opt 21 sort-order uint 4
panel_plugin_opt 21 window-scrolling bool false

panel_separator 29 true 0

panel_plugin 99 pager

panel_separator 98 false 0

panel_plugin 31 systray
panel_plugin_opt 31 square-icons bool true

panel_plugin 32 clock

panel_plugin 33 showdesktop

# now we create the plugin array
xfconf-query -c xfce4-panel -p /panels/panel-1/plugin-ids -n \
  $(echo "$PLUGINS" | sed -e 's, , -t int -s ,g')

pidof xfce4-panel 2>&1 >/dev/null \
  || (xfce4-panel 2>&1 >/dev/null &) \
  && xfce4-panel -r

exit
```


