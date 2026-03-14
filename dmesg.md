`
```
# enable dmesg for all users

sudo tee /etc/sysctl.d/99-no-dmesg_restrict.conf >/dev/null <<EOF
kernel.dmesg_restrict=0
EOF

sudo systemctl restart systemd-sysctl

# use human-readable time

LINE="alias dmesg='dmesg -HP'"
grep -qs -xF "$LINE" ~/.bashrc || echo "$LINE" >> ~/.bashrc

exit
```

