# PENTA∵DACTYL

> Learining Time - 24 Hours
> Efficiency - Badly
> Complete Situation - 40 Percent

## Models

1. 普通模式
2. 命令行模式
3. command模式
4. visual模式
5. text-edit模式 (类似于vim的修改编辑)

        模式之间很容易进行转换

## 常用命令

1. 导航 包括页内导航以及切换tab
2. 快速打开标签页 ( sS搜索 OT扩展当前URL gP黏贴)

3. 快速操作标签页

        <C-x>\<C-a> URL尾端自动减\加一
        <C-o>\<C-i>\H\L\ [d\ ]d  切换历史

4. 自动导航到本地目录等

        pwd cd ~ gh gH(主页) gu gU(上级)
        rR reload 
        <C-c> stopa[ll]
        g<C-g> print information - :pageinfo
        gf gF 源代码
        zi zm zo zr zz 都是调节大小的
        ]f 转移框架
        :frameonly 只显示
        yY 复制
        :pages[tyle] [stylesheet] 切换样式表
        {n}b g0 g$ g^ gT gt <C-n> gb gB 切换标签页
        tabmove {N}\{+-N}\{match} 快速移动tab
        tabdettach tabattach //窗口分离和合并,合并部分,可以group或者合并到不同的window窗体的某一个index位置
        :tabonly 删除其余tab
        :u[ndoall] 恢复
        :tabdo {cmd} 所有窗体都做某一个命令
        :pintab 将标签固定,之后打开ff也会直接载入
        f {hint} 查找
        ;{mode} {hint} //这个命令非常有价值,例如

        ; to focus a link
        ;?
        ? to show information about the element (incomplete)
        ;s
        s to save its destination
        ;f
        f to focus a frame
        ;F
        F to focus a frame or pseudo-frame
        ;o
        o to open its location in the current tab
        ;t
        t to open its location in a new tab
        ;b
        b to open its location in a new background tab
        ;w
        w to open its destination in a new window
        ;O
        O to generate an :open prompt with hint’s URL
        ;T
        T to generate a :tabopen prompt with hint’s URL (like ;O)
        ;W
        W to generate a :winopen prompt with hint’s URL (like ;T)
        ;a
        a to add a bookmark
        ;S
        S to add a search keyword for the hint’s form
        ;v
        v to view its destination source
        ;V
        V to view its destination source in the external editor
        ;y
        y to yank its destination location
        ;Y
        Y to yank its text description
        ;A
        A to yank its anchor URL
        ;c
        c to open its context menu
        ;i
        i to open an image
        ;I
        I to open an image in a new tab.




5. 映射\命令 以及 各种自定义

        [count]@:  Repeat the last Ex command [count] times.
        q {a-z 0-9} [count]@{a-z0-9} // 定制marco 
        map unmap   //映射
        > 在map中有部分特殊字符为 <Space><lt><Left>, <Right>, <Up>, and <Down> <CapsLock>, <NumLock>, <Insert> <Del>, <Tab>, <PageUp>, <PageDown>, and <Esc> <Return> or <CR> <BS> <F1> through <F12> <K0> through <K9> <Uxxxx>, where xxxx is any 4 hexadecimal digits, represents the character at that Unicode codepoint. For instance, <U263a> represents ☺. 

        例如<A-b>之后command的默认命令就会被优先化 (不确定) 反正这部分的知识只有在有需求的时候,才能被运用

6. I_<C-t> 从Insert模式 进入 Text Edit模式,方便撰写博客之类的

7. mark
        
        A //快速bmark
        M {char/digital} //qmark
        m {a-z} // local marks
        m {A-Z} // URL marks global



# 附录

        各种查看信息:
        :addons
        :dialog
        :emenu

        :command
        :map
        :macros

        :qmarks
        :bmarks
         
        :history
        :jumps
        :buffers

        :set go+=mTB<CR>
        :set go&<CR>


其实还有很大一部分的说明我是用不上,或者说没有开发经验的
这必须从接触相关论坛开始,从实践角度出发来进行研究
如automatic commands等
而且js的部分我也不太理解,更加不用说如何进行组合做marco等了
不过我觉得可以使用这个扩展来对元素进行大量的定制
当然,如果能更新到ff17就更好了
如果再加上firebug和grasymonkey那就无敌了~~