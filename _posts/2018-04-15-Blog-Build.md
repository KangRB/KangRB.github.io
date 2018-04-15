---
title: "使用Jekyll和GitHub搭建个人博客"
categories:
  - Experience
  - technology
  - 中文
tags:
  - GitHub Pages
  - jekyll
---

#### 写在前面的话
搭建这个小博客的目的一是为了记录自己学习全栈开发的过程和遇到的问题，二是为了将无意看到的比较好的文章收录下来，方便以后能很快的找到并查看。

# 使用的技术
1. [GitHub Pages](https://pages.github.com/) 是可以将静态网页托管在GitHub上的技术。用户可以使用GitHub Pages提供的或者一些开源主题来显示自己的GitHub Pages主页，当然也可以自己设计。
  + 可以将自己的静态html文件托管在GitHub上，在这个Repository的网址前加上```http://htmlpreview.github.io/?```便可在线查看页面。eg.[点我查看dome](http://htmlpreview.github.io/?https://github.com/KangRB/2017.12-ke-cheng-shi-ji/blob/master/index.html)
2. [Jekyll](https://www.jekyll.com.cn/) 将纯文本转化为静态网站和博客。
3. [So Simple Theme](https://github.com/mmistakes/so-simple-theme) 一个简单的Jekyll主题，可以为自己的文章和图片文章提供清晰的排版，响应式布局，完美适配了移动端。

# 过程
1. 首先在电脑上安装Windows上运行的Jekyll [这里是官方教程](http://jekyll-windows.juthilo.com/1-ruby-and-devkit/)
2. 克隆主题
> 有3个安装主题的方法
  + 如果正在运行Jekyll v3.5 + 自行托管，则可以快速将主题安装为Ruby gem。
    1. 将以下代码添加到自己的jekyll网站Gemfile
    ```markdown
    ruby gem "jekyll-theme-so-simple"
    ```
    2. 将以下代码添加到自己的jekyll网站的_config.yml文件中
    ```markdown
    yaml theme: jekyll-theme-so-simple
    ```
    3. 然后运行Bundler来安装 theme gem 和依赖关系
    ```markdown
    terminal bundle install
    ```

  + 可以安装为远程主题
    >GitHub Pages增加了对任何GitHub托管主题的全面支持。
    1. 替换```gem "jekyll"```为：
    ```markdown
    ruby gem "github-pages", group: :jekyll_plugins
    ```
    2. 运行```bundle update```并验证所有gem安装正确
    3. 添加```remote_theme: "mmistakes/so-simple-theme"```到_config.yml文件并删除任何其他```theme:```或```remote_theme: ```条目

  + 直接将所有主题文件复制到项目中
    可以删除不必要的文件和文件夹：
    + .github
    + docs
    + example
    + .editorconfig
    + .gitattributes
    + banner.js
    + CHANGELOG.md
    + Gemfile
    + jekyll-theme-so-simple.gemspec
    + package.json
    + Rakefile
    + README.md
    + README-OLD.md
    + screenshot.png

  #### 我用的第三种方法，直接复制粘贴
  直接复制粘贴后需要在根目录下添加index.html文件，这里就可以使用```/example/index.html```example目录中的index.html文件，并且如果需要其他如post、categories、tags、search等页面，就直接把example目录中对应的md文件复制进项目根目录中。其他修改项就根据README.md提供的教程自定义修改、添加自己想要的功能
3. 将项目托管于GitHub
  + 申请github账号
  + 创建名称为USERNAME.github.io(USERNAME为自己的用户名)的仓库
  + 用[GitHub桌面版](https://desktop.github.com/)Push到新建的仓库中

4. 将写好的md格式的文章存储在根目录下的_post文件夹中
  + 文件名格式：yyyy-mm-dd-标题
  + 文件内容头：
    ```
    ---
    title: 标题
    categories:
      - 分类

    tags:
      - 标签1
      - 标签2
    ---
    ```

# 心得
经过一个周末的倒腾，试了很多主题，最后选择了这个界面简洁明了的开源主题。在安装本地Jekyll环境，和迁移这个主题的过程中遇到了很多困难。因为刚开始看到那么长篇幅的英文说明文档，就有点不耐烦了，主要原因还是对整个主题的结构不熟悉，而且还不太明白Jekyll到底是怎么工作的，因为这和普通的html+css构建的网站大不相同。**但是** 因为这个主题深深吸引了我，非常喜欢这种风格，因此沉住气仔细阅读了READEME说明，在仔细了解主题整体结构，踩过很多坑后，终于成功将网页搭建起来。
## END
这个Jekyll主题有很多可选功能，类似基于Disqus的评论功能，还有在文章中加入目录的插件。在此感谢此主题的维护者们。
