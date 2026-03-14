`
```
power_set() { xfconf-query -c xfce4-power-manager -p /xfce4-power-manager/"$1" -n -t "$2" -s "$3" ; }

power_set lid-action-on-ac int 1
power_set lid-action-on-battery int 1
power_set logind-handle-lid-switch bool true
power_set show-panel-label int 0
power_set show-tray-icon bool true
power_set general-notification bool true


exit
```

