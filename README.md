# Tips

## Macのセットアップ

* homebrewのインストール

  [homebrewのwebsite](https://brew.sh/index_ja)に書いてあるインストールコマンドを実行する．
  2020年10月16日現在では下記．
  ```
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
  ```
  このノートでは，以降homebrewがインストールされている前提で話を進める．

* TeX Liveのインストール

  [TeX wiki](https://texwiki.texjp.org/?TeX%20Live%2FMac#texlive-install-brew)を参考にした．
  下記のコマンドを実行する．通信速度にもよるが，1行目と2行目の実行で，それぞれ1時間以上はかかると考えておいた方が良い．
  ```
  brew cask install mactex
  sudo tlmgr update --self --all
  sudo tlmgr paper a4
  ```
  また，現在となっては必須ではなくなったが，ヒラギノフォントを用いたい場合は，以下の通りにすると良い．
  
  1. tlmgrを実行して，TeX Liveを最新の状態に更新
  ```
  sudo tlmgr update --self --all
  ```
  
  2. いくつかのパッケージをインストール
  ```
  sudo tlmgr repository add http://contrib.texlive.info/current tlcontrib
  sudo tlmgr pinning add tlcontrib '*'
  sudo tlmgr install japanese-otf-nonfree japanese-otf-uptex-nonfree ptex-fontmaps-macos cjk-gs-integrate-macos
  ```
  
  3. 下記のコマンドを実行
  ```
  sudo tlmgr path add
  sudo cjk-gs-integrate --link-texmf --cleanup
  sudo cjk-gs-integrate-macos --link-texmf
  sudo kanji-config-updmap-sys --jis2004 hiragino-highsierra-pron
  ```
