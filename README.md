# MySQL Docker Compose YML File


## 简介
    docker 一键启动 mysql 容器的 docker-compose.yml 配置


## 镜像环境：
	mysql:8.0


## 启动命令：
	docker-compose up -d


##  安装及生成数据路径：
    ├── mysql 
        ├── conf                        配置文件目录
            └── mysql.cnf                  mysql 配置文件
        ├── data                        数据目录
        ├── log                         日志目录
        ├── docker-compose.yml          docker-compose.yml
        └── README.md                   README.md


## 隐私信息配置：
	1. 修改 MySQL root账号的初始密码, 文件路径：docker-compose.yml
    2. 修改 MySQL 配置, 文件路径：./conf/mysql.cnf


