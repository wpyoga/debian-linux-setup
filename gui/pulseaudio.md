`
```
cat | sudo tee /etc/pulse/default.pa.d/suspend-on-idle.pa <<EOF
load-module module-suspend-on-idle timeout=5
EOF

pulseaudio -k

exit
```

