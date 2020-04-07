---
layout: article
title: 部署YouComic
mathjax: true
author: allentom
pageview : true
mermaid: true
show_subscribe	: true
---

YouComic最早的开发计划是部署在文件服务器上（即网络附加存储NAS）上，但是随着需求的不断扩张，部署方式日渐灵活。用户可以选择不同的方式来部署YouComic服务，从简单的一体化套件和分布式部署方案都能满足。

在部署上，每一个服务都提供了完整的安装引导，全部配置都在引导页面完成，不需要用户去修改复杂的配置文件。大部分的设置选项只需要保持默认即可，不需要用户进行麻烦的配置。
![](/assets/images/posts/2/init_page.png)
## Docker ![](https://img.icons8.com/color/48/000000/docker.png)
Docker 是最佳的部署方案，只要能运行Docker的地方都可以部署；不仅仅是Linux、Windows等操作系统，还可以在群晖(Synology)、Freenas、unRaid等NAS系统中进行部署。

部署的节点清单

|-|-|-|
|1|数据库|部署数据库的节点（如果选用Sqlite作为数据库则不需要)|
|2|YouComic Server|核心服务节点|
|3|YouComic Supervisor|管理界面节点(管理页面不一定需要部署在服务端，也可以在客户端启动Standalone Edition)|
|4|YouComic Web|内容浏览器(同上，也包含Standalone Edition)|

最少需要部署一个节点，其他的功能可以根据自身需要开启。

## 单机

Standalone版本可以直接部署在Windows、Linux、macOS多平台。只需要下载或编译目标平台的文件，运行后即可
套件地址:

- [YouComic Supervisor Standalone Edition](https://github.com/Project-XPolaris/YouComic-Supervisor-Standalone)
- [YouComic Web Standalone Edition](https://github.com/Project-XPolaris/YouComic-Explore)


## YouComic Server
选择相应的版本下载

[下载地址](https://github.com/Project-XPolaris/YouComic-Server/releases)

### Docker
docker可以使用`Dockerfile`或者docker-compose的方式来部署，在部署时请映射安装端口`8880`

使用`docker compose up`命令部署。

### 独立部署

运行文件夹内的`main`文件即可。访问浏览器[安装地址](http://localhost:8880)

### 配置

第一次启动程序会进入安装引导页面，大部分的配置内容都具有默认选项。

#### 选择数据库

![](/assets/images/posts/2/server_install_select_database.png)

数据库有两种选择，Sqlite和Mysql。未来将会支持更多的数据库。

1.Mysql

MySQL需要在启动MySQL的数据库基础上进行配置，在存取效率、功能、安全性上更加优秀。

2.Sqlite

轻量的文件数据库，不需要过多的配置，适合轻量用户。


#### 配置SQLite
![](/assets/images/posts/2/server_install_sqlite.png)

配置Sqlite文件的位置，可以使用相对路径（根目录为main所在的目录）和绝对路径。

#### 配置MySQL
![](/assets/images/posts/2/server_install_mysql.png)

配置MySQL的相关选项。MySQL数据库(Sechma)不需要提前创建（Create database），服务会自动创建数据库。

#### 配置存储地址

![](/assets/images/posts/2/server_install_store.png)

需要配置两个储存地址，一是程序运行额外的数据地址，另一个是书籍存放地址，两者都可以使用相对路径和绝对路径。

书籍存储地址请选择空间较大的路径。

#### 配置账户

![](/assets/images/posts/2/server_install_user.png)

配置账户的用户名和密码。

#### 配置应用

![](/assets/images/posts/2/server_install_app.png)

应用默认监听8880端口。

#### 完成
完成配置之后需要手动启动应用程序，等待启动完成后就可以运行。

