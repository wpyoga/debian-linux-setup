`
```
while IFS= read -r LINE; do
  grep -qs -xF "$LINE" ~/.bashrc || echo "$LINE" >> ~/.bashrc
done <<"EOF"
alias diff='diff --color=auto'
alias grep='grep --color=auto'
#alias ip='ip --color=auto'
EOF

exit
```

