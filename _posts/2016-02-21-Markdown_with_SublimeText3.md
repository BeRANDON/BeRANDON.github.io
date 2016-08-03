---
date: "2016-02-21T13:08:48Z"
draft: false 
title: "2016-02-08-Markdown_with_SublimeText.md"
---

[TOC]

# Sublime Text + Markdown

SublimeText是一款我比较青睐的编辑器，由于扩展多，开源，社区庞大，与python无缝连接等等好处，除了vi，我觉得最应该熟悉的平台就是ST了。（毕竟跨平台）

在其上做markdown的文档编写之后，可以高效转换成html。在ST3以后的版本，都内建有markdown builder。查看了其代码，应该使用了`markdown preview`的插件。所生成的文档可以支持GFM（github flavoured markdown）格式。但是缺陷是不支持table之类的扩展。如果研究一下其生成html格式，可以发现，它是利用css来做渲染的。内容还是转换成html格式。

| Perspect | Markdown Preview | Markdown Html Preview | Markdown GFM Preview |
| --- | --- | --- | --- |
| html | 利用嵌入的css做渲染，markdown内容转换成html标签 | 无渲染，直接转成标签 | 利用script做渲染，markdown内容保持一致，方便于后期的截取，以及更换解释器 |
| support features | GFM，代码高亮，可是连表格都不支持 | 几乎就不支持什么feautres | 同样GFM |

个人觉得，至于其内部的parser如何更换之类的，就是我研究的命题。我需要扩展当前的parser，让其能够支持马克飞象的流程图的功能。

> 其实，可以从多个角度自行度娘。现在可以先从markdown的发展历史开始厘清思路。然后规划下一步发展。

`MarkdownEditing-sublimeText-中文版` http://lucifr.com/2012/07/12/markdownediting-for-sublime-text-2/ 
`MarkdownEditing-sublimeText-英文原版` http://brettterpstra.com/2012/05/17/markdown-editing-for-sublime-text-2-humble-beginnings/ 

## `Markdown Editing` and `Markdown Preview`

安装SublimerText 的Markdown语法解释器
`sublimetext-markdown-preview` https://github.com/revolunet/sublimetext-markdown-preview
`MarkdownEditing` http://ttscoff.github.com/MarkdownEditing/ 

1. Use the `package control` to install the `Markdown Editing` and `Markdown Preview` (**Noticed that you should quit all opened markdown files to reactivate the files.**),

2. shortcut

> Bind the shortcut for markdown preview. The command `markdown_preview` can render the html and open browser, while `markdown_preview_select` can manually select markdown style between `github` and `markdown`.
> `configure:` In `Preference`-->`Key Binding User`, input to set shortcut.   

```
{"keys": ["alt+r"], "command": "markdown_preview", "args": { "target": "browser"} },
{"keys": ["command+e"], "command": "markdown_preview_select" }
```

3. Extension Support

> In `Preferences` -> `Package Settings` -> `Markdown Preview` -> `Setting` - `User` input the following codes:  

```
    {
    /*
        Enable or not mathjax support.
    */
    "enable_mathjax": true,
    /*
        Enable or not highlight.js support for syntax highlighting.
    */
    "enable_highlight": true,
    }
```

`Ref`:
* MarkdownEditing : https://github.com/SublimeText-Markdown/MarkdownEditing
* MarkdownPreview : https://github.com/revolunet/sublimetext-markdown-preview
* Deploy Markdown with sublimetext : http://www.cnblogs.com/IPrograming/p/Sublime-markdown-editor.html
* OmniMarkupPreviewer : http://macplay.leanote.com/post/%E8%BF%91%E4%B9%8E%E5%AE%8C%E7%BE%8E%E7%9A%84-Markdown-%E5%86%99%E4%BD%9C%E4%BD%93%E9%AA%8C-Sublime-Text-3-OmniMarkupPreviewer 


### PyMdown

There is a third party python script named `pymdown`<http://facelessuser.github.io/PyMdown/>
It can support more extension, like `flow chart` and `latex formular`.
However, it is more complicated to configure it for sublimetext3.

可惜到现在为止我都无法配置成功。每次都会报错`TypeError: 'unicode' object is not callable`。不想花时间配置，等作者自行修复；需要弄清楚，因为这个pymdown的扩展非常强大，而且那群发烧友写了一个sublimetext的插件，可以直接调用系统的pymdown命令解析。现如今，可先使用替换的方法来渲染一些高级，但有用的功能。参考`Adanced Usage`。


