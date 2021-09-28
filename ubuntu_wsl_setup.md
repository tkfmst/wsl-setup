## OS

```sh
sudo apt update
sudo apt upgrade
```


# various

```sh
sudo apt install locales-all pkg-config
```

# ssh

```sh
eval $(ssh-agent)
ssh-add $HOME/.ssh/id_XXX
```


## zsh

```sh
chsh -s /usr/bin/zsh

# install commandが失敗するのでgit cloneを使った
# curl -sL --proto-redir -all,https https://raw.githubusercontent.com/zplug/installer/master/installer.zsh | zsh
export ZPLUG_HOME=$HOME/.zplug
git clone https://github.com/zplug/zplug $ZPLUG_HOME
```

## dotfiles

```sh
git clone git@github.com:tkfmst/dotfiles.git
ln -s dotfiles ~/
arr="
  .gitconfig
  .alias
  .config
  .colorrc
  .tmux.conf
  .zshrc
  .zprofile
  os
"
for fname in $arr; do ln -s ~/dotfiles/$fname .; done
```

## Node

```sh
sudo apt install npm yarn
```


## Python

```sh
sudo apt install python3-dev python3-pip
```

## Rust

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

cargo install cargo-edit
```

## neovim

```sh
sudo apt install neovim

sudo npm install -g neovim
pip3 install --user pynvim
pip3 install --upgrade pynvim
```

## utilities

```sh
sudo apt install ripgrep
```

## docker

```
# Docker公式ののGPG鍵を追加
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# Docker公式のstableリポジトリをセットアップ
sudo -E add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# Docker CE(Community Edition)をインストール
sudo apt install docker-ce
```
