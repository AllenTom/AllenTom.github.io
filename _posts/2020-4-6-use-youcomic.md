---
layout: article
title: 使用YouComic来管理你的漫画
mathjax: true
author: allentom
cover: /assets/images/posts/1/web_pv_1.png
pageview : true
mermaid: true
show_subscribe	: true
---

<style>
.headerWrap {
    width:100%;
    height:120px;
    overflow: hidden
}
.headImage {
    
}
</style>
<div class="headerWrap">
<img class="headImage" src="/assets/images/posts/1/web_pv_1.png"/>
</div>


随着收藏的内容越来越多，普通的文件夹的传统方式已经不能满足需要了。这是需要一个新的管理系统，搜索了一下，找了一圈也没有找到合适的，于是YouComic的想法诞生了。YouComic 专注的的是对于内容的整理和浏览，最终目的是漫画资源整理井井有条。目前YouComic项目以开源的方式托管在Github上，是Project Polaris的一员。



## 都有啥？

YouComic 目前是一个成长中的计划。初期版本由[@AllenTom](https://github.com/AllenTom)完成基础工作，并在自己的NAS服务器上成功运行。基本内容完成后便上传至GitHub。

YouComic 包含四个套件。

### YouComic Server
这是最核心的组件，提供管理功能的API接口，一般是运行在服务端。


### YouComic Web
Web 端是提供浏览用户自己的资源库存的应用，你可以把网页部署在服务器端，供本地端浏览；同时也可以使用Standalone版本，独立运行与桌面端。

桌面端
<img  src="/assets/images/posts/1/web_pv_1.png"/>

移动设备适配

![](/assets/images/posts/1/web_pv_2.png)

### YouComic Supervisor
该套件提供了管理功能的用户GUI，主要的功能是管理书籍，编辑书籍的内容。修改书籍信息，上标签等整理操作。

![](/assets/images/posts/1/supervisor_pv_1.png)

### YouComic Studio
主要功能为编辑和上传。支持批处理资源或者编辑单个资源，添加书籍信息、编辑书页等功能。
- 编辑
![](/assets/images/posts/1/studio_pv_1.png)

- 扫描批处理
![](/assets/images/posts/1/studio_pv_2.png)