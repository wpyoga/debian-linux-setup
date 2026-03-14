`
```
sudo tee /etc/systemd/system/mic-mute-led-off.service >/dev/null <<EOF
#[Unit]
#Description=Turn off mic mute LED
[Service]
ExecStart=sh -c "echo 0 | tee /sys/class/leds/platform::micmute/brightness >/dev/null"
[Install]
WantedBy=basic.target
EOF

sudo systemctl enable --now mic-mute-led-off.service

exit
```


