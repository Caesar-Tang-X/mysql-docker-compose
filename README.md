# MySQL Docker Compose YML File


## 简介
    docker 一键启动 mysql 容器的 docker-compose.yml 配置


## 镜像环境：
	mysql:8.0


## 导入镜像：
	docker load -i 镜像包


## 启动命令：
	docker-compose up -d


## 安装及生成数据路径：
    ├── mysql 
        ├── images                      镜像文件文件目录
        ├── mysql                       容器挂载目录
            ├── conf                        配置文件目录
                └── mysql.cnf                   mysql 配置文件
            ├── data                        数据目录
            └── log                         日志目录
        ├── docker-compose.yml          docker-compose.yml
        └── README.md                   README.md


## 隐私信息配置：
	1. 修改 MySQL root 账号的初始密码, 文件路径：docker-compose.yml
    2. 修改 MySQL 配置, 文件路径：./mysql/conf/mysql.cnf


## 后续操作：
### 1. 容器启动时提示忽略配置文件
    mysql: [Warning] World-writable config file '/etc/mysql/conf.d/mysql.cnf' is ignored

#### （1）问题原因
    MySQL 发现挂载的配置文件 /etc/mysql/conf.d/my.cnf 具有全局可写权限，因此忽略了该文件

#### （2）解决方案
    Windows：
        右键 mysql.cnf 文件，勾选只读

    Linux：
        进入容器：docker exec -it mysql-8.0 /bin/bash
        修改文件权限：chmod 644 /etc/mysql/conf.d/mysql.cnf
        重启容器：docker restart mysql-8.0
