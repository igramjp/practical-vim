# 実践 Vim
## TIP1: ドットコマンドとは
ドットコマンドを使うと，直前に行った変更を繰り返せる
=> 何が「直前の変更」となるのかを把握する必要がある

Line one
Line two
Line three
Line four

* x コマンド
カーソル位置にある1文字を削除する
{start}
x
.
..

* dd コマンド
カーソルがある行をまるごと削除する
{start}
dd
.

* >G コマンド
現在の行からファイルの末尾までのインデントを1段階深くする
{start}
>G
j
.
j.

### 挿入モードに入った瞬間からノーマルモードに戻るまでの間，Vimはすべてのキーストロークを記録する．ドットコマンドを実行するとこのキーストロークが繰り返される
(参照) TIP9，TIP23

---

## TIP2: DRY (Don't Repeat Yourself)
何行にも渡ってセミコロンを追加するといったよくある状況について，Vimは2つの手順を一度で行える専用のコマンドを用意している
=> 余計なカーソル移動をなくす

var foo = 1
var bar = 'a'
var foobar = foo + bar

* A コマンド
現在の行の末尾に追加を行う
カーソル移動には $ コマンドが使える．そして a;<Esc> で変更できる．A を押せば挿入モードになり，カーソルは行末に移動する．つまり，$a を一度のストロークにまとめられる
{start}
A;<Esc>
j
.
j.

### A コマンドのような複合コマンドはほかにもある
* C == c$
* s == cl
* S == ^C == cc
* I == ^i
* A == $a
* o == A<CR>
* O == ko
(参照) TIP30

---


