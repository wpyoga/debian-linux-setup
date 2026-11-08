`
```
. /etc/os-release

sudo curl https://pkgs.tailscale.com/stable/debian/$VERSION_CODENAME.noarmor.gpg --output /etc/apt/keyrings/tailscale.gpg

sudo tee /etc/apt/sources.list.d/tailscale.list <<EOF
deb [signed-by=/etc/apt/keyrings/tailscale.gpg] https://pkgs.tailscale.com/stable/debian $VERSION_CODENAME main
EOF

sudo tee /etc/NetworkManager/conf.d/99-tailscale.conf <<EOF
[keyfile]
unmanaged-devices=interface-name:tailscale0
EOF

sudo apt update

# install openresolv so that NetworkManager (default for Debian desktop) and Tailscale
# don't fight over DNS
sudo apt install -y openresolv tailscale

exit
```

