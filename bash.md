`
```
dpkg-query -W command-not-found 2>/dev/null >/dev/null \
  || (sudo apt install -y command-not-found && sudo apt update)

LINE="export HISTSIZE=9999"
grep -qs -xF "$LINE" ~/.bashrc || echo "$LINE" >> ~/.bashrc

sed \
  -e '/\\u@\\h\\\[\\033/i \# FG colors: 30 Black / 31 Red / 32 Green / 33 Yellow / 34 Blue / 35 Magenta / 36 Cyan / 37 White\nHOSTNAME_COLOR=33' \
  -e 's,\(\\u\)\(@\\h\\\[\\033\),\1\\[\\033[01;'"'\$HOSTNAME_COLOR'"'m\\]\2,' \
  -i ~/.bashrc

exit
```

