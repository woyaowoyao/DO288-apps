# DO288 Containerized Example Applications

oc new-app https://github.com/openshift/ruby-hello-world -l name=hello-world

# oc new-app -i java:8 https://github.com/openshift/test-maven-app --name=my-maven-app

oc new-app https://github.com/sclorg/cakephp-ex -l name=my-php-app

# Chapter1

oc new-app --name hello --build-env npm_config_registry=http://services.lab.example.com:8081/nexus/content/groups/nodejs http://services.lab.example.com/nodejs-helloworld 

# local-start

[source-build]

oc new-app --name hello -i onbuild-demo/nodejs-8-centos7~https://github.com/woyaowoyao/DO288-apps.git --context-dir=nodejs-helloworld

#1.需要先导入镜像Add to Project  https://github.com/openshift/origin/blob/master/examples/image-streams/image-streams-centos7.json
#2.oc new-app --name myap2 centos/nodejs-8-centos7~https://github.com/woyaowoyao/DO288-apps.git --context-dir=app-config

# opentlc oc new-app --name hello https://github.com/RedHatTraining/DO288-apps --context-dir=nodejs-helloworld

# opentlc oc new-app --name hello https://github.com/woyaowoyao/DO288-apps --context-dir=nodejs-helloworld

 oc new-app --name webui-cool https://github.com/woyaowoyao/coolstore-microservice --context-dir=coolstore-ui

curl -X POST -k 

 npm config set registry https://registry.npm.taobao.org 

npm info underscore

oc new-app --name hello     --build-env npm_config_registry=http://services.lab.example.com:8081/nexus/content/groups/nodejs     

http://services.lab.example.com/nodejs-helloworld

oc new-app --name hello --build-env npm_config_registry=https://registry.npm.taobao.org --code https://github.com/woyaowoyao/DO288-apps.git --context-dir=nodejs-helloworld

 python -m json.tool nodejs-helloworld/package.json

[source-build]

# 导入image 生成is,以便进行new-app 

oc import-image tomcat:8.5-alpine --from docker.io/tomcat:8.5-alpine --confirm
 
#进行new-app //上一步导入镜像到project onbuild-demo

oc new-app -i chapter2/tomcat:8.5-alpine --name my-tomcat-app

# local-end
 
oc new-app php~http://gitserver.example.com/mygitrepo

oc new-app -i php http://gitserver.example.com/mygitrepo

oc new-app php:7.0~http://gitserver.example.com/mygitrepo

oc new-app -i php:7.0 http://gitserver.example.com/mygitrepo

oc new-app myis~http://gitserver.example.com/mygitrepo

oc new-app -i myis http://gitserver.example.com/mygitrepo

oc new-app -i myis --strategy source --code http://gitserver.example.com/mygitrepo

? the standard S2I image streams provided by OpenShift

oc new-app registry.example.com/mycontainerimage

oc delete all -l app=test

oc new-app --strategy docker http://gitserver.example.com/mydockerfileproject

oc new-app --strategy source http://gitserver.example.com/user/mygitrepo

oc new-app --code http://gitserver.example.com/mygitrepo 

# 由docker镜像直接生成项目
# oc new-app --docker-image registry.example.com/mycontainerimage

oc new-app --name hello -i php --code http://gitserver.example.com/mygitrepo

oc delete all -l app=test

oc new-app -o json registry.example.com/mycontainerimage

oc new-app --name='blue' --labels=name="blue" php~https://github.com/redhat-gpte-devopsautomation/cotd.git -o json

oc import-image myis --confirm \    --from registry.acme.example.com:5000/acme/awesome --insecure

<deploy-image 

oc new-project common
 
oc import-image apache-httpd --confirm \    --from docker-registry.default.svc:5000/hello/ahttpd --insecure #local-vm

oc new-app --name ahttpd httpd:2.4

[docker-build]

student@workstation ~]$ lab docker-build setup

git clone http://services.lab.example.com/rhel7-echo

cat ~/rhel7-echo/Dockerfile

FROM registry.lab.example.com:5000/rhel7:7.3 CMD bash -c "while true; do echo test; sleep 5; done" 

git clone https://github.com/woyaowoyao/D288-ch1-01-rhel7-7-echo.git

# oc new-app --name echo --insecure-registry  https://github.com/woyaowoyao/D288-ch1-01-rhel7-7-echo.git

oc new-app --name echo2 --insecure-registry=true http://gogs-cicd.apps.os311.test.it.example.com/root/D288-ch1-01-rhel7-7-echo.git

# oc new-app --name echo --insecure-registry=true https://github.com/woyaowoyao/DO288-apps.git --context-dir=rhel7-echo 

# CMD bash -c "while true; do echo test; sleep 5; done"

# oc new-app --name info --insecure-registry=true https://github.com/woyaowoyao/DO288-apps.git --context-dir=rhel7-info

