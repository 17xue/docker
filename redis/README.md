**### 搭建说明 ###**
# 创建镜像

    **方式一：**
    1.docker search  redis 
    2.docker pull  redis:3.2 # 拉取官方的镜像,标签为3.2
    3.docker images redis 
    
    **方法二、通过 Dockerfile构建**
    1.创建Dockerfile
    
    2.通过Dockerfile创建一个镜像，替换成你自己的名字 
    docker build  -t redis:3.2 .
#启动镜像
    
    winpty docker run  --privileged=true -p 6382:6382 
    -v //d/docker/redis/data_test:/data  
    -d redis:3.2 redis-test3 
    --appendonly yes  #在容器执行redis-server启动命令，并打开redis持久化配置
    --privileged=true #--privileged=true 开启特权模式。


#进入容器
    
    1.进入mysql容器
    winpty docker exec -it redis bash
    


    
    
   
   
   


