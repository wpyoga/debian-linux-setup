`
```
# the default vim installed is vim.tiny

grep -q '^ *source /etc/vim/vimrc.local *$' /etc/vim/vimrc.tiny ||
sudo tee -a /etc/vim/vimrc.tiny >/dev/null <<EOF

runtime! debian.vim
" load local customizations
if filereadable("/etc/vim/vimrc.local")
  source /etc/vim/vimrc.local
endif
EOF

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
