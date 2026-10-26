`
```
sudo apt install -y fasttrack-archive-keyring

. /etc/os-release

sudo tee /etc/apt/sources.list.d/fasttrack.sources <<EOF
Types: deb
URIs: http://fasttrack.debian.net/debian-fasttrack
Suites: $VERSION_CODENAME-fasttrack
Components: main contrib non-free
Signed-By: /usr/share/keyrings/fasttrack-archive-keyring.gpg
EOF

sudo apt update

sudo apt install -y virtualbox

exit
```

