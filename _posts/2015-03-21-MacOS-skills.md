Mac OS Skills
---

## Skills

### 连续按键

> Mac OS 键盘输入默认是不接受连续输入的，如果长按会跳出字母音标选项。
> 可用命令行，手动设定为连续输入

```
# 开启连续输入
defaults write -g ApplePressAndHoldEnabled -bool false
# 关闭
defaults write -g ApplePressAndHoldEnabled -bool true
# 单独为一个程序（sublime text）开启连续输入
defaults write com.sublimetext.2 ApplePressAndHoldEnabled -bool false

# 以下这个命令没有测试过
#defaults write NSGlobalDomain KeyRepeat -int 0
```

`Ref`:
https://www.v2ex.com/t/148740
http://vicjang.logdown.com/posts/39605-mac-os-x-hold-to-repeat

### 替换应用程序图标

`图形操作流程`
1. 打开应用程序信息列表`⌘＋i`
2. 拖动图标替换左上角的原图标
3. 刷新Dock程序`killall Dock`

### [How to create text shortcuts in OS X Yosemite](http://www.imore.com/how-create-text-shortcuts-os-x-yosemite)

1. 在**`keyboard`-->`text`**，添加相应的Replacement，然后勾选`Correct spelling automatically`即可。

### changing the icon types

http://superuser.com/questions/178316/how-to-set-an-icon-for-a-file-type-on-mac

```
As an example, my system does not yet know about .scala, and I want TextMate to handle it.

First, I Show Package Contents of TextMate.app, navigate to Contents/ and open Info.plist, either with a text editor, or Property List Editor, part of Apple's developer tools.

TextMate uses an unusual format for Info.plist (it's usually binary or XML), an excerpt of which looks like this:

CFBundleDocumentTypes = (
    {   CFBundleTypeName = "ADA source";
        CFBundleTypeExtensions = (adb, ads); 
        CFBundleTypeIconFile = ADA; 
    },
The parent key CFBundleDocumentTypes is what we want. The first child element of it, enclosed in curly braces, contains a file type definition, complete with name (for file type column in Finder), file extensions, and the name of the icon file (ADA for TextMate.app/Contents/Resources/ADA.icns).
```

## command line tools
| name | explain |
| :===: | :===: |
| screenfetch| 在命令行显示系统资讯 |

## Software

### shortcat 键盘代替鼠标

－ autodesk： 没有ps强大，但足够（缺少透明度调试，往后要做测试）

－ controlpad： 其实controlpad可以通过修改其对应的sqlite数据库来做修改，但是既然德国人写了一个工具，就使用他的好了，只是缺陷太多了。

－ pulstate： 点击屏幕出现声波波纹，波纹相撞会自动收缩并发出声音，不错的创意

－ 利用修改…/sounds／中的basso.aiff可以修改默认的NotificationCenter的提示声音，比起不断地设置默认提示音来得要快捷。

afloat - 将mac app窗口置顶 

mac os 平台录音工具：
1.quick time 自带的录音，亲清晰度不错
2.evernote自带录音存储，可是感觉不太清晰
录音机pro，在appstore中可免费下载，可添加标记，语音，并上传icloud。只是这一款个人开发的软件，其前途如何，值得商榷。

serial box 用于搜集mac app的序列号


mac 如何查看gif
暂定资讯接收渠道：

微信：可用于闲散时间阅读的精品公众号（不多于42个），大量的实用商业账号（如排队公众号），部分名人信息私人公布账号（如杨石头每天60秒），以及你的朋友圈

微博：
各类嘈杂信息，做好一定分类即可。
朋友圈（几乎没用，但也暂时保留），技术类，闲散的信息类
名人（大部分名人更偏向于微博发布信息，微信私人信息未必不一样）

RSS订阅：
指向性订阅方式，主要是一个账号，一个渠道快速浏览
 1）大量业界资讯，产品的迭代情况，更新情况
2）单一项目进展
3）某一种技术的深入探讨和宣讲（这个包括个人博客）
4）一些与你类似，或你感兴趣的人的博客跟新
