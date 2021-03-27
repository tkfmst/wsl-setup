## windows terminal

### 起動設定を変更する

guidはlistから選択
```
    "defaultProfile": "{1777cdf0-b2c4-5a63-a204-eb60f349ea7c}",
```

### 起動ディレクトリを変更する

listの該当ディストリビューション配下に追加
```
    "startingDirectory": "//wsl$/Alpine/home/【ユーザー名】",
```

### font変更

listに以下を設定
```
    "fontFace": "Cascadia Mono",
    "fontSize": 10
```

### keybindsの変更 

```diff
- // { "command": {"action": "copy", "singleLine": false }, "keys": "ctrl+c" },
+ { "command": {"action": "copy", "singleLine": false }, "keys": "ctrl+shift+c" },
- // { "command": "paste", "keys": "ctrl+v" },
+ { "command": "paste", "keys": "ctrl+shift+v" },
```

## Alpine

### package repository update

```
$ su -
# apk update
```

### install man-pages

```
$ sudo apk add mandoc man-pages
```

### install sudo

```
# apk add sudo
# visudo
## 以下みたいに書く
## takafumi ALL=(ALL) ALL
##
```

### install lib

```
$ sudo apk add zlib-dev
$ sudo apk add bzip2-dev
$ sudo apk add readline-dev
$ sudo apk add openssl-dev
```

### install basic command

```
# ncurses: tputとかinstallされる
# coreutils: dircolorsとかinstall
$ sudo apk add curl make file ncurses coreutils

$ sudo apk add tree
```

### install ssh

```
$ sudo apk add openssh
$ eval `ssh-agent`
$ ssh-add ~/.ssh/id_XXX
```

### install rsync

```
$ sudo apk add rsync
```

### install git

```
$ sudo apk add git
```

### install tmux

```
$ sudo apk add tmux
```

### install zsh

```
$ sudo apk add zsh zsh-vcs
$ curl -sL --proto-redir -all,https https://raw.githubusercontent.com/zplug/installer/master/installer.zsh | zsh
```

### install bash

```
$ sudo apk add bash
```

### install c, c++

```
$ sudo apk add gcc g++
```

### install perl

```
$ sudo apk add perl
```

### install java

```
# see: https://docs.aws.amazon.com/ja_jp/corretto/latest/corretto-8-ug/generic-linux-install.html
$ sudo wget -O /etc/apk/keys/amazoncorretto.rsa.pub  https://apk.corretto.aws/amazoncorretto.rsa.pub
$ sudo echo "https://apk.corretto.aws/" >> /etc/apk/repositories
$ sudo apk update

$ sudo apk add amazon-corretto-8
```

### install python

```
$ sudo apk add python3 python3-dev py3-pip
# pyenv
$ git clone https://github.com/pyenv/pyenv.git ~/.pyenv
# pyenv-virtualenv
$ git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenvjjjjkkkjjkkkkkjjjjjjjkkkkkk
```

### install node

```
$ sudo apk add npm yarn
$ mkdir ~/.node_modules                                                                                                     ~
$ npm config set prefix ~/.node_modules                                                                                     ~
```

### install golang

```
$ sudo apk add go
```

### install rust

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup component add rls rust-analysis rust-src

// エラーになる
// $ zsh: segmentation fault
cargo install cargo-edit
```

### install neovim

```
$ sudo apk add vim neovim neovim-doc
$ npm install -g neovim
$ pip install neovim
```

### install plantuml

```
$ sudo apk add  graphviz fontconfig ttf-dejavu
$ sudo dot -c

# https://plantuml.com/ja/starting
# からplantuml.jarをダウンロード
$ mv plantuml.jar ~/lib/
```

### install tool

```
$ sudo apk add ripgrep fd exa
# ripgrep: 高速grep
# fd: find系
# exa: ls代替
```

### setup dotfiles

```
$ mkdir -p ~/github/tkfmst
$ cd ~/github/tkfmst
$ git clone git@github.com:tkfmst/dotfiles.git
$ cd ~

$ ln -s ~/github/tkfmst/dotfiles .

$ arr="
  .gitconfig
  .alias
  .config
  .colorrc
  .tmux.conf
  .zshrc
  .zprofile
  .zplug
  os
"
$ for fname in $arr; do ln -s ~/dotfiles/$fname .; done
```
