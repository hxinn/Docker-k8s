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

