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
