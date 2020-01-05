## 1. docker install on centos 7.x
### 1.1 升级centos 7 软件包
确保联网情况下，在centos终端执行如下命令：
``` shell 
    yum update
```
### 1.2 Installing Docker
清除老的docker版本,安装最新的docker,执行:
``` sh
yum remove docker \
                docker-client \
                docker-client-latest \
                docker-common \
                docker-latest \
                docker-latest-logrotate \
                docker-logrotate \
                docker-engine
```
安装所需的yum package,,执行:
``` sh
yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2

```
设置稳定的repository,执行:
``` sh
yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```
安装docker,执行:
``` sh
yum install docker-ce docker-ce-cli containerd.io
```
列出docker可用版本,执行:
``` sh
yum list docker-ce --showduplicates | sort -r
```
安装指定的docker版本,执行:
``` sh
sudo yum install docker-ce-19.03.5-3.el7 docker-ce-cli-19.03.5-3.el7 containerd.io
```

启动docker,执行:
``` sh
systemctl start docker
``` 

验证docker,执行:
```sh 
docker run hello-world

有如下输出信息，说明docker安装成功.
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:d1668a9a1f5b42ed3f46b70b9cb7c88fd8bdc8a2d73509bb0041cf436018fbf5
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
```

卸载docker,执行:
``` sh
yum remove docker-ce

清理文件,执行:

rm -rf /var/lib/docker
```

## 2. mysql on docker minimize mirroring
### 2.1 下载官方MySQL版本，注意检查checksum的值. 

## 3. standardize mysql on docker


## 4. verification mysql    


