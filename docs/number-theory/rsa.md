author:  2044-space-elevator

RSA 加密算法在信息学奥赛上没有应用，但是在密码学以及数论领域是一个重要工具。现代很多银行、金融机构、政府机关对 RSA 加密算法都有很多的运用。

RSA 加密算法是由罗纳德·李维斯特 (Ron Rivest)、阿迪·萨莫尔 (Adi Shamir) 和伦纳德·阿德曼 (Leonard Adleman) 一起提出的。算法的名字是由他们三人姓氏首字母组成的。

行文方便，后面对 RSA 加密算法统称 RSA。
## RSA 的破解瓶颈

RSA 的破解瓶颈在于因式分解，只要对大整数的质因数分解没有重大的突破，且所采用的素数值足够大，那么 RSA 至少在有效的时间内是无法被破解的。而且 RSA 不是对称加密，就是说获得了加密用的密钥也没法解密，甚至你把公钥给窃密者看他也无法破解，这也是 RSA 的厉害之处。

## 算法具体内容

RSA 有待加密文本 $M(0\le M<n)$，公钥 $P=(e,n)$ 以及私钥 $S=(d,n)$。

具体过程如下：

1. 选取两个大素数 $p$ 与 $q$，它们的位数最好在 700 位 到 1000 多位。然后我们计算 $n=pq$ 以及 $n$ 的欧拉函数值 $\varphi(n)$。其中易得 $\varphi(n)=(p-1)(q-1)$。

2. 选取一个数 $e$，$e\nmid 2$ 且 $\gcd(e,\varphi(n))=1$，**其中 $e$ 不要等于 $1$，不然加密的意义也就不存在了，这么说的原因请往下看。**
3. 计算模 $\varphi(n)$ 的情况下 $e$ 的乘法逆元 $d$（也就是方程 $ed\equiv 1(\bmod \varphi(n))$ 中 $d$ 的值），根据乘法逆元的原理，保证 $d$ 有解且只有 1 个解。
4. 公开公钥，私钥保密。
加密过程如下：
1. 设 $P(M)$ 表示加密信息，那么 $P(M)=M^e\bmod n$。
2. 设 $S(C)$ 表示解密密文，那么 $S(C)=C^d\bmod n$。

RSA 的特性：

1. 对于所有的公钥和密钥，满足 $S(P(M))=M$，同理也满足 $P(S(C))=C$。

我们这里解释一下为什么 $e$ 不能为 $1$：

> 在 $e=1$ 的情况下，$P(M)=M\bmod n$，因为 $1\le M<n$，所以 $P(M)=M$，失去加密作用。
>
> 在 $e=1$ 的情况下，$d=\varphi(n)+1$，也就是 $S(C)=C^{\varphi(n)+1}\bmod n$。根据欧拉定理 $C^{\varphi(n)}\bmod n=1$，所以我们可以得到 $S(C)=(C^{\varphi(n)}\bmod n)(C\bmod n)\bmod n=C\bmod n\bmod n=C\bmod n$，但是因为 $C$ 是由 $P(M)$ 加密过来的，所以 $1\le C< n$，那么 $S(C)=C$，失去解密作用。

再解释一下为什么 $0\le M< n$：

> 在 $M \ge n$ 时，必定存在一个数 $M_2$（$0\le M_2 < n$，使得 $P(M_2)=P(M)$，这就会使解密过程中无法返回正确结果。之所以会有这种歧义，是因为当 $M\ge n$ 的时候，$M^e\bmod n$ 肯定是小于 $n$ 的。
## RSA 正确性证明

证明 RSA 无非就是证明 $P(S(M))=M$，那么我们就展开它，可以得到 $P(S(M))$ 等价于：
$$
M^{ed}\bmod n
$$
因为 $e$ 和 $d$ 是对 $\varphi(n)=(p-1)(q-1)$ 的乘法逆元，所以存在整数 $k$，使得：

$$
ed=1+k(p-1)(q-1)
$$
展开其得到：

$$
\begin{aligned}
M^{ed}\bmod n&=M^{1+k(p-1)(q-1)} & \bmod n\\
&=M((M\bmod n)^{k(p-1)(q-1)})& \bmod n\\
&=M(M^{\varphi(n)-1}\bmod n)& \bmod n\\
\end{aligned}
$$
因为 [欧拉定理](https://m-wiki.github.io/Math-Wiki/number-theory/basic/#_5)，所以我们可以得到：
$$
M(M^{\varphi(n)-1}\bmod n)\bmod n=M\bmod n
$$
由于：
$$
1\le M < n
$$
因此得证。

## 参考文献

[1] 《算法导论》第 31 章 RSA 加密算法

[2] 转载于 [2044-space-elevator 的博客](https://www.cnblogs.com/2044-space-elevator/articles/17840785.html)
