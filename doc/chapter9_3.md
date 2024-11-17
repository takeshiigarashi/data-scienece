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

# 9.3 行列

参考: 文部科学省 高等学校数学科教材（行列入門） https://www.mext.go.jp/a_menu/shotou/new-cs/senseiouen/1394142_00001.html

## 行列

$$A = \begin{pmatrix}
65 & 82 & 78 & 70 \\
85 & 63 & 90 & 65 \\
76 & 90 & 82 & 85
\end{pmatrix}$$

上記は行が３個、列が４個の行列。
一般に行がm個、列がn個の行列をm行n列の行列 または $m \times n$ 行列という。

行と列の個数が等しい行列を**正方行列**という。n行n列の正方行列を**n次正方行列**という。

$\begin{pmatrix}1 & 3 \\ 2 & 6\end{pmatrix}$ は２次正方行列、 $\begin{pmatrix}a & b & c \\ b & c & a \\ c & a & b\end{pmatrix}$ は３次正方行列の例。

横方向にだけ成分がならんだものや縦方向にだけ成分が並んだものも行列と考える。これらは**行ベクトル**や**列ベクトル**と呼ぶ。

 $\begin{pmatrix}1 & 2 & 3\end{pmatrix}$ は、3次行ベクトル、$\begin{pmatrix}1 \\ 2 \\ 3\end{pmatrix}$は、３次列ベクトルの例。

## 行列の加法・減法・定数倍

加法は、型（サイズ）が等しい行列の各成分を加算すればよい。行列の減法も、加法と同様に成分ごとに差を求める。


例）

$\bm{A} = \begin{pmatrix}a_{11} & a_{12} \\
a_{21} & a_{22}\end{pmatrix}, \bm{B} = \begin{pmatrix}b_{11} & b_{12} \\ b_{21} & b_{22}\end{pmatrix}$ であるとき、 $\bm{A} + \bm{B}$ は、以下のように計算する。

$$\bm{A} + \bm{B} = \begin{pmatrix}
a_{11} + b_{11} & a_{12} + b_{12} \\
a_{21} + b_{21} & a_{22} + b_{22}
\end{pmatrix} $$

定数倍は、各要素に定数をかければよい。

例）

$\bm{A} = \begin{pmatrix}a_{11} & a_{12} \\
a_{21} & a_{22}\end{pmatrix}$ であるとき、 $c\bm{A}$ は、以下のように計算する。

$$c \bm{A} = \begin{pmatrix}
c \cdot a_{11} & c \cdot a_{12} \\
c \cdot a_{21} & c \cdot a_{22}
\end{pmatrix}$$

## いくつかの性質

$\bm{A}$ 、 $\bm{B}$ 、 $\bm{C}$ を同じ型の行列、 $\bm{O}$ を同じ型の零行列、 $k$ 、 $l$ を実数とするとき、次が成り立つ。
- 和の交換法則: $\bm{A} + \bm{B} = \bm{B} + \bm{A}$
- 和の結合法則: $(\bm{A} + \bm{B}) + \bm{C} = \bm{A} + (\bm{B} + \bm{C})$
- $\bm{A} + \bm{O} = \bm{O} + \bm{A} = \bm{A}$
- $k(l\bm{A}) = (kl)\bm{A}$
- $(k + l)\bm{A} = k\bm{A} + l\bm{A}$
- $k(\bm{A} + \bm{B}) = k\bm{A} + k\bm{B}$

## 例題

(1) 以下を確かめよ。

$$7\begin{pmatrix}-8 & 0 \\ -2 & 4\end{pmatrix} + 5 \begin{pmatrix}12 & 0 \\3 & -6\end{pmatrix} = \begin{pmatrix}4 & 0 \\ 1 & -2\end{pmatrix}$$

(問1.13) 次の等式が成立する数 $a, b, c, d$ を求めよ。

$$2\begin{pmatrix}a & b \\-2 & c\end{pmatrix} - 3\begin{pmatrix}2 & b \\ d & 3\end{pmatrix} = \begin{pmatrix}a+c & b \\ d & -c\end{pmatrix}$$

