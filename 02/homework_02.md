## 一、判断题

1. Java 是编译型语言。(正确)
2. Javascript 中，不区分大小写字母，也就是说 A 和 a 是同一个变量。(错误)
3. Javascript 中的常量包括 String、Number、Boolean、Null、Undefined。(错误)
4. String 字符串的语法中既可以使用单引号，也可以使用双引号。(正确)
5. typeof 是用来判断变量类型，不可以当作运算符使用。(错误)
6. 任何值和 undefined 运算，undefined 可看做 0 运算。(错误)

## 二、请分别描述下列代码中“+”的作用。

1. console.log(“年龄:” + 20);---字符串连接符
2. console.log(11+22+33);---算术加法运算符
3. console.log(“网络 + 安全”);---普通字符
4. var a = 1;
   var b = 2;
   console.log(“a” + b);---字符串连接符
5. var a = 1;
   var b = 2;
   console.log(“a + b”);---普通字符

## 三、计算下述代码的打印值

var a = 10;
var b = 10;

- console.log(a++);---(10)
- console.log(++a);---(12)
- console.log(–b);---(-10)
- console.log(b–);---(10)

## 四、分别使用行内式、内嵌式、引入外部文件的方法造成网页弹窗，要求触发弹窗的 JavaScript 命令不止一种（alert、print、prompt）。

### 1.行内式

```html
<button onclick="alert('这是一个alert弹窗')">点击我展示alert弹窗</button>
<button onclick="prompt('这是一个prompt弹窗', '默认值')">点击我展示prompt弹窗</button>
<button onclick="print()">点击我展示print窗口</button>
```

### 2.内嵌式

```html
<script>
function showAlert() {
    alert('这是一个alert弹窗');
}

function showPrompt() {
    prompt('这是一个prompt弹窗', '默认值');
}

function showPrint() {
    print();
}
</script>

<button onclick="showAlert()">点击我展示alert弹窗</button>
<button onclick="showPrompt()">点击我展示prompt弹窗</button>
<button onclick="showPrint()">点击我展示print窗口</button>
```

### 3.引入外部文件

```javascript
// scripts.js
function showAlert() {
    alert('这是一个alert弹窗');
}

function showPrompt() {
    prompt('这是一个prompt弹窗', '默认值');
}

function showPrint() {
    print();
}

```

```html
<script src="scripts.js"></script>

<button onclick="showAlert()">点击我展示alert弹窗</button>
<button onclick="showPrompt()">点击我展示prompt弹窗</button>
<button onclick="showPrint()">点击我展示print窗口</button>
```

## 五、安装 Docker 并练习以下基础命令、帮助命令、镜像命令和容器命令:

### 帮助命令

#### docker 命令 --help

```shell
[root@localhost ~]# docker --help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Common Commands:
  run         Create and run a new container from an image
  exec        Execute a command in a running container
  ps          List containers
  build       Build an image from a Dockerfile
  pull        Download an image from a registry
  push        Upload an image to a registry
  images      List images
  login       Log in to a registry
  logout      Log out from a registry
  search      Search Docker Hub for images
  version     Show the Docker version information
  info        Display system-wide information

Management Commands:
  builder     Manage builds
  buildx*     Docker Buildx (Docker Inc., v0.11.2)
  compose*    Docker Compose (Docker Inc., v2.20.2)
  container   Manage containers
  context     Manage contexts
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  plugin      Manage plugins
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Swarm Commands:
  swarm       Manage Swarm

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes

Global Options:
      --config string      Location of client config files (default "/root/.docker")
  -c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with
                           "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket to connect to
  -l, --log-level string   Set the logging level ("debug", "info", "warn", "error", "fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/root/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/root/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/root/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Run 'docker COMMAND --help' for more information on a command.

For more help on how to use Docker, head to https://docs.docker.com/go/guides/
```

### 镜像命令

#### docker images 列出所有镜像

```shell
[root@localhost ~]# docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
```

#### docker search 搜索镜像

