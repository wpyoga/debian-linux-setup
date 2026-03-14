`
```

sudo tee /etc/apt/apt.conf.d/99no-translations >/dev/null <<"EOF"
Acquire::Languages "none";
EOF

sudo sed -e 's,^deb-src,#deb-src,' -i /etc/apt/sources.list

exit
```

