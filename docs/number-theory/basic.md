
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


## 模运算

对于两个正整数 $a$ 和 $b$，在相除后没除尽的部分 $k$，称为它们的余数，记作 $a\bmod b=k$ 或者 $a\equiv k(\bmod b)$。

模运算满足以下性质：

- $(a+b)\bmod k = (a\bmod k + b\bmod k)\bmod k$。
- $(a-b)\bmod k = (a\bmod k - b\bmod k + k)\bmod k$。
- $(ab)\bmod k = (a\bmod k)(b\bmod k)\bmod k$。

## 欧拉定理

设 $a,m \in N^{+}$，且 $\gcd(a,m) = 1$，则公式有:

$$
a^{\varphi (m)} \equiv 1(\bmod m)
$$

其中 $\varphi (m)$ 称为对模 $m$ 缩系的元素个数。
此外，$a$ 对模 $m$ 的阶 $\delta_m(a)$ 必整除 $\varphi (m)$。

## 费马小定理

若 $p$ 为质数，则 $a^{p} \equiv a(\bmod p)$ 即 $a^{p-1} \equiv 1(\bmod p)$（但是当 $p|a$ 时不等价）。

## 孙子定理（中国剩余定理，CRT） 
 
设整数 $m_{1},m_{2},m_{3},···,m_{n}$ 两两互质，令 $m=m_{1}m_{2}m_{3}···m_{n}$（$m_{i}$ 的连乘）。则对于任意的 $j$ 在 $(1,n)$ 中的整数，下列联立的同余式有解：
 
$$
x_{j}=1\mod m_j,
x_{j}\equiv 0(\mod m_{i}),i\neq j .
$$

令 $x$ 为从 $1$ 到 $n$，$a_{j}x_{j}$ 的和，则 $x$ 适合下列联立同余式，

$$
x\equiv a_{j}(\mod m_{j}),j=1,2,3,···,n
$$
