---
date: "2016-02-23T20:50:40Z"
draft: false 
title: "Tools for flowchart presentation"
---

Previously, I only use `Microsoft Visio` as the SVG generator. However, it is not free and not suitable for portable mobile working. Recently, website-based online flowchart tools are popular because one can access services and files from anywhere. Besides, one can also use statistic language description, like TikZ/Latex to generate the SVG you need.

# Abstract 

`My opinion`:
<font color=red>笔者推荐使用Tikz，yEd。前者为latex扩展包，后者为开源工具。网络版编辑推荐使用lucidchar，毕竟可以导出为visio。而如果不需要导出其余便携格式，可以尝试使用gliffy；虽然gliffy免费版本无法导出svg，可是它支持publish，博客可以直接使用其提供的链接作为插图。如果只写Markdown博客，内嵌flowchart.js & js-sequence-diagrams的js代码，并使用其规定语法就足够显示了；当然如果能转换成base64的格式就能更好地内嵌了。如果害怕浏览器显示效果的差异，建议将流程图转换成png格式，或者可以内嵌入网页的svg格式。</font>

其他人的意见：
> (https://www.zhihu.com/question/20177573)

> 类图用代码直接生成，主要是给个大致概念，ER图用 railsroady 输出模型图代替，其它用于思考的主要是各种架构图、时序图、鲁棒图，用 dia 或者 yEd 就可以了
 
## Desktop Tools

Ref:
http://jiaren.org/2009/02/13/several-flow-charts-maker-software/
https://xbeta.info/visio-alternative.htm

这些免费软件可以用来绘制流程图。介绍顺序是按照体积从小到大：EVE、Diagram Designer、Dia、EDraw Mind Map、OOo Draw。其中Dia与EDraw 推荐人数较多。没有逐一尝试使用过，单看画面，感觉不太精美。

`EVE` (http://barryk.org/goosee/) 100k以内
`Diagram Designer` (http://meesoft.logicnet.dk/DiagramDesigner/) 2M左右
`Dia` (https://wiki.gnome.org/Apps/Dia) 基于`GTK+`的图形界面，几M大小，功能较为单一。
`EDraw Mind Map 亿图` (https://www.edrawsoft.com/) 只有Win平台
`OOo Draw` (https://www.openoffice.org/product/draw.html) office的开源对应版本
`yEd` (https://www.yworks.com/products/yed) 基于java的开源编辑器，完全免费。**支持xml,ged,xls import &automatically arrange。**

### yEd

ref:
https://www.yworks.com/products/yed (official)
http://www.jianshu.com/p/be4a2e7f60af


## Online Tools

| Features | [cacoo] | [processon] | [gliffy] | [lucidchart] | [draw.io] |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 精美度(满分10) | 6 | 6 | 7 | 4 | 4 |
| 操作度(满分10) | 6 | 7 | 7 | 4 | 5 |
| 导入方法 | － | Xmind, Visio, txt | visio, gliffy | Google Drive (??sync only 5 files), Visio, Gliffy, Omnigraffle | One Drive, Dropbox, Google Drive |
| 导出格式 | png,svg,pdf.ps.ppt,免费版只支持png | SVG,png,pdf,pos | 免费版只能倒出gliffy | SVG(透明),png(透明),pdf,visio | SVG,png,pdf,html,xml |
| 导出云端 | - | - | 可以publish | Sync google drive | - | 
| Free Version Limit | - | - | 不能导出通用格式 | 25M, 每幅图只能有60个元素 | - | 
| 收费版本特色 | 空间大，插入大尺寸图 | free | - | More Storage | free |
| 教育免费版本 | √ | - | - | - | - |

[cacoo]:https://cacoo.com
[processon]:https://www.processon.com/
[gliffy]:https://www.gliffy.com/
[draw.io]:https://www.draw.io/
[lucidchar]:https://www.lucidchart.com/
[^pdf unkown usage]:仍然不清楚如何在Lucidchart发布pdf格式的文件

## Programmatical Flowchart

### flowchart.js

http://adrai.github.io/flowchart.js/

### js-sequence-diagrams

http://bramp.github.io/js-sequence-diagrams/

### TikZ

TikZ and PGF are TeX packages for creating graphics programmatically. TikZ is build on top of PGF and allows you to create sophisticated graphics in a rather intuitive and easy manner. Ref to Official Link (http://www.texample.net/tikz/).

One should add `\usepackage{tikz}` and `\usetikzlibrary{mindmap,trees}` at the front of latex source file to activiate the tikz feature. Using online latex compilers, like [sharelatex] & [overleaf], to create such file easily.

[sharelatex]:https://www.sharelatex.com/ 
`[sharelatex]`:https://www.sharelatex.com/
[overleaf]:https://www.overleaf.com/ 
`[overleaf]`:https://www.overleaf.com/

## Charged Tools

`http://www.lovelycharts.com/` win＋web＋ipad工具，亮点是文字列表转树状结构。可惜费用不清。
