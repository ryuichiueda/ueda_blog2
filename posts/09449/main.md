---
Keywords: Raspberry,ROS,執筆
Copyright: (C) 2017 Ryuichi Ueda
---

# 「Raspberry Piで学ぶ ROSロボット入門」を安価に楽しむ方法
先月30日に発売された「<a href="http://www.nikkeibp.co.jp/atclpubmkt/book/17/261040/">Raspberry Piで学ぶ ROSロボット入門</a>」ですが、やっぱりロボットが高くて手が出しにくいという反応をいただいておりますので、なくても楽しめるように、いくつかロボットなしのプランを提示します。ついでに本書の内容もどんなものか匂わせます。

もちろん、実機があるのがベストです。
<h2>Travis CIとの格闘を楽しむ</h2>
本書はロボットを動かすための本ですが、テストがたくさん盛り込んであり、Travis CIも裏の操作対象のような位置付けになっています。また、ロボットがなくても、テストが通るかどうかで、コードが正しいかどうかは、完全ではありませんがだいたい分かります。ということで、勉強だけならTravis CIでテストを通すことを目標にしてコードを書くことができます。

また、講義では、ロボットを1人1台ではなく、<span style="color: #ff0000;"><strong>教室に数台だけにしておき、テストを通した人から実機を試すという運用</strong></span>も考えられます。これはテストを扱っているからこそ可能になることです。また、私も職業柄、当然講義を持っておりますので、ちゃんと講義や実習が成立するように考えて書いておりますです。
<h2>実機を作る</h2>
これはかえってコストがかかるかもしれませんが、少しずつ部品を揃えて試していくこともできます。ハードウェアの使用は<a href="https://github.com/rt-net/RaspberryPiMouse_Hardware">こちら</a>に公開されていますので、挑戦してみるのも良いかもしれません。
<h2>シミュレータと接続</h2>
最後、<a href="https://github.com/rt-net/raspimouse_sim">ラズパイマウスのシミュレータ</a>で試すという方法もあります。ただ、本書のコードとシミュレータのつなぎこみには少し手間がかかります。少しだけ付録で説明しましたが、ちょっと本書を読み進めないと難しいかと。

ということで、シミュレータの作者にどんどんissueを投げていけば、そのうち答えが出てくるものと予想されます（ひどい）。

また、シミュレータは、入出力口を全てROSのインタフェースで持っています。が、実機はデバイスファイルがインタフェースなので、そういう点ではシミュレータは不完全です。ここをデバイスファイル（もちろん普通のファイルでも可）でブリッジできればシミュレータとして完全なのですが・・・。この点は気になっているところなので、こちらでも働きかけを続けます。
<h2>おわりに</h2>
3つ挙げたうちの後ろの2つは大変ですが、最初の項目のように、本書は一つのロボットを多人数でシェアしても大丈夫な構成になっています。また、ロボットは持っている人のところで動かして、あとはテスト環境でソフトウェアを書くということもできるようになっています。

ということで、ぜひ一読いただければと。

[amazonjs asin="4822239292" locale="JP" title="Raspberry Piで学ぶ ROSロボット入門"]

[amazonjs asin="B06XKWFQM6" locale="JP" title="【限定】すぐ使えるRaspberry Piで学ぶ ROSロボット入門（ロボット付）"]
