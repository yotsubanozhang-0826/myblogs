# 基于Github Pages + docsify搭建个人博客
**用docsify写一个自己的网站**
## 1. 准备工作
### 1.1.准备git环境

   **请先注册git账号:https://github.com/**

   - 1)下载git安装包:https://git-scm.com/downloads
   - 2)安装过程配置全部选择默认配置，点击下一步即可。
   - 3)安装成功后，开始菜单会看到git的三个图标（git bash,git cmd,git cli），表示你安装成功啦

### 1.2.准备node环境

**参考以下链接，亲测有效，非常详细:https://www.cnblogs.com/goldlong/p/8027997.html**

**一点提示:**
- a.安装过程中，选择"Add to PATH",免于后面设置环境变量,可以在cmd中输入echo %PATH% 确认环境变量是否有node
- b.安装结束后，通过node -v查看是否正确安装
- c.公司的网络情况，你需要设置一个代理:) npm config set https-proxy http://192.168.13.190:7777
- d.修改后你可以关注一个配置文件，看是否正确：C:\Users\Administrator\.npmrc

## 2.使用docsify命令生成文档站点
**你也可以参考官网:https://docsify.js.org/#/**

- 2.1.因为我们已经安装了node环境，所以，直接打开cmd窗口执行以下命令：npm i docsify-cli -g
- 2.2.初始化一个项目
 - 1)例如先在E盘建立一个目录:myblogs
 - 2)cmd窗口进入到myblogs
 - 3)执行docsify init ./docs

  **如果收到initialization succeeded！表示初始化成功啦。**

- 2.3.启动项目
 - 1)cmd窗口执行(先进入到你的目录F:myblogs)：docsify serve docs

 **如果收到 listening at http://localhost:3000 表示你启动成功啦。**

 **浏览器输入http://localhost:3000可以访问。**

- 2.4.接下来就是开始布置你的blog了:)

- 2.4.1.你可以配置左侧导航栏:

    在 E:\myblogs\docs目录下新建一个_sidebar.md 的md文件，内容如下：  
        
    这只是一个例子，你可以按照你的排版填充你需要的内容

``` 
- linux运维

  - [docsify](desgin-pattern/github_pages+docsify.md)
  - [工厂模式](desgin-pattern/工厂模式超详解（代码示例）.md)
  - [原型模式](desgin-pattern/设计模式之原型模式.md)
  - [代理模式](desgin-pattern/设计模式之代理模式.md)

- Spring框架

  - [初识spring框架](spring/【10分钟学Spring】：（一）初识Spring框架.md)
  - [依赖注入及示例](spring/【10分钟学Spring】：（二）一文搞懂spring依赖注入（DI）.md)
  - [spring的条件化装配](spring/【10分钟学Spring】：（三）你了解spring的高级装配吗_条件化装配bean.md)

- 数据库
```

只修改了_sidebar.md 文件是不行滴，还需要在index.html文件中配置一下。在内嵌的js脚本中加上下面这句：

    loadSidebar: true
	
ps:markdown的常用语法和效果可以参考以下：https://www.cnblogs.com/wuxin123/p/12809257.html

 - 2.4.2.配置你的封面:

    首先新建一个 _coverpage.md 的md文件，这里面的内容就是你封面的内容。

``` 
# Myblogs


	> yotsubanozhang


	[github](https://github.com/yotsubanozhang-0826/myblogs/)
	[滚动鼠标](#introduction)
```

然后在index.xml文件中修改js脚本配置，添加一句：

coverpage: true

# 3.部署到Github上

- 3.1.登录github的官网，创建一个仓库，起个名字吧，就叫myblogs。
- 3.2.创建本地仓库，推送到github

   首先我们进入我们的本地博客站点目录，也就是 E:\myblogs

   右键Git Bash Here 打开git命令行初始化一个仓库，并提交所有的博客文件到git本地仓库。

   涉及命令如下:
``` 
	git init // 初始化一个仓库
	git add -A // 添加所有文件到暂存区，也就是交给由git管理着
	git commit -m "myblogs first commit" // 提交到git仓库，-m后面是注释
	git remote add origin https://github.com/yotsubanozhang-0826/myblogs.git
	git push -u origin master // 推送到远程myblogs仓库
```

- 3.3.使用Github Pages功能建立站点

   在myblogs仓库下，选中 Settings 选项，

   GitHub Pages的source选择为：master branch / docs folder

   OK，现在你可以通过github page来访问你的站点了：

	 Your site is published at https://yotsubanozhang-0826.github.io/myblogs/