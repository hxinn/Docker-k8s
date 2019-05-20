# docker 基础命令

## 列出镜像
要想列出已经下载下来的镜像，可以使用 `docker image ls` 命令。

```bash
$ docker image ls
REPOSITORY           TAG                 IMAGE ID            CREATED             SIZE
redis                latest              5f515359c7f8        5 days ago          183 MB
nginx                latest              05a60462f8ba        5 days ago          181 MB
mongo                3.2                 fe9198c04d62        5 days ago          342 MB
<none>               <none>              00285df0df87        5 days ago          342 MB
ubuntu               18.04               f753707788c5        4 weeks ago         127 MB
ubuntu               latest              f753707788c5        4 weeks ago         127 MB
```
列表包含了 `仓库名`、`标签`、`镜像ID`、`创建时间` 以及 `所占用的空间`
**镜像ID**是镜像的唯一标识符，一个镜像可以对应多个**标签**因此我们可以看到`ubuntu:18.04`和`ubunutu:latest`拥有相同的ID，因为他们对应的是同一个镜像

## 清理无用镜像

```shell
$ docker image prune
```

# 操作Docker 容器

容器是Docker 又一核心概念。

简单的说，容器是独立运行的一个或一组应用，以及它们的运行态环境。

## 启动容器

启动容器有两种方式，一种是基于镜像新建一个容器并启动，另一个是将在终止状态的容器重新启动

因为Docker的容器实在太轻量级了 很多时候用户都是随时删除和新创建容器

## 新建并启动

启动容器的主要命令为 `docker run`
```bash
Options:
        -t      让docker分配一个伪终端并绑定到容器的标准输入上
        -i      让容器的标准的输入保持打开
        -d      让容器再后台运行
        --name  为容器指定一个别名 之后可通过别名操作
        -p      容器暴露端口与宿主机关联(: 之前的是宿主机端口，之后的是容器暴露的端口)
        -v      指定容器内目录与宿主机目录共享(: 之前的是宿主机文件夹，之后是容器需共享的文件夹)
```
```shell
$ docler run -dit --name doc-nginx -p 8080:80 nginx:latest
```

