### 1. 启动命令:

    docker run -d -p 3306:3306 
    --restart always 
    --privileged=true
    --name mysql-store
    -e MYSQL_USER="store" 
    -e MYSQL_PASSWORD="pwd123" 
    -e MYSQL_ROOT_PASSWORD="rootpwd123"
    -v=$DOCKER_RUNTIME/mysql/config/my.cnf:/etc/my.cnf 
    -v=$DOCKER_RUNTIME/mysql/data:/var/lib/mysql 
    mysql：5.7


### 2. 参数说明：

    –restart always：开机启动
    –privileged=true：提升容器内权限
    -v=/mysqltest/config/my.cnf:/etc/my.cnf：映射配置文件
    -v=/mysqltest/data:/var/lib/mysql：映射数据目录


