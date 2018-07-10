---
title: hexo搭建个人博客
---
Welcome to [CVICSE](http://www.cvicse.com/)! 

## Quick Start
本文内容只做一个简单的入门，深入的学习，需要自己去学习研究。(本文内容是结合网上教程和实际操作编写)
参考：[https://www.cnblogs.com/visugar/p/6821777.html](https://www.cnblogs.com/visugar/p/6821777.html) 
<br>基本流程：
### 安装Git Bash
我一直不太喜欢在cmd中操作各种命令，所以挑了这个比较好使的Git Bash, 我的是windows环境，所以下载windows版本并安装就可以了。
<br>•下载地址
<br>•安装步骤：双击下载好的exe文件，一路next就好
<br>•安装好后，打开gitbash，查看版本

``` bash $ git version " ```

### 安装NodeJs

Hexo是基于nodeJS环境的静态博客，里面的npm工具很有用啊，所以还是老老实实把这玩意儿装了吧（安装时，建立自己的安装目录）
<br>•下载地址(说明：LTS为长期支持版，Current为当前最新版)
<br>•安装步骤：反正下载好msi文件后，双击打开安装，也是一路next，不过在Custom Setup这一步记得选 Add to PATH ,这样你就不用自己去配置电脑上环境变量了（默认的应该是添加的，留心注意），装完在按 win + r 快捷键调出运行，然后输入cmd确定，在cmd中输入path可以看到你的node是否配置在里面（环境变量），没有的话你就自由发挥吧。

### 安装hexo
看到这么多安装，别怕，因为后面的东西都是在gitbash中用npm工具安装就好了。
(NPM: npm 是 JavaScript 世界的包管理工具,并且是 Node.js 平台的默认包管理工具。通过 npm 可以安装、共享、分发代码,管理项目依赖关系。)
<br>•先创建一个文件夹（用来存放所有blog的东西），然后cd到该文件夹下，在该目录下鼠标(shift)右键
<br>•安装hexo命令：npm i -g hexo
<br>•安装完成后，查看版本
<br>
``` bash $ hexo -v ```
<br>•初始化命令：hexo init 。(在自己定义的工作目录下执行此命令)初始化可能会报错，下图情况是要在空的目录中进行初始化。

### 生成SSH并添加到github
没账号的创建账号，有账号的看下面，登录账号后在系统首页面或者配置管理中都能找到新建配置库按钮。
<br>1.创建一个New repository，名称为cvicse-work, 其中cvicse-work是你的github名称。
<br>2.回到gitbash中，配置github账户信息（YourName和YourEail都替换成你自己的）。
<br>3.创建SSH，在gitbash中输入：ssh-keygen -t rsa -C "youremail@example.com，生成ssh然后按下图的方式找到 id<u> </u>rsa.pub 文件的内容。
<br>4.将上面获取的ssh放到github中，添加一个 New SSH key ，title随便取，key就填刚刚那一段。
<br>5. 在gitbash中验证是否添加成功：ssh -T git@github.com
<br>6.用编辑器打开你的blog项目，修改_config.yml文件的一些配置(冒号之后都是有一个半角空格的)。
``` deploy:  ```
<br>``` type: git  ```
<br>``` repo: https://github.com/foate/cvicse-work.git  ```
<br>``` branch: master ```
<br>7.回到gitbash中，进入你的blog目录，分别执行以下命令
<br>```  bash $ hexo clean ```
<br>```  bash $ hexo generate ```
<br>```  bash $ hexo server ```
<br> (注：hexo 3.0版本把服务器独立成个别模块，需要单独安装：npm i hexo-server。)
<br> <u> 打开浏览器输入：http://localhost:4000 </u>