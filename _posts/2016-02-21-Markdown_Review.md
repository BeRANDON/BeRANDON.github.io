---
date: "2015-03-22T00:00:01Z"
draft: false 
title: "Markdown Review"
---

[TOC]

## Syntax

Ref to (https://github.com/fletcher/MultiMarkdown/wiki/MultiMarkdown-Syntax-Guide) to access the github multiMarkdown syntax.

## 编辑器

这里先简单介绍已经有的比较好的markdown编辑器

`Windows 平台`    

- `MarkdownPad` http://markdownpad.com/
- `MarkPad` http://code52.org/DownmarkerWPF/

`Linux 平台`

- `ReText` http://sourceforge.net/p/retext/home/ReText/

`Mac 平台`

- `mou` http://mouapp.com/ 轻量级MacOS专用编辑器，WYSIWYG的实时加载翻译。可导出到tumbler等平台  

`Cross-platform`

- `Haroopad` 韩国出品的应用，跨平台软件，传说是可以支持evernote以及tumblr，但其实仅仅是发送邮件到其对应的邮箱而已，没任何安全保护，而且服务器不稳定（我没发送成功过）。但可以参考一下它的[css](https://github.com/rhiokim/markdown-css)配置文件。

`在线编辑器`

- `Markable.in` http://markable.in/
- `Dillinger.io` http://dillinger.io/
- `mahua` http://mahua.jser.me/ 
- `cmd markdown` 网页编辑器，只能发布到它们自己的平台上，如果download了其翻译出来的html，其css也必须同步，才能有比较优秀的展示效果。由于支持流程图，以及序列图，因此功能还是不错的。
- `马克飞象` 一款网页markdown编辑器，与evernote账号无缝连接。但属于第三方应用，传说免费一段时间，需要收费，否则无法即时同步。（这个未来如何不好说）其功能与cmd markdown几乎一致，估计是相互抄袭的。
    
`chrome浏览器插件`

- `MaDe` https://chrome.google.com/webstore/detail/oknndfeeopgpibecfjljjfanledpbkog



## Markdown Implementations

可以参考[W3C的连接](http://www.w3.org/community/markdown/wiki/MarkdownImplementations)

它搜集了大多数能解析markdown，甚至转换成html的应用。

**在我理解中的，sundown，hoedown都是markdown的一种规则的子类，并且每一种都有各自的实现。在安装了Haroopad之后，可以在view中很清晰地看到各个不同实现binding中的不同功能，包括[GFM],[原始的markdown]，[sundown]实现等等。因此，如果要讲自己的想法提出来，则说不定可以称为新的一种标准。然后有人就按照这种标准做binding。**

`GFM`:<https://help.github.com/articles/github-flavored-markdown/>

## 2014 - Lepture [Mistune]

Lepture曾做过分析，对当前的python parsers做对比。

[Misaka]不再更新，不支持footnote，给予CPython。而Lepture的[Mistune]基于PyPy。Misaka是sundown的实现，而sundown已经停止维护了。

[Hoedown]继承于sundown，而且基于pypy，支持footnote。进一步可以使用[Hoep]来实现，为一个python binding。

[cMarkdown & Discount]基于[upskirt]，而sundown其实是upskirt的分支。cMarkdown比misaka慢，而且与misaka的缺点一致。

[Markdown & Markdown2]几乎就是最原始的markdown了。[Python-Markdown]也叫markdown，其实是最原始的[John Gruber’s Markdown]的一种python实现。而 [markdown2]几乎是markdown速度的1/2，所以不推荐。

以上就是发展历史，而Lepture自己提出的[Mistune]号称比原[Python-Markdown]快上4～5倍（使用[benchmark]来测试）。所以可以参考一下它的实现。可是，主要不妥的一点是，它的扩展其实还是不够，离马克飞象的距离还是比较远的。

[benchmark]:https://github.com/lepture/mistune/issues/1
[John Gruber’s Markdown]:http://daringfireball.net/projects/markdown/
[MisakaPypi]:https://pypi.python.org/pypi/misaka
[Misaka]:http://misaka.61924.nl
[Hoedown]:https://github.com/hhatto/python-hoedown/issues/5
[Hoep]:https://github.com/Anomareh/Hoep
[Python-Markdown]:https://github.com/waylan/Python-Markdown
[Mistune]:http://lepture.com/en/2014/markdown-parsers-in-python
[MistuneGithub]:https://github.com/lepture/mistune

## Markdonw Extension

现在最为急切的其实不是开发一个新的parser，而是在现有基础的各种python解释器上，看看是否能添加一些extension，来支持马克飞象一样的扩展。其实，在markdown中，直接集成markdown.Extension做一个新的类即可，然后再parser过程中，`markdown.markdown(raw_text, [my_markdown_extension], safe_mode = '')`添加自己的扩展即可。可以参考 @isaced 的[文章](http://www.isaced.com/post-249.html)

@fletcher的[MultiMarkdown]支持了非常多的类似于latex的功能，例如Bibliography，citations等，看起来非常臃肿。他提到[php Markdown Extra]的实现，因为他们实现的一些扩展功能是类似的，如table的列的合并。[fletcher]提到，其经历了大概4个版本，支持了latex，而且能输出为pdf。第四个版本是基于[ parsing expression grammar (PEG) ](http://en.wikipedia.org/wiki/Parsing_expression_grammar)重写的。

各种扩展的发展历史，也可以从<http://segmentfault.com/blog/p_chou/1190000000601562>看到。github都推荐使用Kramdown，可以重点看看这个markdown语法和feature。

[fletcher]:http://fletcherpenney.net/multimarkdown/
[php Markdown Extra]:https://michelf.ca/projects/php-markdown/extra/
[MultiMarkdown]:https://github.com/fletcher/MultiMarkdown/wiki/MultiMarkdown-Syntax-Guide#footnotes

## 文件格式间的转换

格式转换，是老生常谈话题，接触了markdown的之后，有了更多了解。如MultiMarkdown，`maruku`,`kramdown`，都可能利用`pandoc`来实现转换成html之类的文件的（没研究过代码，不太清楚）。如何利用pandoc＋markdown来做开发，可以参考 <http://blog.csdn.net/duqi_yc/article/details/8974041>

`kramdown` 是由ruby写的'markdown->html格式转换器'。可以说实现了 `maruku`, `php Markdown Extra` and `pandoc` 的各种features。注意的是，它的公式转换使用了`mathjax`（一款可以在各个browsers良好展示公式的javascript）。

`maruku`:<http://maruku.rubyforge.org/index.html>
`kramdown`:<http://kramdown.gettalong.org/index.html>
`pandoc`:<http://johnmacfarlane.net/pandoc/>
`mathjax`:<http://www.mathjax.org/>


## Extension

@joeyespo 开发的grip可以通过Github的api进行实时翻译，然后在本地浏览器上显示上传后的展示情况。

[grip]:https://github.com/joeyespo/grip
[PyMdown]:http://bitexplosion.com/PyMdown/index.html

## 设想

markdown项目设想：
有一个自动回顾模块，可以加强阅读 记忆 。

选择题：
选择标明markdown的TOC的目录结构的（顺序）

连线题目：
让人选择模块及其功能
或者填空一些简单的代码语句

默写题目：
1， 给目录结构，填写关键字，如果在其中，则通过。
给一个ipython的.ipynb文件给其下载使用？？？？其中有文档测试功能

### Markdown构想：

花括号｛｝用于标识精彩部分
^^代表自己的留言
？！表示Q&A
% 表示标签

### markdown 其实可以有非常多有趣的扩展应用：

1）例如@语法，应该可以像超链接一样，在文章末尾，提供各种社交链接号
如twitter，facebook，gravatar等，但一个人统一写一个名字

2）？！号，做提问，解答两种的Q&A布局最好
而根据问号数量，来作为衡量次问题严峻性的一种标志

3）大括号｛｝用来标注高亮一些语句，而这些高亮可以因人而异

## how to apply the third party markdown extension

https://github.com/waylan/Python-Markdown/wiki/Third-Party-Extensions

stack_flow -> pymdown
```
python -m markdown -x 'pymdownx.magiclink' -x 'pymdownx.arithmatex' a.md -x 'pymdownx.superfences' -x 'markdown.mdx_math' > output.html

this can trigger the magiclink extension,
but failed to trigger the arithmatex
```

## 缺陷 

1. 参考式链接中若title描述中的引号为空,则无法正常解释

        如: [id]: http://mahua.jser.me ""
  
    而有一个已知的问题是 Markdown.pl 1.0.1 会忽略单引号包起来的链接 title  

        如: [foo]: http://wowubuntu.com/markdown/index.html#link  'Optional Title Here'

2. 列表项中若空格行多于一行,则认为前后段落分开. 只有数字项开头的列表项才会进行排列. 
   且段落内的列表项并不做解释.这就说明了,其实很多markdown语法下的文字排版很奇怪,就是由一两个bug积累导致的

3. 编辑器众多,每个编辑器的解释器都不一致.像`markdownPad`,`sublimeText-priview`,`mahua`的解释器都不一致.导致无法完全按照语法规则来进行操作.但大部分是正确的

## 反思

1. Markdown为轻量级语法应用,但其格式存在着巨大的缺陷.看起来能够简易操作,但实质上
   只对在网页上撰写轻量级文档有辅助作用.涵盖的范围并无法满足一些细节性的定制化
   的控制. 例如层叠的markdown语法的解释等等. 但总体来说已经表现得非常不错了

2. 可以深入到开源项目`https://gitcafe.com/riku/Markdown-Syntax-CN/`中,了解这个解释器是如何工作的.从而了解一个格式编制是如何一步步实现的.

## 外部链接

1. 在线文档
    
    * [中文]: http://wowubuntu.com/markdown/ "中文完整版Markdown语法"
    * [中文快速入门]: http://wowubuntu.com/markdown/basic.html "中文快速入门版Markdown语法"
    * [English]: http://daringfireball.net/projects/markdown/syntax "英文Markdown语法"
    * [gitCafe]: https://gitcafe.com/riku/Markdown-Syntax-CN/blob/master/syntax.md "GitCafe原始项目"  

2. 参考文献
  
   * [wumii]: http://www.wumii.com/item/U4Yz63A3 "MarkDown 用標記來寫一篇文章吧！"







