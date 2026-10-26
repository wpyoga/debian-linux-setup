`
```
sudo apt install -y ibus-rime


sudo tee /etc/environment.d/99ibus.conf <<EOF
GTK_IM_MODULE=ibus
QT_IM_MODULE=ibus
XMODIFIERS=@im=ibus
EOF

sudo tee /etc/xdg/autostart/ibus.desktop >/dev/null <<EOF
[Desktop Entry]
Type=Application
Name=Ibus
Exec=ibus-daemon -drxR
Icon=ibus
EOF

gsettings set org.freedesktop.ibus.panel property-icon-delay-time 0
gsettings set org.freedesktop.ibus.general switcher-delay-time 0

gsettings set org.freedesktop.ibus.general engines-order "['xkb:us::eng', 'rime']"
gsettings set org.freedesktop.ibus.general preload-engines "['xkb:us::eng', 'rime']"
gsettings set org.freedesktop.ibus.general.hotkey triggers "['<Control>space']"

gsettings set org.freedesktop.ibus.panel lookup-table-orientation 0
gsettings set org.freedesktop.ibus.panel use-custom-font true
gsettings set org.freedesktop.ibus.panel custom-font "'Sans 14'"

tee ~/.config/ibus/rime/user.yaml <<EOF
var:
  option:
    ascii_punct: false
    full_shape: false
  previously_selected_schema: luna_pinyin_simp
EOF

tee ~/.config/ibus/rime/ibus_rime.custom.yaml <<EOF
patch:
  style:
    horizontal: true
EOF

tee ~/.config/ibus/rime/luna_pinyin_simp.custom.yaml <<"EOF"
# Save this file as ~/.config/ibus/rime/luna_pinyin_simp.custom.yaml
# Run `ibus restart`, then switch window focus (Alt-Tab) to refresh ibus state
# Or run: rime_deployer --build ~/.config/ibus/rime /usr/share/rime-data ~/.config/ibus/rime/build
# Configure half-width mode (半角) and full width punctuation (。，)
# The following overrides specific punctuation keys for full-width characters
patch:
  reverse_lookup: {}      # to override "`"
  recognizer: {}          # to override "`"
  punctuator:
    half_shape:
      # Number row
      "~": { commit: "～" }
      "`": { commit: "`" }
      "!": { commit: "！" }
      "$": { commit: "￥" }
      "^": { commit: "……" }
      "(": { commit: "（" }
      ")": { commit: "）" }
      "_": { commit: "——" }
      # Symbols near Enter key
      "{": { commit: "『" }
      "}": { commit: "』" }
      "[": { commit: "【" }
      "]": { commit: "】" }
      "\\": { commit: "、" }
      ":": { commit: "：" }
      ";": { commit: "；" }
      "\"": { pair: ["“", "”"] }
      "'": { pair: ["‘", "’"] }
      "<": { commit: "《" }
      ">": { commit: "》" }
      ",": { commit: "，" }
      ".": { commit: "。" }
      "?": { commit: "？" }
EOF

ibus restart
#rime_deployer --build ~/.config/ibus/rime /usr/share/rime-data ~/.config/ibus/rime/build

exit
```

