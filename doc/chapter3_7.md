<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/es5/tex-mml-chtml.min.js">
</script>
<script type="text/x-mathjax-config">
 MathJax.Hub.Config({
 tex2jax: {
 inlineMath: [['$', '$'] ],
 displayMath: [ ['$$','$$'], ["\\[","\\]"] ]
 }
 });
</script>

# 3.7 ロジスティック回帰

複数の説明変数をもとに、目的変数である「**ある事象が発生する確率**」を求める<u>非線形回帰</u>の手法。

ロジスティック回帰は、**二値分類**と**マルチクラス分類**の両方に適用できる。（回帰なのに分類となっているが、ロジスティック回帰は、カテゴリになる確率を予測する）。

例
- 顧客が商品をリピート買いする確率
- 病気の発症確率
- スパムメールである確率
- 発行されたクーポンを使用する確率

## 二値分類を扱うロジスティック回帰

説明変数を $X_i$ 、目的変数を $Y$ としたとき、ロジスティック回帰は以下の式になる。

$$Y = \frac{1}{1 + e^{-(a_1X_1 + a_2X_2 + \cdots + a_nX_n + b)}}$$

この式は、シグモイド関数に説明変数 $X_i$ の線形結合を代入した式になっている。

シグモイド関数は、以下で表される

$$f(x) = \frac{1}{1+e^{-x}}$$

シグモイド関数の値域は0から1になるため、確率として扱いやすい。

ロジスティック回帰の偏回帰係数も最小二乗法により求めることができる（そうだが）、損失関数として**交差エントロピー**を使うものもあるとのこと。

例えば、病気に罹患しているかどうかを、年齢、血圧、糖尿病歴をもとに予測することを考える。学習データとして、病気に罹患しているかどうかも含め、年齢、血圧、糖尿病歴の情報を用意し、学習プロセスにより、パラメータ $a_1, a_2, \cdots, a_n, b$ を求める。未知のデータに対して、ロジスティック回帰の式を適用すると、0 から 1 の値が返されるため、0.5以上なら陽性、0.5未満なら陰性などと評価する。


## マルチクラス分類を扱うロジスティック回帰

https://datawokagaku.com/multinomial/

マルチクラス分類に適用する方法は２つ

**One vs Rest (OvR)**: １つのクラスとそれ以外の全クラスの二値分類器をクラスの数だけ作って、<u>最も高い確率のクラスを予測結果とする</u>。OvRはロジスティック回帰だけでなく、他の二値分類のアルゴリズムにも応用できる。

**多項ロジスティック回帰**: 

ロジスティック回帰によるマルチクラス分類を多項ロジスティック回帰という。

多項ロジスティック回帰では、シグモイド関数の代わりに**ソフトマックス関数**を使う。

ソフトマック関数は、以下で表される

$$p_k(x) = \frac{e^{x_k}}{e^{x_1} + e^{x_2} + \cdots + e^{x_K}}$$

ここで、 $K$ はクラス数（赤、青、黄色に分類したいなら、 $K=3$ ）になる。

この関数は、各クラス毎の値が各クラスの確率を表し、各クラス毎の値を計算して足し合わせると１になる。

実際の予測値を算出する式は複雑になるが、簡単のため、説明変数が１つとして展開してみる。

線形回帰では、予測値を説明変数の線形式で表した。今、説明変数は１つとしているので、予測値 $Y$ に対する線形回帰は以下になる。

$$Y = aX + b$$

二値分類のロジスティック回帰では、右辺の線形結合をシグモイド関数に代入していた。観測データに対する予測値が1になる確率は、以下で与えられる。

$$P(y=1) = \frac{1}{1 + e^{-(aX+b)}}$$

マルチクラス分類の多項ロジスティック回帰では、各クラスごとに回帰係数があるとイメージ。赤、青、黄色などの３クラス分類を想定すると、確率としては $P(y=1)$ , $P(y=2)$ , $P(y=3)$ の３つの確率が考えられる。

多項ロジスティック回帰で、観測データがあるクラスに分類される確率は以下で与えられる。

$$P(y=k) = \frac{e^{a^{(k)}X+b^{(k)}}}{e^{a^{(1)}X+b^{(1)}}+e^{a^{(2)}X+b^{(2)}}+ \cdots + e^{a^{(K)}X+b^{(K)}}}$$

ここで、 $K$ はクラス数を表す。

回帰係数も、各クラスごとにあるようなイメージとなり、以下のようにたくさんのパラメータが出てくる。

$$a^{(1)}X+b^{(1)}\\
a^{(2)}X+b^{(2)}\\
a^{(3)}X+b^{(3)}$$
