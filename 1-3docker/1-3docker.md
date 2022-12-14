Docker 是一个开源的应用容器引擎，让开发者可以打包他们的应用以及依赖包到一个可移植的[镜像](https://baike.baidu.com/item/%E9%95%9C%E5%83%8F/1574?fromModule=lemma_inlink)中，然后发布到任何流行的 [Linux](https://baike.baidu.com/item/Linux?fromModule=lemma_inlink)或[Windows](https://baike.baidu.com/item/Windows/165458?fromModule=lemma_inlink)操作系统的机器上，也可以实现[虚拟化](https://baike.baidu.com/item/%E8%99%9A%E6%8B%9F%E5%8C%96/547949?fromModule=lemma_inlink)。容器是完全使用[沙箱](https://baike.baidu.com/item/%E6%B2%99%E7%AE%B1/393318?fromModule=lemma_inlink)机制，相互之间不会有任何接口 
每个运行的容器都是可重复的； 包含依赖环境在内的标准，意味着无论你在哪里运行它都会得到相同的行为。
容器将应用程序从底层的主机设施中解耦。 这使得在不同的云或 OS 环境中部署更加容易。

#### 虚拟机与DOCKER架构对比
![image.png](https://cdn.nlark.com/yuque/0/2022/png/32431933/1670852928885-ee463688-4176-476e-93e0-38281cc70815.png#averageHue=%23cfdee2&clientId=u60fd8d4c-11a1-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=239&id=u908ec5a0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=239&originWidth=678&originalType=binary&ratio=1&rotation=0&showTitle=false&size=49201&status=done&style=none&taskId=u70d3bfce-3643-4344-bda6-7bb57e6f623&title=&width=678)
![image.png](https://cdn.nlark.com/yuque/0/2022/png/32431933/1670852968529-2eec3f45-4d64-4243-8aa8-cf5f7d484634.png#averageHue=%23c7dde3&clientId=u60fd8d4c-11a1-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=188&id=ucd80cb62&margin=%5Bobject%20Object%5D&name=image.png&originHeight=241&originWidth=865&originalType=binary&ratio=1&rotation=0&showTitle=false&size=80968&status=done&style=none&taskId=u2cc34b59-1f54-4598-b613-4328415ce7e&title=&width=676)
从应用软件的角度来看，Dockerfile、Docker镜像与Docker容器分别代表三个不同阶段，

- Dockerfile定义镜像的描述文件
- Docker镜像是通过描述文件所产生的是软件的交付品
- Docker容器是镜像的运行态，也是依照镜像运行的实例

Dockerfile面向开发，Docker镜像成为交付标准，Docker容器则涉及部署与运维。
#### 核心概念
##### 镜像、容器、仓库三者之间的联系
![image.png](https://cdn.nlark.com/yuque/0/2022/png/32431933/1670896343383-36025456-789b-4dc1-8bcf-cd4a24fe812c.png#averageHue=%23fdfcfb&clientId=ua4e81159-2b14-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=344&id=u12535a05&margin=%5Bobject%20Object%5D&name=image.png&originHeight=344&originWidth=489&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8000&status=done&style=none&taskId=u1048ddf6-988d-4059-b7c5-618c0379990&title=&width=489)
镜像好比关盘，仓库就是存放CD的盒子，容器就是把CD放到机器里所呈现出来的状态。
#### Docker 架构图
![](https://cdn.nlark.com/yuque/0/2022/png/32431933/1670897912162-79a2ff75-7ee5-4584-aecf-871c3a1043ee.png#averageHue=%23f4f4ed&clientId=ua4e81159-2b14-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=uf737a5a0&margin=%5Bobject%20Object%5D&originHeight=410&originWidth=874&originalType=url&ratio=1&rotation=0&showTitle=false&status=done&style=none&taskId=u36a9369d-9212-4850-8ca2-1b5822c79a1&title=)
#### Docker 客户端
Docker 客户端其中 docker 命令是 Docker 用户与 Docker 服务端交互的主要方式。除了使用 docker 命令的方式，还可以使用直接请求 REST API 的方式与 Docker 服务端交互，甚至还可以使用各种语言的 SDK 与 Docker 服务端交互。目前社区维护着 Go、Java、Python、PHP 等数十种语言的 SDK，足以满足你的日常需求。
#### Docker 服务端
Docker 服务端是 Docker 所有后台服务的统称。其中 dockerd 是一个非常重要的后台管理进程，它负责响应和处理来自 Docker 客户端的请求，然后将客户端的请求转化为 Docker 的具体操作。例如镜像、容器、网络和挂载卷等具体对象的操作和管理。

#### 特性

- **灵活**：复杂的应用程序也可以容器化。
- **轻量级**：容器利用并共享了主机内核，在系统资源方面比虚拟机更加有效。
- **可移植性**：可以在本地构建，部署到云并在任何地方运行。
- **松散耦合**：容器是高度自给自足并封装的容器，使在不破坏其他容器的情况下更换或升级。
- **可扩展**：在数据中心内增加并自动分布容器副本。
- **安全**：容器将积极的约束和隔离应用于流程，而无需用户方面的任何配置。
### Docker 操作
![image.png](https://cdn.nlark.com/yuque/0/2022/png/32431933/1670899539590-8a08b8df-9967-4649-8237-56c516071e53.png#averageHue=%23f9f7f7&clientId=ua4e81159-2b14-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=634&id=udd2b4b1f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=634&originWidth=593&originalType=binary&ratio=1&rotation=0&showTitle=false&size=34086&status=done&style=none&taskId=u1d569b62-aea6-459e-93ec-3d43fc50295&title=&width=593)

上图是一些docker的基础命令，详细内容查看docker -h
```
k8s-master@k8s-master:~$ docker -h
Flag shorthand -h has been deprecated, please use --help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
--config string      Location of client config files (default "/home/k8s-master/.docker")
-c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with "docker context use")
-D, --debug              Enable debug mode
-H, --host list          Daemon socket(s) to connect to
-l, --log-level string   Set the logging level ("debug"|"info"|"warn"|"error"|"fatal") (default "info")
--tls                Use TLS; implied by --tlsverify
--tlscacert string   Trust certs signed only by this CA (default "/home/k8s-master/.docker/ca.pem")
--tlscert string     Path to TLS certificate file (default "/home/k8s-master/.docker/cert.pem")
--tlskey string      Path to TLS key file (default "/home/k8s-master/.docker/key.pem")
--tlsverify          Use TLS and verify the remote
-v, --version            Print version information and quit

Management Commands:
builder     Manage builds
config      Manage Docker configs
container   Manage containers
context     Manage contexts
image       Manage images
manifest    Manage Docker image manifests and manifest lists
network     Manage networks
node        Manage Swarm nodes
plugin      Manage plugins
secret      Manage Docker secrets
service     Manage services
stack       Manage Docker stacks
swarm       Manage Swarm
system      Manage Docker
trust       Manage trust on Docker images
volume      Manage volumes

Commands:
attach      Attach local standard input, output, and error streams to a running container
build       Build an image from a Dockerfile
commit      Create a new image from a container's changes
cp          Copy files/folders between a container and the local filesystem
create      Create a new container
diff        Inspect changes to files or directories on a container's filesystem
events      Get real time events from the server
exec        Run a command in a running container
export      Export a container's filesystem as a tar archive
history     Show the history of an image
images      List images
import      Import the contents from a tarball to create a filesystem image
info        Display system-wide information
inspect     Return low-level information on Docker objects
kill        Kill one or more running containers
load        Load an image from a tar archive or STDIN
login       Log in to a Docker registry
logout      Log out from a Docker registry
logs        Fetch the logs of a container
pause       Pause all processes within one or more containers
port        List port mappings or a specific mapping for the container
ps          List containers
pull        Pull an image or a repository from a registry
push        Push an image or a repository to a registry
rename      Rename a container
restart     Restart one or more containers
rm          Remove one or more containers
rmi         Remove one or more images
run         Run a command in a new container
save        Save one or more images to a tar archive (streamed to STDOUT by default)
search      Search the Docker Hub for images
start       Start one or more stopped containers
stats       Display a live stream of container(s) resource usage statistics
stop        Stop one or more running containers
tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
top         Display the running processes of a container
unpause     Unpause all processes within one or more containers
update      Update configuration of one or more containers
version     Show the Docker version information
wait        Block until one or more containers stop, then print their exit codes

Run 'docker COMMAND --help' for more information on a command.

To get more help with docker, check out our guides at https://docs.docker.com/go/guides/

```

**info        系统信息**
```
k8s-master@k8s-master:~$ docker info
Client:
Context:    default
Debug Mode: false

Server:
Containers: 1
Running: 1
Paused: 0
Stopped: 0
Images: 12
Server Version: 20.10.12
Storage Driver: overlay2
Backing Filesystem: extfs
Supports d_type: true
Native Overlay Diff: true
userxattr: false
Logging Driver: json-file
Cgroup Driver: cgroupfs
Cgroup Version: 1
Plugins:
Volume: local
Network: bridge host ipvlan macvlan null overlay
Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
Swarm: inactive
Runtimes: io.containerd.runc.v2 io.containerd.runtime.v1.linux runc
Default Runtime: runc
Init Binary: docker-init
containerd version:
runc version:
init version:
Security Options:
apparmor
seccomp
Profile: default
Kernel Version: 5.4.0-132-generic
Operating System: Ubuntu 20.04.3 LTS
OSType: linux
Architecture: x86_64
CPUs: 8
Total Memory: 8.294GiB
Name: k8s-master
ID: 3JC2:TLS3:JUZO:OZTM:4QQU:Y4LE:A6NZ:AJ5E:R65S:IBEH:YRV2:IGRZ
Docker Root Dir: /var/lib/docker
Debug Mode: false
Registry: https://index.docker.io/v1/
Labels:
Experimental: false
Insecure Registries:
127.0.0.0/8
Live Restore Enabled: false

WARNING: No swap limit support
```
**version     版本信息**
```
k8s-master@k8s-master:~$ docker version
Client:
 Version:           20.10.12
 API version:       1.41
 Go version:        go1.16.2
 Git commit:        20.10.12-0ubuntu2~20.04.1
 Built:             Wed Apr  6 02:14:38 2022
 OS/Arch:           linux/amd64
 Context:           default
 Experimental:      true

Server:
 Engine:
  Version:          20.10.12
  API version:      1.41 (minimum version 1.12)
  Go version:       go1.16.2
  Git commit:       20.10.12-0ubuntu2~20.04.1
  Built:            Thu Feb 10 15:03:35 2022
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.5.9-0ubuntu1~20.04.5
  GitCommit:
 runc:
  Version:          1.0.1-0ubuntu2~20.04.1
  GitCommit:
 docker-init:
  Version:          0.19.0
  GitCommit:

```
#### search 查找镜像
#### 

#### pull 下载镜像(docker hub)
#### 

#### images 查看本地的镜像
#### 

#### run        运行容器

- -i : 交互模式
- -t： 分配一个终端
- -d： 后台运行
- --name： 指定容器的名称
- -p: 端口绑定
#### ps 查看容器进程（ -a 所有的，正在运行、已经停止的）
#### 

#### tag重命名
#### 

#### rm 删除容器 （-f 强制）
#### 

#### start/restart/stop/ 容器控制
#### 

#### stats 显示容器使用的资源（CPU）
#### 

#### logs 查看容器日志（-f 动态更新）
#### 

#### inspect 显示容器的详细属性信息
#### 

#### kill 关闭容器进程
#### 

#### top 查看容器进程
#### 

#### exec 进入容器执行命令
#### 

#### port 显示容器端口绑定信息
#### 

#### cp 文件复制
#### 

#### diff 容器文件系统发生的变化
#### 

#### export 导出容器文件系统到本地归档
#### 

#### import 导入压缩文件到镜像
#### 

#### history 查看镜像的更新历史
#### 

#### login /logout     Docker registry
#### 

#### commit 将容器变化为镜像
#### 

#### build 构建镜像
#### 

#### save 将镜像制作归档文件
#### 

#### create 创建一个容器
#### 

#### update 更新容器的配置
#### 

#### Dockerfile构建镜像
docker build

- -f 指定dockerfile 
- -t 指定镜像名称
