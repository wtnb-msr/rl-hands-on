# 強化学習ハンズオン

## 学習用セット

```
wget https://github.com/icoxfog417/techcircle_openai_handson/archive/master.zip
unzip master
```

## ビルド

```
docker build . -t rl-handson
```

## GUI 表示

ポート転送版

```
brew install socat
brew install caskroom/cask/brew-eask
brew cask install xquartz
open -a XQuartz

# 別ターミナルで
socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"

# 起動
docker run -e DISPLAY=172.19.193.27:0 -v $(pwd):/work  /bin/bash
```

## GUI 表示

ソケット共有版

```
# 起動
docker run -it \
  -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix \
  -v $(pwd):/work \
  rl-handson /bin/bash
```