```shell
[root@localhost ~]# docker search mysql
NAME                            DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
mysql                           MySQL is a widely used, open-source relation…   14391     [OK]       
mariadb                         MariaDB Server is a high performing open sou…   5492      [OK]       
percona                         Percona Server is a fork of the MySQL relati…   620       [OK]       
phpmyadmin                      phpMyAdmin - A web interface for MySQL and M…   849       [OK]       
bitnami/mysql                   Bitnami MySQL Docker Image                      93                   [OK]
circleci/mysql                  MySQL is a widely used, open-source relation…   29                   
bitnami/mysqld-exporter                                                         5                    
ubuntu/mysql                    MySQL open source fast, stable, multi-thread…   51                   
cimg/mysql                                                                      0                    
rapidfort/mysql                 RapidFort optimized, hardened image for MySQL   23                   
rapidfort/mysql8-ib             RapidFort optimized, hardened image for MySQ…   9                    
google/mysql                    MySQL server for Google Compute Engine          23                   [OK]
hashicorp/mysql-portworx-demo                                                   0                    
rapidfort/mysql-official        RapidFort optimized, hardened image for MySQ…   9                    
newrelic/mysql-plugin           New Relic Plugin for monitoring MySQL databa…   1                    [OK]
elestio/mysql                   elestio mysql Docker Image                      0                    
databack/mysql-backup           Back up mysql databases to... anywhere!         89                   
bitnamicharts/mysql                                                             0                    
linuxserver/mysql               A Mysql container, brought to you by LinuxSe…   39                   
mirantis/mysql                                                                  0                    
docksal/mysql                   MySQL service images for Docksal - https://d…   0                    
linuxserver/mysql-workbench                                                     50                   
vitess/mysqlctld                vitess/mysqlctld                                1                    [OK]
eclipse/mysql                   Mysql 5.7, curl, rsync                          0                    [OK]
drupalci/mysql-5.5              https://www.drupal.org/project/drupalci         3                    [OK]
```

#### docker pull 下载镜像

```shell
[root@localhost ~]# docker pull mysql:8
8: Pulling from library/mysql
b193354265ba: Pull complete 
14a15c0bb358: Pull complete 
02da291ad1e4: Pull complete 
9a89a1d664ee: Pull complete 
a24ae6513051: Pull complete 
b85424247193: Pull complete 
9a240a3b3d51: Pull complete 
8bf57120f71f: Pull complete 
c64090e82a0b: Pull complete 
af7c7515d542: Pull complete 
Digest: sha256:c0455ac041844b5e65cd08571387fa5b50ab2a6179557fd938298cab13acf0dd
Status: Downloaded newer image for mysql:8
docker.io/library/mysql:8
```

#### docker rmi 删除镜像

```shell
[root@localhost ~]# docker rmi nginx
Untagged: nginx:latest
Untagged: nginx@sha256:104c7c5c54f2685f0f46f3be607ce60da7085da3eaa5ad22d3d9f01594295e9c
Deleted: sha256:eea7b3dcba7ee47c0d16a60cc85d2b977d166be3960541991f3e6294d795ed24
Deleted: sha256:589bcc284f24d6548cd3cef06ace5f6ebc4f23a48a5763f2f9d3d30b0f9dadf5
Deleted: sha256:b3addc7069fafd183d88d1a40bb3dfe51227d45e4fe8e59b81a2fda7614ebbc1
Deleted: sha256:5bf28af6a2188fa2d657e451213761b03e115e4c24ee72c41da34a241fe81ca1
Deleted: sha256:2496134da21702d935bee1334ae42baf26d0197af91275e5c1a11eee31299121
Deleted: sha256:c7e60968a54882c23483c3acb0ff1f415ce0f98184dfbed3fb9080447d79b313
Deleted: sha256:49bfd4a4ea578aefcacdfd87efdc4999d6a4e4b7f00322484cac67ff7671389e
Deleted: sha256:511780f88f80081112aea1bfdca6c800e1983e401b338e20b2c6e97f384e4299
```