(問1.14) $\bm{A} = \begin{pmatrix}1 & 3 \\ -5 & 2\end{pmatrix}$ 、 $\bm{B} = \begin{pmatrix}1 & 1 \\ -1 & 2\end{pmatrix}$ のとき、 $3\bm{A} + 2\bm{X} = 5\bm{B}$ をみたす行列 $\bm{X}$ を求めよ。

## 行列の積

n次行ベクトルにn次列ベクトルを右からかける計算を次のように定める。

$$\begin{pmatrix}a_1 & a_2 & \cdots & a_n\end{pmatrix} \begin{pmatrix}b_1 \\ b_2 \\ \vdots \\ b_n\end{pmatrix} = a_1b_1 + a_2b_2 + \cdots + a_nb_n$$

$m \times n$ 行列 $\bm{A}$ と、$n \times r$ 行列 $\bm{B}$ の積は、 $i$ 行の行ベクトルと $j$ 行の列ベクトルの積を $i, j$ 成分とすることで定義する。

例:

$$\begin{pmatrix}a & b \\ c & d\end{pmatrix}\begin{pmatrix}x & z \\ y & w\end{pmatrix} = \begin{pmatrix}ax+by & az + bw \\ cx + cy & cz + cw\end{pmatrix}$$

## 例題

(問1.17) 次を計算せよ。

(1) $\begin{pmatrix}1 & 2 \\ 0 & -1\end{pmatrix}\begin{pmatrix}5 \\ 4\end{pmatrix}$

(5) $\begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9\end{pmatrix}\begin{pmatrix}a & 0 & 0 \\ 0 & b & 0 \\ 0 & 0 & c\end{pmatrix}$

## 対角行列

対角成分以外がすべて0である正方行列を**対角行列**という。次は対角行列の例である。

$$\begin{pmatrix}1 & 0 \\ 0 & 2\end{pmatrix}, \begin{pmatrix}a & 0 & 0 \\ 0 & b & 0 \\ 0 & 0 & c\end{pmatrix}$$

零行列も対角行列の１つである。

行列に対角行列を右からかけると、対角成分に従って列ごとに定数倍され、行列に対角成分を左からかけると、対角成分にしたがって行ごとに定数倍される。

例:

$$\begin{pmatrix}a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23}\end{pmatrix}\begin{pmatrix}2 & 0 & 0\\ 0 & 3 & 0 \\ 0 & 0 & 4\end{pmatrix} = \begin{pmatrix}2 \cdot a_{11} & 3 \cdot a_{12} & 4 \cdot a_{13} \\ 2 \cdot a_{21} & 3 \cdot a_{22} & 4 \cdot a_{23}\end{pmatrix}$$

列ごとに定数倍されている。

$$\begin{pmatrix}2 & 0 & 0 \\ 0 & 3 & 0 \\ 0 & 0 & 4\end{pmatrix}\begin{pmatrix}b_{11} & b_{12}\\ b_{21} & b_{22} \\ b_{31} & b_{32}\end{pmatrix} = \begin{pmatrix}2 \cdot b_{11} & 2 \cdot b_{12} \\ 3 \cdot b_{21} & 3 \cdot b_{22} \\ 4 \cdot b_{31} & 4 \cdot b_{32}\end{pmatrix}$$

行ごとに定数倍されている。

(問 1.21) 次を計算せよ。

(1) $\begin{pmatrix}a & b \\ c & d\end{pmatrix}\begin{pmatrix}2 & 0 \\ 0 & 3\end{pmatrix}$

(2) $\begin{pmatrix}3 & 0 & 0 \\ 0 & 5 & 0 \\ 0 & 0 & 1\end{pmatrix}\begin{pmatrix}1 & 4 & 2 \\ -4 & 2 & 0 \\ -5 & 9 & -1\end{pmatrix}$

## 単位行列

対角行列において、対角成分がすべて１の行列を**単位行列**という。

## 転置行列

