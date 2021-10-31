# 2021/05/22 田中
##   theme: シェルスクリプトについて


## そもそも
そもそも、OSやカーネルを操作しやすくするためのシェル(外殻)という認識
/bin/sh 以外に拡張としてbashが大きなシェアを占めており(要出典)、zshなんかも人気(macは2018出荷分からデフォルトになった。)
気持ちzshはtab補完が強い印象がある。



デフォルトのターミナルのバックグラウンドを変えて、zshにoh my zshをかまして、
.zshrcでプロンプトのスタイルを定義している。(これの引き継ぎでPCの新調も楽だったりする)
放送でターミナルを開くことも多いため、できるだけログインユーザ名やホスト名が出ないようにしている。
コマンドライン構成をディレクトリ+gitブランチ表示、右プロンプトで時刻を表示しているいわゆる二行プロンプト形式。

iterm2とか使うとコマンドライン上に画像が表示できたりするので、CVとかする人はそっちが便利かも
mattn氏のlongcatとかも使えたと思う。

ちなみにフォントをmonacaフォントにしているので、全角スペースが豆腐として表現されるのでミスが減る
プロンプトに4バイト以上の文字を入れるのはどうなの？という感じがしなくはない
また、>>で行頭を表現するのはやや危険で#とかにしたいが、rootとわかりにくいのでここら辺は工夫がいるかも



Winのひと -> WSL , Cygwin, GitBash , Docker for windows のいずれかを入れよう！！ 
詳しくは[ここ https://qiita.com/Ted-HM/items/9a60f6fcf74bbd79a904]


シェルの便利さいろいろ


[前回 https://scrapbox.io/mentaicode/04%2F25_sun_%E3%81%9F%E3%81%AA%E3%81%8B] 触れたcURLでもよく使うが、「パイプ」が結構便利  `$command1 hoge | command2`

例えばLinuxの各種ディストリにdocker入れるときのコマンドの
`curl -sSL https://get.docker.com | sh`
とか。
curlで叩いた結果を標準出力として二つ目のコマンドに渡している
(メモ:CLIでjsonあつかうならjq入れとくと便利)

鍵を渡して認可得て情報をおろしたりもできる

curlのよく使うオプション
`curl https://hoge.com -o {ファイル名}` 「名前をつけて保存」ってやつ/レスポンスボディの出力 `-I ` でヘッダーのみ出せる
`curl -sSL https://hoge.com `  s:進捗の非表示 S:エラーを表示 L:リダイレクトを有効化
`curl -X {PUTやGETなどのHTTPメソッド} https://hoge.com` 

curlの役割は広い意味で「データの転送」である

コマンドラインベースの各種パッケージマネージャも便利
FeduraとかRHEL、あるいはCent系ならyum (かつてはrpm)
DebianとかUbuntuはapt



エイリアスは便利だぞ
`alias gg="git add .;git commit;"`
雑エイリアス

あとは環境変数を適宜設定するのもいいかも
`export DEV=$HOME/dev`
ってしているので、どこにいても`cd $DEV`でdevディレクトリにうつれる

便利コマンドその他
witch
`witch ruby` でどのバージョンのrubyを使ってるか、や、どこのディレクトリに実体が格納されているか調べる。
とくに2~3系でバージョンによる差異が大きいpythonなんかは知ってると便利かも。
pyenvとかanacondaで管理するとそれも反映されるぞ。

unix系のOSのディストリなんかを教えてくれる
`neofetch` これは試して欲しい aptとかbrewで入る



シェル上でTwitterできるツールなんかを作ってる人がいて、
piroor/tweet.sh: Twitter client written in simple Bash script https://github.com/piroor/tweet.sh
とかある
あとはrubyのgemでflumtterがある

DJするツールすらある



sudoコマンドから始める#管理者権限とは というのもやってみたかった

windowsにおける権限のadminへの昇格的な...
案外タスクスケジューラとかでもお世話になるんだよな
Windows Terminal におけるgsudo的な...


WindowsユーザだとbrewとかaptのノリでChocolateyがキテるらしい
みんなで充実させていこう


cdコマンドのやばい拡張を見つけた
[https://twitter.com/TaKOBKi/status/1394148301407096832?s=20 TaKO8Ki on Twitter: "cdコマンドをラップして、いい感じにカレントディレクトリを変更できるようにした。… "]



# 次回
Web系のインターンにいきたいよ〜という声もあったし、なんかみんなでロードマップを読んでいくの会とかやるか
https://roadmap.sh/devops
