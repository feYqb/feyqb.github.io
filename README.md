# 基本操作规范
## 域名及仓库介绍

网站访问域名：https://feyqb.github.io/
Github地址：https://github.com/feYqb

我们需要共同维护的repo：
**feyqb.github.io**
**feyqbRepo**

## 需要的工具和知识库：

- 翻墙
- 注册Github账号 
- Node.js环境 (版本不能太旧)
- Git
- **本地搭建Hexo静态博客**
- **Markdown语法**

## 本地搭建静态博客

如何搭建属于自己的静态博客：
官方文档：https://hexo.io/

实例教程：https://xuanwo.org/2015/03/26/hexo-intor/

**我们要做的：**

从github仓库中clone源码
- 仓库名：feYqb/feyqbRepo
- 仓库地址：https://github.com/feYqb/feyqbRepo
	
本地项目目录下执行命令：

-  npm install -g hexo-cli
- npm install hexo --save
- hexo -v
- npm install
- hexo g
- hexo s

npm install将会自动安装你需要的组件
完成本地初始化博客
本地访问：localhost:4000

更换端口或是在执行时遇到了 EADDRINUSE 错误，执行命令
$ hexo server -p 5000


##项目目录介绍
###feyqbRepo

- scaffolds
- **source** 源文件存储目录
 + _posts
     * schedule.md
     * redux.md
     * background.md
 + img
- themes
- public
- .gitignore
- _config
- package.json
### feyqb.github.io
部署成功后的public目录

## 仓库介绍
 - feyqbRepo：博客源码
  + master
  + group ：共同维护的分支,每个人拥有write权限
 - feyqb.github.io：项目部署目录
 
## 文章撰写规范

###  新建文章：

```
hexo new name

```

所有文章默认以md形式保存在Hexo目录下的source/_post文件夹中。
或者可以直接在该目录下新建md类型的文档，就能在执行hexo g的时候渲染。新建的文章需要添加一些yml信息，如下：

```
---
title:Redux		//标题
date: 2017-03-21 19:11:05  //编辑这篇文章的时间
tags:				//文章tag
- React框架
- RN技术
- Node技术
---
```
###  新建codeReview:（为文章添加分类）

```
---
title: 第二篇code review
date: 2017-07-28 19:02:08
tags:
categories:
- codeReview
---

# code2

```
###  新建页面：

```
hexo new page codeReview

```
打开codeReview目录下的index.md编辑
添加：```layout: page-codeReview```
再在主题配置_config文件menu中添加： ```codeReview: /codeReview```

**慎用 hexo d **
hexo deployed部署本地博客到github的命令

## 标题规范

**所属线-xx-xx-xx-name**

	nodejs-2017-03-21-schedule.md
因此文章在编写时一定要严格添加分类(categories)和标签(tags)	
**categories:**
 - nodejs
 - reactjs
 - codeReview
 
 
**tags:**
 - RN技术
 - react框架
## 提交规范
node_modules
public
db.json 文件不需要提交
因此注意.gitignore文件存在的必要性

## 参考文档
markdown语法：http://www.jianshu.com/p/q81RER

Git使用指南：
http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

hexo官方文档：https://hexo.io/zh-cn/docs/