行列の行と列を入れ替えた行列を**転置行列**という。 $\bm{A}$ の転置行列を $\bm{A}^\top$ と書く。

$\bm{A}$ 、 $\bm{B}$ を同じ型の行列、 $k$ を実数とするとき、次が成り立つ。

- $(\bm{A}^\top)^\top = \bm{A}$
- $(\bm{A} + \bm{B})^\top = \bm{A}^\top + \bm{B}^\top$
- $(k\bm{A})^\top = k \bm{A}^\top$

## 対称行列

正方行列 $\bm{A}$ が、 $\bm{A} = \bm{A}^\top$ を満たすとき、　$\bm{A}$ を**対称行列**という。

## 行列の積の性質

- $\bm{A}\bm{E} = \bm{A}, \bm{E}\bm{A} = \bm{A}$
- $\bm{A}\bm{O} = \bm{O}, \bm{O}\bm{A} = \bm{O}$
- $(k\bm{A})\bm{B} = k(\bm{A}\bm{B}) = \bm{A}(k\bm{B})$
- $\bm{A}(\bm{B} + \bm{C}) = \bm{AB} + \bm{AC}, (\bm{A} + \bm{B})\bm{C} = \bm{AC} + \bm{BC}$ (分配法則)
- $(\bm{AB})\bm{C} = \bm{A}(\bm{BC})$ (積の結合法則)

(例題 1.2) 次を計算して確認せよ。

(1) $\begin{pmatrix}1 & 2 \\ 2 & 4\end{pmatrix} \Bigg( \begin{pmatrix}10 & 9 \\ -5 & 7\end{pmatrix} + \begin{pmatrix}13 & 15 \\ 8 & -\frac{15}{2}\end{pmatrix} \Bigg) = \begin{pmatrix}29 & 23\\ 58 & 46\end{pmatrix}$

通常に計算したときと、分配法則を用いたときの２通りで計算せよ。

(2) $\begin{pmatrix}1 & 3 \\ 4 & -5\end{pmatrix}\begin{pmatrix}8 & -14 & -2 \\ 6 & 12 & 10\end{pmatrix} - \begin{pmatrix}2 & 6 \\ 8 & -10\end{pmatrix}\begin{pmatrix}3 & -7 & -1 \\ 3 & 5 & 5\end{pmatrix} = \begin{pmatrix}2 & 6 & 0 \\ 8 & -10 & 0\end{pmatrix}$

通常に計算したときと、分配法則を用いたときの２通りで計算せよ。

## 正則行列と逆行列

n次正方行列 $\bm{A}$ に対して、
$$\bm{AB} = \bm{BA} = \bm{E}$$
を満たすn次正方行列 $\bm{B}$ が存在するとき、 $\bm{A}$ を**正則行列**、または $\bm{A}$ は**正則**であるという。また、行列 $\bm{B}$ は $\bm{A}$ の**逆行列**といい、 $\bm{A}^{-1}$ と表す。

すべての行列が逆行列を持つわけではない。例えば、 $\bm{A} = \begin{pmatrix}1 & 2 \\ 2 & 4\end{pmatrix}$ は、逆行列を持たない（連立方程式を考えるとよい）。

逆に、正則行列の逆行列はただ１つに定まることが知られている。

(例1.14) $\bm{A} = \begin{pmatrix}5 & 2 \\ 2 & 1\end{pmatrix}$ とする。このとき、 $\bm{B} = \begin{pmatrix}1 & -2 \\ -2 & 5\end{pmatrix}$ とすると、 $\bm{AB} = \bm{BA} = \bm{E}$ となることを確認せよ。

### 二次正方行列の逆行列

二次正方行列 $\bm{A} = \begin{pmatrix}a & b \\ c & d\end{pmatrix}$ が、 $ad - bc \ne 0$ を満たすとき、 $\bm{A}$ の逆行列 $\bm{A}^{-1}$ は、以下になる。

$$\bm{A}^{-1} = \frac{1}{ad - bc}\begin{pmatrix}d & -b \\ -c & a\end{pmatrix}$$


