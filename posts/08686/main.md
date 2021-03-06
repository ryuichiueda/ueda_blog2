---
Keywords: Sphinx,執筆
Copyright: (C) 2017 Ryuichi Ueda
---

# 【メモ】Sphinxを使ってpLaTeX経由でPDFを作る時にdvipdfmxで「Unknown token "SDict"」と警告が出る場合の対処
原稿のトップディレクトリで
```bash
make latexpdfja
```
した後に、_build/latex下に行き、原稿を手直しして
```bash
make all-pdf-ja
```
すると、
```bash
dvipdfmx:warning: Unknown token "SDict"
dvipdfmx:warning: Interpreting PS code failed!!! Output might be broken!!!
dvipdfmx:warning: Interpreting special command ps: (ps:) failed.
dvipdfmx:warning: >> at page="10" position="(72, 586.048)" (in PDF)
dvipdfmx:warning: >> xxx "ps:SDict begin [/View [/XYZ H.V]/Dest (section.1.3) cvn /DES..."
（延々と続く）
```
という風にガーッとエラーが出ておっそい。


<h2>対策</h2>

<a href="http://www.hnagata.net/archives/142">こちら</a>を参考に、_build/latexのsphinx.styからhyperrefに関する部分を探す。

```bash
436 % Include hyperref last.
437 \\RequirePackage[colorlinks,breaklinks,
438 linkcolor=InnerLinkColor,filecolor=OuterLinkColor,
439 menucolor=OuterLinkColor,urlcolor=OuterLinkColor,
440 citecolor=InnerLinkColor]{hyperref}
```
で、上のリンクのように、dvipdfmxをオプションに指定。下のように[]の最後にdvipdfmxを追加。
```bash
436 % Include hyperref last.
437 \\RequirePackage[colorlinks,breaklinks,
438 linkcolor=InnerLinkColor,filecolor=OuterLinkColor,
439 menucolor=OuterLinkColor,urlcolor=OuterLinkColor,
440 citecolor=InnerLinkColor,dvipdfmx]{hyperref}
```
で、make all-pdf-jaするとエラーが出ない。



以上、ニッチすぎるメモ。
