---
Keywords: opy, Python, ワンライナー, シェル芸
Copyright: (C) 2019 Ryuichi Ueda
---

# Pythonをコマンドラインで使いたいのでopyというコマンドを作った

　一つ前の記事をもうちょい真面目に書きました。

## この記事の要旨

* Pythonをコマンドラインで直接使うのは面倒。Pythonワンライナーは地獄。
* 解決のために [opy](https://github.com/ryuichiueda/opy) というコマンドを作って公開
    * 使い方はREADMEにあります
* なかなかいいので使ってみてください
* opyを変な呼び方しないでください

## 経緯

　Rubyに[rbというワンライナー用のコマンド（Rubyのラッパー）があるという話](https://yhara.jp/2018/12/21/rb-command)を聞いたので、Pythonでも作ってみました。

## 設計指針と実装

### 行指向で、さらにAWKより便利に

　ワンライナー中で使う汎用的な言語というとAWKです（コマンドとしては`awk`）。ワンライナーやコマンドライン中でAWKが他のものより親和性が高いのは行指向だからです。`awk`は、次のようにコードもオプションもなにもなしで、標準入力を一行ずつ読み込んで変数にフィールド（空白で区切られたデータ）をセットしてくれます。

```
$ seq 3 | awk '{print $1*3}'  # 1列目に3をかける
3
6
9
```

また、上記のように数字は数字として解釈してくれるのも、短く書ける理由です。


　一方、Pythonは行指向でもなく、インデントのルールがあるのでワンライナーとは程遠い言語です。同じことをしようとすると次のように大変なことになります。

```
$ seq 3 | python3 -c 'import sys;print("\n".join([ str(int(x)*3) for x in sys.stdin ]))'
3
6
9
```

　ただ、Pythonにはリストがあります。そして、`awk`が一行読んで`$1, $2, ...`とデータを分けたり、ユーザがそれを加工して空白区切りでデータを出力することは、Pythonのリスト操作に似ています。そこで、**最初から一行読んで一行出力するなら、`awk`で`{print $1*3}`と書くところ（アクション）にリストを書けばそのまま出力してくれるようにすればいいのではないか**、という発想に至りました。

　そういう考えで作ったコマンド`opy`（おーぴーわい or おーぱい。<span style="color:red">促音しないこと！！</span>）を使うと、上のPythonワンライナーと等価なワンライナーを、次のように記述できます。

```
$ seq 3 | opy '[F1*3]'
3
6
9
```

Python3どころか、AWKより短くできました。


　AWKのパターンも使えます。次の例は入力が奇数のときのみ出力する場合です。

```
### AWK ###
$ seq 3 | awk '$1%2{print $1*3}'
3
9
### Python3 ###
$ seq 3 | python3 -c 'import sys;print("\n".join([ str(int(x)*3) for x in sys.stdin if int(x)%2 ]))'
3
9
### opy ###
$ seq 3 | opy 'F1%2:[F1*3]'
3
9
```

複数の列も次のように出力できます。

```
$ seq 3 | opy 'F1%2:["%dは奇数"%F1, F1*3]'
1は奇数 3
3は奇数 9
```

また、リストを与えるだけでは済まない処理も、AWKと同様`'{}'`で可能です。

```
$ seq 3 | opy '{print(F1, end="")}'
123
```

このタイプのアクションは「ノーマルアクション」と呼ぶことにしました。リストをアクションとして渡したものは「リストアクション」とします。

### 文法の追加


　Pythonの文法の外側に、ルール（パターンとアクションの組、あるいはどちらか一方）が追加されます。文法を書き出すと次のようになります。

```
<rules> ::= <rule> | <rule> ";" <rules>
<rule> ::= <pattern> | <pattern> ":" <action> | <action>
<action> ::= <list action> | <normal action>
<pattern> ::= Pythonのbool式 | "B" | "BEGIN" | "E" | "END" 
<normal action> ::= "{" Pythonの文 "}"
<list action> ::= Pythonのリスト
```


  `B, BEGIN, E` and `END` means the begin/end patterns, which are also seen in AWK. We can use BEGIN pattern for initialization and the other for post-processing. This is an example. 


```
$ seq 100 | opy 'B:{a=0};{a+=F1};E:[a]'
5050
```

### module

  We can use any modules in `opy`. There are three kinds of ways for import of modules. In a list action, modules are imported automatically. 

```
### obtaining the number of sin 1 ###
$ opy 'B:[math.sin(1)]'
0.8414709848078965
### calculation of sqrt(3*3 + 4*4) ###
$ opy 'B:[numpy.hypot(3,4)]'
5.0
```

Though it is crude implemntation, the module is imported when an NameError occurs. After that, `opy` evaluates the list again. Therefore, we must not write any procedure that has side effects in the list. Otherwise, a procedure runs twice. 

  We can import modules more safely with `-m` option.

```
$ opy -m numpy 'E:{print(numpy.pi)}'
3.141592653589793
### join module names with commas for multiple module import ###
$ opy -m math,numpy 'B:[math.e,numpy.e]'
2.718281828459045 2.718281828459045
```

　We can also use a begin pattern.

```
$ opy 'B:{import numpy};E:{print(numpy.pi)}'
3.141592653589793
$ opy 'B:{import numpy as np};E:{print(np.pi)}'
3.141592653589793
### -m オプション ###
```

### computational speed

  I put less importance on computational speed than convenience.


### repository

* https://github.com/ryuichiueda/opy
