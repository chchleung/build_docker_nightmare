apt-get update
apt-get install -y git
apt-get install -y vim
apt-get install -y curl

curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash

source ~/.bashrc

nvm install stable

git clone https://liangzhichong@bitbucket.org/yimian/taobao_sub.git

# rm old node_module
# update new.index.js to local mongo redis

npm init



cnpm install -g yarn
yarn config set registry https://registry.npm.taobao.org

cnpm install nightmare --save
cnpm install bluebird --save
cnpm install debug --save
cnpm install mongodb --save
cnpm install nightmare-window-manager --save
cnpm install redis --save
cnpm install uuid --save
cnpm install vo --save

apt-get install -y \
  xvfb \
  x11-xkb-utils \
  xfonts-100dpi \
  xfonts-75dpi \
  xfonts-scalable \
  xfonts-cyrillic \
  x11-apps \
  clang \
  libdbus-1-dev \
  libgtk2.0-dev \
  libnotify-dev \
  libgnome-keyring-dev \
  libgconf2-dev \
  libasound2-dev \
  libcap-dev \
  libcups2-dev \
  libxtst-dev \
  libxss1 \
  libnss3-dev \
  gcc-multilib \
  g++-multilib


touch entrypoint.sh
vi entrypoint.sh

######entrypoint########

#!/usr/bin/env bash
set -e

# Start Xvfb
Xvfb -ac -screen scrn 1280x2000x24 :99.0 &
export DISPLAY=:99.0

exec "$@"

#########################

chmod +x . entrypoint.sh

. entrypoint.sh node index.js
