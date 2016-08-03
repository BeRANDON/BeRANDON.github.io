2016-01-27-How-to-Build-Up-Your-Blog-with-Github-and-Hexo-or-Jekyll
---

## Quick Deploy Guide

如何搭建一个独立博客——简明Github Pages与Hexo教程 [http://www.jianshu.com/p/05289a4bc8b2]() 

>
`Quick Remind` install hexo => configure => deploy  
Refer websites:  
[http://www.jianshu.com/p/05289a4bc8b2]()  

1. `Install Hexo Official Manual`[https://hexo.io/docs/]()  
```bash
npm install hexo-cli -g    
```

2. Initial hexo blog and Test on local machine  
```bash
hexo init blog  
cd blog  
npm install  
hexo server
```

3. Configure 
4. Generate & Deploy
``` bash
hexo g
hexo d
```

## Theme

主题我喜欢简洁实用的  
1. [http://notes.iissnan.com/]()  
2. very-simple [https://github.com/lotabout/very-simple]()  
3. Tranquilpeak [https://github.com/LouisBarranqueiro/hexo-theme-tranquilpeak]()

## 安装Hexo可能遇到的问题

1. `@2016Jan`Hexo-3.0为什么运行hexo deploy没有反应 

```
#_config.yaml 配置文件最后几行
deploy:
  type: git
  repo: git@github.com:`username`/`gitRepo`  
  branch: gh-pages 
```
>   
1. 配置文件为yaml格式，需要在冒号后使用tab或空格来进行缩进，否则会出现问题
2. type改为git，之前hexo-2.x版本是github
3. branch改为master，github pages已经允许在master分支上部署代码了，如果写成gh-pages会出现问题

2. Hexo-3.x版本中，git deploy函数过时，需要手动添加支持。[https://github.com/hexojs/hexo/issues/1013]()
 
 ```
 $ cd hexo目录
 $ npm install hexo-deployer-git —save
```


### SSH密钥设置问题

https://help.github.com/categories/ssh/

```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"  
$ cat ~/.ssh/id_rsa.pub > pbcopy
$ #paste the id_rsa.pub to your github account SSH management
$ ssh-add ~/.ssh/id_rsa #添加ssh代理
$ ssh -T git@github.com #测试链接是否成功
```
只要出现以下代码，就表示成功。

```
$ Hi username! You've successfully authenticated, but GitHub does not
provide shell access.
```

### 多github账户连接

[http://stackoverflow.com/questions/3225862/multiple-github-accounts-ssh-config]()

`core核心思想`:就是在`~/.ssh`目录下创建不同的rsa公私钥对，并且把它们都登记到`~/.ssh/config`文件中；然后对应本地不同的git仓库，依据config文件中设置的公私钥别名，设置对应的远程仓库连接。

```  
 # ~/.ssh/config 配置  
Host Name1  
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa

Host Name2
    HostName github.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/id_rsa_work
```

一定要添加这些私钥到可信任列表中；然后才能成功做链接测试。  

```  
$ ssh-add ~/.ssh/id_rsa  
$ ssh-add ~/.ssh/id_rsa_work  
$ ssh -T git@github.com  
$ ssh -T git@work.github.com  
```

## jekyll部署

把别人的jekyll或jekyll bootstrap的库下载到本地，修改远程仓库地址为你自己的地址之后，就能直接上传部署到自己的仓库中。[https://help.github.com/articles/changing-a-remote-s-url/]()或[http://huangziwei.com/tech/blogging-with-git-github-and-jekyll/]()

```
$ git clone https://github.com/plusjade/jekyll-bootstrap.git
$ cd jekyll-bootstrap
$ git remote set-url origin git@github.com:UserName/UserRepo.git
```

**! [rejected] master -> master (fetch first)**
> 起因是服务器的版本更新，而本地在没有pull的情况下就push。因此要不就先将文档pull下来，合并后再上传，要不就直接`git push origin master --force`强制上传

### jekyllbootstrap Disqus 设置

在Disqus的介绍文档[https://disqus.com/admin/universalcode/]()中说，可以通过粘贴html代码或者在主题配置的形式在jekyll boostrap中支持讨论代码。

[http://www.zxbing0066.com/Blog/jekyll/2014/11/12/disqus.html]()
[http://write.liyishan.me/words/2015/01/25/duoshuo-plugin/]()


### jekyllbootstrap 主题安装

由于主题安装各自所需的依赖文件不一致，通过以下链接
[http://jekyllbootstrap.com/usage/jekyll-theming.html]()查找所对应主题的主页，一般都会有安装步骤介绍。

其中推荐的简洁主题为:  

```
$ rake theme:install git="https://github.com/jekyllbootstrap/theme-the-program.git"
```