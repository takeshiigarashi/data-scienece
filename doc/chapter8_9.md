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

# 8.9 確率・確率変数・確率分布

## 条件付き確率

事象Bが起こる条件の下で、事象Aが起こる条件付き確率を $P(A|B)$ と下記、以下の式で求める。

$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

上の式は、次のように書き換えることができる。（ベイズの定理）

$$P(A|B) = \frac{P(A)P(B|A)}{P(B)}$$

## 確率変数

**確率変数**とは、確率的に決まる値を保持できる変数。

数学的な定義: 確率変数 $X$ は、確率空間 $(\Omega, \mathscr{F}, P)$ から実数の集合 $\mathbb{R}$ への関数として定義される。ここで、
- $\Omega$ は、試行のすべての結果からなるサンプル空間
- $\mathscr{F}$ は、 $\Omega$ 上の $\sigma$-加法族
- $P$ は、確率測度

である。確率変数 $X$ は、サンプル空間の各店 $\omega \in \Omega$ に対して、実数値 $X(\omega)$ を対応させる関数である。

確率変数には、**離散型確率変数**と**連続型確率変数**の２種類がある。

**離散型確率変数**は、有限または可算無限個の値を取る確率変数。離散型確率変数は、確率関数によってその確率を記述する。
- $X$ が離散型確率変数で、値 $x_1, x_2, \cdots, x_n$ を取る場合、その確率関数は次のように表される。
$$P(X=x_i) = p_i \text{  for  } i=1,2,\cdots,n$$

**連続型確率変数**は、無限に多くの値を取る確率変数で、実数の範囲で値を取る。連続型確率変数は、確率密度関数によってその確率を記述する。
- $X$ が連続型確率変数で、確率密度関数 $f(x)$ を持つ場合、任意の区間 $[a,b]$ における確率は次の積分で求められる。
$$P(a \leq X \leq b) = \int_a^b f(x)dx$$

確率変数を用いた場合の期待値（平均）と分散は次で定義される。

- **期待値**(**平均**)
  - 離散型の場合: $E(X) = \sum_{i=1}^n x_ip_i$
  - 連続型の場合: $E(X) = \int_{-\infin}^\infin xf(x)dx$
- **分散**
  - 離散型の場合: $Var(X) = \sum_{i=1}^n (x_i - \mu)^2p_i$
  - 連続型の場合: $Var(X) = \int_{-\infin}^\infin (x - \mu)^2 f(x) dx$