### LiveReload
To automatically reload the generated pages in web-browser. (Useful for markdown reload.)
> Package control to install `LiveReload` which is only work on st3.
> `Need the administrator to install extension software.`
`It is still waiting for solved.`
One solution is to use command to generate html but not open browser.
Second solutiong is find the alternative codes online.

`Ref`
`LiveReload-sublimetext2` SublimeTeXt的同步器 https://github.com/dz0ny/LiveReload-sublimetext2
`LiveReload-Browser` 浏览器chrome插件 http://feedback.livereload.com/knowledgebase/articles/86242-how-do-i-install-and-use-the-browser-extensions-


## Altertative Method to Realize Advanced Markdown Feature

### Latex Formular

#### MathJax

> `MathJax`(<https://www.mathjax.org/>) is the open-sourced js-based maths formualr render script, which can support MathML, TeX and ASCIImath. The codes can be found in <https://github.com/mathjax/>.

```
//To enable the mathjax.js, just add following codes to your .md file (anywhere), and the markdown_preview command will automatically translate the formular in double "$$...$$" to the latex presentation.
<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML">
</script>
```

```
//Additionally, you can also add following codes (anywhere) to specify the inline latex symbols.
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}});
</script>
```

<script type="text/x-mathjax-config">
  MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}});
</script>
<script type="text/javascript" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML">
</script>

Inline codes are `$a_b = \frac{c}{d}$` as $a_b = \frac{c}{d}$.
The center formualrs can be represented as $$\color{blue}{x} = {\color{green}{-b} \pm \color{orange}{\sqrt{b^2-4ac}} \over \color{red}{2a}}$$.


#### latex.codecogs

> Embed the .jpg formualr file with the <img> tag via the .js script from website <https://latex.codecogs.com>

```html
<img src="https://latex.codecogs.com/gif.latex?a_b=\frac{a}{b}"/>
```

As shown as <img src="https://latex.codecogs.com/gif.latex?a_b=\frac{a}{b}"/>.
However, the pixel is not high-level resoultion.


### chart

#### flowchart.js

The `flowchart.js` depends on Raphaël, which can draw colorful flowchart in SVG format. Ref to <https://adrai.github.io/flowchart.js/>. Add following codes in fornt of flowchart.js usage.

```html
<script src="http://cdnjs.cloudflare.com/ajax/libs/raphael/2.1.0/raphael-min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
<script src="http://flowchart.js.org/flowchart-latest.js"></script>
```

<script src="http://cdnjs.cloudflare.com/ajax/libs/raphael/2.1.0/raphael-min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
<script src="http://flowchart.js.org/flowchart-latest.js"></script>

The Example of flowchart is shown as:

```
<div id="flowchart"><script>
var codes = "st=>start: Start|past:>http://www.google.com[blank]\n\
e=>end: End|future:>http://www.google.com\n\
op1=>operation: My Operation|past\n\
op2=>operation: Stuff|current\n\
sub1=>subroutine: My Subroutine|invalid\n\
cond=>condition: Yes\n\
or No?|approved:>http://www.google.com\n\
c2=>condition: Good idea|rejected\n\
io=>inputoutput: catch something...|future\n\
\n\
st->op1(right)->cond\n\
cond(yes, right)->c2\n\
cond(no)->sub1(left)->op1\n\
c2(yes)->io->e\n\
c2(no)->op2->e "
var chart = flowchart.parse(codes);
chart.drawSVG('flowchart', {
                              'x': 0,
                              'y': 0,
                              'line-width': 3,
                              'line-length': 50,
                              'text-margin': 10,
                              'font-size': 14,
                              'font-color': 'black',
                              'line-color': 'black',
                              'element-color': 'black',
                              'fill': 'white',
                              'yes-text': 'yes',
                              'no-text': 'no',
                              'arrow-end': 'block',
                              'scale': 1,
                              // style symbol types
                              'symbols': {
                                'start': {
                                  'font-color': 'red',
                                  'element-color': 'green',
                                  'fill': 'yellow'
                                },
                                'end':{
                                  'class': 'end-element'
                                }
                              },
                              // even flowstate support ;-)
                              'flowstate' : {
                                'past' : { 'fill' : '#CCCCCC', 'font-size' : 12},
                                'current' : {'fill' : 'yellow', 'font-color' : 'red', 'font-weight' : 'bold'},
                                'future' : { 'fill' : '#FFFF99'},
                                'request' : { 'fill' : 'blue'},
                                'invalid': {'fill' : '#444444'},
                                'approved' : { 'fill' : '#58C4A3', 'font-size' : 12, 'yes-text' : 'APPROVED', 'no-text' : 'n/a' },
                                'rejected' : { 'fill' : '#C45879', 'font-size' : 12, 'yes-text' : 'n/a', 'no-text' : 'REJECTED' }
                              }
                            });
</script></div>
```