(証明) $\bm{X} = \begin{pmatrix}x & y \\ z & w\end{pmatrix}$ として、 $\bm{AX} = \bm{E}$ を満たす $\bm{X}$ を求める

$$\begin{aligned}
\bm{AX} &= \begin{pmatrix}a & b \\ c & d\end{pmatrix}\begin{pmatrix}x & y \\ z & w\end{pmatrix} \\
 &= \begin{pmatrix}ax + bz & ay + bw \\ cx + dz & cy + dw\end{pmatrix} = \begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix}
\end{aligned}$$

上記より、以下の４式を得る。

$$\begin{aligned}
ax + bz &= 1 \\
cx + dz &= 0 \\
ay + bw &= 0 \\
cy + dw &= 1
\end{aligned}$$

上記の連立方程式を解くことで、求める答える得る。
 b
### 行列式

二次正方行列 $\bm{A} = \begin{pmatrix}a & b \\ c & d\end{pmatrix}$ に対し、 $ad - bc$ を $\bm{A}$ の**行列式**といい、 $|\bm{A}|$ または $\det({A})$ と書く。

二次正方行列 $\bm{A} = \begin{pmatrix}a & b \\ c & d\end{pmatrix}$ が正則であるための必要十分条件は、 $|A| \ne 0$ であり、このとき、 $\bm{A}$ の逆行列 $\bm{A}^{-1}$ は、

$$\bm{A}^{-1} = \frac{1}{|A|}\begin{pmatrix}d & -b \\ -c & a\end{pmatrix}$$

である。

(問1.52) 次の各行列の正則性を判定し、正則であれば、逆行列を求めよ。

(1) $\begin{pmatrix}1 & 1 \\7 & 6\end{pmatrix}$

(2) $\begin{pmatrix}-2 & 4 \\ -6 & 12\end{pmatrix}$

### 対角行列の逆行列

対角行列 $\bm{A}$ が正則であるための必要十分条件は、対角成分に0を含まないことであり、 $\bm{A}^{-1}$ は、各対角成分の逆数を対応する順に並べたものになる。

$\bm{A} = \begin{pmatrix}a & 0 & 0 \\ 0 & b & 0 \\ 0 & 0 & c\end{pmatrix}$ に対して、 $\bm{A}^{-1} = \begin{pmatrix}\frac{1}{a} & 0 & 0 \\ 0 & \frac{1}{b} & 0 \\ 0 & 0 & \frac{1}{c}\end{pmatrix}$

### 連立方程式への応用

連立一次方程式を、行列を用いて $\bm{Ax} = \bm{b}$ と表したとき、 $\bm{A}$ が正則であれば、その解は $\bm{x} = \bm{A^{-1}b}$ で得られる。

(例題) 次の連立方程式の解が $x = -\frac{17}{7}, y = \frac{11}{7}$ であることを、逆行列を用いて計算せよ。

$$
\begin{aligned}
2x + 5y &= 3 \\
3x + 4y &= -1
\end{aligned}
$$

## 行列の固有値

$\bm{A}$ を $n$ 次正方行列とする。零ベクトルではないベクトル $\bm{x}$ に対して、 $\bm{Ax} = \lambda\bm{x}$ が成り立つとき、 $\lambda$ を $\bm{A}$ の**固有値**、 $\bm{x}$ を $\lambda$ に属する**固有ベクトル**という。

固有値は、行列式から求めることができる。

まず、正方行列 $\bm{A}$ に対して、 固有値、固有ベクトルの定義より、
$$\bm{Ax} - \lambda\bm{x} = 0$$
である。

$\bm{E}$ を単位行列とすると、$\lambda\bm{x} = \lambda\bm{Ex}$ であるから、

$$\begin{aligned}
\bm{Ax} - \lambda\bm{Ex} &= 0 \\
(\bm{A} - \lambda\bm{E})\bm{x} &= 0
\end{aligned}$$

