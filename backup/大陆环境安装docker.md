pip速度太慢，永久配置镜像代理：`pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
`

在Linux云服务器上安装Docker，步骤：
1. **更新系统软件包索引**：
   首先，您需要更新服务器的软件包索引。这可以通过运行以下命令来完成：
   ```bash
   sudo apt-get update && apt-get upgrade
   ```
2. **安装必要的软件包**：
   安装Docker需要一些先决条件，比如`apt-transport-https`、`ca-certificates`、`curl`和`software-properties-common`。运行以下命令来安装这些软件包：
   ```bash
   sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
   ```
3. **添加Docker官方的GPG密钥**：
   为了确保下载的Docker软件包是官方的，需要添加Docker的官方GPG密钥：
   ```bash
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   ```
4. **添加Docker的APT软件库**：
   将Docker的官方APT仓库添加到系统中：
   ```bash
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
   ```
5. **再次更新软件包索引**：
   添加了新的软件库后，需要更新软件包索引：
   ```bash
   sudo apt-get update
   ```
6. **安装Docker CE（社区版）**：
   现在可以安装Docker了：
   ```bash
   sudo apt-get install docker-ce
   ```
7. **验证Docker是否成功安装**：
   通过运行以下命令来验证Docker是否已正确安装：
   ```bash
   sudo docker --version
   ```
8. **将当前用户添加到docker组**：
   为了避免每次运行Docker命令时都需要使用`sudo`，可以将当前用户添加到`docker`组：
   ```bash
   sudo usermod -aG docker ${USER}
   ```
   添加用户后，需要退出并重新登录，以便组成员身份生效。
9. **启动Docker服务**：
   在某些系统中，可能需要手动启动Docker服务：
   ```bash
   sudo systemctl start docker
   ```
10. **设置Docker开机自启**：
    如果希望Docker在系统启动时自动运行，可以执行以下命令：
    ```bash
    sudo systemctl enable docker
    ```
11. **运行测试命令**：
    最后，运行一个测试命令来确认Docker运行正常：
    ```bash
    sudo docker run hello-world
    ```
按照以上步骤操作，您应该能够在Linux云服务器上成功安装并运行Docker。如果遇到任何问题，可以查看Docker的官方文档或寻求技术支持。


Docker Compose 是一个定义和运行多容器 Docker 应用程序的工具。可以通过以下步骤在 Linux 系统上安装 Docker Compose：
1. **下载 Docker Compose**：
   首先需要下载 Docker Compose。可以使用 `curl` 命令来下载 Docker Compose 的最新版本。运行以下命令来下载 Docker Compose：
   ```bash
   sudo curl -L "https://github.com/docker/compose/releases/download/v2.24.6/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   # 速度慢的话可改用wget命令：
   # sudo wget -O /usr/local/bin/docker-compose https://github.com/docker/compose/releases/download/v2.24.6/docker-compose-$(uname -s)-$(uname -m)
   ```
   注意：您可以访问 Docker Compose 的 [GitHub 发布页面](https://github.com/docker/compose/releases) 来查找最新的版本，并替换命令中的版本号。
2. **给 Docker Compose 授予执行权限**：
   下载完成后，需要给 Docker Compose 可执行权限：
   ```bash
   sudo chmod +x /usr/local/bin/docker-compose
   ```
3. **创建软链接（可选）**：
   为了方便使用，可以创建一个软链接到 `/usr/bin` 目录：
   ```bash
   sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
   ```
4. **验证 Docker Compose 安装**：
   通过运行以下命令来验证 Docker Compose 是否已正确安装：
   ```bash
   docker-compose --version
   ```
按照以上步骤操作，您应该能够在 Linux 系统上成功安装 Docker Compose。如果遇到任何问题，可以查看 Docker Compose 的官方文档或寻求技术支持。




查看正在运行的docker : docker ps
运行容器：docker run IMAGE_NAME
停止容器：docker stop CONTAINER_ID
启动已停止的容器：docker start CONTAINER_ID
重启容器：docker restart CONTAINER_ID
删除容器：docker rm  CONTAINER_ID