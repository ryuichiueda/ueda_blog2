---
Keywords: 作文技術
Copyright: (C) 2019 Ryuichi Ueda
---

# 説明文の書き方（修論・卒論のために）

　最近、学生さんの執筆能力向上のために、講義の最初に「○○を説明してください」という作文の課題を出しているのですが、講義本編の方が重要なため、細かく書き方を解説する時間がありません。ですので、ここにシステマティックに説明文を書き下していく方法を解説しておきます。卒論、修論にも役に立つかと。（さすがに博士論文を書く人は、この段階は卒業しているはず・・・）

* 注意: 昼休みの殴り書きなので、分からんところは分からんと言っていただければと。

## 問題の例

　「デバイスドライバ」について説明してください。

## 説明文を作っていく

### 最初の文

　まず、最初の文を決めます。（あくまで例なので、作文の内容への細かいツッコミはご容赦を・・・ご容赦を・・・わたしコンピュータなんにもわからない。）


```
　デバイスドライバとは、外部接続機器をオペレーティングシステム上
で利用できるようにするためのソフトウェアです。
```

　最初の一文には、「全体を通して一番言いたいこと」を書きます。難解な用語が出てきても大丈夫です。短くスパッと、国語辞典のように書きます。実は、説明文において一番難しいのは、この最初の文です。これが書ければ仕事の8割は終わりです。例えば「デバイスドライバについて60字で説明しなさい」という問題ならこれで（たぶん）正解となります。この記事ではもっと長い文章を書きますが、はっきり言ってしまえば、あとは全部補足です。

　逆に言うと、この一文が書けないと、必ずグダグダ作文になります。書いている本人がきっちり説明対象の本質を捉えていないわけですから、当然と言えば当然です。実は書く前に勝負は決まっています。

　じゃあ書けない場合はどうするのという話になりますが、優れた書き手というのは、試験中でもない限り、「自分が理解していない」ということを理解して、しっかり調査するという行動に出ます。**「書くことは調べること」**です。きっちりとしたライターの人は、書くことに対して裏をとります。逆に、すぐ炎上しちゃう人たちはこれができていません。

　さらに余計なことを書くと、ちゃんと調べられる人は、全然知らない分野でも専門家より抜け目なく上手に説明が書けてしまうことがあります。入念な調査と「知らないものは知らないと素直に書く」ことで、そういうことが可能となります。そして、知らないことを潰していけば、少なくとも紙の上やインターネット上では「専門家」になってしまいます。それほど書く技術というものは強力なので、研究室では習得の最優先事項になります。ただし、専門家が同じようにできると、専門家の方がより良いものが書けるのは間違いありません。手で覚えてることや本当の勘所は、さすがに書くだけでは分かりません。専門性があるなら、へんちくりんなブロガーに仕事をとられないように、作文技術も鍛える必要があります。


　ところで、上に書いた1文目についていろいろ考えすぎると、「OSない場合はどうなるの」とか「擬似デバイスは？」とかツッコミが出てきますが、そういう場合はこの文章を書いている状況（コンテキスト）を考えて、この文がそのコンテキストに沿っているか考えます。人間にはコンテキストに束縛されない作文は無理です。そして、ツッコミが入っても、自分は悪くないと開き直ることはせず、とりあえずは受け入れる覚悟が必要です。また、気になる場合はちゃんと調べます。調べることによって知識が増えます。もう一度書きますが、**「書くことは調べること」**です。


### 2文目以降

　2文目以降は、1文目を読んだときの疑問点を挙げることで決まります。例えば、

```
　デバイスドライバとは、外部接続機器をオペレーティングシステム上
で利用できるようにするためのソフトウェアです。
```

ならば、読者の側に立つと、

* 外部接続機器って何？
* オペレーティングシステムって何？
* どんなソフトウェアかもうちょっと教えて！

といろいろ知りたいことが出てきます。

　2文目は、大抵の場合、この列挙した「知りたいこと」の中で、読者が最も先に知りたいことを説明します。ただ、これが難しくて、ほんとに伝えたいこと（上の3番目の項目）の前に用語の説明が入ります（1, 2番目の項目）。用語の説明をどこまでするのかを決めるときは、想定する読者の知識との相談が必要になります。例えば、「外部接続機器」や「オペレーティングシステム」なら、IT業界の人なら知ってるけど、そうでないと知らないという話になります。この場合、迷ったらとりあえず全部説明しておくといいでしょう。

