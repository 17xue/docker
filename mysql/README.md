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
    
**### 搭建说明 ###**
# 创建镜像

    **方式一：**
    1.docker pull mysql:5.6 # 我们拉取官方的镜像,标签为5.6
    2.docker images |grep mysql
    
    **方法二、通过 Dockerfile构建**
    1.创建Dockerfile
    
    2.通过Dockerfile创建一个镜像，替换成你自己的名字 
    docker build -t mysql .
#启动镜像
    
    winpty docker run -p 3306:3306              #将容器的 3306 端口映射到主机的 3306 端口。
    --name mysql_server 
    -v $PWD/mysql/conf:/etc/mysql/conf.d        #将主机当前目录下的 conf/my.cnf 挂载到容器的 /etc/mysql/my.cnf。
    -v $PWD/mysql/logs:/logs                    #将主机当前目录下的 logs 目录挂载到容器的 /logs
    -v $PWD/mysql/data:/var/lib/mysql           #将主机当前目录下的data目录挂载到容器的 /var/lib/mysql 
    -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.6  #初始化 root 用户的密码


#进入容器
    
    1.进入mysql容器
    winpty docker exec -it mysql bash
    2.mysql -uroot -p123456
    


    
    
   
   
   


