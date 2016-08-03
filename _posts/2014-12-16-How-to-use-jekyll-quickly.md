---
layout: post
title:  "Quick guide to Jekyll!"
date:   2014-12-16 10:57:02
categories: jekyll update
---

在这里，我们使用最简单的步骤来说明如何在github上进行部署jekyll的博客系统。
适用于那些浮躁而没有时间仔细看内容的匆匆过客，更加详细的内容，应该参考jekyll官网或阮一峰的中文博客。由于技术不断在发展，快捷消费往往是最高效的。

> 在此，我假设你已经（1）了解了git的基础命令（2）明白如何链接本地和github（3）知道jekyll其实是一个博客系统，类似于wordpress，但更加简化，更专注于写作（如markdown）

*搭建步骤为：*

1. 在github上建立仓库
2. 开通仓库的gh-pages分支（可用xxx.github.io/**进行访问）xxx是你的github用户名，**为你仓库名
3. git clone仓库到本地
3. 在本地安装jekyll（基于ruby，先安装ruby，再用rubyGem安装jekyll）
4. 在本里使用jekyll new blogname（blogname为文件夹名字）
5. 然后将这部分文件将拷贝到仓库目录下，然后git push更新github上的代码即可
