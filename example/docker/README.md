# ubuntu-安装docker-CE

![](../../img/docker.png)

# step 1: 安装必要的一些系统工具
    apt-get update
    apt-get -y install apt-transport-https ca-certificates curl software-properties-common

# step 2: 安装GPG证书
    curl -fsSL https://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -

# Step 3: 写入软件源信息
    sudo add-apt-repository "deb [arch=amd64] https://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"


# Step 4: 更新并安装Docker-CE
    sudo apt-get -y update
    sudo apt-get -y install docker-ce

    docker -v
    Docker version 20.10.8, build 3967b7d