# linux-command
linux　zshインストール設定

# ログインシェルの変更

## linux-debian zshをインストール  
-curl　と　ｓｈ　で　ウェブからローカルに保存してインストール  

 
### 初回起動で　zshの　設定画面が出るが<br>

oh-my-zsh を入れるので設定しないで終了

<#>　oh-my-zsh　は　githubからクローンでインストール


#　テーマを変更する
zsh テーマの設定

~~
　　　vim ~/.zshrc
         ﾎｰﾑﾃﾞｨﾚｸﾄﾘの　設定ファイル　で　テーマ名を steef と記述　
         
         steeef.zsh-theme **フルパスで記述しないこと**
**フルパスで記述しないこと**
         

プラグインでの設定

　　プラグイン　＝　（）
  source コマンド

                    重要　　プラグインを書いた行の後には　ソースコマンドを記述しないと反映されない
                    
    zsh　の　ログインシェルは　使えるまで時間がかかる
   debian　linux　では　wslのターミナルアプリを使用において
   
   開始してから　   1分くらいの待ち時間が　steeef　テーマのログインシェルになるまで時間がかかる。
   
   
   他にも　~/　から　ユーザディレクトリに戻る時にも　ログインシェルが反映されない。
   
   
   
   # マークダウン入力時の注意
   
   ##　マークダウン記号は最初から　入力
   　日本語入力で　＃を半角で入力しても　このように　マークダウン記法にならない
    
   ## 半角文字で最初から入力　
   
   
   - 半角で入力　　
   - 修正は　行ごと一度削除
   
   
   
   
   
   #  groups コマンド
username adm cdrom sudo dip plugdev

# パーミッションを　数字で表示する  

- stat --format="%a %U %G %n" /etc/*
  - 755 root root /etc/X11  
644 root root /etc/adduser.conf  
755 root root /etc/alternatives  
755 root root /etc/apparmor.d  
755 root root /etc/apt  
644 root root /etc/bash.bashrc  

   
   
   
# mysqld 起動できないとき　linux　debian
## for UNIX socket file don't exists. メッセージ
- sudo mkdir /var/run/mysqld
- sudo chown mysql:mysql /var/run/mysqld

## 起動　mysqld
 - sudo mysqld_safe &
 
 ## mysql 接続
  - mysql -u root -p
  ## mysql データベース一覧
  - SHOW DATABASES;
  ## テーブルを表示
   - SHOW TABLES FROM (database);
  ## mysqladmin で　確認
   - mysqladmin -u root -p ping
Enter password:
mysqld is alive

# mysql ターミナルを落とす、debianを再起動すると  
# /var/run/ ディレクトリの　mysqld が無くなるので  
# 毎回　ディレクトリ作成　グループの設定をする

## wsl では　mysqldを　起動するコマンドが使えない
