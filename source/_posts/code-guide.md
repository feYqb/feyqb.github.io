---
title: 如何新建codeReview页面？
date: 2017-08-16 14:01:22
categories:
- codeReview
---

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
如果要新建一篇code-review，需要为文章添加其分类信息`categories: codeReview`
系统会自动为其归档为codeReview类目

```
---
title: 第二篇code review
date: 2017-07-28 19:02:08
tags:
categories:
- codeReview
---

some code review
```

codeReview的文章，请在头部添加categories分类为codeReview，编译时会自动添加到codeReview文章列表

*PS*: 我们会定期部署[codeReview](http://git.yqb.pub/h5/codeReview)库内部的md文档

> 目前categories只有codeReview，react，其他类型统一归类为other。如需新增分类，请联系管理员。
