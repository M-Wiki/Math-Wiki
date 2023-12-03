author: 2044_space_elevator

## 什么是自然常数？

自然常数通常被记作 $e$，也被称为欧拉数，其在数学里的地位甚至比圆周率还高。其近似值为 $2.718281\ldots$。

通过以下几个示例，我们将体验到自然常数的“自然”之处。

## 自然常数是如何被计算出来的？

### 泰勒展开 (Taylor Formula)

已知函数 $f(x)=e^x$ 存在任意导数。将其在点 $e$ 进行泰勒展开，有：

???+ note 

	$$
	f(x)=\sum_{i=0}^n \frac{f^{i}(x)}{i!}+R_n(x)
	$$

令 $x=1$（即 $f(x)=e$）得：

$$
f(1)=\sum_{i=0}^n\frac{f^(i)(0)}{i!}+o(1)
$$

故有：

$$
f(1)=\lim_{n\to \infty}\sum_{i=0}^n \frac{1}{i!}
$$

即：

$$
e=\sum_{i=0}^{\infty}\frac{1}{i!}
$$

### 极限法

这个方法很简单：

???+ note

	$$
	e=\lim_{x\to\infty}(1+\frac{1}{x})^x
	$$

易证，反过来式子也成立：

$$
e=\lim_{x\to0}(1+x)^{\frac{1}{x}}
$$

## $e$ 的一些特性

### 在复平面上的特性

在实数域里，$e$ 与 $\pi$ 是八竿子都打不着的关系，但是如果拓展到虚数域，$e$ 和 $\pi$ 就能发生巧妙的关系。

相信大家都已经听闻欧拉公式这个名字，很多数学家也认为它是“最美公式”，即：

???+ note

	$$
	e^{\mathrm{i}\pi}=-1
	$$

欧拉公式的一般形式是：

$$
e^{\mathrm{i}x}=\cos x + \mathrm{i}\sin x
$$

通俗地说，欧拉公式相当于从 $1$ 开始逆时针转 $x$ 度，也就是说如果转了 $a{\degree}$，那么其值就等于 $e^{\mathrm{i}a}$，这也是为什么 $e^{\mathrm{i}\pi}=-1$。

欧拉公式巧妙地将数学中两个重要常数 $e$ 和 $\pi$ 结合在了一起，这也是为什么它能获得“最美公式”的美称。

### 唯一一个导数等于自身的函数

设 $f(x)=e^x$，那么可以证明，对于任意的一个数 $n$，均满足 $f^{(n)}(x)=e^x$。也就是说 $e^x$ 的导数是其自身。

如何证明呢？我们先考虑一般函数 $y=a^x$ 的导数，根据导数的定义有：

???+ note

	$$
	\lim_{\Delta x\to 0}\frac{a^x(a^{\Delta x}-1)}{\Delta x}
	$$

其等价于：

$$
a^x\lim_{\Delta x\to 0}\frac{a^{\Delta x} - 1}{\Delta x}
$$

因为：

$$
\lim_{\Delta x\to 0}\frac{a^{\Delta x} - 1}{\Delta x}=\log a
$$

将 $a$ 替换成 $e$，得 $(e^x)'=e^x$，故得证。

### 反比例函数的积分

设 $f(x)=\log x$，是 $e^x$ 的反函数。

大家应该都知道积分的基本公式之一：

$$
\int x^{\beta}\mathrm{d}x=\frac{x^{\beta + 1} - 1}{\beta + 1}
$$

当 $\beta$ 趋向于 $-1$ 时，该积分式子就变成了了反比例函数的积分：

$$
\int \frac{1}{x} \mathrm{d}x=\lim_{\beta \to 0} \frac{x^{\beta + 1} - 1}{\beta + 1}
$$

所以要求的是：

$$
\lim_{\beta \to 0}\frac{x^{\beta + 1} - 1}{\beta + 1}
$$

根据前面的公式，将对数函数代入，得到：

???+ note

	$$
	\int \frac{1}{x}\mathrm{d}x = \log x
	$$

## 参考文献

[1] [知乎 常用极限无穷小推导](https://zhuanlan.zhihu.com/p/463746935)

[2] [百度百科 等价无穷小](https://baike.baidu.com/item/%E7%AD%89%E4%BB%B7%E6%97%A0%E7%A9%B7%E5%B0%8F/7796020?fr=ge_ala)

[3] [百度百科 自然常数 e](https://baike.baidu.com/item/%E8%87%AA%E7%84%B6%E5%B8%B8%E6%95%B0/1298918?fr=ge_ala)

[4] [百度百科 泰勒展开](https://baike.baidu.com/item/%E6%B3%B0%E5%8B%92%E5%85%AC%E5%BC%8F/7681487?fromtitle=%E6%B3%B0%E5%8B%92%E5%B1%95%E5%BC%80&fromid=56292244)

[5] 《简单微积分》  [日] 神永正博著