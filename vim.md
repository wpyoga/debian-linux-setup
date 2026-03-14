`
```
# use regular vim for syntax highlighting and more
sudo apt install --autoremove vim vim-tiny-

sudo tee /etc/vim/vimrc.local >/dev/null <<EOF
runtime! defaults.vim
let g:skip_defaults_vim = 1
set mouse=
set noincsearch
set paste
set ruler
set nocompatible
EOF

exit
```
