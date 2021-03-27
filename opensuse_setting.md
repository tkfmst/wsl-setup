sudo zypper in gcc-c++ libopenssl-devel git tmux

## install ssh

```sh
eval `ssh-agent`
ssh-add ~/.ssh/id_XXX
```

## install zsh

```
sudo zypper in zsh
curl -sL --proto-redir -all,https https://raw.githubusercontent.com/zplug/installer/master/installer.zsh | zsh
```

## python

```sh
# 2021/03/27現在 3.6しか入らない
sudo zypper in python3 python3-devel python3-pip 
```

## node

```sh
sudo zypper in npm
mkdir ~/.node_modules
npm config set prefix ~/.node_modules
```

## install rust

```sh
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf
echo 'source $HOME/.cargo/env' >> ~/.zshrc

cargo install cargo-edit
```


## neovim

```sh
sudo sypper in neovim
npm install -g neovim
pip install neovim
```

## setup dotfiles

```sh
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
  os
"
$ for fname in $arr; do ln -s ~/dotfiles/$fname .; done
```
