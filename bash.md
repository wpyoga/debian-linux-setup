`
```
dpkg-query -W command-not-found 2>&1 >/dev/null \
  || (sudo apt install command-not-found && sudo apt update)

LINE="export HISTSIZE=9999"
grep -qs -xF "$LINE" ~/.bashrc || echo "$LINE" >> ~/.bashrc

exit
```

