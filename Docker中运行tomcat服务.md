# Docker中运行tomcat服务
## 一、编写dockerfile文件
    FROM tomcat:8.5.33-jre8-alpine
    add exmobile.war /usr/local/tomcat/webapps/
    add exwebresource.war /usr/local/tomcat/webapps/

    CMD ["/usr/local/tomcat/bin/catalina.sh","run"]
## 二、Build Docker Image,指令如下
    docker build -t tomcatserver .
### 这里指定的Image Name为tomcatserver,页面如下所示
 ![](https://raw.githubusercontent.com/guodonghe/docker_doc/master/images/docker.png)

## 三、使用Build完成的Docker Image,执行Docker container
    docker run -d --name tomcat -p 8080:8080 tomcatserver
## 四、使用docker ps指令，查看运营中的docker 容器
    docker ps
![](https://raw.githubusercontent.com/guodonghe/docker_doc/master/images/1.png)

## 五、在页面中访问输入地址：http://192.168.18.210:8080，可以访问到如下界面:
![](https://raw.githubusercontent.com/guodonghe/docker_doc/master/images/2.png)

