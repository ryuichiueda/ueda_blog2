---
Keywords: Mastodon,Raspberry,日記,確率ロボティクス
Copyright: (C) 2017 Ryuichi Ueda
---

# 日記 --- graph-based SLAMの解説文（書きかけ）、OS不具合尻拭いスクリプト、ますとどん、今週はシェル芸勉強会
<p style="padding-left: 30px;">今週末のことを重要なことから。</p>

<h2>graph-based SLAMの解説書</h2>
<a href="http://amzn.to/2nRJyXl">確率ロボティクス</a>の日本語ドキュメント・サンプル充実プロジェクトとして、先週は<a href="/?post=09479">コードのサンプルをjupyter notebookに書く</a>ということをやっていましたが、今週は<a href="https://github.com/ryuichiueda/commentary_on_graph-based_slam">数式で解説するための文章</a>を書いてました。うん。10年仕事が遅い。

まだ書きかけで粗いですが、世界で一番簡単に理解できるようにするつもりです。
<h2>Raspberry Pi3にUbuntu 16.04 Serverをインストールするときの便利スクリプト</h2>
3月以来、<a href="https://bugs.launchpad.net/ubuntu/+source/linux-raspi2/+bug/1652270">device treeのアドレスがアレでOSをアップデートするとクラッシュ</a>するというアレな感じになっている <a href="https://wiki.ubuntu.com/ARM/RaspberryPi">https://wiki.ubuntu.com/ARM/RaspberryPi</a> のラズパイ3用Ubuntu 16.04イメージですが、今度はアップデートでwlan0が見えなくなるというアレな状況になりました。いくらサポートしてないからと言ってなんなんでしょう。

ということで、これらの不具合を回避しながらカーネルをアップデートするためのシェルスクリプトをGitHubの<a href="https://github.com/ryuichiueda/raspimouse_book_ubuntu_init">ryuichiueda/raspimouse_book_ubuntu_init</a>に置きました。このリポジトリにある <a href="https://github.com/ryuichiueda/raspimouse_book_ubuntu_init/blob/master/after_os_install.bash">after_os_install.bash</a>です。ここにも同じコードを貼りつけておきます。 <a href="https://wiki.ubuntu.com/ARM/RaspberryPi">https://wiki.ubuntu.com/ARM/RaspberryPi</a>のイメージをmicroSDに書き込んでOSを立ち上げてsshでログインし、すぐに適用します。

```bash
#!/bin/bash

# (c) 2017 Ryuichi Ueda

# This software is released under the MIT License, see LICENSE at https://github.com/ryuichiueda/raspimouse_book_ubuntu_init.

tmp=/tmp/$$

### purge of the cloud-init ###
sudo apt -y purge cloud-init

### remove the bug on the device tree address ###
cat /boot/firmware/config.txt |
sudo tee /boot/firmware/config.txt.org |
sed 's/device_tree_address=0x100/device_tree_address=0x02008000/' |
sed 's/device_tree_end=0x8000/#&/'					|
sudo tee $tmp-config 

sudo mv $tmp-config /boot/firmware/config.txt

### stop network device update ###
echo linux-firmware-raspi2 hold |
sudo dpkg --set-selections

### update ###
sudo apt update
sudo apt -y upgrade

### install WiFi tools ###
sudo apt -y install wireless-tools wpasupplicant

sudo reboot
```

このコードを読むと分かりますが、ファームウェアの自動アップデートを止めていますのでご注意ください。このリポジトリにある他のシェルスクリプトは、<a href="http://amzn.to/2oDns9H">ラズパイマウス本</a>の各パートのコードをラズパイにインストールして、各章を飛ばしてしまうためのチート的なものです。
<h2>ますとどん</h2>
遊んでます。
<ul>
 	<li><a href="https://mstdn.jp/@ryuichiueda">https://mstdn.jp/@ryuichiueda</a></li>
</ul>
<a href="136aed74fd1009042bd6d998ede2e07a.png"><img class="aligncenter size-full wp-image-9561" src="136aed74fd1009042bd6d998ede2e07a.png" alt="" width="630" height="608" /></a>

今のところ謎論理を展開する変なおじさんおばさんがいなくて非常に開放的です。多分、スキル的に彼らがやってくるのは当面先の話でしょう。Twitterでよく絡んでいる人たちも、束の間の自由を楽しんでいるご様子でした。自分が小難しいことをTwitterでたまに言ってしまうのは、変なおじさんおばさんを見てイライラして、そっちの側に回ってしまうという一種の集団ヒステリーなんだなーと反省しました。

&nbsp;

このサービスについていろいろ評論している人がいますが、もし何かあるなら自然淘汰されるだけなので、ブックメーカーが賭けをしない限り、なんの意味もないと思います。そういう人たちは自分の仕事に集中していないだけなので、気にすることはないと思います。管理者さん頑張れ。
<h2>今週末はシェル芸勉強会</h2>
今回は募集が早すぎたような気がして、ドタキャンが多い予感がします。どうなることやら。内容は「普通のsed」にしました。普通とは。

寝る。