<div id="flowchart"><script>
var codes = "st=>start: Start|past:>http://www.google.com[blank]\n\
e=>end: End|future:>http://www.google.com\n\
op1=>operation: My Operation|past\n\
op2=>operation: Stuff|current\n\
sub1=>subroutine: My Subroutine|invalid\n\
cond=>condition: Yes\n\
or No?|approved:>http://www.google.com\n\
c2=>condition: Good idea|rejected\n\
io=>inputoutput: catch something...|future\n\
\n\
st->op1(right)->cond\n\
cond(yes, right)->c2\n\
cond(no)->sub1(left)->op1\n\
c2(yes)->io->e\n\
c2(no)->op2->e "
var chart = flowchart.parse(codes);
chart.drawSVG('flowchart', {
                              'x': 0,
                              'y': 0,
                              'line-width': 3,
                              'line-length': 50,
                              'text-margin': 10,
                              'font-size': 14,
                              'font-color': 'black',
                              'line-color': 'black',
                              'element-color': 'black',
                              'fill': 'white',
                              'yes-text': 'yes',
                              'no-text': 'no',
                              'arrow-end': 'block',
                              'scale': 0.8,
                              // style symbol types
                              'symbols': {
                                'start': {
                                  'font-color': 'red',
                                  'element-color': 'green',
                                  'fill': 'yellow'
                                },
                                'end':{
                                  'class': 'end-element'
                                }
                              },
                              // even flowstate support ;-)
                              'flowstate' : {
                                'past' : { 'fill' : '#CCCCCC', 'font-size' : 12},
                                'current' : {'fill' : 'yellow', 'font-color' : 'red', 'font-weight' : 'bold'},
                                'future' : { 'fill' : '#FFFF99'},
                                'request' : { 'fill' : 'blue'},
                                'invalid': {'fill' : '#444444'},
                                'approved' : { 'fill' : '#58C4A3', 'font-size' : 12, 'yes-text' : 'APPROVED', 'no-text' : 'n/a' },
                                'rejected' : { 'fill' : '#C45879', 'font-size' : 12, 'yes-text' : 'n/a', 'no-text' : 'REJECTED' }
                              }
                            });
</script></div>

#### diagram.js

The `diagram.js` depends on Raphaël and provides SVG format of sequence-chart. Ref to <http://bramp.github.io/js-sequence-diagrams/>.  Add following codes before embed diagram.js html codes.

```
<script src="http://cdnjs.cloudflare.com/ajax/libs/raphael/2.1.0/raphael-min.js"></script>

<script src="http://bramp.github.io/js-sequence-diagrams/js/underscore-min.js"></script>
<script src="http://bramp.github.io/js-sequence-diagrams/js/sequence-diagram-min.js"></script> 
```

<script src="http://cdnjs.cloudflare.com/ajax/libs/raphael/2.1.0/raphael-min.js"></script>

<script src="http://bramp.github.io/js-sequence-diagrams/js/underscore-min.js"></script>
<script src="http://bramp.github.io/js-sequence-diagrams/js/sequence-diagram-min.js"></script> 

Here is the example of digram.js html codes.

```html
<div id="diagram1"></div>
<script>
var diagram = Diagram.parse("\r\n\
Alice->Bob: Hello Bob, how are you? \r\n\
Note right of Bob: Bob thinks \r\n\
Bob-->Alice: I am good thanks!");
  diagram.drawSVG("diagram1", {theme: 'hand'});
</script>
```

<div id="diagram1"></div>
<script>
var diagram = Diagram.parse("\r\n\
Alice->Bob: Hello Bob, how are you? \r\n\
Note right of Bob: Bob thinks \r\n\
Bob-->Alice: I am good thanks!");
  diagram.drawSVG("diagram1", {theme: 'hand'});
</script>

## ToDo

1. Translate the flowchart and sequencechart to base64 format.
2. Install and use `pymdown`
3. Translate local image to base64 format.
4. Support different synatax highlight.
5. List the basic and important features for `latex`, `flowchart` and `sequence chart`
6. Control the size of flowchart or sequence-chart