## 基本操作规范

网站访问域名：https://feyqb.github.io/
Github地址：https://github.com/feYqb

我们需要共同维护一个repo：**feyqb.github.io**

## 需要的工具和知识库：

- 翻墙
- 注册Github账号 
- Node.js环境
- Git
- **本地搭建Hexo静态博客**
- **Markdown语法**

## 本地搭建静态博客

如何搭建属于自己的静态博客：

https://xuanwo.org/2015/03/26/hexo-intor/

**我们要做的：**

从github仓库中clone源码
仓库名：feYqb/feyqbRepo
仓库地址：https://github.com/feYqb/feyqbRepo
本地项目目录下执行命令：

- npm install hexo--cli-g
- npm install hexo --save
- hexo -v
- hexo init
- hexo g
- hexo d
- hexo s

完成本地初始化博客
本地访问：localhost:4000

##项目目录介绍

- scaffolds
- **source** 源文件存储目录
 + _posts
     * nodejs-2017-03-21-schedule.md
     * reactjs-2017-03-28-redux.md
     * 公告-2017-03-26-background.md
 + img
- themes
- .gitignore
- .npmignore
- _config
- package.json

## 仓库介绍
 - feyqbRepo：博客源码
  + master
  + group ：共同维护的分支,每个人拥有write权限
 - feyqb.github.io：项目部署目录
 
## 文章撰写规范

 新建文章：

```
hexo new name
```

所有文章以md形式保存在Hexo目录下的source/_post文件夹中。
或者可以直接在该目录下新建md类型的文档，就能在执行hexo g的时候别渲染。新建的文章需要添加一些yml信息，如下：

```
---
title: reactjs-2017-03-28-redux		//标题
date: 2017-03-21 19:11:05  //编辑这篇文章的时间
tags:				//文章tag
- react框架
- RN技术
- node技术
---
```

### 标题规范

**所属线-xx-xx-xx-name**

	nodejs-2017-03-21-schedule.md
### 参考文档
markdown语法：http://www.jianshu.com/p/q81RER
Git使用指南：
http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000


