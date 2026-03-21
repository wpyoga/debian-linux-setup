`
```

echo 'Binary::apt::Pager "false";' | sudo tee /etc/apt/apt.conf.d/99no-pager >/dev/null

echo 'Acquire::Languages "none";' | sudo tee /etc/apt/apt.conf.d/99no-translations >/dev/null

sudo sed -e 's,^deb-src,#deb-src,' -i /etc/apt/sources.list

sudo apt update

exit
```

