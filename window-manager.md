`
```
wm_set() { xfconf-query -c xfwm4 -p /general/"$1" -n -t "$2" -s "$3" ; }



wm_set button_layout string "O|HMC"
wm_set title_font string "Noto Sans Bold 10.5"

wm_set snap_to_windows bool true

wm_set scroll_workspaces bool false
wm_set wrap_cycle bool false
wm_set wrap_layout bool false
wm_set wrap_windows bool false

wm_set raise_with_any_button bool false

kill `pidof xfwm4`

exit
```

