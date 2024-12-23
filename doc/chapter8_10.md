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

# 8.10 代表的な確率分布の紹介

## 二項分布（ベルヌーイ分布）

**結果が２通りしかない試行をn回実施したとき、ある事象が何回起こるか**を示す確率分布

例

- コインを5回なげて裏が3回出る確率
- 100人にある治療を施したとき、80人以上に症状の緩和が見られる確率
- 100名の腫瘍を精密検査すしたとき、10名以上が悪性になる確率


1と0の2通りの結果が出る試行において、1が出る確率を $p$ とする。 $n$ 回の試行で $k$ 回だけ1となる確率は次になる。

$$P(p,n,k) = {n \choose k} p^k (1-p)^{n-k}$$

- 二項分布の期待値: $E(X) = np$
- 二項分布の分散: $Var(X) = np(1-p)$

二項分布は、試行回数nを大きくしていくと正規分布に近づいていく。

## ポアソン分布

**ある確率で起こる事象が一定の時間内に発生する回数**を表す確率分布

単位時間あたり平均 $\lambda$ 回起こるランダムな減少が、その単位時間の期間中に $k$ 回起こる確率は次になる。

$$P(X=k) = \frac{\lambda^k e^{-\lambda}}{k!}$$

- ポアソン分布の期待値: $E(X) = \lambda$
- ポアソン分布の分散: $Var(X) = \lambda$

ポアソン分布は、 $\lambda$ がある程度大きくなると、 $\lambda$ を中心とする正規分布に近づく。

ポアソン分布は二項分布を近似した確率分布になっている。二項分布において、期待値( $n\cdot p$ )を一定に保ちつつ、 $n \to \infin$ , $p \to 0$ という近似を適用するとポアソン分布になる。

$e$ (ネイピア数)は、 $e \simeq 2.718$ である。覚える必要があるかはわからないが、参考として書いておく。

## 正規分布

正規分布は、平均 $\mu$ を中心として、左右対称の鐘形をしている。標準偏差 $\sigma$ は、平均から山の変曲点までの距離に相当する。

正規分布では、平均から $\pm1\sigma$ の範囲に全体の約68%、 $\pm2\sigma$ の範囲に約95%、 $\pm3\sigma$ の範囲に約99%のデータが収まる。

正規分布の確率密度関数は次になる。

$$f(x) = \frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$

## 標準化と正規化

**標準化**:

$$\hat{x}_i = \frac{x_i - \mu}{\sigma}$$

標準化は、各データ値から全データの平均値を引いて、標準偏差で割り算する操作。平均を0、標準偏差を1に変換することができる。

**正規化**:

データを0と1の間に揃える操作で**スケーリング**とも呼ばれる。
以下の計算を行う。

$$(データの値 - 最小値) / (最大値 - 最小値)$$

標準化と正規化の目的:
- データを扱いやすい形式に整える
- データ分析の精度や効率をよくする
- 単位や範囲の異なるデータ属性を比較しやすくする

特徴
- 正規化は標準化に比べて計算量が少ない。
- 正規化は外れ値、偏り、最大値、最小値に敏感に反応しやすい。
- 標準化はデータの外れ値や偏りの影響を補正できる。


## 標準正規分布（Z分布）

正規分布に確率変数 $X$ を標準化した確率変数 $Z$ を**Z値**と呼ぶ。

$$Z = \frac{X-\mu}{\sigma}$$

このZは、平均0、標準偏差1の正規分布で、**標準正規分布**と呼ばれる。

Z値が従う確率密度関数は以下になる。

$$f(x) = \frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}}$$

## 偏差値の計算（Z分布の応用）

偏差値は以下の式で計算される。

$$t_i = 50 + 10 \times \frac{x_i-\mu}{\sigma}$$

偏差値は、点数を標準化することで、平均0、標準偏差1の分布に変換した後、更に10倍して50を加算することで、平均50、標準偏差10の正規分布に変換した値になっている。

正規分布は、 $\pm1\sigma$に全体の68%のデータが収まるので、偏差値40から60に全体の68%が収まることになる。


## 期待値、標準偏差の性質

確率変数 $X$ と実数 $a$ に対して、以下が成り立つ。

$$\begin{aligned}
E(X+a) &= E(x) + a\\
Var(X+a) &= Var(X)\\
Std(X+a) &= Std(X)\\
\\
E(aX) &= a \cdot E(X)\\
Var(aX) &= a^2 \cdot Var(X)\\
Std(aX) &= a \cdot Std(X)
\end{aligned}$$

- 実数の加減算に対して、平均は変化するが、分散、標準偏差は影響を受けない。
- 実数を掛けると、平均、標準偏差はともに、元の値に実数をかけた値になる。

標準偏差を計算するときに、標準化された点数は平均 0 、分散 1 (つまり標準偏差が 1)になっている。この標準化された点数に対して、10倍して50を加算すると、平均は50になり、標準偏差は10になる。


