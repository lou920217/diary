---
layout: post
title: Jekyll 搭建静态博客，并部署到Github Pages。
category: summaries
tags: [Jekyll, Git]
---
一直想搭建一个博客，来记录自己工作、生活中的点滴。15年的时候，记得当时在学习nodejs，所以就用nodejs + express + mongoose的简单博客管理系统，想在搭建的过程中学习nodejs。然而一直拖拖拉拉，用了半年时间才完成，虽然完成了博客的组建，但是却没了写博客的欲望，唉，还真是没有毅力的家伙。前几天突然就又有了写博客的想法，所以就又来折腾了。。。生命不息，折腾不止。

闲话不说，进入正题：

## [#](#section) <span id="section">目录</span>
1. [Jekyll和Github Pages的介绍](#section1) 
2. [安装Jekyll本地开发环境](#section2)
3. [Jekyll进阶](#section3)
    1. [结构目录](#section3.1)
    2. [配置](#section3.2)
    3. [文件路径](#section3.3)
    4. [分页功能](#section3.4)
4. [必须的知识：Git, Markdown](#section4)
5. [总结](#section5)
6. [补充](#section6)
  
## [#](#section1) <span id="section1">Jekyll和Github Pages的介绍</span>

### [#](#-jekyll) Jekyll

下面是引用[Jekyll](http://jekyll.com.cn/?_blank)的介绍:

> 将纯文本转化为静态网站和博客
>
> 简单 无需数据库、评论功能，不需要不断的更新版本——只用关心你的博客内容。
>
> 静态 只用 [Markdown](http://daringfireball.net/projects/markdown/?_blank) (或 [Textile](http://textile.sitemonks.com/?_blank))、[Liquid](http://wiki.shopify.com/Liquid?_blank)、HTML & CSS 就可以构建可部署的静态网站。
>
> 博客形态 自定义地址、分类、页面、博客内容 以及 自定义的布局设计 都是系统中的一等公民。

Jekyll官网的简介已经很全面了，在此就不在赘述。

### [#](#-github-pages) Github Pages

附上[Github Pages介绍跟快速开始的指南](https://pages.github.com/?_blank)(偷懒是不对的...)

我们可以创建三种不同类型的Github Pages，分别是account，project，organization。本博客用的是project类型的Github Pages，虽说有三种类型，但是创建过程大同小异，这里重点介绍project的创建。

1. 注册Github

    到[Github](https://github.com/?_blank)注册账号。这步就不用介绍了吧...

2. 创建一个新的仓库(repository)

    这步也就不用介绍了吧...(偷懒小能手)，创建时，最好把Initialize this repository with a README这个选项勾选上，这样我们就先不用创建其他文件来填充这个项目了。

3. 设置Github Pages

    进入仓库，选择setting来进行Github Pages的配置，附图一张：

    [![setting]({{ '/assets/images/Jekyll_blog/setting.png' | prepend: site.baseurl | replace: '//', '/' }} '配置Github Pages')]({{ '/assets/images/Jekyll_blog/setting.png?_blank' | prepend: site.baseurl | replace: '//', '/' }})

    然后仓库版本设置为master，再附图一张：

    [![setting]({{ '/assets/images/Jekyll_blog/set_version.png' | prepend: site.baseurl | replace: '//', '/' }} '配置Github Pages')]({{ '/assets/images/Jekyll_blog/set_version.png?_blank' | prepend: site.baseurl | replace: '//', '/' }})

    现在就一切ok，开始下一步骤：安装Jekyll本地服务。

## [#](#section2) <span id="section2">安装Jekyll本地开发环境</span>

1. Jekyll是基于Ruby的开发的，所以要先安装Ruby。[Ruby下载传送门](http://www.ruby-lang.org/en/downloads/?_blank)，Ruby下载成功后，按照安装引导程序一步步的选择，安装成功后，用下面的命令行检测有没有安装成功：

    ```
    ruby -v
    # 成功后会显示: 安装成功的ruby版本等信息
    ```
2. 用gem安装Jekyll

    ```
    gem install jekyll
    ```
3. 新建项目目录，进入目录用以下命令创建站点,并运行启动站点：

    ```
    cd myblog
    jekyll new myblog
    jekyll server
    ```
    jekyll默认服务端口为4000，然后打开浏览器访问127.0.0.1:4000，自动进入默认页面，站点创建成功。

## [#](#section3) <span id="section3">Jekyll进阶</span>

进阶神马的，你们自己看Jekyll文档吧...23333333

## [#](#section4) <span id="section4">必须的知识：Git, Markdown</span>

1. [Git常用命令]({{site.baseurl}}{% post_url /interview/2018-06-22-git_command %})

2. [Markdown基本语法]({{site.baseurl}}{% post_url /interview/2018-06-22-markdown_syntax %})

## [#](#section5) <span id="section5">总结</span>

总结是神马...

## [#](#section6) <span id="section5">补充</span>

#### 2018.06.22  补充：

由于换新电脑了，要重新配置ruby，jekyll，bundle环境了，以为是手到擒来的事情，没想到，还是出了问题...

所以把这些问题补充进来做个备忘笔记。
    
1. ruby的安装问题，忘了第一次安装的是那个安装包了，所以就选了一个体量比较小的不带msys2 devkit的安装包，结果安装完成后，运行命令行 `ridk install` 安装msys2时，却安装不上，结果只能再重新下载了带有devkit的安装包，才安装上msys2（因为用gem安装jekyll必须要安装msys2）。

2. msys2安装好以后，紧接着jekyll也安装成功，自以为大功告成，没想到进入项目文件中用命令行运行却报错

    [![error]({{ '/assets/images/Jekyll_blog/error.png' | prepend: site.baseurl | replace: '//', '/' }} 'jekyll命令报错')]({{ '/assets/images/Jekyll_blog/error.png?_blank' | prepend: site.baseurl | replace: '//', '/' }})

    查了相关资料后发现是没有安装bundle这个ruby的包管理器，于是就 `gem install bundle` 安装bundle，安装完成后还是不行，于是又是一顿狂搜，结果是因为用的是别人的jekyll模板，还有就是Gemfile的jekyll的版本问题，然后运行下面的命令就可解决问题：

    ```
    bundle update
    bundle exec jekyll serve
    ```

    最后在附一个解决方案的地址：[戳这里](http://idratherbewriting.com/documentation-theme-jekyll/#option2)
