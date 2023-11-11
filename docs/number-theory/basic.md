
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


