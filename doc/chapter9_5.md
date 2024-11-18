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

# 9.5 積分

参考
- https://math-masteeer.com/basic-knowledge/archive-basic-differential-and-integral.html
- https://examist.jp/mathematics/integration/sekibunkousiki/

## 不定積分

次で定義される $\int f(x) dx$ を $f(x)$ の**不定積分**という。

$$\int f(x) dx = F(x) + C$$

ここで、 $C$ は積分定数。

## 定積分

関数 $f(x)$ の原始関数の１つを $F(x)$ とするとき、 $F(b) - F(a)$ を $f(x)$ の $a$ から $b$ までの定積分といい、次のように書く。

$$\int_a^b f(x)dx = [F(x)]_a^b = F(b) - F(a) $$

## 公式

xのn乗の不定積分

$n \ne -1$のとき、
$$\int x^n ~ dx = \frac{1}{n+1}x^{n+1} + C$$

$n = -1$のとき
$$\int x^{-1} ~ dx = \int \frac{1}{x} = \log |x| + C$$

三角関数

$$\begin{aligned}
\int \sin x ~ dx &= -\cos x + C\\
\int \cos x ~ dx &= \sin x + C\\
\int \frac{1}{\cos^2 x} ~ dx &= \tan x + C\\
\int \frac{1}{\sin^2 x} ~ dx &= - \frac{1}{\tan x} + C
\end{aligned}$$

指数関数

$$\begin{aligned}
\int e^x ~ dx &= d^x + C \\
\int a^x ~ dx &= \frac{a^x}{\log a} + C
\end{aligned}$$

ここで、 $a > 0, a \ne 1$ とする。

対数関数

$$\int \log x ~ dx = x \log x - x + C$$


定数倍

$$\int k f(x) ~ dx = k \int f(x) ~ dx$$

和の積分

$$\int f(x) + g(x) ~ dx = \int f(x)dx + \int g(x) ~ dx$$

積分区間の幅が0の積分

$$\int_a^a f(x) ~ dx = 0$$

積分区間の入れ替え

$$- \int_a^b f(x) ~ dx = \int_b^a f(x) ~ dx$$

積分区間の分割

$$\int_a^b f(x) ~ dx + \int_b^c f(x) ~ dx = \int_a^c f(x) ~ dx$$

奇関数の積分

$f(x) = x^{2n-1}$ のとき、
$$\int_{-a}^a f(x) ~ dx = 0$$

偶関数の積分

$f(x) = x^{2n}$ のとき、
$$\int_{-a}^a f(x) ~ dx = 2 \int_0^a f(x)dx$$

1/6公式

$$\int_\alpha^\beta (x-\alpha)(x-\beta) ~ dx = - \frac{(\beta-\alpha)^3}{6} $$

## 問題

https://examist.jp/mathematics/integration/sekibunkeisan/

次の積分を確認せよ。（以下は、式を展開すれば基本公式のみで溶ける）

(1) $$\int \frac{(2x+3)^2}{x^2} ~ dx = 4x + 12 \log |x| - \frac{9}{x} + C$$

(2) $$\int \frac{(\sqrt{x}-1)^2}{\sqrt{x}} ~ dx = \frac{2}{3}x\sqrt{x} - 2x + 2\sqrt{x} + C$$

(5) $$\int_{\log 2}^{\log 5} \frac{e^{2x} - 1}{e^x + 1} ~ dx = 3 - \log \frac{5}{2}$$

(6) $$\int \frac{4^x-1}{2^x} ~dx = \frac{2^x + 2^{-x}}{\log 2} + C$$

## 置換積分

$f(x)$ の積分において、 $x = g(t)$ とすると、
$$\int f(x) ~ dx = \int f(g(t)) g'(t) dt$$

もしくは $f(g(x))g'(x)$ の形式において $g(x)=u$ とすると、
$$\int f(g(x))g'(x) ~ dx = \int f(u) ~ du$$


(例1) $f(x) = \frac{x}{\sqrt{x-1}}$ に対して、 $\sqrt{x-1} = t$ と置き換えると $x = t^2 + 1$ なので、

$$\int \frac{x}{\sqrt{x-1}} ~ dx = \int \frac{t^2+1}{t} (t^2+1)' ~ dt = \int \frac{t^2+1}{t} \cdot 2t ~ dt$$

(例2) $$\int \sin^2 x ~ \cos x ~ dx = \int u^2 ~ du$$

## 定積分の置換積分

定積分の置換積分では、積分範囲が変わることに注意が必要。

$$\int_2^3 \frac{x}{\sqrt{x-1}} ~ dx$$

この定積分は、 $\sqrt{x-1} = t$ と置き換えると、 $x:2 \to 3$ が $t: 1 \to \sqrt{2}$ となるので、

$$\int_1^{\sqrt{2}} \frac{t^2+1}{t} \cdot 2t ~ dt$$


