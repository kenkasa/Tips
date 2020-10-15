# Tips

## Macのセットアップ

* homebrewのインストール

  [homebrewのwebsite](https://brew.sh/index_ja)に書いてあるインストールコマンドを実行する．
  2020年10月16日現在では下記．
  ```
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
  ```
  このノートでは，以降homebrewがインストールされている前提で話を進める．

* TeXliveのインストール

  [TeX wiki](https://texwiki.texjp.org/?TeX%20Live%2FMac#texlive-install-brew)を参考にした．
  下記のコマンドを実行する．通信速度にもよるが，1行目と2行目の実行で，それぞれ1時間以上はかかると考えておいた方が良い．
  ```
  brew cask install mactex
  sudo tlmgr update --self --all
  sudo tlmgr paper a4
  ```
  
