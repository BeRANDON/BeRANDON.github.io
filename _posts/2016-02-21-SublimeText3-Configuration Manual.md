---
date: "2016-02-21T12:33:00Z"
draft: false 
title: "SublimeText3 Configuration Manual"
---

> One can scan through this configuration manual and choose your necessary function to customsize your own sublime-text steps-by-steps. 
> The one want to configure on one machine and sync all the configurations can ref to package control website https://packagecontrol.io/docs/syncing, while I choose the github to sync them through different machines. Significantlly, one can just sync the folder `Packages/User` through cloud storage services, because the file `Package Control.sublime-settings` records all the installed packages from `Package Control`. Once you sync the `Package/User` and install package control service, then sublime-text will automatically install the packages.
> Moreover, I will save the user-made-plugins in the directory `Packages/User/` & save the user-made-snippets in directory `Packages/User/Snippets/`. For some settings cross different platforms, like windows, linux and OSX, they may be different sometimes. One can add the platform description in the sublime-setting, like `git (Windows).sublime-settings` will contain the `git.exe` path, to activiate them in different platform.

[TOC]

## install package control

> https://packagecontrol.io/installation#st3
```
import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```


## vi model

> To disable it, just add following codes in User.Setting
```
"ignored_packages": [vinage]
```

`Ref`: https://www.sublimetext.com/docs/3/vintage.html


## open containing folder
```
{ "keys": ["shift+command+o"], "command": "open_dir", "args": {"dir": "$file_path", "file": "$file_name"} }
```

`Ref`
http://stackoverflow.com/questions/19410938/sublime-text-open-containing-folder

## Show the command in console.
Just type `sublime.log_input(True)` in sublimetext console to reveal all the commands you uses.

## 'Close other tabs'-command
https://forum.sublimetext.com/t/list-of-all-available-commands-close-others-command/8989


## Select same words together
???

## Minimap Setting

> `Minimap` refers to the instant shortcut of current file on the right side panel.

`Requirements`:  

* Change the minimap color 
* Make minimap always flow
* Show the minimap border 

`Setting`:

```
//Enable minimap color & always shown in file `User/Default.sublime-theme`
    {
        "class": "minimap_control",
        "settings": ["!always_show_minimap_viewport"], 
        "viewport_color": [68, 200, 240, 255],   //Color for minimap panel
        "viewport_opacity": { "target": 0.2, "speed": 20.0, "interpolation": "smoothstep" },
    }
```

```
//Enable minimap border in `User/Preferences.sublime-setting` 
{
    "draw_minimap_border": true
}
```

```
//Set minimap border color in your own `xxx.tmTheme` file.
//If not working, pls delete the theme cache file and restart sublime-text.
    <key>minimapBorder</key>
    <string>#00FF00</string>
```

`Ref`:

- <http://stackoverflow.com/questions/25239473/how-to-change-the-color-of-right-sidebar-minimap-in-sublime>@2015

## Tab Setting

> Noticed that, tabs in st3 have two attributes, dirty & select. `dirty` means modified without saving, while `select` means the current file.

`Requirements`:

- Highlight current selected tab. 
- Highlight the modified tabs (dirty tabs).

```
//Enable highlight for current selected tab in `User/Default.sublime-theme`
[{
        "class": "tab_control", 
        "attributes": ["selected", "file_medium_dark"],
        "tint_modifier":[ 0, 255, 255, 150]
},]
```

```
//Enable highlight_modified_tabs in `User/Preferences.sublime-setting`, which will make the color for modified tab as orange.
{
    "highlight_modified_tabs": true
}
```

However, how to change the orange color for modified_tabs to other color is still unkown. One can find more clues from <http://stackoverflow.com/questions/11294620/sublime-text-2-colour-of-edited-file-tab>@2012, <http://stackoverflow.com/questions/14685989/sublime-to-change-color-of-highlight-modified-tabs>@2013, <https://forum.sublimetext.com/t/hot-to-change-active-tab-title-color/9309/2>@2013.


### User Preference setting

