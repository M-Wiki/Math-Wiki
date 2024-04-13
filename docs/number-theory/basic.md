author: 2044-space-elevator,taoyiwei17-cfynry

## 素数与合数

对于一个正整数 $n$，如果只有 $1$ 和 $n$ 能被 $n$ 整除，则称 $n$ 为素数 (prime number)，否则称其为合数 (composite number)。

特别地，$1$ 既不是素数也不是合数。

素数也称为质数。

## 算术基本定理（唯一分解定理）

对于任意一个正整数 $n$，均能分解成：

$$
n=p_1^{r_1}p_2^{r_2}p_3^{r_3}\ldots p_k^{r_k}
$$

其中 $p_i$ 为素数。

## 最大公约数和最小公倍数 

对于两个正整数 $a$ 和 $b$，存在一个最大的 $k$，使得 $k|a$ 且 $k|b$，那么记作 $\gcd(a,b)=k$。

同理，如果存在一个最小的 $q$，使得 $a|q$ 且 $b|q$，那么记作 $\operatorname{lcm}(a,b)=q$。


### 性质

1. 如果 $a,b$ 互素，那么我们可以得到 $\gcd(a,b)=1$。
2. 如果 $a_1,a_2,\ldots,a_n$ 互素，那么我们可以得到 $\gcd(a_1,a_2,\ldots,a_n)=1$。
3. 对于任意 $a,b$ 有 $\operatorname{lcm}(a,b)=\dfrac{ab}{\gcd(a,b)}$，当 $a,b$ 互素时 $\operatorname{lcm}(a,b)=ab$。
4. 根据辗转相除法有 $\gcd(a,b)=\gcd(b,a\bmod b)$。

???+ note "证明"

	以下片段摘自 [OI-Wiki](https://oi-wiki.org/math/number-theory/gcd/#%E6%AC%A7%E5%87%A0%E9%87%8C%E5%BE%97%E7%AE%97%E6%B3%95)

	设 $a=bk+c$，显然有 $c=a \bmod b$。设 $d \mid a,~d \mid b$，则 $c=a-bk, \frac{c}{d}=\frac{a}{d}-\frac{b}{d}k$。
    
    由右边的式子可知 $\frac{c}{d}$ 为整数，即 $d \mid c$，所以对于 $a,b$ 的公约数，它也会是 $b,a \bmod b$ 的公约数。
    
    反过来也需要证明：
    
    设 $d \mid b,~d\mid (a \bmod b)$，我们还是可以像之前一样得到以下式子 $\frac{a\bmod b}{d}=\frac{a}{d}-\frac{b}{d}k,~\frac{a\bmod b}{d}+\frac{b}{d}k=\frac{a}{d}$。
    
    因为左边式子显然为整数，所以 $\frac{a}{d}$ 也为整数，即 $d \mid a$，所以 $b,a\bmod b$ 的公约数也是 $a,b$ 的公约数。
    
    既然两式公约数都是相同的，那么最大公约数也会相同。
    
    所以得到式子 $\gcd(a,b)=\gcd(b,a\bmod b)$

## 模运算

对于两个正整数 $a$ 和 $b$，在相除后没除尽的部分 $k$，称为它们的余数，记作 $a\bmod b=k$ 或者 $a\equiv k\pmod{b}$。

模运算满足以下性质：

- $(a+b)\bmod k = (a\bmod k + b\bmod k)\bmod k$。
- $(a-b)\bmod k = (a\bmod k - b\bmod k + k)\bmod k$。
- $(ab)\bmod k = (a\bmod k)(b\bmod k)\bmod k$。

## 欧拉定理

设 $a,m \in N^{+}$，且 $\gcd(a,m) = 1$，则公式有:

$$
a^{\varphi (m)} \equiv 1\pmod{m}
$$

其中 $\varphi (m)$ 称为对模 $m$ 缩系的元素个数。
此外，$a$ 对模 $m$ 的阶 $\delta_m(a)$ 必整除 $\varphi (m)$。

## 费马小定理

若 $p$ 为质数，则 $a^{p} \equiv a\pmod{p}$ 即 $a^{p-1} \equiv 1\pmod{p}$（但是当 $p\mid a$ 时不等价）。

## 孙子定理（中国剩余定理，CRT） 
 
设整数 $m_{1},m_{2},m_{3},···,m_{n}$ 两两互质，令 $m=m_{1}m_{2}m_{3}···m_{n}$（$m_{i}$ 的连乘）。则对于任意的 $j$ 在 $(1,n)$ 中的整数，下列联立的同余式有解（注意 $i \ne j$）：
 
$$
\begin{cases}
x_{j}\equiv 1 \pmod{m_j}\\\
x_{j}\equiv 0\pmod{m_{i}}
\end{cases}
$$

令 $x$ 为从 $1$ 到 $n$，$a_{j}x_{j}$ 的和，则 $x$ 适合下列联立同余式（前提条件是满足 $j$ 属于 $(1, n)$）：

$$
x\equiv a_{j}\pmod{m_{j}}
$$