```
　デバイスドライバとは、外部接続機器をオペレーティングシステム上
で利用できるようにするためのソフトウェアです。外部接続機器とは、
例えばUSBで接続するハードディスクや、プリンタのことを指します。オ
ペレーティングシステムとは、WindowsやmacOS、Linux、UNIXなど、我々
がコンピュータでソフトウェアを使うときに、基盤となるソフトウェア
のことです。
```

細かいですが、ここで「Linux、UNIXなど」と書くかどうかは少し考える必要があるでしょう。オペレーティングシステムを知らない人にとっては、LinuxやUNIXを知らないでしょうからこの説明は意味がありません。しかし、例えば業界何十年という人がこれを読んでLinuxとかUNIXを無視したと怒るかもしれません。基本的には、可能な限り、紙面の許す限りいろんな読み手のことを考えて言葉を置いていきます。

　また、用語を説明するときにまた別の用語が出てきましたが、もしこれも説明したいというときは、脚注や用語集にして分けたほうがよいかなという判断になります。そこまで丁寧にするのはちょっと無理という場合は、「別の本で知識をつけて」と文献引用でもよいでしょう。

### 段落を改める


　さて、これで「どんなソフトウェアかもうちょっと教えて！」に応える準備ができましたが、ここで判断すべきは、段落を改めるかどうか、です。「どんなソフトウェアかもうちょっと教えて！」には、「デバイスドライバとは、・・・」という段落最初の文の補足説明という側面もありますが、話題が変わるきっかけという側面もあります。

　この例の場合、補足というよりは説明文で本当に伝えたいことの一部と捉えるのが自然でしょうから、段落を改めましょう。

```
　デバイスドライバとは、外部接続機器をオペレーティングシステム上
で利用できるようにするためのソフトウェアです。外部接続機器とは、
例えばUSBで接続するハードディスクや、プリンタのことを指します。オ
ペレーティングシステムとは、WindowsやmacOS、Linux、UNIXなど、我々
がコンピュータでソフトウェアを使うときに、基盤となるソフトウェア
のことです。

　デバイスドライバがどのようなソフトウェアなのか説明します。
```

これで、「デバイスドライバがどのようなソフトウェアなのかを説明する段落」が誕生します。段落は、必ずその段落の主題（トピック）を持ちます。このように段落1文目（あるいは2文目）に何をこれから説明するのかを宣言してあげると、読者は安心します。そして、宣言した内容について知識のある読者は、安心してその段落を読み飛ばすことができます。たとえば、1段落目の「デバイスドライバとは、・・・」は、そこそこコンピュータを使う読者なら斜め読みして、2段落目の「デバイスドライバがどのようなソフトウェアなのか」を真剣に読むかもしれません。このときに、**段落内に、その段落の主題と関係ないことが書いてあると、読者はものすごくイライラします**。段落にはこのような役割があります。


### 2段落目の2文目以降

　第2段落の2文目以降は、おそらく

* デバイスドライバはユーザやプログラムから外部機器の操作方法を受け取って、外部機器に伝える
* また、外部機器からデータを受け取ってユーザやプログラムに伝える
* この機能を実現するため、デバイスドライバはカーネルの一部として動く

ということを説明することになります。そのまま素直に作文します。

```
　デバイスドライバとは、外部接続機器をオペレーティングシステム上
で利用できるようにするためのソフトウェアです。外部接続機器とは、
例えばUSBで接続するハードディスクや、プリンタのことを指します。オ
ペレーティングシステムとは、WindowsやmacOS、Linux、UNIXなど、我々
がコンピュータでソフトウェアを使うときに、基盤となるソフトウェア
のことです。

　デバイスドライバがどのようなソフトウェアなのか説明します。デバイ
スドライバはオペレーティングシステム（以後OSと略記）を操作している
人や、OS上で動いているソフトウェアと外部機器とデータをやりとしりま
す。OS上から機器へ何かデータを送りたいときには、デバイスドライバは
「デバイスファイル（後述）」を通してデータを受け取り、OSやインタフ
ェース（USBなど）の規格で決められた方法で機器にデータを送ります。
機器からデータをOS上に送る要求を受けたときは、今の説明の逆をたどっ
てデータを送ります。
```

