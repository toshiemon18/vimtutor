# L2.3 operator and motion
- 多くのコマンドはoperatorとmotionからテキストに変更を加える
- 削除コマンド d
	- operator は `d motion`
	  - d : 削除コマンド
		- motion : 何に対して働きかけるか
	- motion の一部
		- w : カーソル位置から空白を含む単語の末尾まで
		- e : カーソル位置から空白を含まない単語の末尾まで
		- $ : カーソル位置から行末まで
- example
```
dw
de
d$
```

# L2.4 use counts to motion
- 繰り返しを行う場合は motion の前に数値をタイプする

# L2.5 more deletion with counts
- 2.3で紹介した組み合わせにカウントを挟み込むことでより多く削除できる
- `d [count] motion`
- `[count] d motion` でも同じ動作をする

# L2.6 line manipuration
- `dd` で行全体を削除できる
- `[count] dd` で n行削除できる

# L2.7 undo command
- `u` : 操作の取り消し ( undo )
- `U` : 行全体に対する操作の取り消し ( undo line-wise )
- `C-R` : 取り消しの取り消し ( redo )

# L3.1 paste command
- `p` : カーソルのあとに貼り付け

# L3.2 replace command
- `r` : カーソル直下の文字を置き換える

# L3.3 modify command
- `cw` : 単語の一部, もしくは全体の変更を行う
	- カーソルを変更したい箇所の先頭においてcw
	- 単語を削除したあとにinsertモードになることに注意!

# L3.4 other modify with c
- `c [number] motion` : 削除コマンドと同様に動作する

# L4.1 position and file information
- `C-g` : ファイル名や行番号, カーソル位置が全体のうちどこに位置するかを表示してくれる
- `gg` : ファイルの先頭行にカーソルを移動する
- `G` : ファイルの最下行にカーソルを移動する
- `[number] G` : 指定した行番号にカーソルを移動する

# L4.2 search command
- `/` : 検索したい単語をこのあとに入れて enter を押すとカーソル以降の一番最初に出てくるところに移動する
	- `n` : 検索ワードが次に出現する箇所にカーソルが移動する
	- `N` : 検索ワードがそれ以前に出現する箇所にカーソルが移動する
- `?` : 検索したい単語をこのあとに入れて enter を押すとカーソル以前の一番最初に出てくる箇所に移動する
- `C-O` : 元の場所に戻る
- `C-I` : 前方向にすすむ

# L4.3 search corresponding braket
- `%` : 対応する), ], }の上でタイプ

# L4.4 fix typo
- `:s/old/new` : カーソル行で最初に見つかった old を newに置換する
- `:s/old/new/g` : 行内のすべての old を new に置換する
- `#,@s/old/new/g` : #行目から@行目のoldをすべてnewに置換する
- `:%s/old/new/g` : ファイル全体で old をすべて newに置換する
- `:%s/old/new/gc` : ファイル全体で old を1つずつ確認を取りながら置換する

# 5.1 execute external commands
- `:! [command]` : [command] が実行される

# 5.2 write to other files
- `:w TEST` : TESTはファイル名. TESTというファイルにbufferの内容を書き込む

# 5.3 selected write
- vモーションと :w [filename]で選択領域を別ファイルとして保存する
- vを押すとvisualモードになる
- カーソルを移動すると選択領域を変化させることができる
- 選択範囲に対してオペレータを適用できる

# 5.4 files import and merge
- `:r [file]` : カーソル位置にファイルの中身を挿入する

# 6.1 open command
- `o` : カーソルの下の行が開いて挿入モードになる
- `O` : カーソルの上の行が開いて挿入モードになる

# 6.2 add command
- `a` : カーソルの後ろで挿入モードに遷移する

# 6.3 other replace methods
- `R` : 複数文字の置換. 置換モードに遷移し, カーソル下の文字をタイプした文字で置換する. ESCでnormalモードに遷移

# 6.4 text copy and paste
- `y` : 選択領域を yank
	- y をオペレータとして操作もできる
- `p` : カーソル位置に yank した内容をpaste

# 6.5 set options
- 検索時に `:set ic` としてオプションを設定すると検索時に大文字と小文字の区別をしない
- 検索時に `:set is` としてオプションを設定すると検索フレーズにマッチしている部分を表示する
- 検索時に `:set hls` としてオプションを設定するとマッチするすべてを強調表示する
- 上記のオプションたちを無効化したいときは `no` を頭につけてオプションを設定する

# 7.1 online help command
- `:help [command]` : :help単体 もしくは コマンド名, insert-index, user-manual等の文字列を入れるとヘルプが開く

# 7.2 boot script