ここで、 $\bm{A} - \lambda\bm{E}$ が逆行列を持つ場合、両辺に左から逆行列をかけると $\bm{x} = \bm{0}$ になる。しかし、 $\bm{x} \ne \bm{0}$ であるから、 $\bm{A} - \lambda\bm{E}$ は逆行列を持たない。

つまり、 $\bm{A} - \lambda\bm{E}$ の行列式が０になるように $\lambda$ を求めればよい。

(例題 3.2) $\bm{A} = \begin{pmatrix}1 & 1 \\ -2 & 4\end{pmatrix}$ とする。このときの固有値と固有ベクトルを求める。

固有値は $\bm{A} - \lambda\bm{E}$ の行列式より求める。

$$\bm{A} - \lambda\bm{E} = \begin{pmatrix}1 - \lambda & 1 \\ -2 & 4 - \lambda\end{pmatrix}$$

である。この行列の行列式が 0 なので、

$$(1-\lambda)(4-\lambda) - 1 \cdot (-2) = 0$$

上記を解くと $\lambda = 2, 3$ を得る。

続いて $\lambda = 2, 3$ それぞれの場合で、以下を解いて固有ベクトルを求める。

$$\begin{pmatrix}1-\lambda & 1 \\ -2 & 4-\lambda\end{pmatrix}\begin{pmatrix}x \\y\end{pmatrix} = \begin{pmatrix}0\\0 \end{pmatrix}$$

上記を解くと、 $\lambda = 2$ に属する固有ベクトルは $\begin{pmatrix}1\\1\end{pmatrix}$ となり、 $\lambda = 3$ に属する固有ベクトルは $\begin{pmatrix}1\\2\end{pmatrix}$ となる。

(問3.5) 次の行列の固有値と各固有値に属する固有ベクトルを求めよ。

(1) $\begin{pmatrix}2 & 3 \\3 & 2\end{pmatrix}$

(2) $\begin{pmatrix}1 & 5 \\2 & -2\end{pmatrix}$

(3) $\begin{pmatrix}1 & 1 \\0 & 1\end{pmatrix}$

## 行列の対角化

$\bm{A}$ を2次正方行列とし、

$$\bm{P}^{-1}\bm{AP} = \begin{pmatrix}\alpha &0 \\0 & \beta\end{pmatrix}$$

と対角化できたとする。この両辺に $\bm{P}$ を左からかけると、

$$\bm{AP} = \bm{P}\begin{pmatrix}\alpha & 0\\0 & \beta\end{pmatrix}$$

となる。

列ベクトルを用いて $\bm{P} = \begin{pmatrix}\bm{p_1} & \bm{p_2}\end{pmatrix}$ と書くと、上式の左辺、右辺はそれぞれ、次のように書ける。

$$\begin{aligned}
\bm{AP} &= \begin{pmatrix}\bm{A}\bm{p_1} & \bm{A}\bm{p_2} \end{pmatrix}\\
\bm{P}\begin{pmatrix}\alpha & 0\\0 & \beta\end{pmatrix} &= \begin{pmatrix}\alpha\bm{p_1} & \beta\bm{p_2}\end{pmatrix}
\end{aligned}$$

この２つが等しいので、

$$\begin{aligned}
\bm{Ap_1} &= \alpha\bm{p_1}\\
\bm{Ap_2} &= \beta\bm{p_2}
\end{aligned}$$

つまり、　$\alpha, \beta$ は行列 $\bm{A}$ の固有値で、 $\bm{p_1}$ は $\alpha$ に属する固有ベクトル、 $\bm{p_2}$ は $\beta$ に属する固有ベクトルとなる。

すなわち、ある行列を対角化したいときは、その行列の固有値と固有ベクトルを求めることで上記の行列 $\bm{P}$ を得ることができる。

(例題) $\bm{A} = \begin{pmatrix}3 & 2\\1 & 4\end{pmatrix}$ を対角化すると、行列 $\begin{pmatrix}2 & 0 \\0 & 5\end{pmatrix}$ が得られることを確認せよ。