「人」と「OS上で動いているソフトウェア」が並列に語れるものなのかどうかはここでは置いておきましょう。もし不安なら、段落の後ろにでも言い訳の文を書いておきます。段落の終盤は、そのためにあります（段落: 言いたいこと->説明->補足や余談）。「ユーザランド」などの用語を出すともっと簡潔に書けますが、読者のレベルに依存します。

### さらに段落を増やす

　ここまで書くと、「デバイスファイルって何？」、「OSやインタフェース（USBなど）の規格って何？」という新たな疑問が読者に生じます。また、「この機能を実現するため、デバイスドライバはカーネルの一部として動く」という説明をしていません。これはどこに書くべきでしょうか。


　実は、私がこの例文を書いているとき、「デバイスドライバはカーネルの一部として動く」をこの段落に書こうとしたのですが、やめました。たぶん、「デバイスファイルって何？」、「OSやインタフェース（USBなど）の規格って何？」が読者の現在の興味で、「デバイスドライバはカーネルの一部として動く」は興味の対象でないからです。なぜかというと、「デバイスドライバはカーネルの一部として動く」の話は、まだ自分の頭のなかだけにあるからです。まだ話をしていないのですから、読者には今のところ興味がないことになります。

　したがって、先に、「デバイスファイルって何？」、「OSやインタフェース（USBなど）の規格って何？」から説明しようかという判断になります。よくありがちなミスに、あまりにも「デバイスドライバはカーネルの一部として動く」が**書き手にとって好きな話**で、それが文章に早いうちに出てしまって文章が壊れるということがあります。今は、今の時点で読者が持っている疑問を解消するときです。自分の書きたいことはグッと我慢します。たぶん、カーネルの一部という話は説明しているうちに自然に出てくるので、そのときに自然に書きましょう。

　これで、おそらく作文は次のように進んでいくことでしょう。

```
　デバイスドライバとは、外部接続機器をオペレーティングシステム上
で利用できるようにするためのソフトウェアです。外部接続機器とは、
例えばUSBで接続するハードディスクや、プリンタのことを指します。オ
ペレーティングシステムとは、WindowsやmacOS、Linux、UNIXなど、我々
がコンピュータでソフトウェアを使うときに、基盤となるソフトウェア
のことです。

　デバイスドライバがどのようなソフトウェアなのか説明します。デバ
イスドライバはオペレーティングシステム（以後OSと略記）を操作して
いる人や、OS上で動いているソフトウェアと外部機器とデータをやりと
しります。OS上から機器へ何かデータを送りたいときには、デバイスド
ライバは「デバイスファイル（後述）」を通してデータを受け取り、OS
やインタフェース（USBなど）の規格で決められた方法で機器にデータを
送ります。機器からデータをOS上に送る要求を受けたときは、今の説明
の逆をたどってデータを送ります。

　さきほど説明を後回しにしたデバイスファイルについて説明します。・・・

　今度はOSと機器側のデータ送受信について説明します。・・・（メモ
リマップドI/Oとかの話）・・・このようなメモリアドレスの使い方はOS
レベル行わないと大変ですので、デバイスドライバはOSの一部として動き
ます。

　デバイスドライバをOSの一部として動かすためには・・・（カーネルモ
ジュールの説明など）・・・。
```

作文の例は、今回はこの辺にしておきます。よく学生さんは「書くことがない」と短いレポートをよこしてきますが、いままでのように作文をしていくと、今度は書くことがありすぎて止まらなくなります。止める方法については、さきほど少し書きましたが、参考文献を紹介したり、脚注を入れたり、用語集を別に設けたり、調べる方法を示したり、ということになります。

### まとめ

　ということで、長々と書きましたが、以下がまとめとなります。

* 文章の頭に文章で一番言いたいことを書く。段落の頭に段落の一番言いたいことを書く。章、節、項も同じ。一番言いたいことの後ろは補足となる。補足から次の段落に。
* 段落は頭以外、読み飛ばしても問題ないように書く。
* 書くことは自分の知識不足を明らかにすることでもある。調べる。国語辞典も引く。
* 補足を丁寧にしていくと、書くことがないなどということはあり得なくなる。


　また、この記事とは少し矛盾しますが、もっと最初から構造を決めて書くということも大切です。おそらく書いていくと、最初に決めたような構造にはなりませんが、頭を整理するには有効です。「何を伝えたいか」は案外、自分自身でも気づいていないものです。


## 反省文

　この記事、コンピュータに詳しくないと分からん・・・。自分自身、読者に合わせることができてないですね・・・。すんません・・・。