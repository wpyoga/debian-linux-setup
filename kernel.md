`
```
. /etc/os-release

sudo tee /etc/apt/sources.list.d/backports.list <<EOF
deb http://deb.debian.org/debian $VERSION_CODENAME-backports main contrib non-free non-free-firmware
EOF

sudo tee /etc/apt/preferences.d/backports-kernel <<EOF
Package: linux-image-amd64 linux-headers-amd64
Pin: release n=$VERSION_CODENAME-backports
Pin-Priority: 500
EOF

sudo apt update

sudo apt install -y linux-image-amd64

exit
```

