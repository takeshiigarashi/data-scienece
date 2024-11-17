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

# 9.2 対数の計算

参考: https://rikeilabo.com/formula-and-transformation-of-logarithm

## 対数の定義

$a > 0, a \ne 1, M > 0$のとき、
$$a^p = M \iff \log_a M =p$$

$\log_a M$ を、 $a$ を**底**とする $M$ の**対数**という。 $M$ を、 $\log_a M$ の**真数**という。

## 対数の性質

$a > 0, a \ne 1, M > 0, N > 0$とする。

【対数の性質】
$$\log_a a = 1$$
$$\log_a 1 = 0$$

【積の対数】
$$\log_a MN = \log_a M + \log_a N$$

【商の対数】
$$\log_a \frac{M}{N} = \log_aM - \log_aN$$

【累乗の対数】
$$\log_a M^r = r\log_aM$$

【底の変換公式】  
$a,b,c$ は正の数で、 $a \ne 1$ 、 $b \ne 1$ 、 $c \ne 1$ のとき

$$\log_a b = \frac{\log_c b}{\log_c a}$$

特に、 $c = b$ とすると、

$$\log_ab = \frac{1}{\log_b a}$$

## 積の対数の証明

$\log_a M = p$ , $\log_a N = q$ とおくと、
$$M = a^p, N = a^q$$
よって
$$MN = a^p \cdot a^q = a^{p+q}$$
両辺に対して $a$ を底とする対数をとると

$$\begin{aligned}
\log_a MN &= \log_a a^{p+q} \\
 &= p + q \\
 &= \log_a M + \log_a N
\end{aligned}$$

## 例題

(1) $\log_6 4 + \log_6 9 = 2$ を実際に計算して証明せよ。

(2) $\log_4 96 - \log_4 6 = 2$ を実際に計算して証明せよ。

(3) $\frac{1}{2}\log_2 25 + log_2 \frac{1}{10} = -1$ を証明せよ

(4) $\frac{3}{2}\log_3 \sqrt[3]{12} = \log_3 2\sqrt{3}$ を証明せよ

(5) $\log_{27} 9 = \frac{2}{3}$ を証明せよ

(6) $\log_4 9 - \log_2 12 = -2$ を証明せよ。

