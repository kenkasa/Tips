# Tips

## Macのセットアップ

* キーボード，トラックパッド，マウスの設定

  MacBook Proの初期設定での，キーボード入力速度，トラックパッド及びマウスのレスポンス速度はかなり遅めなので，各自の好みに応じて調整する．
  
  - キーボード
  
  画面左上のリンゴ => 「環境設定」 => 「キーボード」 => 「キーボード」タブ内の『キーのリピート』と『リピート入力認識までの時間』のメーターを調整する．個人的には，メーター最大に当たる『速い』，『短い』がおすすめ．
  
  - トラックパッド 
  
  画面左上のリンゴ => 「環境設定」 => 「トラックパッド」 => 「ポイントとクリック」タブ内の『軌跡の速さ』のメーターを調整する．個人的にはメーター最大に当たる『速い』がおすすめ．
  
  - マウス
  
  画面左上のリンゴ => 「環境設定」 => 「マウス」 => 「ポイントとクリック」タブ内の『軌跡の速さ』のメーターを調整する．個人的にはメーター最大に当たる『速い』がおすすめ．
  
  

* homebrewのインストール

  [homebrewのwebsite](https://brew.sh/index_ja)に書いてあるインストールコマンドを実行する．
  2020年10月16日現在では下記．
  ```
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
  ```
  このノートでは，以降homebrewがインストールされている前提で話を進める．
  
* Catalina上のhomebrewで起こりうる問題

  もし，なんらかのアプリをインストールしようとして，下記のようなエラーメッセージが出てきたら，参考になるかもしれない．
  ```
  You should change the ownership of these directories to your user.
  sudo chown -R $(whoami) .........
  ```
  このメッセージが出るときは，homebrewがある場所にファイルを置こうとして，その権限がないために失敗していることが原因である．
  そこで，メッセージに書いてある通りのコマンドを実行する．つまり，
  ```
  sudo chown -R $(whoami) .........
  ```
  を実行する．これで解決するはずである．

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
  
  - Gromacs 2020.4
  ```
  brew install gromacs
  ```
  
  - LaTeX
  
    インストール手順が他よりも若干複雑なので，[別ページ](./LaTeX_brew.md)にまとめた
    またインストール時間も長いので，まずは他のソフトを優先的にインストールすると良い．
  
  
* .bashrcの設定

  下記のキーバインディングを入れておくと便利．
  ```
  if [ -t 1]; then
    bind '"\e[A": history-search-backward'
    bind '"\e[0A": history-search-backward'
    bind '"\e[B": history-search-forward'
    bind '"\e[0B": history-search-forward'
    bind '"\C-n": history-search-forward'
    bind '"\C-p": history-search-backward'
  fi
  ```
