2016-01-01-知识收集，管理和显示
===

@(_Research)[Manual, Knowledge]

[TOC]


## Evernote系列

- 马克飞象 [Maxiang.io](https://maxiang.io/)
> 一个非常棒的markdown编辑工具，比`GitHub Flavored Markdown`的语法支持更多的东西，例如`Latex公式`，`时序图`，`复选框`。
> 而且其生成的html文件渲染效果不错
> 缺点是，其同步到Evernote帐号是需要收费的，￥78一年不算便宜，但效果和便利性也算值得
> 如果谁能找到类似的替代工具，望周知

- 微信共享
> 有时候微信的文章分享，也可以通过分享直接发送到evernote上。方法就是先关注Evernote微信号，然后绑定帐号即可。下次无论在哪儿登录微信，都可以直接分享，不需要重复绑定。

## SimpleNote 系列

`选用SimpleNote系列，是因为它比其他知识类软件（Evernote）更轻便，更集中于文字写作。`

`Cons缺点`在于，SimpleNote做摘要的时候不是富文本格式，也即是说**文字字体格式**，**对其方式**，**加粗**等属性不会被摘录到软件记录中，这些属性倒不算重要，可是倘若一些link地址无法被捕获，后期编辑起来就很麻烦。

SimpleNote在其[官网](http://simplenote.com/downloads/)介绍有若干个Windows平台软件，包括：

1. [ResophNotes](http://www.resoph.com/)
> A Simplenote client for Windows, by C.Y. Yen.

2. [Click.to](http://www.clicktoapp.com/)
> Send text from your Windows clipboard to Simplenote with a single click. By Axonic.

3. [CintaNotes](http://www.cintanotes.com/)
> Lightweight note management app, supports tagging and searching. Pro version syncs with SimpleNote. By Cinta Software.

4. [Notation](http://getnotation.com/)
> Note-taking app for Windows with support for Simplenote.

`其中，优先选用ResophNotes和CintaNotes组合工作。原因一是他俩都可以portable，其次CintaNotes可以使用快捷键捕获剪贴板的内容，而ResophNotes可以识别并转换 GitHub Flavored Markdown 的语法成Html文件（不支持时序图等）。`

## Android平台笔记工具

Evernote和SimpleNote之类的笔记工具在Android平台上有自己官方的App，因此不需要第三方软件。但是，如果你需要一些其它编辑特性，可以尝试安装其他笔记工具。利用他们编辑文档后，再分享到对应的Evernote或SimpleNote帐号中。例如：

1. ListNote
> 可以识别中文语音输入的笔记软件。其中中文识别率比google语音输入还精确，而且对那些中文夹杂英文的语境特别适用。

2. MarkdownX
> `MarkdownX是目前发现的，Android平台最好的Markdown编写工具`
> 左右滑动即可切换Markdown Review和源代码
> 可共享导出为txt，md，html或者图片文件（其中还不清楚如何导出共享html文件到Evernote等平台上）
> 可同步Dropbox
> 快捷输入Markdown语法（例如加粗，插入代码）

3. Writeily
> 支持markdown语法，可生成浏览html文件（需要按按钮）
> 可share为html文档（这是唯一MarkdownX无法做到的一点，可是说真的，谁又需要在Android平台就发布html文档呢？）
> 上传到evernote的html文件也只是一堆html代码，未编译的。

4. neutriNote
> 支持markdown语法，可生成浏览html文件（需要按按钮）
> 软件说可以导出为html或md文件，但似乎无法共享到其他平台上（或者说共享有问题）
> 可以输入多媒体内容，例如图片，扫描二维码等。但是，尝试过共享到Evernote或者转换成html后再共享，都失败。其多媒体内容不会同步上传。但是，这款App还是`值得关注`的。

## Vi ＆ SublimeText

与Android平台相对比，`vi` 和 `Sublime Text` 在桌面端是非常实用的两个编辑器，而且在程序员间非常通用。两者都能支持多平台；虽然与markdown语法没有直接的联系，但都能通过os系统插件，或者软件自身插件来达到Markdown编写的目的。

# 使用建议

1. 利用`SimpleNote`，在windows平台下非常便利的做第一层纯txt数据收集，简单快捷
2. 利用Evernote及其周边产品进行写作的输出，相当于SimpleNote为输入，Evernote为输出。
```flow
st=>start: Input
e=>end: Html Blogs
sn=>operation: SimpleNote Collection
tk=>operation: Thinking
en=>operation: Evernote Reconstruction
#cond=>condition: Yes or No?

st->sn->tk->en->e
#cond(yes)->e
#cond(no)->op
```

## Further Work 下一步调查

`@21Jan2016`
- [ ] 替代maxiang.io的工具（同样的渲染效果即可）
- [ ] 网络上支持将latex公式转换的js工具，究竟如何工作的，能否集成到其它平台（st）。
- [ ] 是否已经存在了markdown编辑器
- [ ] 除了时序图，是否支持其它图形
- [ ] 搜集vi或sublimetext所支持markdown的资料，并补充此文档 
