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
  
* セキュリティソフト

  口頭で指示する．
  
* Microsoft Office

  大学配布サイトよりインストーラーをダウンロードすること．
  その際，サイト上で『大学管理PCにインストール』を選択する．
  
* iTerm2のインストール及びセットアップ
  
  - ダウンロード
  
    iTerm2は[公式サイト](https://iterm2.com/)からダウンロードできる．
  
  - ログインシェルの変更（zsh => bash）
  
    現在，皆さんはログインシェルとしてbashを利用しているはずである（~/.bashrcをいじっている場合）．
    しかし，現バージョンのMacでは，デフォルトがzshになっており，仕様が若干異なる．
    もちろん，zshも優れており（むしろzshを推奨する玄人は私の観測範囲では結構多い），デフォルトのzshのまま環境を構築しても良い．
    ただし，その場合は，これまで研究室で蓄積してきたbashrcの設定などを自力でzsh用に書き換える必要があるので，少なくとも最初はbashを使うのが良いだろう．
  
    今，自分が使っているログインシェルが何かは下記コマンドで確認できる．
    ```
    echo $SHELL
    ```
    ```/bin/zsh```と出力されればzshがログインシェルで，```/bin/bash```ならbashがログインシェルである．
    最初はzshになっているはずなので，変更する場合は下記コマンドを実行する．
    ```
    chsh -s /bin/bash
    ```
    このコマンドを実行後，一度iTerm2を閉じて再度起動すれば，bashに変更されているはずである．
    再度，```echo $SHELL```を実行して確認してみよう．
    
    大した問題でもないが，この状態の設定ではiTerm2を起動するたびに次のようなメッセージが出てくる．
    ```
    The default interactive shell is now zsh.
    To update your account to use zsh, please run `chsh -s /bin/zsh`.
    For more details, please visit https://support.apple.com/kb/HT208050.
    ```
    要するに，ログインシェルがzshになっているが，それをbashに変更しなさい，と言っているわけで，無視しても良い．
    とはいっても，毎回出てこられるのも鬱陶しいので，```~/.bash_profile```に下記の内容を書いておく（なければ作る）．
    ```
    export BASH_SILENCE_DEPRECATION_WARNING=1
    ```
    また，これから自分の設定を書いていくファイルを```~/.bashrc```にするために，ついでに下記を書き加えておこう．
    ```
    source ~/.bashrc
    ```

* homebrewのインストール

  [homebrewのwebsite](https://brew.sh/index_ja)に書いてあるインストールコマンドを実行する．
  2020年10月16日現在では下記コマンドを実行すると良い．
  
  （注） homebrewに似たアプリケーションとして，MacPortsがあるが，homebrewをインストールした後はMacPortsは決してインストールしないこと．(homebrewとMacPortsの共存はかなり危険)
  
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
  
  - Gromacs 2020.4
    ```
    brew install gromacs
    ```
  
  - LaTeX
  
    インストール手順が他よりも若干複雑なので，[別ページ](./LaTeX_brew.md)にまとめた．
    またインストール時間も長いので，まずは他のソフトを優先的にインストールすると良い．

* 研究活動で必要になるもの

  - VMD
  
    [公式サイト](https://www.ks.uiuc.edu/Research/vmd/)よりダウンロードできる．
    その際，アカウント登録が必要になる．もし，登録が嫌な人は連絡してください．

* Optional

  - Clipy (T中くんイチオシ）
  
    [公式サイト](https://clipy-app.com/)よりダウンロードできる．
  
* .bashrcの設定

  下記のキーバインディングを書き加えておくと便利（任意です）．
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
