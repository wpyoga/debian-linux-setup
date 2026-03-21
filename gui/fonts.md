`
```
dpkg-query -W fonts-noto 2>/dev/null >/dev/null \
  || (sudo apt install -y fonts-noto)

exit
```