# error: chmod: changing permissions of '/tmp/info.sh': Operation not permitted->
切换为管理员登录 再oc adm policy add-scc-to-user anyuid  -z default -n chapter1

oc new-app --name info2 --insecure-registry=true https://github.com/woyaowoyao/DO288-apps.git --context-dir=ubi-info

#ERROR:build error: Failed to push image: unauthorized: unable to validate token-> 重启虚拟机

oc start-build echo
 
oc get all --export  --as-template=jeesite-demo
 
https://github.com/RedHatTraining/DO288-apps/tree/master/php-helloworld
 
cat /proc/sys/kernel/hostname 
  
oc logs -f bc/echo

oc describe echo-5-htskx 

oc status --suggest

oc logs echo-5-htskx -c echo

[docker-build]

oc adm policy add-scc-to-user anyuid -n do288-cha1 -z default
 
oc import-image php --confirm \    --from  --insecure

oc import-image apache-httpd --confirm  --from  registry.lab.example.com:5000/do288/apache-httpd --insecure 

#  oc import-image apache-httpd --confirm  --from docker.io/httpd --insecure #webconsole  Add to Project 

docker-registry.default.svc:5000/do288-cha1/apache-httpd --insecure 

oc cp frontend-1-zvjhb:/var/log/httpd/error_log /tmp/frontend-server.log

oc rsh hello-1-89mhn ps ax

oc rsh -t hello-1-89mhn

 oc policy add-role-to-user view system:serviceaccount:top-secret:robot

oc get templates -n openshift | grep php | grep mysql 
 
oc get templates/cakephp-mysql-example -o yaml >cakephp-mysql-example.yaml -n openshift
 
oc new-app --template openshift/cakephp-mysql-example -p NAME=quotesapi   -p APPLICATION_DOMAIN=quotes-do288-cha1.apps.os311.test.it.example.com -p SOURCE_REPOSITORY_URL=http://gogs-cicd.apps.os311.test.it.example.com/root/do288-apps  -p CONTEXT_DIR=quotes -p DATABASE_SERVICE_NAME=quotesdb  -p DATABASE_USER=user1 -p DATABASE_PASSWORD=mypa55   --name quotes
  
cd /C/cloud/openshift/servers/test-files/rhoar-getting-started/origin-examples/quickstarts

oc create -f cakephp-mysql.json

oc logs -f bc/quotesapi

oc describe svc quotesdb | grep Endpoints 

oc describe pod quotesapi-1-5zncm | grep -A 5 Environment

oc rsh quotesapi-1-5zncm bash -c \    'curl $DATABASE_SERVICE_NAME:3306' 

mysql -h 110.110.110.110 -uroot -p abcd123

create database name; 创建数据库use databasename; 选择数据库drop database name 直接删除数据库，不提醒
show tables; 显示表describe tablename; 表的详细描述mysqladmin drop database name 删除数据库前，有提示。

oc cp ./DO288/labs/build-template/quote.sql \    quotesdb-1-hh2g9:/tmp/quote.sql
 
oc rsh -t quotesdb-1-hh2g9 
 
mysql -u$MYSQL_USER -p$MYSQL_PASSWORD $MYSQL_DATABASE < /tmp/quote.sql 
 
oc start-build --follow bc/hello 

oc adm policy add-scc-to-user anyuid -z apacheuser

oc set env dc/mydcname     --from configmap/myconf

oc set volume dc/mydcname --add     -t configmap -m /path/to/mount/volume \    --name myvol --configmap-name myconf

oc set env dc/mydcname     --from secret/mysecret

oc set volume dc/mydcname --add -t secret -m /path/to/mount/volume     --name myvol --secret-name mysecret

oc set triggers dc/mydcname --from-config --remove

oc set triggers dc/mydcname --from-config

oc rollout latest mydcname

oc describe svc quotesdb | grep Endpoints 

oc start-build hello -F

# 重点-实验：PDF 58 页（阿拉伯数字 40 页）比较重要，必须要完成
======================================================================

1. 创建 名称为 app1 的应用程序

2. 这个应用程序创建完毕后，应该可以通过 http://hello.apps.lab.example.com 地址访问

3. 这个应用程序build时候需要的依赖在 http://services.lab.example.com:8081/nexus/content/groups/nodejs 传递依赖的关键字 npm_config_registry

4. 这个应用程序应该运行在 projecta 中

5. 如果应用无法正常build，提供了一个json文件检查工具 可以通过 python -m json.tool filename.json 使用

6. 本次build 需要使用的源码 http://services.lab.example.com/nodejs-helloworld

oc new-app --name hello \    
--build-env npm_config_registry=http://services.lab.example.com:8081/nexus/content/groups/nodejs \   
 http://hello.lab.example.com/app-config 

 # oc new-app --name hello --build-env npm_config_registry=https://registry.npm.taobao.org --code https://github.com/woyaowoyao/DO288-apps/tree/master/nodejs-helloworld