一些内置的页面显示元素的调试，具体参考(http://linux.cn/article-799-1.html)

```
    “line_numbers”: true,    // 是否显示行号
    “gutter”: true,    // 是否显示行号边栏
    “margin”: 4,    // 行号边栏和文字的间距
    “fold_buttons”: true,    // 是否显示代码折叠按钮
    “word_wrap”: false,    // 是否自动换行，如果选auto，需要加双引号
    “wrap_width”: 0,    // 设置窗口内文字区域的宽度
    “auto_match_enabled”: true,    // 自动匹配引号，括号等
    “dictionary”: “Packages/Language – English/en_US.dic”,    // 拼写检查的单词列表路径
    “spell_check”: false,    // 是否打开拼写检查
    “highlight_line”: false,    // 突出显示当前光标所在的行
    “draw_minimap_border”: false,    // 代码地图的可视区域部分是否加上边框
    ["minimapBorder","blue"]//边框的颜色可在配色方案上加入minimapBorder键
```


### Formatting

    cltr + alt + f : 进行代码的formatting(包括jsFormat和codeFormat)

其中可以参考[这篇文章](http://www.ladyloveit.com/sublime/developers-commonly-used-10-sublime-text-plugin/)

当然，这些天最为困扰我的就是如何利用python开发出一个支持任意格式代码format工作的程序。`code format`可以实现相应代码的重新排版. 但唯一的缺陷就是不支持xml. (而xml恰恰是最为宽泛的一个格式语言).
但是,当我深入了解`code format`的python编程时候,发现其复杂程度远远高于我的想象.因此需要在空闲时才能进行深入了解和功能定制.
JsFormat是个不错的方案,但是其功能单一. 
另外,网上有人提出了一些xml的格式化方案,如[xmllint](http://www.bergspot.com/blog/2012/05/formatting-xml-in-sublime-text-2-xmllint/),[tidyxml](https://gist.github.com/coldnebo/1138554).
有一个工具[lxml](http://lxml.de/index.html).似乎可以进行借鉴,用来实现XMLformat的需求.但由于太麻烦,暂时搁置一段时间.

但我最终还是屈服于使用一个比较简单的方案[indentxml](https://github.com/alek-sys/sublimetext_indentxml),[mrkt的笔记](http://kevintsengtw.blogspot.com/2012/05/sublime-text-2-packages-json-xml.html#.UnHMrdIweyd)

### 码农插件

`ctags`,`BracketHighlighter`,`SublimeAlignment`,`Emmet`(即`ZenCoding`),`Sublime CodeIntel`(自动代码补齐),`Sublime Linter`(自动查找错误),`Dayle Rees Color Theme`

### 替代vim,使用sublime-text进行wordpress博客发布

这个的有点在于sublime-text更加现代化,而且操作起来,比vim的分步式操作要优秀. 但缺点就是,登陆password是明文的.

`Ref`
(http://duyizhuo.com/blog/?p=331)

### 设置全屏模式

写作时，我们希望不受干扰，这时我们可以使用全屏模式。点击View -> Enter Distraction Free Mode，或者使用Control + Shift + Command + F(Mac)或是Shift + F11(Windows)。

### 窗口并排

如果你经常需要在一个窗口里同事查看两个或者多个文件的话，譬如翻译的时候，你会需要窗口并排的功能。在View -> Layouts下可以设置一个窗口还是两个窗口，或者多个窗口。但有时候需要在多个窗口中同时打开一个文件，Origami可以帮到你，它可以随心所欲的打开窗口，还能创建窗口，克隆窗口，销毁窗口。

### 设置编码

写作文档，最怕的是在不同环境下出现乱码。我编写的文档都使用UTF–8编码。要在Sublime Text 2中将默认的编码设为UTF-8很简单。在Preferences -> Settings - User中加入：    "default_encoding": "UTF-8"
另外推荐一款关于编码的插件：EncodingHelper：它可以猜测文档的编码（不过有可能不准确），提供将任何编码UTF-8的功能。可以设置打开文档自动转换成UTF-8或是从猜测的编码转换成UTF-8。这对中文写作很有用。这个插件并不完善，只能从菜单栏查看，而不能从命令面板调出功能。

### Shortcuts 

[ST(windows) 快捷键]\(http://zhifangzi.com/sublime_text_shortcut.html)

## To-do

1. Sync sublime-text setting
2. Sinppet to insert current date
3. Markdown jump tag