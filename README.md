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
   
   
