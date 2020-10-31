# Tips

## Macのセットアップ

* homebrewのインストール

  [homebrewのwebsite](https://brew.sh/index_ja)に書いてあるインストールコマンドを実行する．
  2020年10月16日現在では下記．
  ```
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
  ```
  このノートでは，以降homebrewがインストールされている前提で話を進める．

* homebrewでインストールしておくと良いもの

  - gcc
  ```
  brew install gcc
  ```
  - gnuplot
  ```
  brew install gnuplot
  ```
  - python3 
  ```
  brew install python
  ```
  
  - LaTeX
  
    インストール手順が他よりも若干複雑なので，後で述べる．
  
  
* TeX Liveのインストール

  [TeX wiki](https://texwiki.texjp.org/?TeX%20Live%2FMac#texlive-install-brew)を参考にした．
  下記のコマンドを実行する．通信速度にもよるが，1行目と2行目の実行で，それぞれ1時間以上はかかると考えておいた方が良い．
  ```
  brew cask install mactex
  sudo tlmgr update --self --all
  sudo tlmgr paper a4
  ```
  以上でLaTeXのインストールは完了である．
  もし，ヒラギノフォントを用いたい場合は，以下の通りにすると良い．ただし，これは必須ではない．
  
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
  
* .bashrcの設定

  下記のキーバインディングを入れておくと便利．
  ```
  bind '"\e[A": history-search-backward'
  bind '"\e[0A": history-search-backward'
  bind '"\e[B": history-search-forward'
  bind '"\e[0B": history-search-forward'
  bind '"\C-n": history-search-forward'
  bind '"\C-p": history-search-backward'
  ```
