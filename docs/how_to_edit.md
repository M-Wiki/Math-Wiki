请仔细阅读以下内容后点击开始编辑：

<a style="padding:.75em 1.25em;display:inline-block;line-height:1;text-decoration:none;white-space:nowrap;cursor:pointer;border:1px solid #6190e8;border-radius:5px;background:#6190e8;color:#fff;outline:none;font-size:.75em" id="btn-startedit" href="">开始编辑</a>

<script>
	var btn = document.getElementById("btn-startedit");
	var url = location.search;
	var res = "https://github.com/Math-Wiki/Math-Wiki/edit/master/docs";
	if (url.indexOf("?") != -1) {
		var str = url.substr(1);
		strs = str.split("=");
		res += strs[1];
	}
	btn.href = res;
</script>

## 我们希望接受什么内容

我们不希望贡献者提供应试技巧、学习方法、竞赛指南等，也不希望贡献者提供学术上过于前沿的理论，我们希望贡献者提供的是：

1. 在学术上已经被广泛接受并被广泛利用的理论。

2. 不仅仅是数学公式，应该还有相应的证明过程以及较为通俗的解释。

3. 不是过于简单的知识（在简介中，Math-Wiki 也提出了不希望接受初中代数以下的内容）。

由于 Math-Wiki 不是原创学术内容网站，所以 Math-Wiki 允许大家模仿甚至转载他人文章，前提是对于含有协议的文章，需要申请转载的要向原作者申请，并在参考文献里说明，需要标注原文章链接和原作者的要在参考文献里标注。 

同时，Math-Wiki 因为接受面较广，对内容的要求反而宽松一点。遗憾的是，由于我们的网站在 Github 上托管，所以对于希望提供内容的数学界朋友，可能会有点门槛，敬请谅解。

## 如何贡献？

首先您要注册自己的 Github 账号，然后找到我们的主仓库 [Math-Wiki/Math-Wiki](https://github.com/Math-Wiki/Math-Wiki)，接着就可以编辑了。

编辑后选择 `Commit Changes`，输入 `Commit` 信息，然后回到首页发送 PRs，输入 PR 信息，`Commit` 信息和 PR 信息请在 [Commit 与 PR 约定](#Commit-与-PR-约定)。

## 在哪编辑？

根目录下 `docs` 文件夹中，您会看到大量 `.md` 结尾的文件，需要注意：文件名请用英文命名，如果需要创建新的文章分类，请选择新建文件夹（也用英文）并在新文件夹中添加文章。

## 格式要求

需要注意，我们可能会接受小规模的格式错误（譬如中英内容间没有加空格等），并在接受前修改，但大规模的格式错误可能会直接导致您的贡献内容被拒绝接受。

与常用的 Word 文档以及 PDF 不同，**Math-Wiki 使用的是 Markdown 语法，在书写方式上有很大差异**，这对很多贡献者来说可能也是一道门槛。由于 Markdown 语法这一段内容有些繁杂，所以我们直接给出官方教程：[Markdown 语法教程](https://markdown.com.cn/intro.html)。

### 关于标题（如果您希望撰写新文章，请看这里）

对于新的文章，所有标题应该在二级标题级以下，因为一级标题网站的程序已经自动渲染了。

而对于内容的大标题，请在根目录下有一名为 `mkdocs.yml` 的文件中，在 `nav` 选项中添加您的内容。

### 数学公式

数学公式（块状）的格式如下：

```
一段文本……

$$
Katex 代码……
$$

一段文本……
```

???+note "示例"
	
	一段文本……

	$$
	a^2+b^2=c^2
	$$

	一段文本……

数学公式（行内）格式如下：

```
一段文本 $Katex 代码$ 一段文本
```

???+note "示例"

	一段文本 $a+b=c$ 一段文本

[这是官方的 Katex 文档](https://katex.org/docs/supported.html)，不过为了使结构更加美观，我们单独规定了一些书写方法：


1. 对于模运算符，请使用 $\bmod$ 替代 $\mod$。（`\bmod` 取代 `\mod`）

2. 对于最小公倍数，请使用 $\operatorname{lcm}$ 取代 $lcm$。（`\operatorname{lcm}` 取代 `lcm`）

3. 对于整除，请使用 $\mid$ 取代 $|$（`\mid` 取代 `|`）

### 引用、结论、证明与 FAQ

对于引用部分，可以使用官方指南中的 `>`，也可以使用如下语法：

```
???+quote "text（可以省略）"

	内容……

	内容……

内容……
```

对于结论与证明部分，使用如下语法：

```
???+note "text（可以省略）"

	内容……

	内容……

内容……
```

如果有 FAQ，使用如下语法：

```
???+question "text（可以省略）"
	
	内容……

	内容……

内容……
```

### 其它规定

???+quote "说明"

	下文的“汉字”只包括表达实际意义的方块字，不包含标点符号。

1. 中英译名括号应使用英文括号，并和汉字保留一个空格，示例：`素数 (prime number) 和合数 (composite number)`。

2. 英文、数学行内公式应该与汉字保留一个空格，示例：`$a^2+b^2=c^2$ 被叫做勾股定理 (pythagorean theorem)。`

3. 由于 Markdown 语法的特性，写完一段应该换两行，同时一段的开头不应该空两个。

4. 在文档的开始有一段叫 `author` 的字段，在提交贡献前请在 author 字段后添上您的 Github ID。


## Commit 与 PR 约定

1. 如果有多次对不同内容的修改，应当分批提交 Commit 并分批提交 PR。

2. Commit 与 PR 的标题要满足以下规定，并且 Commit 与 PR 的标题应该相同：

	- 如果是对一个内容的小型错误修改或者格式修改，那么请在标题上书写 `fix(/docs下文件夹/下内容)修改……`。

	- 如果是对一个内容的大幅度修改或者彻底重构，请在标题上书写 `rewrite(/docs下文件夹/下内容)修改……`。

	- 如果是新撰写一个内容，请在标题上书写：`add(/docs下文件夹/下内容)添加……`。

	- 如果是对集成程序 CI 的修改，请在标题上书写：`fix ci 添加/修改了……功能`，并能证明 CI 能按预期运行。

## 合并方式

1. 对于质量低的提交，采用 `Squash` 合并。

2. 对于质量高的提交，采用 `Rebase` 合并。

3. 不应采用默认方式合并。

