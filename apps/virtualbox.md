`
```
. /etc/os-release

sudo tee /etc/apt/sources.list.d/virtualbox.list <<EOF
deb [signed-by=/etc/apt/keyrings/oracle_vbox_2016.asc] https://download.virtualbox.org/virtualbox/debian $VERSION_CODENAME contrib
EOF

cd /etc/apt/keyrings
sudo wget -nc https://www.virtualbox.org/download/oracle_vbox_2016.asc

sudo apt update

sudo apt install -y virtualbox-7.2

exit
```

