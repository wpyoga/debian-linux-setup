`
```
sudo tee /etc/apt/apt.conf.d/99no-pager <<EOF
Binary::apt::Pager "false";
EOF

sudo tee /etc/apt/apt.conf.d/99no-translations <<EOF
Acquire::Languages "none";
EOF

sudo sed -e 's,^deb-src,#deb-src,' -i /etc/apt/sources.list

. /etc/os-release

sudo tee /etc/apt/sources.list.d/backports.list <<EOF
deb http://deb.debian.org/debian $VERSION_CODENAME-backports main contrib non-free non-free-firmware
EOF

sudo apt update

exit
```

