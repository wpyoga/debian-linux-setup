`
```

sudo mkdir -p -m 755 /etc/apt/keyrings
cd /etc/apt/keyrings
sudo wget -nc https://cli.github.com/packages/githubcli-archive-keyring.gpg
sudo chmod go+r githubcli-archive-keyring.gpg

sudo tee /etc/apt/sources.list.d/github-cli.list <<EOF
deb [signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main
EOF

sudo apt update

sudo apt install -y gh

exit
```

