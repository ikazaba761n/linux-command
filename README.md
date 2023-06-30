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

#  TMPFS マウントのファイルシステム /var/run とは  
  -オラクルの説明によると  
  - ディスクベースのファイルシステムではなく、メモリーベースのファイルシステム  
  - 

## wsl では　mysqldを　起動するコマンドが使えない    
## sudo service mysqld & 
## 一応起動するが　?        TN     0:00 sudo mysqld start   
## service を除いて  
## sudo mysqld_safe & 　これでmysqldが起動する  

  
  ### 文字コード確認  
    
    ### mysql> show variables like '%char%';
+--------------------------+--------------------------------+  
| Variable_name            | Value                          |  
+--------------------------+--------------------------------+  
| character_set_client     | utf8mb4                        |  
| character_set_connection | utf8mb4                        |  
| character_set_database   | utf8mb4                        |  
| character_set_filesystem | binary                         |  
| character_set_results    | utf8mb4                        |  
| character_set_server     | utf8mb4                        |  
| character_set_system     | utf8mb3                        |  
| character_sets_dir       | /usr/share/mysql-8.0/charsets/ |  
+--------------------------+--------------------------------+  
8 rows in set (0.16 sec)    




###  apache2 起動　debianの場合
### sudo /etc/init.d/apache2 start
### sudo /etc/init.d/apache2 stop
### init.d/apache2  シェルスクリプトである  


## シェルスクリプト　./　ドットスラッシュ　を使う理由
## ./はカレントディレクトリの意味、フルパス指定でもスクリプトは動く
## #!/bin/bash シバンは使うスクリプトを指定すること　shでは動かないn/

## awk　列の評価　式は　if で　＞＝　判別
##  awk '{ if ( $5 >= 10000  ) { print$0,"test"}}'
## 上記は　列５　１００００以上なら　列全部を出力　testという文字を後ろにつける



# expr  文字の演算ができる　: の次に　評価式を

## expr "$file" : ' ..\(...\)'
## 三番目から五番目を表示する
## expr "$file" : ' .*\(\..*\) '
## .* コンマ以降 \. コンマを認識させる


