---
Keywords: 研究
Copyright: (C) 2019 Ryuichi Ueda
---

# 固定障害物回避のためのPFC法の拡張

## このドキュメント

　書いている途中の日本語プレプリントです。支障のないものはすべて手の内をオープンにして研究することにしました。

## 背景

　移動ロボットはいまだにセンシングできない角を安全に曲がれない。どんなにセンサが良くなろうとも、どんな環境条件でも正確な値を返してくるセンサなど存在しない。センシング条件が悪い場合に、移動ロボットが事故を予測して適切に回避するアルゴリズムを考えることは有用である。

　　このニッチながら重要な問題に数理モデルで取り組んでいる研究は（あんまり調査していないものの）見られない。

## 従来研究

　移動ロボットの自己位置推定は本質的に曖昧で、推定結果は確率的に表現されることが多い[[Thrun 2005]](https://mitpress.mit.edu/books/probabilistic-robotics)。この場合、自己位置推定結果は、環境中でロボットが到達する可能性のある全位置・向き（以後、まとめて「姿勢」と表記）