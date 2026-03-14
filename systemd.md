`
```
LINE="export SYSTEMD_PAGER="
grep -qs -xF "$LINE" ~/.bashrc || echo "$LINE" >> ~/.bashrc

exit
```

