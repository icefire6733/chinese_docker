CRUX Linux
===

在CRUX Linux可以通过由 [James Mills](http://prologic.shortcircuit.net.au/) 提供的 ports，或者官方的 [contrib](http://crux.nu/portdb/?a=repo&q=contrib) ports.

- docker
- docker-bin

`docker` port 将安装最新版本的 Docker，`docker-bin` port 将从二进制文件安装最新版本的 Docker。

###安装

如果你的版本允许，更新你的 ports 目录树并且安装docker(用root用户)：

	# prt-get depinst docker

如果你想节省你的编译时间，你可以安装`docker-bin`

###内核要求

如果使 CRUX + Docker 主机正常工作，你必须确保你的内核安装必要的模块来保证LXC容器所需要的函数和docker进程的正常运行。

请阅读`README`：

	$ prt-get readme docker

`docker` 和 `docker-bin` ports 安装由 Docker 发行版提供的 contrib/check-config.sh 脚本，以供检查你的内核配置是否适合 Docker 主机。

	$ /usr/share/docker/check-config.sh

###启动docker

我们提供一个 rc 脚本来创建 Docker.请使用下列命令来启动 Docker 服务(root用户):

	# /etc/rc.d/docker start

设置开机启动

- 编辑 `/etc/rc.conf`
- 将 `docker` 放到 `SERVICES=(...)` 数组 `net` 之后.

###支持

寻求更多技术支持，请查看 [CRUX 邮件列表](http://crux.nu/Main/MailingLists) 或加入在 [FreeNode](http://freenode.net/) 网络上的 [IRC Channels](http://crux.nu/Main/IrcChannels).
