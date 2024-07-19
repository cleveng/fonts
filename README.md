## Configuring the fonts for linux
> as your known, fonts are not installed in linux by default, btw the all web sites use them. so, I install them here.

```
PingFang SC,Hiragino Sans GB,Microsoft YaHei UI,Microsoft YaHei,Source Han Sans CN,sans-serif
```

```shell
$ sudo mv ./*/*.{ttf,otf} /usr/share/fonts/truetype
$ cd /usr/share/fonts/truetype
$ sudo fc-cache
$ sudo xset fp rehash
```

## Configuring the development environment for linux

#### install nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
nvm install 20.15.1
nvm alias default 20.15.1
npm install --global yarn
yarn -v

#### install bun
curl -fsSL https://bun.sh/install | bash

#### config node memory
export NODE_OPTIONS="--max-old-space-size=8192"

#### install composer with php8.*
sudo apt install composer

#### config debian, synaptic 新立得
sudo apt remove synaptic

#### install arc-theme
sudo apt install arc-theme

#### hide clock gnome
https://extensions.gnome.org/extension/1110/hide-clock/
https://extensions.gnome.org/extension/307/dash-to-dock/


#### install java
sudo apt update
sudo apt install default-jre
sudo apt install default-jdk
javac -version

export ANDROID_HOME=$HOME/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator:$ANDROID_HOME/tools:$ANDROID_HOME/tools/bin:$ANDROID_HOME/platform-tools
export NDK_HOME="$ANDROID_HOME/ndk/27.0.11718014"

#### install git tldr rsync autojump ripgrep
sudo apt install git tldr rsync autojump ripgrep
git config --global user.email "cleveng@gmail.com"
git config --global user.name "cleveng"


#### install gradle
sudo apt install gradle

#### install ohmyzsh plugins
https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md
https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md

#### install docker
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo 'http_proxy=http://127.0.0.1:7897' apt update
sudo 'http_proxy=http://127.0.0.1:7897' apt install docker-ce docker-ce-cli containerd.io
sudo systemctl start docker

```
sudo mkdir -p /etc/systemd/system/docker.service.d
sudo tee /etc/systemd/system/docker.service.d/proxy.conf <<-'EOF'

[Service]
Environment="HTTP_PROXY=http://127.0.0.1:7897/"
Environment="HTTPS_PROXY=http://127.0.0.1:7897/"
Environment="NO_PROXY=localhost,127.0.0.1,.example.com"
EOF
```

sudo systemctl daemon-reload
sudo systemctl restart docker

#### install tauri-cli
sudo apt update
sudo apt install libwebkit2gtk-4.1-dev \
  build-essential \
  curl \
  wget \
  file \
  libxdo-dev \
  libssl-dev \
  libayatana-appindicator3-dev \
  librsvg2-dev

https://v2.tauri.app/start/prerequisites/

#### install lua
sudo apt install lua5.3 luajit luarocks

#### install nunu
go install github.com/go-nunu/nunu@latest

#### install protobuf
sudo apt install -y protobuf-compiler

#### install imagemagick
sudo apt install imagemagick

#### install upyun upx command for linux
https://github.com/upyun/upx?tab=readme-ov-file
chmod +x upx
sudo mv upx /usr/local/bin

#### install htop for linux
sudo apt install htop

#### install sdk
https://sdkman.io/

sdk install gradle kotlin

#### install psysh

wget https://psysh.org/psysh
chmod +x psysh
./psysh

#### link applications
eg: clash-verge.desktop
```
[Desktop Entry]
Name=Clash Verge
Exec=/opt/clash-verge.appimage
Icon=~/.local/share/icons/clash/clash_logo.png
Terminal=false
X-MultipleArgs=false
Type=Application
Encoding=UTF-8
Categories=Application;Utility;
StartupNotify=false
```
