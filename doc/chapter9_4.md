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

# 9.4 微分

参考: https://math-masteeer.com/basic-knowledge/archive-basic-differential-and-integral.html

## 導関数

次の式で表される $f'(x)$ を、 $f(x)$ の**微分**、または**導関数**という。

$$f'(x) = \lim_{h \to 0} \frac{f(x+h)-f(x)}{h}$$

微分にかいくつかの記号がある。以下は、すべて微分を表す。

$$y', \frac{dy}{dx}, \frac{d}{dx}y, f'(x), \frac{df(x)}{dx}, \frac{d}{dx}f(x)$$

## 微分の公式

xのn乗の微分
$$(x^n)' = nx^{n-1}$$

定数の微分
$$(c)' = 0$$

kが定数のとき
$$\{kf(x)\}' = kf'(x)$$

２つの関数に対して
$$\{f(x) + g(x)\}' = f'(x) + g'(x)$$

積の微分
$$\{f(x)g(x)\} = f'(x)g(x) + f(x)g'(x)$$ 

商の微分
$$\Bigg\{ \frac{f(x)}{g(x)} \Bigg\}' = \frac{f'(x)g(x)-f(x)g'(x)}{\{g(x)\}^2}$$

合成関数の微分
$$\{f(g(x))\}' = f'(g(x))g'(x)$$

逆関数の微分
$$\frac{dy}{dx} = \frac{1}{\frac{dx}{dy}}$$

三角関数の微分
$$\begin{aligned}
(\sin x)' &= \cos x \\
(\cos x)' &= -\sin x \\
(\tan x)' &= \frac{1}{\cos^2 x}
\end{aligned}$$

指数関数の微分
$$\begin{aligned}
(a^x)' &= a^x \log a \\
(e^x)' &= e^x
\end{aligned}$$

対数関数の微分
$$\begin{aligned}
(\log_a x)' &= \frac{1}{x \log a} \\
(\log x)'   &= \frac{1}{x}
\end{aligned}$$

## 極大値・極小値

微分係数が0となる点を曲値という。

$y = x^4 - \frac{4}{3}x^3 - 2x^2 + 4x$ の極値を求めてみる。

$f'(x) = 0$ を解けばよいので、

$$\begin{aligned}
f'(x) = 4x^3 - 4x^2 -4x + 4 &= 0\\
x^3 - x^2 -x + 1 &= 0\\
(x + 1)(x^2 -2x + 1) & = 0\\
x &= -1, 1
\end{aligned}$$

極小、極大を判定するため、増減表は以下のように書く。

| $x$     | $\cdots$ | $-1$ | $\cdots$ | $1$ | $\cdots$
|---------|----------|------|----------|-----|------
| $f'(x)$ | $-$      | 0    | $+$      | 0   | $+$
| $f(x)$  | $\searrow$ | $-\frac{11}{3}$ | $\nearrow$ | $\frac{5}{3}$ | $\nearrow$

すると、 $x=-1$ で極小値 $-\frac{11}{3}$ をとる。極大値は存在しない。

