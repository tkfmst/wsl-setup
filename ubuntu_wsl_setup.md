## OS

```sh
sudo apt update
sudo apt upgrade
```


# various

```sh
sudo apt install locales-all pkg-config zip unzip
```

# ssh

```sh
eval $(ssh-agent)
ssh-add $HOME/.ssh/id_XXX
```


## zsh

```sh
sudo apt install zsh
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
for fname in $arr; do ln -s ~/dotfiles/$fname ~/; done
```

## Node

```sh
sudo apt install npm yarn
npm install -g n
n stable
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

## Go

```sh
# versionは最新に
wget https://golang.org/dl/go1.17.1.linux-amd64.tar.gz

rm -rf /usr/local/go && tar -C /usr/local -xzf go1.17.1.linux-amd64.tar.gz
```

## Scala

```sh
# install sdkman
# 必要なjavaなどをまとめて準備できる
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
sdk version
```

```sh
sdk install java $(sdk list java | grep -o "8\.[0-9]*\.[0-9]*\.hs-adpt" | head -1)
sdk install sbt
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
